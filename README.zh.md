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
hermes skills install github:iPythoning/b2b-sdr-hermes-skill
```

### 2. 适用于 Claude Code / Codex / Cursor 用户

```bash
npx skills add iPythoning/b2b-sdr-hermes-skill
```

### 3. 本地手动克隆

```bash
cd ~/.hermes/skills
git clone https://github.com/iPythoning/b2b-sdr-hermes-skill.git b2b-sdr-agent
```

## 快速配置

安装完成后，在 Hermes 终端中新建会话并输入：

```
为我的业务配置 B2B SDR 智能体
```

Agent 将引导你依次完成以下初始化配置：

- **企业基本信息**：企业名称、主营行业及目标出海国家/市场。
- **CRM 存储选型**：支持选择 Google Sheets、Notion、本地 JSON 文件或 HubSpot。
- **巡检任务启动**：激活商机管道自动化定时任务。
- **WhatsApp 账号配对**（如尚未连接）。

## 定时巡检任务 (Cron Schedules)

本技能预置了 7 套标准化商机管道自动化巡检流程：

| 任务名称 | 触发周期 | 说明 |
| :--- | :--- | :--- |
| 新线索检测 | 每 4 小时 | 检查并清洗未建档的新入境潜客信息 |
| 停滞商机预警 | 工作日 09:00 | 标出超过 5 天未联系的停滞客户 |
| 报价跟进 | 工作日 10:00 | 为已发出报价单的商机自动起草跟进策略邮件 |
| 跟进序列 | 每天 11:00 | 自动执行第 3/7/14 天的冷邮件跟进序列 |
| 主动潜客挖掘 | 每天 10:00 | 在目标行业与市场中定向抓取新采购商 |
| 销售周报 | 每周一 09:00 | 汇总并输出管道数据、转化率及周度分析 |
| 沉默线索激活 | 每周一 09:00 | 对已流失或冷冻阶段的联系人进行二次触达 |

## 运行环境要求

- Hermes Agent v0.7.0+
- **WhatsApp**：通过 `hermes whatsapp` 完成授权配对。
- **网络检索**：系统内置 DuckDuckGo，亦可配置 Brave Search 或 Jina API Key 获得更高质量的检索能力。
- **邮件支持**：通过 `hermes agentmail` 或在配置中填入 SMTP 账密以发送跟进邮件。

## CRM 支持选项

| 类型 | 适用场景 | 配置方式 |
| :--- | :--- | :--- |
| Google Sheets | 快速开箱、轻量团队共享协同 | 技能将自动创建在线数据表模板 |
| 本地 JSON | 私有化部署、纯本地运行、无第三方依赖 | 默认保存在 `~/sdr-crm.json` |
| Notion | 需要富文本备注与看板视图展示 | 填入 Notion Integration Token 即可 |
| HubSpot | 成熟企业级现有销售漏斗系统 | 填入 HubSpot API Key 即可 |

## 从 OpenClaw 迁移

如果你之前在 OpenClaw 上使用过 b2b-sdr-agent-template，可直接执行平滑迁移：

```bash
hermes claw migrate --preset full
hermes skills install github:iPythoning/b2b-sdr-hermes-skill
```

原有的 SOUL.md、MEMORY.md 以及 CRM 数据会自动保留并映射至新环境。

## 开源协议

本项目基于 MIT License 开源。欢迎提交 Issue 与 Pull Request 定制特定细分行业的拓客配置。
