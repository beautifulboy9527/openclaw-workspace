# Skills 科学分类体系

> 基于 Anthropic/OpenAI 官方最佳实践
> 更新时间：2026-04-15 15:00

---

## 📊 总览

| 统计项 | 数量 |
|--------|------|
| **Skills 总数** | 71 |
| **一级分类** | 8 |
| **二级分类** | 20+ |

---

## 🗂️ 分类体系

### 一、数据获取层 (Data Acquisition) - 15 个

> 负责从各种来源获取数据

#### 1.1 金融数据
| Skill | 描述 | 数据源 |
|-------|------|--------|
| yfinance-data | 美股数据 | Yahoo Finance |
| akshare-data | A股/港股数据 | AkShare |
| akshare-stock | A股数据查询 | AkShare |
| funda-data | 财务数据 | Funda API |

#### 1.2 内容抓取
| Skill | 描述 | 目标平台 |
|-------|------|----------|
| wechat-article-fetcher | 微信文章抓取 | 公众号 |
| xiaohongshu-mcp | 小红书操作 | 小红书 |
| douyin-video-extractor | 抖音视频提取 | 抖音 |
| youtube-downloader | YouTube下载 | YouTube |
| feedgrab | 通用网页抓取 | 任意URL |
| feedgrab-batch | 批量抓取 | 多平台 |
| telegram-reader | Telegram读取 | Telegram |
| twitter-reader | Twitter读取 | Twitter/X |
| discord-reader | Discord读取 | Discord |
| opencli | 多平台读取 | B站/知乎等 |
| wechat-mp-reader | 微信阅读 | 公众号 |

### 二、分析处理层 (Analysis & Processing) - 20 个

> 负责数据分析和处理

#### 2.1 金融分析
| Skill | 描述 | 功能 |
|-------|------|------|
| **unified-finance-skill** | 🎯 统一金融分析入口 | 整合所有金融能力 |
| stock-market-pro | 行情+图表 | K线/技术指标 |
| stock-assistant | 股票助手 | 行情查询入口 |
| stock-correlation | 相关性分析 | 股票关联 |
| stock-liquidity | 流动性分析 | 买卖盘分析 |
| stock-valuation-monitor | 估值监控 | PE/PB监控 |
| finance-sentiment | 情绪分析 | 多平台情绪 |
| china-stock-analysis | A股分析 | 深度研究 |
| china-stock-research | 中国市场研究 | 8阶段框架 |
| earnings-preview | 财报预览 | 财报前瞻 |
| earnings-recap | 财报回顾 | 财报分析 |
| estimate-analysis | 估值分析 | 分析师预期 |
| options-payoff | 期权收益 | 期权图表 |
| agent-stock | AI股票助手 | 综合分析 |

#### 2.2 内容分析
| Skill | 描述 |
|-------|------|
| analyzer | 内容分析器 |
| video | 视频/播客摘要 |

#### 2.3 企业分析（DBSkill 系列）
| Skill | 描述 |
|-------|------|
| dbs | 企业分析入口 |
| dbs-diagnosis | 商业模式诊断 |
| dbs-deconstruct | 企业解构 |
| dbs-content | 内容分析 |
| dbs-action | 行动分析 |
| dbs-benchmark | 对标分析 |
| dbs-hook | 短视频开头优化 |

### 三、执行操作层 (Execution & Automation) - 6 个

> 负责自动化操作和任务执行

| Skill | 描述 | 能力 |
|-------|------|------|
| **agent-browser** | 🎯 浏览器自动化 | 网页交互 |
| agent-reach | 信息获取 | 17平台搜索 |
| bb-browser | 信息提取 | 登录态抓取 |
| web-access | 网页访问 | 通用网页 |
| docx | Word文档 | 创建/编辑 |
| frontend-slides | 幻灯片 | HTML演示 |

### 四、知识管理层 (Knowledge Management) - 5 个

> 负责知识库管理和内容创作

| Skill | 描述 | 功能 |
|-------|------|------|
| **knowledge-manager** | 🎯 知识管理入口 | Obsidian+IMA |
| obsidian-cli-official | Obsidian CLI | 笔记操作 |
| obsidian-cli | Obsidian备用CLI | 笔记操作 |
| wechat-article-generator | 公众号生成 | 写作助手 |
| content-intel-cn | 内容智能 | 多平台运营 |

