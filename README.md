# Design Anatomy

A Claude Code Skill that X-rays any AI Skill, tool, or prompt — revealing its hidden design decisions, tradeoffs, and transferable principles — then renders a magazine-quality HTML page you can share.

## What it does

Feed it a Skill (or any AI tool), and it:

1. **Reads the source code** — not the output, the actual SKILL.md or tool definition
2. **Extracts 3-5 non-obvious design decisions** — what was chosen, what was rejected, and why
3. **Generates a shareable HTML page** — editorial magazine layout, not a bland summary

## Example output

`/learn /advisor` produces a page like this:

- **Hero**: Skill name + one-line summary + inline flow diagram
- **Pipeline**: Interactive step-by-step architecture walkthrough
- **Design Insights**: Each decision with pull quote, chose/rejected comparison, and expandable source annotations
- **Steal These**: 3 actionable takeaways you can apply tomorrow
- **Build Challenge**: A hands-on exercise using the principles you just learned

## Install

Copy the `SKILL.md` file into your Claude Code skills directory:

```bash
# As a project-level skill
mkdir -p .claude/skills/learn
cp SKILL.md .claude/skills/learn/SKILL.md

# Or as a global skill
mkdir -p ~/.claude/skills/learn
cp SKILL.md ~/.claude/skills/learn/SKILL.md
```

## Usage

```
/learn /advisor          # Anatomy of a specific skill
/learn /implement        # Works with any skill
/learn [URL]             # Analyze any AI tool by URL
/learn                   # Analyze the most recent skill you used
/learn stats             # Show your design principle library stats
```

## Design principles

The HTML output follows an editorial magazine aesthetic:

- **Typography over decoration** — Satoshi + Instrument Sans, no card borders or shadows
- **Restrained color** — only 3 functional colors: indigo (emphasis), green (chose), red (rejected)
- **Pull quotes as anchors** — each insight has a scannable one-liner in large type
- **Progressive disclosure** — source annotations are expandable, not forced

## Knowledge accumulation

Each run appends to a design principle library in Obsidian (or any markdown vault):

- `design-principles/index.md` — deduplicated index of all principles encountered
- `design-principles/{name}.md` — detailed page per principle with usage history

Over time, this builds a personal design wisdom knowledge base.

## Requirements

- Claude Code (Claude Max or API)
- A browser (for viewing HTML output)
- Obsidian vault (optional, for knowledge accumulation)

## License

MIT
