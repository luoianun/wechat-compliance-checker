# 微信公众号合规检测 | WeChat Compliance Checker

[English](#english) | [中文](#中文)

---

## 中文

微信公众号文章发布前合规自检工具。包含结构化规则库，可与任意 AI Agent / AI 编辑器集成使用，帮助内容运营者规避删文、限流、封号风险。

### 功能

对公众号文章进行结构化风险检测，覆盖以下模块：

| 模块 | 检测内容 |
|------|---------|
| 标题检测 | 标题党、极限词、诱导分享、政治敏感 |
| 封面图检测 | 尺寸规范、内容合规、文字叠加比例 |
| 正文配图检测 | 图片内容违规、版权问题、诱导引导 |
| 正文内容检测 | 政治敏感、虚假信息、医疗金融违规、低质量内容 |
| 营销表达检测 | 广告法极限词、诱导关注/转发、虚假促销 |
| 综合风险评估 | 整体风险等级、核心风险点、发布建议 |

### 快速安装

**适用任意 AI Agent（Cursor、Windsurf、Claude Code 等）——一句话安装：**

> 把以下任意一行发送给你的 AI Agent，让它帮你完成安装。

```
帮我从 https://github.com/luoianun/wechat-compliance-checker 克隆这个仓库，了解 SKILL.md 的内容，之后每次我说"合规检测"时，按 SKILL.md 描述的工作流执行检测任务。
```

**Claude Code Skill 安装（命令行）：**

```bash
# macOS / Linux
git clone https://github.com/luoianun/wechat-compliance-checker \
  ~/.claude/skills/wechat-compliance-checker

# Windows
git clone https://github.com/luoianun/wechat-compliance-checker \
  %USERPROFILE%\.claude\skills\wechat-compliance-checker
```

### 使用方式

安装后，将文章内容发送给 AI，并触发检测。

**Claude Code 用户：**

```
/wechat-compliance-checker

标题：XXX
正文：（粘贴文章内容）
```

**其他 AI Agent / 编辑器（Cursor、Windsurf 等）：**

```
请对以下公众号文章进行合规检测：

标题：XXX
封面图描述：（可选）
正文：（粘贴文章内容）
```

**输入字段说明：**

| 字段 | 是否必填 |
|------|---------|
| 文章标题 | 建议提供 |
| 正文内容 | 建议提供（全文或片段） |
| 封面图描述 | 可选 |
| 正文配图描述 | 可选 |

### 局限性

- 本工具基于公开规则进行风险评估，**无法保证 100% 通过微信审核**
- 图片内容检测仅基于文字描述，无法扫描实际图片内容
- 微信平台规则持续更新，建议结合官方最新公告使用
- 政治敏感内容判断依赖上下文，工具只能做风险提示

---

## English

A pre-publication compliance checker for WeChat Official Account (公众号) articles. Contains a structured rule library that works with any AI agent or AI-powered editor, helping content operators avoid article removal, traffic restrictions, or account suspension.

### Features

Performs structured risk analysis across the following modules:

| Module | What's Checked |
|--------|---------------|
| Title | Clickbait, superlatives, share-baiting, political sensitivity |
| Cover Image | Size requirements, content compliance, text overlay ratio |
| Body Images | Prohibited content, copyright issues, embedded CTAs |
| Body Content | Political sensitivity, misinformation, medical/financial violations, low quality |
| Marketing & Ads | Ad law prohibited words, engagement baiting, fake promotions |
| Overall Risk | Risk level, key risk summary, publish recommendation |

### Quick Install

**For any AI Agent (Cursor, Windsurf, Claude Code, etc.) — one-liner install:**

> Send the following to your AI agent and let it handle the setup.

```
Please clone https://github.com/luoianun/wechat-compliance-checker, read SKILL.md to understand the workflow, and from now on run a compliance check following that workflow whenever I say "compliance check".
```

**Claude Code Skill install (CLI):**

```bash
# macOS / Linux
git clone https://github.com/luoianun/wechat-compliance-checker \
  ~/.claude/skills/wechat-compliance-checker

# Windows
git clone https://github.com/luoianun/wechat-compliance-checker \
  %USERPROFILE%\.claude\skills\wechat-compliance-checker
```

### Usage

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

### Limitations

- This tool assesses risk based on publicly known rules — it **cannot guarantee 100% approval** by WeChat's review system
- Image checks rely on text descriptions; actual image pixels are not scanned
- WeChat's policies evolve — cross-reference with official announcements when in doubt
- Political sensitivity judgments depend on context; the tool provides risk signals, not definitive rulings

### Rule Files

- [references/title-rules.md](references/title-rules.md) — Title compliance rules
- [references/image-rules.md](references/image-rules.md) — Cover and body image rules
- [references/content-rules.md](references/content-rules.md) — Body content compliance rules
- [references/marketing-rules.md](references/marketing-rules.md) — Marketing expression and ad law rules
