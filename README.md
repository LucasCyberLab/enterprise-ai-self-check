# Enterprise AI Self-Check · 企业 AI 逐题复盘 Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-violet.svg)](LICENSE)

> **GenSight AI** 开源 · 先业务，后工具 · 先复盘，后试点

这是一个让 AI 像访谈主持人一样，带企业做 AI 落地前管理层复盘的 Agent Skill。它不会一次抛出一张长问卷：**一次只问一个问题，每题都经过初答、拷问、完善回答两轮，再进入下一题。**

## 它解决什么问题

企业准备上 AI 时，最容易直接问“该买什么工具”。这个 Skill 先帮助你把下面的问题带到管理层会议上：

1. 公司未来 3–6 个月真正想改善什么业务结果？
2. 一条真实业务链卡在哪里：个人动作慢，还是跨部门交接、等待与返工？
3. 相关部门每周反复在做什么，谁该共同负责？
4. 公司最该先理顺哪一个工作内容？

完成后输出一份 Markdown《企业 AI 管理层复盘会议讨论稿》，可直接发给老板和部门负责人会前阅读。

## 访谈方式

```text
第 1 题：确认使用者身份
  ↓
初答
  ↓
拷问：AI 用 1–3 个尖锐问题检查事实、责任、频率和业务后果
  ↓
完善回答（或回复「维持原答」）
  ↓
下一题
```

它先识别使用者身份，再走相应路径：

| 使用者身份 | Skill 做什么 | 最终结论边界 |
| --- | --- | --- |
| 老板 / 总经办 | 完整复盘业务重点、流程、部门与优先事项 | 可带进会议拍板一个优先工作内容 |
| 部门负责人 | 深挖本部门真实场景与上下游断点 | 形成部门事实稿，交由管理层确认 |
| 顾问 / 服务商 | 标明信息来源，梳理客户访谈与会议议程 | 不把顾问推测写成客户决策 |
| 其他 | 先确认了解范围，再按部门路径访谈 | 明确其不替代管理层拍板 |

### 防止“系统方案抢跑”

本 Skill 只允许收敛业务工作，不能把“建平台、上 CRM、做系统、开发接口、买 AI、做 MVP、批预算”写成优先事项。若回答者提出这些内容，AI 会原样暂存为**实现手段假设**，并追问：

> 先不谈系统。在没有任何新工具的情况下，哪个人必须把什么信息或决策交给谁，才能改善业务结果？

只有得到“起点 → 人的动作与交接 → 接收方 → 业务结果”的表述后，才进入候选项比较。老板在本阶段只拍板优先工作、共同牵头人和流程基础，不拍预算、功能、开发或上线计划。

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
请用 enterprise-ai-self-check，带我做一次企业 AI 管理层复盘。
```

第一题会是：

> 你今天以什么身份参与这次企业 AI 自查？请选择并说明：老板 / 总经办、部门负责人（请注明部门）、顾问 / 服务商、其他。

之后 AI 严格一次只推进一个核心问题。每题初答后都会给一次“拷问”，你再补充一次；没有补充时回复 **「维持原答」** 即可。

详细问题顺序：[references/interview-protocol.md](references/interview-protocol.md)

四张表逻辑：[references/checklist.md](references/checklist.md)

最终报告格式：[references/report-template.md](references/report-template.md)
示例输出：[examples/sample-report.md](examples/sample-report.md)

## 交付物

最终 Markdown 报告包含：

- 使用者身份与信息边界；
- 每一个问题的初答、拷问、完善回答；
- 已确认事实、初步判断与待会议补充项；
- 业务重点、流程断点、部门事实、候选优先事项；
- 建议参会人、60–90 分钟会议议程、需要老板拍板的事项。

## 不做什么

本 Skill 不推荐 AI 工具、不设计提示词、不承诺自动化，也不规划试点；更不会输出系统立项、预算申请、IT 人数、功能清单、MVP 或上线时间表。只有管理层先确认“优先理顺哪件工作”，才进入下一阶段讨论 AI 如何参与。

## 公众号配套文章

- 《员工都会用 AI 了，为什么公司还是没有变快？》— 方法论总述
- 《上 AI 之前，先回答这四张表里的问题》— 管理层复盘清单使用说明

关注 **GenSight AI** 公众号，回复 **「流程体检」** 领取 Excel 版。

## 文件结构

```text
enterprise-ai-self-check/
├── SKILL.md
├── references/
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

**免责声明**：本 Skill 用于管理层复盘与会议准备，不构成商业、技术、法律、财务或组织变革建议。
