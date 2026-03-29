# Design Anatomy

> AI 让你高效，但不让你成长。这个 Skill 让你每用一次 AI 工具，就学到一个设计思维。

[中文](#问题) | [English](#the-problem)

---

## 问题

你每天用 AI 完成大量工作，但有没有想过：

- AI 帮你做了决策分析，你知道它**为什么**用 3 路并行而不是单线程吗？
- AI 帮你写了代码，你理解它**为什么**选择这个架构而不是另一个吗？
- 你用了一个很好用的 AI Skill，你能说清它背后的**设计原理**吗？

**用得越多，理解越浅。** MIT 研究显示 83% 的 AI 用户几分钟后就记不住 AI 做了什么。你在"用工具"，但你没有在"学设计"。

## 解决方案

`/learn` 拆解你用过的任何 AI Skill / 工具，告诉你：

- 它做了哪些**设计决策**（选择了什么、放弃了什么、为什么）
- 这些决策背后对应什么**通用设计原理**
- 你**明天就能用**的 3 条行动指南

## 你能得到什么

### 1. 看透工具，而不只是使用工具

比如拆解 `/advisor`（一个决策分析 Skill），你会学到：

| 你以前知道的 | 拆解后你知道的 |
|-------------|---------------|
| 它会帮我对比方案 | 它用 3 路**并行**分析消除认知锚定，串行会让后面的分析被前面的结论污染 |
| 它会给我一个推荐 | 推荐附带**可证伪的假设**——如果假设不成立，推荐可能是错的 |
| 它有个反对者角色 | **角色分离原则**：让一个人兼顾正反是谎言，法庭分原告被告，不让一个律师"全面分析" |

### 2. 积累个人设计智慧库

每次拆解自动提取设计原理，去重后存入你的笔记库。用得越多，库越厚。三个月后你手里有一个结构化的设计原理知识库，而不是一堆零散的使用记忆。

### 3. 从"会用 AI"变成"会设计 AI"

当你理解了 20 个工具的设计逻辑，你自然会开始用这些原理设计自己的工具。这是从"AI 使用者"到"AI 构建者"的跃迁。

## 安装

```bash
# 一行安装
mkdir -p ~/.claude/skills/learn && curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o ~/.claude/skills/learn/SKILL.md
```

## 使用

```
/learn /advisor          # 拆解指定 Skill
/learn /implement        # 任何 Skill 都行
/learn [URL]             # 分析任意 AI 工具
/learn                   # 分析最近使用的 Skill
/learn stats             # 查看设计原理库统计
```

## 输出示例

每次拆解生成一份 HTML 页面（自动在浏览器打开），包含：

- **这个工具做什么**——一句话 + 流程图，10 秒看懂
- **设计决策**——每个决策的"选择了/放弃了/为什么"，配核心洞察一句话
- **源码注解**——关键代码片段 + 设计意图解读（可展开）
- **明天就能用**——3 条可直接迁移到你工作中的行动指南
- **动手挑战**——用学到的原理自己设计一个简化版工具

## 环境要求

- Claude Code（Claude Max 或 API）
- 浏览器（查看输出）
- Obsidian（可选，用于设计原理积累）

## License

MIT

---

## The Problem

You use AI tools every day. But can you explain WHY they're designed the way they are?

AI makes you efficient, but it doesn't make you grow. MIT research shows 83% of AI users can't recall what the AI did minutes later. You're using tools without absorbing the design thinking behind them.

## The Solution

`/learn` dissects any AI Skill or tool and reveals:

- **Design decisions**: what was chosen, what was rejected, and why
- **Underlying principles**: transferable design wisdom you can reuse
- **Actionable takeaways**: 3 things you can apply tomorrow

## What you get

1. **Understand tools, not just use them** — see the hidden tradeoffs behind every design choice
2. **Build a personal design wisdom library** — principles auto-accumulate in your notes with deduplication
3. **Go from "AI user" to "AI builder"** — after understanding 20 tools' design logic, you start designing your own

## Install

```bash
mkdir -p ~/.claude/skills/learn && curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o ~/.claude/skills/learn/SKILL.md
```

## Usage

```
/learn /advisor          # Anatomy of a specific skill
/learn [URL]             # Analyze any AI tool
/learn                   # Analyze the most recent skill used
/learn stats             # Design principle library stats
```

## Requirements

- Claude Code (Claude Max or API)
- A browser
- Obsidian (optional)
