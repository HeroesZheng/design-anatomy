---
name: learn
description: Design Anatomy：拆解任何 Skill/工具/Prompt 的设计智慧，输出杂志级 HTML 解剖页。当用户说 /learn、拆解一下、设计解剖、design anatomy、为什么这么设计、学习这个skill、这个工具怎么设计的 时触发。
---

# Learn — Design Anatomy

## 定位

把任何 Skill / 工具 / Prompt 变成一堂杂志级的设计课。
读源码，不读输出。输出一份可分享的 HTML 解剖页。

## 输出路径

- **HTML**：`~/AI-Outputs/design-anatomy-{skill-name}-{YYYYMMDD}.html`，自动浏览器打开
- **原理库**：`~/Documents/DolpNote/知识/设计原理/`（Obsidian 长期积累）
- **终端**：只输出确认 + 文件路径，不重复 HTML 内容

## 触发模式

| 调用 | 行为 |
|------|------|
| `/learn /advisor` | 拆解指定 Skill 的 SKILL.md 源码 |
| `/learn [URL或工具名]` | 拆解任意 AI 工具/方法论 |
| `/learn` | 拆解当前 session 中最近使用的 Skill |
| `/learn stats` | 展示原理库统计 |

## 执行流程

### Step 1：定位目标（静默）

1. 指定 Skill → 查 `~/.claude/skills/{name}/SKILL.md` 或 `.claude/skills/{name}/SKILL.md`
2. URL → WebFetch 获取内容
3. 工具名/描述 → 基于描述分析
4. 无参数 → 读当日流水账找最近 Skill

**必须拿到源码。** 没有源码在 HTML 中标注"基于推断"。

### Step 2：深度分析（静默，不输出）

**2.1 架构解剖**
- 执行步骤、顺序、分支
- 数据流（读什么/写什么/存到哪）
- 交互模式（问几个问题、什么时候问、为什么）

**2.2 设计决策挖掘（3-5 个）**
每个决策包含：决策点、选择了什么、放弃了什么、深层原因、对应设计原理

**挖掘重点：**
- 约束条件（为什么限制只问 2 个？为什么固定 3 路？）
- 不做什么（刻意排除的功能）
- 顺序（为什么先 A 后 B？）
- 默认值（默认行为暴露对用户的假设）

**2.3 可迁移的 Takeaway（3 条）**
每条必须是"明天就能用"的具体行动，不是抽象原理。

### Step 3：生成 HTML

输出到 `~/AI-Outputs/design-anatomy-{skill-name}-{YYYYMMDD}.html`

#### 设计规范（必须遵守）

**美学：杂志编辑风。用字号和留白建立层级，不用边框和卡片。**

**配色（克制）：**
- 背景：`#faf9f6`（暖白）
- 文字：`#1a1714`（墨）/ `#6b6560`（次）/ `#a39e96`（辅）/ `#c7c2ba`（淡）
- 强调色：`#4338ca`（深靛蓝）——只用在 5 处：Design Anatomy 标签、原理名称、Pipeline 选中数字、Takeaway 标题、Overview 中的 Skill 名
- 功能色：`#1a7a5a`（✓ 选择了）、`#a8243c`（✗ 放弃了）
- **除此之外不用任何颜色**

**字体：**
```html
<link href="https://api.fontshare.com/v2/css?f[]=satoshi@300,400,500,700,900&f[]=instrument-sans@400,500&display=swap" rel="stylesheet">
```
- 标题/编号/Pull Quote：Satoshi
- 正文：Instrument Sans
- 标签/代码：SF Mono, Fira Code

**排版规则：**
- 最大宽度 720px
- 左侧标签栏 140px（What it does / How it works / Design insights / Steal these / Build challenge）
- Section 间距 36px
- 无卡片边框，无阴影，无圆角容器
- 分隔用 1px 细线 `#ddd9d1`
- 洞察编号用大号淡色字（2.8em, color: #f0eeea），不抢内容

#### 页面结构（5 个区块）

**Hero**
```
标签：DESIGN ANATOMY（mono, 强调色）
标题：/{skill-name}（Satoshi 900, 4.8em，最大视觉权重）
副标题：一句话概括做什么（Satoshi 400, 1.35em，次要色）
内联 Flow：● 输入 → ● 步骤... → ● 输出（mono, 小字, 彩色圆点区分角色）
细分隔线
```

