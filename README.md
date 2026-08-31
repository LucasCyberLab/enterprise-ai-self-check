# Enterprise AI Self-Check · 企业 AI 落地复盘与试点选择 Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-violet.svg)](LICENSE)

> **GenSight AI** 开源 · 先复盘真实业务，再选择 AI 试点，再进入工具与实施

这是一个面向老板、部门负责人和顾问的 Agent Skill。它不把“企业 AI 落地”简化成买工具，也不止于做流程诊断；它通过逐题访谈，帮助企业选出一个适合实际落地的 **AI 试点流程 / 项目**。

## 它的路径

```text
企业 / 职业身份
  → 主业务目标与真实事件
  → 业务链、断点、部门事实
  → 3 个候选流程比较
  → 选定 1 个 AI 试点流程
  → 个人 / 部门 / 跨部门 / 流程四层 AI 应用地图
  → 最小试点卡
  → 工具、系统、资源与后续实施路径
```

每次只问一个问题；每题均经历：**初答 → 拷问 → 完善回答**。最后输出 Markdown《企业 AI 落地复盘与试点讨论稿》，可直接带到管理层会议。

## 它如何处理“建平台 / 上系统”

系统、CRM、预算、开发和工具都不是禁区，但顺序不能反：

1. 先确定试点流程，例如“会计发现客户异常 → 形成机会信息 → 销售跟进 → 提升留存”；
2. 再讨论 AI 在个人、部门、协作和流程中能辅助什么；
3. 最后再判断现有工具能否支撑，是否需要集成、预算或平台建设。

如果使用者过早说“要搭建客户信息平台”，Skill 会保留该想法为“实现手段假设”，并要求先说明平台要支持的业务工作。等到实现路径阶段，平台建设、预算和工具选择可以被认真讨论，但必须服务于已选试点。

## 适合谁

| 使用者身份 | Skill 的产出边界 |
| --- | --- |
| 老板 / 总经办 | 完整复盘、试点流程选择和实施路径讨论输入 |
| 部门负责人 | 本部门事实、AI 应用机会、带回管理层确认的建议 |
| 顾问 / 服务商 | 标明信息来源的客户复盘稿与访谈 / 会议设计 |

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

## 使用

对 AI 说：

```text
请用 enterprise-ai-self-check，带我们做一次企业 AI 落地复盘，并选择一个试点流程。
```

详细问答顺序：[references/interview-protocol.md](references/interview-protocol.md)

四层 AI 应用地图：[references/ai-application-map.md](references/ai-application-map.md)

最终报告格式：[references/report-template.md](references/report-template.md)

示例输出：[examples/sample-report.md](examples/sample-report.md)

## 交付物

- 每题初答、拷问、完善回答与证据状态；
- 一个主业务目标、真实业务链与关键断点；
- 三个候选流程及一个选定 AI 试点流程；
- 个人、部门、跨部门协作和端到端流程的 AI 应用地图；
- 最小 AI 试点卡：输入、输出、人工审核、样本范围、指标和风险；
- 工具能力、现有系统、数据权限、预算和平台建设的后续实现路径。

## 公众号配套内容

- 《员工都会用 AI 了，为什么公司还是没有变快？》— 企业 AI 方法论总述
- 《上 AI 之前，先回答这四张表里的问题》— 深度业务复盘与试点选择
- 后续文章：围绕试点流程讲 AI 工具怎么选、怎么用、怎样与部门协作和业务流程结合

## 文件结构

```text
enterprise-ai-self-check/
├── SKILL.md
├── references/
│   ├── ai-application-map.md
│   ├── checklist.md
│   ├── interview-protocol.md
│   └── report-template.md
├── examples/
│   └── sample-report.md
├── README.md
└── LICENSE
```

## 许可

MIT © 2026 [GenSight AI](https://github.com/LucasCyberLab)

**免责声明**：本 Skill 用于企业业务复盘、AI 试点选择和实施准备，不构成商业、技术、法律、财务或组织变革承诺。
