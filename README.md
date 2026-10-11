# B2B SDR Hermes Skill

面向 B2B 业务场景的 SDR（Sales Development Representative，销售开发代表）智能体技能包，专为自动化客户洞察、冷启动触达（Cold Outreach）与商机跟进设计。

---

## 核心功能

* **客户画像与痛点分析（ICP Analysis）**：快速解析目标企业公开信息，提炼行业痛点与决策人关注点。
* **个性化多渠道触达（Multi-channel Outreach）**：针对高管、业务线负责人等不同层级角色，自动生成定制化邮件、领英私信与电话开场白。
* **异议处理与话术建议（Objection Handling）**：预置高频异议应答策略，辅助销售人员平滑推进转化漏斗。
* **标准化 Prompt & 工作流规范**：遵循 Hermes Skill / 智能体规范设计，开箱即用，便于集成到主流 Agent 框架中。

---

## 目录结构

```text
├── b2b-sdr-hermes-skill/
│   ├── ...               # 核心 Prompt、配置文件或执行脚本
├── LICENSE               # MIT 开源协议
└── README.md             # 项目说明文档
快速上手
1. 导入技能
将 b2b-sdr-hermes-skill 文件夹导入至你的 Agent 工作流（或对应的 Hermes 运行环境）中。

2. 配置参数
根据实际业务需求，在配置文件中填入目标行业类型、产品解决方案及 ICP（Ideal Customer Profile）关键字段。

3. 调用示例
输入目标企业的相关信息及触达目标，智能体将自动输出结构化的触达计划与话术。

开源协议
本项目基于 MIT License 开源。
