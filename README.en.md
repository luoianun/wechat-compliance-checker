# WeChat Compliance Checker

[中文](README.md)

A pre-publication compliance checker for WeChat Official Account (公众号) articles. Contains a structured rule library that works with any AI agent or AI-powered editor, helping content operators avoid article removal, traffic restrictions, or account suspension.

## Features

Performs structured risk analysis across the following modules:

| Module | What's Checked |
|--------|---------------|
| Title | Clickbait, superlatives, share-baiting, political sensitivity |
| Cover Image | Size requirements, content compliance, text overlay ratio |
| Body Images | Prohibited content, copyright issues, embedded CTAs |
| Body Content | Political sensitivity, misinformation, medical/financial violations, low quality |
| Marketing & Ads | Ad law prohibited words, engagement baiting, fake promotions |
| Overall Risk | Risk level, key risk summary, publish recommendation |

## Quick Install

### Option 1: Let your AI Agent install it (works with any agent)

Send the following to your AI agent (Cursor, Windsurf, Claude Code, etc.) and let it handle the setup:

```
Please install this skill: https://github.com/luoianun/wechat-compliance-checker
Clone the repo into your skills directory, read SKILL.md to understand the workflow, and run a compliance check following that workflow whenever I ask for one.
```

### Option 2: Claude Code CLI install

```bash
# macOS / Linux
git clone https://github.com/luoianun/wechat-compliance-checker \
  ~/.claude/skills/wechat-compliance-checker

# Windows
git clone https://github.com/luoianun/wechat-compliance-checker \
  %USERPROFILE%\.claude\skills\wechat-compliance-checker
```

## Usage

After setup, send your article content to the AI and trigger a check.

**Claude Code users:**

```
/wechat-compliance-checker

Title: XXX
Body: (paste article content)
```

**Other AI agents / editors (Cursor, Windsurf, etc.):**

```
Please run a WeChat compliance check on the following article:

Title: XXX
Cover image description: (optional)
Body: (paste article content)
```

**Input fields:**

| Field | Required |
|-------|----------|
| Article title | Recommended |
| Body content | Recommended (full or partial) |
| Cover image description | Optional |
| Body image descriptions | Optional |

## Limitations

- This tool assesses risk based on publicly known rules — it **cannot guarantee 100% approval** by WeChat's review system
- Image checks rely on text descriptions; actual image pixels are not scanned
- WeChat's policies evolve — cross-reference with official announcements when in doubt
- Political sensitivity judgments depend on context; the tool provides risk signals, not definitive rulings

## Rule Files

- [references/title-rules.md](references/title-rules.md) — Title compliance rules
- [references/image-rules.md](references/image-rules.md) — Cover and body image rules
- [references/content-rules.md](references/content-rules.md) — Body content compliance rules
- [references/marketing-rules.md](references/marketing-rules.md) — Marketing expression and ad law rules