### 五、系统管理层 (System Management) - 7 个

> 负责 OpenClaw 系统管理

| Skill | 描述 | 功能 |
|-------|------|------|
| **openclaw-control-center** | 🎯 控制中心 | 状态监控 |
| openclaw-expert | 学习专家 | 文档查询 |
| openclaw-backup | 备份恢复 | 加密备份 |
| openclaw-server-secure-skill | 安全加固 | 部署指南 |
| skill-manager | Skill管理 | 生命周期 |
| skill-vetter | Skill审核 | 安全检查 |
| find-skills | 技能发现 | 搜索安装 |

### 六、Skill 开发层 (Skill Development) - 4 个

> 负责创建和改进 Skills

| Skill | 描述 | 功能 |
|-------|------|------|
| **bggg-skill-taotie** | 🎯 饕餮进化器 | Skill优化 |
| dbskill-upgrade | DB升级 | 版本更新 |
| self-improving-agent | 自改进Agent | 学习优化 |
| skill-finder-cn | 技能发现中文 | ClawHub |

### 七、UI/交互层 (UI & Interaction) - 2 个

> 负责用户界面和交互

| Skill | 描述 |
|-------|------|
| generative-ui | 生成UI组件 |
| ima-skill | IMA集成 |

### 八、特殊场景层 (Special Scenarios) - 5 个

> 特定场景的专用 Skills

| Skill | 描述 | 场景 |
|-------|------|------|
| stock-cli | 股票CLI | 命令行股票 |
| hormuz-strait | 霍尔木兹海峡 | 地缘政治 |
| chatroom-austrian | 奥地利学派聊天 | 经济学讨论 |
| feedgrab-setup | 抓取配置 | 初始化 |

---

## 🎯 核心入口 Skills

每个分类有一个核心入口 Skill（标记 🎯），其他为辅助：

| 层级 | 核心入口 | 整合能力 |
|------|----------|----------|
| 数据获取 | feedgrab | 通用抓取 |
| 分析处理 | unified-finance-skill | 金融分析 |
| 执行操作 | agent-browser | 浏览器自动化 |
| 知识管理 | knowledge-manager | 知识体系 |
| 系统管理 | openclaw-control-center | 控制中心 |
| Skill开发 | bggg-skill-taotie | 技能进化 |

---

## 📋 规范化状态

| 层级 | 总数 | 已规范化 | 进度 |
|------|------|----------|------|
| 数据获取层 | 15 | 2 | 13% |
| 分析处理层 | 20 | 2 | 10% |
| 执行操作层 | 6 | 1 | 17% |
| 知识管理层 | 5 | 1 | 20% |
| 系统管理层 | 7 | 2 | 29% |
| Skill开发层 | 4 | 1 | 25% |
| UI/交互层 | 2 | 0 | 0% |
| 特殊场景层 | 5 | 0 | 0% |
| **总计** | **71** | **5** | **7%** |

---

## 🔄 分类原则

### 1. 按功能分层
- **数据获取** → 原始数据收集
- **分析处理** → 数据转化为信息
- **执行操作** → 信息转化为行动
- **知识管理** → 行动转化为知识

### 2. 单一职责
- 每个 Skill 做好一件事
- 复杂功能通过 Skill 链组合

### 3. 渐进披露
- 核心 Skill 在 SKILL.md 提供快速开始
- 详细文档在 references/
- 执行逻辑在 scripts/

---

## 📝 待办事项

### 高优先级
- [ ] 为数据获取层 Skills 添加 Gotchas
- [ ] 统一金融分析入口（unified-finance-skill）完善
- [ ] 建立评估框架覆盖更多 Skills

### 中优先级
- [ ] 整理重复 Skills（如多个 Obsidian CLI）
- [ ] 标记废弃 Skills
- [ ] 建立自动化测试

### 低优先级
- [ ] 创建 Skill 依赖图谱
- [ ] 建立使用统计
- [ ] 优化分类结构

---

*by 小灰灰 🐕 | 2026-04-15*
