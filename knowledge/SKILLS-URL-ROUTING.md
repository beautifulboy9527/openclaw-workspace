# Skills URL 路由机制

> 解决多个 Skills 触发条件重叠的问题
> 更新时间：2026-04-15

---

## 🔴 当前问题

### 触发重叠示例

```
用户发送: https://mp.weixin.qq.com/s/xxx

可能触发的 Skills:
1. wechat-article-fetcher  ✅ 最佳选择
2. wechat-mp-reader        ⚠️ 功能较弱
3. feedgrab                ⚠️ 通用抓取
4. web-access              ❌ 最后选择

问题：系统如何知道用哪个？
```

### 当前问题清单

| 问题 | 影响 |
|------|------|
| 触发条件重叠 | 可能选错 Skill |
| 没有优先级 | 无法确定最佳选择 |
| 没有URL模式匹配 | 只能靠关键词触发 |
| 通用Skill太宽泛 | feedgrab/web-access 会抢占专用Skill |

---

## ✅ 解决方案：URL 路由表

### 设计思路

```
1. URL 模式优先匹配（精确 > 模糊）
2. 专用 Skill 优先于通用 Skill
3. 定义明确的优先级
4. 降级机制（首选失败时尝试备选）
```

### 路由表配置

```yaml
# url-routes.yaml

routes:
  # === 微信公众号 ===
  - pattern: "mp.weixin.qq.com/s/"
    primary: wechat-article-fetcher
    fallback: [wechat-mp-reader, feedgrab]
    priority: 100
    reason: "专用微信抓取，支持图片下载和Markdown导出"
    
  # === X/Twitter ===
  - pattern: ["twitter.com/", "x.com/"]
    primary: twitter-reader
    fallback: [opencli, feedgrab]
    priority: 90
    reason: "专用Twitter读取，支持金融研究"
    
  # === 小红书 ===
  - pattern: ["xiaohongshu.com/", "xhslink.com/"]
    primary: xiaohongshu-mcp
    fallback: [feedgrab, opencli]
    priority: 90
    reason: "专用小红书操作"
    
  # === YouTube ===
  - pattern: ["youtube.com/", "youtu.be/"]
    primary: youtube-downloader
    fallback: [feedgrab]
    priority: 90
    reason: "视频下载专用"
    
  # === 抖音 ===
  - pattern: ["douyin.com/", "v.douyin.com/"]
    primary: douyin-video-extractor
    fallback: [feedgrab]
    priority: 90
    reason: "抖音视频提取专用"
    
  # === B站 ===
  - pattern: ["bilibili.com/", "b23.tv/"]
    primary: opencli
    fallback: [feedgrab]
    priority: 85
    reason: "opencli 支持B站登录态"
    
  # === 知乎 ===
  - pattern: "zhihu.com/"
    primary: opencli
    fallback: [feedgrab]
    priority: 85
    
  # === GitHub ===
  - pattern: "github.com/"
    primary: feedgrab
    fallback: [web-access]
    priority: 80
    
  # === 飞书 ===
  - pattern: ["feishu.cn/", "larksuite.com/"]
    primary: feedgrab
    fallback: [web-access]
    priority: 80
    
  # === RSS/通用 ===
  - pattern: "*"  # 通配符，最后匹配
    primary: feedgrab
    fallback: [web-access, agent-browser]
    priority: 10
    reason: "通用抓取，最后选择"
```

---

## 📊 路由优先级

| 优先级 | 类型 | Skills |
|--------|------|--------|
| 100 | 平台专用 | wechat-article-fetcher |
| 90 | 平台专用 | twitter-reader, xiaohongshu-mcp, youtube-downloader |
| 85 | 平台支持 | opencli (B站/知乎/微博) |
| 80 | 通用抓取 | feedgrab |
| 10 | 最后降级 | web-access, agent-browser |

---

## 🔧 实现方案

### 方案1：SKILL.md 添加 URL 模式

```yaml
---
name: wechat-article-fetcher
description: 抓取微信公众号文章...
url_patterns:
  - "mp.weixin.qq.com/s/"
  - "mp.weixin.qq.com/s?__biz="
priority: 100
fallback: [wechat-mp-reader, feedgrab]
---
```

### 方案2：创建路由配置文件

```bash
skills-config/
└── url-routes.yaml  # 统一路由配置
```

### 方案3：OpenClaw 核心路由逻辑

```python
def route_url(url: str) -> Skill:
    """根据 URL 选择最佳 Skill"""
    
    # 1. 精确匹配
    for route in sorted(routes, key=lambda r: r.priority, reverse=True):
        if matches_pattern(url, route.pattern):
            return route.primary
    
    # 2. 降级匹配
    for route in routes:
        if matches_pattern(url, route.pattern):
            for fallback in route.fallback:
                if skill_available(fallback):
                    return fallback
    
    # 3. 最终降级
    return "feedgrab"
```

---

## 📋 立即可做的改进

### 1. 更新各 Skill 的 description（明确边界）

**wechat-article-fetcher**:
```yaml
description: |
  抓取微信公众号文章的完整内容与图片。
  **URL 匹配**: mp.weixin.qq.com/s/
  **优先级**: 100（微信专用）
  **触发**: 用户发送微信文章链接时自动选择此 Skill
```

**feedgrab**:
```yaml
description: |
  通用内容抓取器，支持多种平台。
  **URL 匹配**: *（通配符，最后匹配）
  **优先级**: 80
  **注意**: 当有专用 Skill 时优先使用专用 Skill
```

### 2. 创建路由配置

在 `skills-config/url-routes.yaml` 定义明确的路由规则。

### 3. 更新 SKILL.md 添加元数据

为每个 Skill 添加 `url_patterns` 和 `priority` 字段。

---

## 🧪 测试用例

| URL | 期望选择 | 避免 |
|-----|----------|------|
| `mp.weixin.qq.com/s/xxx` | wechat-article-fetcher | feedgrab, web-access |
| `twitter.com/user/status/123` | twitter-reader | feedgrab |
| `xiaohongshu.com/explore/xxx` | xiaohongshu-mcp | feedgrab |
| `youtube.com/watch?v=xxx` | youtube-downloader | feedgrab |
| `github.com/user/repo` | feedgrab | web-access |
| `some-random-site.com` | feedgrab | - |

---

## 📊 效果对比

| 场景 | 改进前 | 改进后 |
|------|--------|--------|
| 微信链接 | 可能选错4个之一 | ✅ 精确选择 wechat-article-fetcher |
| Twitter链接 | 可能选错4个之一 | ✅ 精确选择 twitter-reader |
| 未知网站 | feedgrab 或 web-access | ✅ feedgrab 优先 |
| 专用平台 | 可能被通用抢占 | ✅ 专用优先 |

---

*by 小灰灰 🐕 | 2026-04-15*
