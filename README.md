# Enterprise AI Self-Check · 企业 AI 管理层复盘 Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-violet.svg)](LICENSE)

> **GenSight AI** 开源 · 与《企业 AI 落地自查清单（管理层复盘版）》同逻辑
> 先业务，后工具 · 先复盘，后试点

---

## 这是什么

一个 **Agent Skill**，让 AI 协助老板带管理层完成一次企业 AI 落地前的业务复盘：

1. 明确未来 3–6 个月最该改善的业务结果；
2. 找到一条真实业务链上的关键断点；
3. 盘点总经办、人事行政培训、财务、销售、项目交付等关键部门的高频工作；
4. 用高频、痛苦、可衡量、风险可控四项，选出 **1 个优先工作内容**。

它不推荐工具，也不设计试点。目标是在买 AI 工具之前，先把“公司最该先理顺哪件工作”讨论清楚。

---

## 四个复盘维度

| 维度 | 核心问题 | 对应 Excel 表 |
| --- | --- | --- |
| 企业背景 | 未来 3–6 个月，公司最想改善什么 | 01-企业背景 |
| 流程自查 | 问题卡在某个人，还是卡在跨部门业务链 | 02-流程自查 |
| 部门盘点 | 关键部门每天在做什么、在哪卡、和谁交接 | 03-部门盘点 |
| 优先事项 | 哪一项工作最值得先理顺 | 04-优先事项 |

详细检查项见 [references/checklist.md](references/checklist.md)。

---

## 适合谁

- 老板 / 总经办：主持复盘并拍板优先事项；
- 销售、人事行政培训、财务、项目交付负责人：提供真实工作事实；
- 顾问：将访谈整理为管理层复盘报告。

建议由老板约齐关键负责人，用 60–90 分钟完成；技术、市场推广、采购等部门按实际问题加入。

---

## 安装

### Cursor

```bash
git clone https://github.com/LucasCyberLab/enterprise-ai-self-check.git
cp -r enterprise-ai-self-check ~/.cursor/skills/enterprise-ai-self-check
```

### Claude Code

```bash
git clone https://github.com/LucasCyberLab/enterprise-ai-self-check.git
cp -r enterprise-ai-self-check ~/.claude/skills/enterprise-ai-self-check
```

### Codex / 其他

将本仓库中的 `SKILL.md` 及 `references/`、`examples/` 目录复制到 Agent skills 目录即可。

---

## 使用

对 AI 说：

```text
请用 enterprise-ai-self-check，带我们做一次企业 AI 管理层复盘。
```

AI 会按四个维度分阶段提问，最后生成一份《企业 AI 管理层复盘报告》。报告不会给工具采购或试点方案，而是明确下一步该带哪一项工作进入试点设计讨论。

报告模板：[references/report-template.md](references/report-template.md)  
示例输出：[examples/sample-report.md](examples/sample-report.md)

---

## Excel vs Skill

| | Excel 清单 | 本 Skill |
| --- | --- | --- |
| 适合 | 线下管理层会议 | 线上访谈或会前准备 |
| 输出 | 填好的 .xlsx | Markdown 管理层复盘报告 |
| 共同终点 | 选出一个优先工作内容 | 选出一个优先工作内容 |

两种方式都在复盘阶段止步；工具选择与试点设计另行进行。

---

## 公众号配套文章

- 《员工都会用 AI 了，为什么公司还是没有变快？》— 方法论总述
- 《上 AI 之前，先回答这四张表里的问题》— 管理层复盘清单使用说明

关注 **GenSight AI** 公众号，回复 **「流程体检」** 领取 Excel 版。

---

## 文件结构

```text
enterprise-ai-self-check/
├── SKILL.md
├── references/
│   ├── checklist.md
│   └── report-template.md
├── examples/
│   └── sample-report.md
├── README.md
└── LICENSE
```

## 许可

MIT © 2026 [GenSight AI](https://github.com/LucasCyberLab)

**免责声明**：本 Skill 用于管理层复盘与沟通，不构成商业、技术、法律或组织变革建议。