**Overview（左标签 + 右正文）**
- 标签：What it does
- 正文：2-3 句话说清这个 Skill 做什么、给用户什么、不做什么
- Skill 名用强调色加粗

**Pipeline（左标签 + 右步骤）**
- 标签：How it works
- 4 个步骤：大号数字 + 标题 + 一行提示，可点击切换详情
- 详情区：一段文字解释设计意图

**Design Insights（核心价值区）**
- 标签：Design insights
- 标题："{N} 个设计决策，每个都有取舍"
- 每条洞察结构（用细分隔线分隔，不用卡片）：
  ```
  [大号淡色编号 01-04]  [标题：为什么...？]
                         [原理名（mono, 强调色）]
                         [Pull Quote：Satoshi 300, 1.1em，核心洞察一句话]
                         [✓ 选择了 / ✗ 放弃了（两列并排，无边框）]
                         [+ 源码注解（可展开，默认折叠）]
  ```
- Pull Quote 始终可见，是扫读的锚点
- 源码注解展开后：左侧代码（mono）+ 右侧解说（两列）

**Steal These（Takeaways）**
- 标签：Steal these
- 标题：明天就能用
- 3 条，每条：标题（强调色）+ 一句话行动指南
- 用细线分隔，不用编号

**Build Challenge（可选）**
- 标签：Build challenge
- 标题 + 时间预估 + 3 条指引

**Footer**
- 一行：/learn Design Anatomy · 日期 · 源码路径

#### 交互

- Pipeline 步骤点击切换详情
- 源码注解 details/summary 展开折叠
- 滚动渐入动画（IntersectionObserver, fade + translateY 12px）

#### 约束

- HTML 必须自包含（inline CSS，无外部依赖除字体 CDN）
- 不超过 400 行
- 不要在终端重复 HTML 内容

### Step 4：打开 + Obsidian 写入

**4.1 打开**
```bash
open ~/AI-Outputs/design-anatomy-{skill-name}-{YYYYMMDD}.html
```

**4.2 原理库更新**

索引：`~/Documents/DolpNote/知识/设计原理/原理索引.md`

不存在则创建：
```markdown
---
title: "设计原理索引"
date: {TODAY}
type: knowledge-index
tags: [设计原理, 知识库]
last_updated: {TODAY}
---

# 设计原理索引

| 原理名称 | 英文名 | 领域 | 首次发现 | 出现次数 | 最近使用 |
|---------|--------|------|---------|---------|---------|
```

去重：精确匹配 → 更新次数。近似 → 加 aliases。新原理 → 新行 + 详情页。

详情页：`~/Documents/DolpNote/知识/设计原理/{原理名}.md`
```markdown
---
title: "{原理名}"
date: {首次发现日期}
type: design-principle
domain: {领域}
aliases: [{英文名}]
tags: [设计原理, {领域}]
encounter_count: {N}
last_seen: {TODAY}
---

# {原理名}（{英文名}）

## 定义
{2-3 句话}

## 使用场景记录

### {TODAY} — {Skill 名} Design Anatomy
- **体现方式**：{怎么体现}
- **Tradeoff**：{相关取舍}

## 关联原理
- [[{相关原理}]] — {关联说明}
```

**4.3 流水账**
```
| {HH:MM} | /learn | Design Anatomy：{Skill名}，提取{N}个原理（{新}个新发现） | 个人O2-KRx.x | ~20k |
```

### Step 5：终端确认

```
✓ Design Anatomy：~/AI-Outputs/design-anatomy-{name}-{date}.html
  新原理：{列出新发现}
```

## /learn stats

读原理索引，输出：
```
原理库：{N} 个原理，{M} 个领域
Top 3：{原理1}({次数}) / {原理2} / {原理3}
最近：{最近 3 个 Skill}
```

## 注意事项

- **必须读源码**，没有源码标注"基于推断"
- **设计决策要具体**，不要"使用了模块化设计"，要"把日历操作独立成 /calendar 而不是内嵌 /daily，因为..."
- **Pull Quote 是全页最重要的文字**，每条洞察的核心"aha"浓缩在一句话里
- **Takeaway 必须 actionable**，不是"了解角色分离原则"而是"Code Review 时指定一个人专门扮演反对者"
- **颜色克制**：全页只有靛蓝（强调）、绿（选择）、红（放弃）三种功能色
- **不要生成卡片、边框、阴影、圆角容器**——用字号对比和留白建立层级
