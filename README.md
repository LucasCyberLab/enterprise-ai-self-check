# Enterprise AI Self-Check · 企业 AI 落地自查 Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-violet.svg)](LICENSE)

> **GenSight AI** 开源 · 与《企业 AI 流程自查清单》Excel 同逻辑  
> 先流程，后工具 · 个人 AI ≠ 企业 AI

---

## 这是什么

一个 **Agent Skill**，让 AI（Cursor / Claude Code / Codex 等）扮演**流程体检顾问**：

1. 按四个维度引导式提问
2. 帮老板/负责人把模糊感受写成结构化描述
3. 输出《企业 AI 落地自查报告》：断点清单 + **1 个线头建议** + 试点判断

**不是**工具推荐器，**不是**打分表。目的是在买 AI 工具之前，先把「卡在哪里」问清楚。

---

## 四个检查维度

| 维度 | 核心问题 | 对应 Excel 表 |
| --- | --- | --- |
| 企业背景 | 你想改什么 | 01-企业背景 |
| 流程自查 | 卡在哪、能否启动 | 02-流程自查 |
| 部门盘点 | 哪些场景先动 | 03-部门盘点 |
| 试点方向 | 从哪开始、怎么验收 | 04-试点方向 |

详细检查项见 [references/checklist.md](references/checklist.md)。

---

## 安装

### Cursor

```bash
git clone https://github.com/LucasCyberLab/enterprise-ai-self-check.git
cp -r enterprise-ai-self-check ~/.cursor/skills/enterprise-ai-self-check
```

或在项目中使用：

```bash
mkdir -p .cursor/skills
cp -r enterprise-ai-self-check .cursor/skills/enterprise-ai-self-check
```

### Claude Code

```bash
git clone https://github.com/LucasCyberLab/enterprise-ai-self-check.git
cp -r enterprise-ai-self-check ~/.claude/skills/enterprise-ai-self-check
```

### Codex / 其他

将本仓库中的 `SKILL.md` 及 `references/`、`examples/` 目录复制到你的 Agent skills 目录即可。

---

## 使用

对 AI 说：

```
请用 enterprise-ai-self-check，帮我做企业 AI 流程自查。
```

或英文：

```
Run enterprise-ai-self-check for our company AI workflow assessment.
```

AI 将分阶段提问（约 20–40 分钟，可分段完成），最后生成 Markdown 报告。

报告模板：[references/report-template.md](references/report-template.md)  
示例输出：[examples/sample-report.md](examples/sample-report.md)

---

## Excel vs Skill

| | Excel 清单 | 本 Skill |
| --- | --- | --- |
| 适合 | 老板、习惯填表 | 懂 AI 的负责人/顾问 |
| 输出 | 填好的 .xlsx | Markdown 自查报告 |
| 领取 | 公众号回复「流程体检」 | 本仓库直接安装 |

两套逻辑一致，选顺手的方式即可。

---

## 公众号配套文章

- [《员工都会用 AI 了，为什么公司还是没有变快？》](https://mp.weixin.qq.com/) — 方法论总述
- [《上 AI 之前，先回答这四张表里的问题》](https://mp.weixin.qq.com/) — 清单拆解 + Skill 说明

关注 **GenSight AI** 公众号，回复 **「流程体检」** 领取 Excel 版，填完可预约 30 分钟流程解读。

---

## 文件结构

```
enterprise-ai-self-check/
├── SKILL.md                 # 主 Skill 指令
├── references/
│   ├── checklist.md         # 完整检查项
│   └── report-template.md   # 报告模板
├── examples/
│   └── sample-report.md     # 脱敏示例
├── README.md
└── LICENSE                  # MIT
```

---

## 贡献

欢迎 Issue 和 PR：检查项翻译、行业适配、报告模板改进。

---

## 许可

MIT © 2026 [GenSight AI](https://github.com/LucasCyberLab)

**免责声明**：本 Skill 输出仅供参考，不构成商业建议。重大组织变革请结合人工诊断。
