# Avi Style Writer

A Claude Code skill that rewrites technical knowledge in the style of [Avi Chawla](https://x.com/_avichawla) (Daily Dose of Data Science).

Not a summarizer. Not a paraphraser. It takes **your** understanding, **your** examples, and **your** aha moment, then structures them into a punchy, scannable technical article.

## What it does

- Collects three inputs: your aha moment, target audience, and a real example from your own experience
- Picks from three article templates based on the knowledge type
- Generates a title with suspense (not a dry label)
- Writes the article following strict style rules: short paragraphs, bold = conclusion, tables for comparisons, three-rule ending

## Templates

| Template | When to use | Structure |
|---|---|---|
| **A: Decision Comparison** | X vs Y choice | Hook → scenario → comparison table → deep diffs → 3 rules |
| **B: Deep Case Study** | How X achieves Y | Hook → scenario → core mechanisms → edge cases → 3 rules → one-liner |
| **C: Reverse Engineering** | Why X happens | Hook → scenario → surface explanation → peel layers → loop back → tradeoffs → 3 rules → one-liner |

## Setup

Place `SKILL.md` in your Claude Code skills directory:

```
~/.claude/skills/avi-style-writer/SKILL.md
```

Add to your `CLAUDE.md`:

```markdown
# avi-style-writer
- **avi-style-writer** (`~/.claude/skills/avi-style-writer/SKILL.md`) - Rewrite technical knowledge in Avi Chawla style. Trigger: `/avi`
When the user types `/avi`, invoke the Skill tool with `skill: "avi-style-writer"` before doing anything else.
```

## Usage

Type `/avi` in Claude Code, then provide:

1. The technical topic you learned
2. Your biggest aha moment
3. Your target audience
4. A real example from your own work/study

The skill handles template selection, title generation, and article writing.

## Style rules

- 1-3 sentences per paragraph, never more
- Bold marks **conclusions**, not emphasis
- Tables for comparisons, not prose
- Ends with 3 sharp takeaway rules + one-liner conclusion
- No transition words, no emoji, no "let's look at...", no "in summary..."
- Never copies examples from reference articles — only uses yours
