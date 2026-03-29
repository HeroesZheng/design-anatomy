# Design Anatomy

> 每次用 AI 工具都是一次免费的大师课。这个 Skill 帮你从中提取智慧。

[中文](#ai-时代的费曼学习法) | [English](#english)

---

## AI 时代的费曼学习法

费曼说：如果你不能简单解释一件事，你就没有真正理解它。

现在的问题是——AI 帮你跳过了"理解"这一步。你用 AI 拿到了结果，但你说不清它为什么这样做。MIT 研究发现 83% 的 AI 用户几分钟后就记不住 AI 做了什么。**你在用工具，但工具背后的智慧没有变成你的。**

`/learn` 做的事情很简单：**在你用完一个 AI 工具之后，帮你把它背后的原理提取出来。**

就像费曼拆解物理学一样，它拆解 AI 工具——这个工具做了哪些关键决策？为什么选 A 不选 B？背后对应什么通用原理？你能把这个原理用在自己的工作里吗？

## 举个例子

拆解 `/advisor`（一个 AI 决策分析工具）后，你会发现：

| 你以前只知道 | 现在你理解了 |
|-------------|-------------|
| 它帮我对比方案 | 它用 3 路**并行**分析是为了消除认知锚定——串行会让后面的判断被前面的结论污染 |
| 它给我一个推荐 | 推荐带**可证伪的假设**——告诉你"如果这个前提不成立，推荐就是错的" |
| 它有个反对者角色 | 这是**角色分离原则**——法庭把原告被告分开，不让同一个律师"全面分析" |

这些不是只对 AI 工具有用的知识。角色分离可以用在你的 Code Review 流程里，可证伪推荐可以用在你给老板做方案汇报里，认知锚定消除可以用在你组织任何一次团队讨论里。

**工具是别人的，原理是你的。**

## 知识会累积

每次拆解提取的原理自动存入你的笔记库，去重、归类、记录使用场景。三个月后你不是记住了 50 个工具的用法——你拥有了一个结构化的**设计原理知识库**，里面是跨领域可复用的思维模型。

## 安装

```bash
mkdir -p ~/.claude/skills/learn && curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o ~/.claude/skills/learn/SKILL.md
```

## 使用

```
/learn /advisor          # 拆解指定 Skill 的设计原理
/learn /implement        # 任何 Skill 都行
/learn [URL]             # 分析任意 AI 工具
/learn                   # 分析你最近用的 Skill
/learn stats             # 查看原理库统计
```

## 每次拆解你会得到

一份 HTML 页面（自动在浏览器打开），包含：

1. **这个工具做什么**——一句话 + 流程图
2. **关键设计决策**——选择了什么 / 放弃了什么 / 为什么
3. **源码注解**——关键代码的设计意图解读
4. **明天就能用**——3 条可迁移到你工作中的行动指南
5. **动手挑战**——用学到的原理设计一个简化版工具

页面可以分享给同事和朋友。

## 环境要求

- Claude Code（Claude Max 或 API）
- 浏览器
- Obsidian（可选，用于原理积累）

## License

MIT

---

## English

> Every time you use an AI tool, it's a free masterclass. This Skill extracts the wisdom from it.

### The Feynman Method for the AI Age

AI gives you results, but skips the understanding. You use tools without absorbing the principles behind them. `/learn` fixes this — it dissects any AI tool after you use it, revealing:

- **Key design decisions** — what was chosen, what was rejected, why
- **Underlying principles** — transferable mental models, not tool-specific trivia
- **Actionable takeaways** — 3 things you can apply in your own work tomorrow

The tool is someone else's. The principles become yours.

### Install

```bash
mkdir -p ~/.claude/skills/learn && curl -sL https://raw.githubusercontent.com/HeroesZheng/design-anatomy/main/SKILL.md -o ~/.claude/skills/learn/SKILL.md
```

### Usage

```
/learn /advisor          # Dissect a specific skill
/learn [URL]             # Analyze any AI tool
/learn                   # Analyze the most recent skill used
/learn stats             # Principle library stats
```

### Requirements

- Claude Code (Claude Max or API)
- A browser
- Obsidian (optional)
