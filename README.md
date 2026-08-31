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
  → 团队实际使用 AI 的工具与执行动作
```

每次只问一个问题；每题均经历：**初答 → 拷问 → 完善回答**。最后输出 Markdown《企业 AI 落地复盘与试点讨论稿》，可直接带到管理层会议。

## 它如何处理“建平台 / 上系统”

系统、CRM、预算、开发和工具都不是禁区，但企业 AI 落地的默认终点不是“搭平台”，而是让真实团队开始在真实流程中使用 AI：

1. 先确定试点流程，例如“会计发现客户异常 → 形成机会信息 → 销售跟进 → 提升留存”；
2. 再讨论 AI 在个人、部门、协作和流程中能辅助什么；
3. 让试点团队用合适工具实际跑起来，复盘结果后再扩大应用。

如果使用者过早说“要搭建客户信息平台”，Skill 会保留该想法为“实现手段假设”，并要求先说明平台要支持的业务工作。它会优先设计不依赖新平台的 AI 试点与团队使用动作；只有试点证明现有条件无法承接，平台才作为单独技术议题讨论。

## 适合谁

| 使用者身份 | Skill 的产出边界 |
| --- | --- |
| 老板 / 总经办 | 完整复盘、试点流程选择和实施路径讨论输入 |
| 部门负责人 | 本部门事实、AI 应用机会、带回管理层确认的建议 |
| 顾问 / 服务商 | 标明信息来源的客户复盘稿与访谈 / 会议设计 |

## 安装运行环境与本 Skill

先选择一个 Agent 运行环境安装，再按对应方式安装本 Skill。三者都可运行同一套 `SKILL.md` 与 `references/` 目录；不需要重复维护不同版本。

### DeepSeek Harness（开发者预览）

DeepSeek Harness 需要先安装 Node.js；它目前仍处于开发者预览。官方快速启动命令：

```bash
npx @deepseek-ai/dsh web
```

另开一个终端，将本 Skill 放入 DeepSeek Harness 的用户级技能目录：

```bash
git clone https://github.com/LucasCyberLab/enterprise-ai-self-check.git
mkdir -p ~/.dsh/skills
cp -R enterprise-ai-self-check ~/.dsh/skills/
```

重新打开 Web 会话后，输入：

```text
请用 enterprise-ai-self-check，带我们做一次企业 AI 落地复盘，并选择一个试点流程。
```

DeepSeek Harness 也会扫描项目级 `.dsh/skills/` 和共享 `.agents/skills/`。其本地目录监视默认开启，新增或更新 Skill 后通常无需重装运行环境。参见 [DeepSeek Harness 快速开始](https://www.deepseek.com/harness/en/) 与 [Skills 子系统说明](https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/subsystems/skills.md)。

### OpenClaw

官方安装器会处理运行时与首次引导：

```bash
# macOS / Linux
curl -fsSL https://openclaw.ai/install.sh | bash

# Windows PowerShell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

安装后，从 GitHub 为所有本地 Agent 安装本 Skill，并检查是否成功发现：

```bash
openclaw skills install git:LucasCyberLab/enterprise-ai-self-check@master --global
openclaw skills list
```

如只想安装到当前工作区，去掉 `--global` 即可。OpenClaw 的首次引导会要求配置可用的模型认证。参见 [OpenClaw 官方安装文档](https://docs.openclaw.ai/install) 与 [Skills 文档](https://docs.openclaw.ai/skills)。

### Hermes Agent

官方 CLI 安装方式：

```bash
# macOS / Linux / WSL2
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
source ~/.zshrc  # Bash 用户改为 source ~/.bashrc

# Windows PowerShell
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

然后将整个 Skill 目录复制到 Hermes 的用户级目录：

```bash
git clone https://github.com/LucasCyberLab/enterprise-ai-self-check.git
mkdir -p ~/.hermes/skills
cp -R enterprise-ai-self-check ~/.hermes/skills/
hermes skills list
```

新开一个 Hermes 会话后，可输入 `/enterprise-ai-self-check`，或用自然语言要求它使用该 Skill。参见 [Hermes 官方快速开始](https://hermes-agent.nousresearch.com/docs/getting-started/quickstart/) 与 [Skills 使用文档](https://hermes-agent.nousresearch.com/docs/guides/work-with-skills)。

### Cursor、Claude Code、Codex

如果已使用下列 Agent，只需安装本 Skill：

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

> **企业数据提醒**：本 Skill 会讨论客户、财务、服务和经营信息。实际试点前，请先确认数据授权、脱敏方式、模型服务的企业安全设置，以及哪些内容必须由人工审核；不要把未授权的客户敏感数据直接粘贴到公共账号或未获批准的工具中。

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
- 试点团队具体如何使用 AI、所需工具能力、数据权限与复盘动作；
- 仅在确有阻塞时记录系统集成或平台建设议题。

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
