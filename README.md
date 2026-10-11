# B2B SDR 智能销售代表 Agent Skill (面向 Hermes)

全天候自主运行的 AI B2B 销售开发代表（SDR）——支持通过 WhatsApp、邮件及 Telegram 自动化挖掘海外买家、资质审核（BANT）、发送个性化触达邮件，并全流程管理 B2B 外贸与出海商机漏斗。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Hermes Agent](https://img.shields.io/badge/Hermes-Agent%20Skill-blue)](https://github.com/hermes-agent)

---

## 核心功能

| 阶段 | 执行动作 | 触达渠道 |
| :--- | :--- | :--- |
| **潜客挖掘 (Lead Discovery)** | 在目标国家与市场全网检索潜在采购商 | 自动化后台 |
| **客户建档 (Lead Capture)** | 收到入境消息后，自动在 CRM 中创建结构化客户档案 | WhatsApp / 邮件 / Telegram |
| **BANT 资格审核** | 通过自然对话智能评估客户的预算、决策权、痛点及采购周期 | WhatsApp / Telegram |
| **深度调研与信息补全** | 自动调研目标企业背景、主营产品及核心决策人联络方式 | 搜索引擎 |
| **智能报价 (Quotation)** | 结合货运、结算与贸易条款自动生成规范化报价单草稿 | 邮件 / WhatsApp |
| **阶梯式开发信触达** | 自动执行 4 轮个性化冷启动邮件（Cold Email）跟进序列 | 邮件 |
| **商机漏斗巡检** | 自动输出日报与周报，对停滞未跟进的商机发出告警 | 定时任务 (Cron) |
| **沉睡客户激活 (Nurture)** | 定期对未成交、已成交或停滞老客户进行自动化关怀与再触达 | 多渠道 |

---

## 安装方法

### 1. 推荐：通过 Hermes Agent 一键安装
```bash
hermes skills install github:sxxcwj/b2b-sdr-hermes-skill
2. 适用于 Claude Code / Codex / Cursor 用户Bashnpx skills add sxxcwj/b2b-sdr-hermes-skill
3. 本地手动克隆Bashcd ~/.hermes/skills
git clone [https://github.com/sxxcwj/b2b-sdr-hermes-skil.git](https://github.com/sxxcwj/b2b-sdr-hermes-skil.git) b2b-sdr-agent
快速配置安装完成后，在 Hermes 终端中新建会话并输入：为我的业务配置 B2B SDR 智能体Agent 将引导你依次完成以下初始化配置：企业基本信息：企业名称、主营行业及目标出海国家/市场。CRM 存储选型：支持选择 Google Sheets、Notion、本地 JSON 文件或 HubSpot。巡检任务启动：激活商机管道自动化定时任务。WhatsApp 账号配对（如尚未连接）。定时巡检任务 (Cron Schedules)本技能预置了 7 套标准化商机管道自动化巡检流程：任务名称触发周期说明新线索检测每 4 小时检查并清洗未建档的新入境潜客信息停滞商机预警工作日 09:00标出超过 5 天未联系的停滞客户报价跟进工作日 10:00为已发出报价单的商机自动起草跟进策略邮件跟进序列每天 11:00自动执行第 3/7/14 天的冷邮件跟进序列主动潜客挖掘每天 10:00在目标行业与市场中定向抓取新采购商销售周报每周一 09:00汇总并输出管道数据、转化率及周度分析沉默线索激活每周一 09:00对已流失或冷冻阶段的联系人进行二次触达运行环境要求Hermes Agent v0.7.0+WhatsApp：通过 hermes whatsapp 完成授权配对。网络检索：系统内置 DuckDuckGo，亦可配置 Brave Search 或 Jina API Key 获得更高质量的检索能力。邮件支持：通过 hermes agentmail 或在配置中填入 SMTP 账密以发送跟进邮件。CRM 支持选项类型适用场景配置方式Google Sheets快速开箱、轻量团队共享协同技能将自动创建在线数据表模板本地 JSON私有化部署、纯本地运行、无第三方依赖默认保存在 ~/sdr-crm.jsonNotion需要富文本备注与看板视图展示填入 Notion Integration Token 即可HubSpot成熟企业级现有销售漏斗系统填入 HubSpot API Key 即可从 OpenClaw 迁移如果你之前在 OpenClaw 上使用过 b2b-sdr-agent-template，可直接执行平滑迁移：Bashhermes claw migrate --preset full
hermes skills install github:sxxcwj/b2b-sdr-hermes-skill
原有的 SOUL.md、MEMORY.md 以及 CRM 数据会自动保留并映射至新环境。开源协议本项目基于 MIT License 开源。欢迎提交 Issue 与 Pull Request 定制特定细分行业的拓客配置。
---

### 如何替换当前页面的 README：
1. 在当前页面右上方的文件操作栏中，点击 **铅笔图标 ✏️**（编辑文件）。
2. 全选当前内容并删除，将上方整段中文 Markdown 粘贴进去。
3. 点击右上角绿色的 **Commit changes...**（提交更改）按钮，保持选择 `Commit directly to the main branch`，再次点击确认即可保存生效。
