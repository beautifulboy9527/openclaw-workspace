# Skills 规范化管理方案

> 基于 Anthropic/OpenAI 官方最佳实践
> 更新时间：2026-04-15 15:45

---

## 📊 当前状态

| 统计项 | 数量 |
|--------|------|
| **Skills 总数** | 71 |
| **有 SKILL.md** | 71 |
| **已添加 Gotchas** | 4 |
| **已添加测试** | 3 |

---

## ✅ 已规范化 Skills

| Skill | Gotchas | 测试 | 仓库 |
|-------|---------|------|------|
| unified-finance-skill | ✅ | ✅ | [GitHub](https://github.com/beautifulboy9527/unified-finance-skill) |
| bggg-skill-taotie | ✅ | ✅ | [GitHub](https://github.com/beautifulboy9527/bggg-skill-taotie) |
| wechat-article-fetcher | ✅ | ✅ | [GitHub](https://github.com/beautifulboy9527/wechat-article-fetcher) |
| agent-browser | ✅ | ✅ | [GitHub](https://github.com/beautifulboy9527/agent-browser-skill) |
| knowledge-manager | ✅ | ✅ | [GitHub](https://github.com/beautifulboy9527/knowledge-manager) |

### 1. 核心金融 (Core Finance) - 10 个

> 统一入口：`unified-finance-skill`

| Skill | 描述 | 状态 |
|-------|------|------|
| **unified-finance-skill** | 🎯 统一金融分析入口，饕餮整合 v2.0 | ✅ 主力 |
| stock-market-pro | 行情数据 + 技术图表 | 已整合 |
| yfinance-data | 美股数据源 | 已整合 |
| akshare-stock | A股数据源 | 已整合 |
| akshare-data | 通用数据获取 | 已整合 |
| stock-assistant | 股票助手 | 已整合 |
| stock-correlation | 相关性分析 | 已整合 |
| stock-liquidity | 流动性分析 | 已整合 |
| finance-sentiment | 情绪分析 | 已整合 |
| stock-valuation-monitor | 估值监控 | 已整合 |

### 2. 中国市场分析 (China Market) - 3 个

| Skill | 描述 | 状态 |
|-------|------|------|
| china-stock-analysis | A股深度分析 | 已整合到 unified |
| china-stock-research | 中国市场研究 | 待评估 |
| funda-data | 基本面数据 | 待评估 |

### 3. 内容获取 (Content Fetching) - 7 个

| Skill | 描述 | 状态 |
|-------|------|------|
| **wechat-article-fetcher** | 微信公众号抓取 | ✅ 规范 |
| **wechat-article-generator** | 公众号文章生成 | 待评估 |
| **wechat-mp-reader** | 公众号阅读 | 待评估 |
| **xiaohongshu-mcp** | 小红书内容 | 待评估 |
| **douyin-video-extractor** | 抖音视频提取 | 待评估 |
| **youtube-downloader** | YouTube 下载 | 待评估 |
| **feedgrab** | RSS/网页抓取 | ✅ 规范 |

### 4. 浏览器自动化 (Browser Automation) - 3 个

| Skill | 描述 | 状态 |
|-------|------|------|
| **agent-browser** | 浏览器自动化 | ✅ 规范 |
| agent-reach | 浏览器扩展 | 待评估 |
| bb-browser | 备用浏览器 | 待评估 |

### 5. 知识管理 (Knowledge Management) - 3 个

| Skill | 描述 | 状态 |
|-------|------|------|
| **knowledge-manager** | 知识管理体系 | 📝 需补充脚本 |
| **obsidian-cli-official** | Obsidian CLI | ✅ 规范 |
| obsidian-cli | 备用 CLI | 待评估 |

### 6. 系统管理 (System Management) - 6 个

| Skill | 描述 | 状态 |
|-------|------|------|
| **openclaw-control-center** | OpenClaw 控制中心 | ✅ 核心技能 |
| **openclaw-expert** | OpenClaw 专家 | ✅ 规范 |
| **openclaw-backup** | 备份管理 | ✅ 规范 |
| **skill-manager** | Skill 管理 | ✅ 规范 |
| **skill-vetter** | Skill 审核 | 待评估 |
| **opencli** | OpenClaw CLI | 待评估 |

### 7. Skill 开发 (Skill Development) - 4 个

| Skill | 描述 | 状态 |
|-------|------|------|
| **bggg-skill-taotie** | 🎯 饕餮 Skill 进化器 | ✅ 规范 |
| **dbskill-upgrade** | DB Skill 升级 | 待评估 |
| **self-improving-agent** | 自改进 Agent | 待评估 |
| **find-skills** | 技能发现 | 待评估 |

### 8. 数据分析 (Data Analysis) - 7 个

| Skill | 描述 | 状态 |
|-------|------|------|
| dbs | 数据库操作 | 待评估 |
| dbs-action | DB 操作 | 待评估 |
| dbs-benchmark | DB 基准 | 待评估 |
| dbs-content | DB 内容 | 待评估 |
| dbs-deconstruct | DB 解构 | 待评估 |
| dbs-diagnosis | DB 诊断 | 待评估 |
| dbs-hook | DB 钩子 | 待评估 |

### 9. 社交媒体 (Social Media) - 3 个

| Skill | 描述 | 状态 |
|-------|------|------|
| **telegram-reader** | Telegram 阅读 | 待评估 |
| **twitter-reader** | Twitter 阅读 | 待评估 |
| **discord-reader** | Discord 阅读 | 待评估 |

### 10. 其他工具 (Other Tools) - 25 个

| Skill | 描述 | 状态 |
|-------|------|------|
| docx | Word 文档处理 | 待评估 |
| video | 视频处理 | 待评估 |
| web-access | 网页访问 | 待评估 |
| chatroom-austrian | 奥地利聊天室 | 待评估 |
| content-intel-cn | 内容智能 | 待评估 |
| earnings-preview | 财报预览 | 待评估 |
| earnings-recap | 财报回顾 | 待评估 |
| estimate-analysis | 估值分析 | 待评估 |
| frontend-slides | 前端幻灯片 | 待评估 |
| generative-ui | 生成 UI | 待评估 |
| hormuz-strait | 霍尔木兹海峡 | 待评估 |
| ima-skill | IMA 技能 | 待评估 |
| options-payoff | 期权收益 | 待评估 |
| stock-cli | 股票 CLI | 待评估 |
| analyzer | 分析器 | 待评估 |
| ... | ... | ... |

---

## 📋 规范化行动计划

### Phase 1: 核心技能规范化（本周）

**高优先级（必须完成）**

| Skill | 改进项 | 状态 |
|-------|--------|------|
| unified-finance-skill | 添加 Gotchas 章节 | ⏳ 待做 |
| unified-finance-skill | 添加测试工作流 | ⏳ 待做 |
| bggg-skill-taotie | 创建 evals 目录 | ⏳ 待做 |
| knowledge-manager | 添加 scripts 目录 | ⏳ 待做 |
| wechat-article-fetcher | 审查 SKILL.md | ⏳ 待做 |

### Phase 2: 分类清理（下周）

1. **标记废弃 Skills** - 识别不再维护的 Skills
2. **合并重复 Skills** - 功能重叠的进行合并
3. **统一命名规范** - 小写连字符分隔
4. **补充 SKILL.md** - 为缺失的 Skill 添加文档

### Phase 3: 质量提升（持续）

1. **建立评估框架** - with-skill vs baseline 对比
2. **创建模板** - 统一 SKILL.md 格式
3. **自动化测试** - CI/CD 集成
4. **持续迭代** - 基于用户反馈改进

---

## 🎯 规范化标准

### SKILL.md 必需元素

```yaml
---
name: skill-name              # 小写、连字符、<64字符
description: |
  功能描述 + 触发条件
---

# Skill Name

## 快速开始
[最核心的 2-3 个用法]

## Gotchas
[环境特定的坑]

## 详细用法
[可选，长的移到 references/]

## 测试
[如何验证功能正常]
```

### 目录结构标准

```
skill-name/
├── SKILL.md              # 必需
├── agents/
│   └── openai.yaml       # 推荐
├── scripts/              # 可执行代码
├── references/           # 参考文档
└── evals/                # 评估（可选）
```

### 行数限制

- SKILL.md: < 500 行
- 描述: ~100 词
- 单个引用文件: < 10k 词需加目录

---

## 📝 改进记录

| 日期 | 改进内容 | 影响 |
|------|----------|------|
| 2026-04-15 | 创建规范化方案 | 启动项目 |
| 2026-04-15 | 学习官方最佳实践 | 指导思想 |

---

*by 小灰灰 🐕 | 2026-04-15*
