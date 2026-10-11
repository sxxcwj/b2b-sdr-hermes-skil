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
