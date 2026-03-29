# Design Anatomy

> 把任何 AI Skill / 工具 / Prompt 变成一堂杂志级的设计课。

A Claude Code Skill that X-rays any AI tool's design decisions, then renders a magazine-quality HTML page you can share.

[English](#english) | [中文](#中文)

---

## 中文

### 它做什么

给它任何一个 Skill（或 AI 工具），它会：

1. **读源码**，不是读输出——直接分析 SKILL.md 或工具定义
2. **提取 3-5 个非显而易见的设计决策**——选择了什么、放弃了什么、为什么
3. **生成一份可分享的 HTML 页面**——杂志编辑风排版，不是干巴巴的总结

### 为什么需要这个

AI 帮你高效完成任务，但你可能越用越不理解工具背后的设计智慧。Design Anatomy 让每次使用 AI 工具都变成一次免费的大师课——你不只是用工具，你在学习工具的设计者是怎么思考的。

### 示例输出

`/learn /advisor` 会生成这样一个页面：

- **Hero**：Skill 名称 + 一句话说明 + 内联流程图
- **Pipeline**：可点击的执行步骤，每步附设计意图解释
- **Design Insights**：每个决策配 Pull Quote（一句话核心洞察）+ 选择/放弃对比 + 可展开的源码注解
- **Steal These**：3 条明天就能用的行动指南
- **Build Challenge**：用学到的设计原理动手造一个简化版

### 安装

```bash
# 一行安装（全局）
mkdir -p ~/.claude/skills/learn && curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o ~/.claude/skills/learn/SKILL.md

# 或项目级安装
mkdir -p .claude/skills/learn
curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o .claude/skills/learn/SKILL.md
```

### 使用

```
/learn /advisor          # 拆解指定 Skill
/learn /implement        # 任何 Skill 都行
/learn [URL]             # 分析任意 AI 工具
/learn                   # 分析最近使用的 Skill
/learn stats             # 查看你的设计原理库统计
```

### 设计语言

HTML 输出遵循杂志编辑风美学：

- **字号和留白建立层级**，不用卡片边框和阴影
- **克制用色**——只有 3 种功能色：靛蓝（强调）、绿（选择了）、红（放弃了）
- **Pull Quote 做扫读锚点**——每条洞察都有一句大号关键句
- **渐进披露**——源码注解可展开，不强制阅读

### 知识积累

每次运行会往 Obsidian（或任何 Markdown 笔记库）追加设计原理：

- `design-principles/index.md`——去重索引
- `design-principles/{原理名}.md`——每个原理的详情页 + 使用记录

用得越多，你的个人设计智慧库越厚。

### 环境要求

- Claude Code（Claude Max 或 API）
- 浏览器（查看 HTML 输出）
- Obsidian（可选，用于知识积累）

---

## English

### What it does

Feed it any Skill (or AI tool), and it:

1. **Reads the source code** — not the output, the actual SKILL.md or tool definition
2. **Extracts 3-5 non-obvious design decisions** — what was chosen, what was rejected, and why
3. **Generates a shareable HTML page** — editorial magazine layout, not a bland summary

### Why

AI makes you efficient but can hollow out your understanding. Design Anatomy turns every AI tool usage into a free masterclass — you don't just use the tool, you learn how its designer thinks.

### Install

```bash
# One-line install (global)
mkdir -p ~/.claude/skills/learn && curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o ~/.claude/skills/learn/SKILL.md
```

### Usage

```
/learn /advisor          # Anatomy of a specific skill
/learn /implement        # Works with any skill
/learn [URL]             # Analyze any AI tool by URL
/learn                   # Analyze the most recent skill you used
/learn stats             # Show your design principle library stats
```

### Design language

The HTML output follows an editorial magazine aesthetic:

- **Typography over decoration** — Satoshi + Instrument Sans, no borders or shadows
- **Restrained color** — 3 functional colors: indigo (emphasis), green (chose), red (rejected)
- **Pull quotes as anchors** — each insight has a scannable one-liner
- **Progressive disclosure** — source annotations are expandable

### Knowledge accumulation

Each run appends to a design principle library in Obsidian (or any markdown vault), building a personal design wisdom knowledge base over time.

### Requirements

- Claude Code (Claude Max or API)
- A browser (for HTML output)
- Obsidian vault (optional, for knowledge accumulation)

## License

MIT
