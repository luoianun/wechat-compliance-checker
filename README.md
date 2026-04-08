# 微信公众号合规检测

[English](README.en.md)

微信公众号文章发布前合规自检工具。包含结构化规则库，可与任意 AI Agent / AI 编辑器集成使用，帮助内容运营者规避删文、限流、封号风险。

## 功能

对公众号文章进行结构化风险检测，覆盖以下模块：

| 模块 | 检测内容 |
|------|---------|
| 标题检测 | 标题党、极限词、诱导分享、政治敏感 |
| 封面图检测 | 尺寸规范、内容合规、文字叠加比例 |
| 正文配图检测 | 图片内容违规、版权问题、诱导引导 |
| 正文内容检测 | 政治敏感、虚假信息、医疗金融违规、低质量内容 |
| 营销表达检测 | 广告法极限词、诱导关注/转发、虚假促销 |
| 综合风险评估 | 整体风险等级、核心风险点、发布建议 |

## 快速安装

### 方式一：让 AI Agent 自动安装（适用任意 Agent）

直接把下面这句话发给你的 AI Agent（Cursor、Windsurf、Claude Code 等），让它完成安装：

```
请帮我安装这个 skill：https://github.com/luoianun/wechat-compliance-checker
将仓库克隆到你的 skills 目录，读取 SKILL.md 了解工作流，之后当我发起合规检测时按该工作流执行。
```

### 方式二：Claude Code 命令行安装

```bash
# macOS / Linux
git clone https://github.com/luoianun/wechat-compliance-checker \
  ~/.claude/skills/wechat-compliance-checker

# Windows
git clone https://github.com/luoianun/wechat-compliance-checker \
  %USERPROFILE%\.claude\skills\wechat-compliance-checker
```

## 使用方式

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

## 局限性

- 本工具基于公开规则进行风险评估，**无法保证 100% 通过微信审核**
- 图片内容检测仅基于文字描述，无法扫描实际图片内容
- 微信平台规则持续更新，建议结合官方最新公告使用
- 政治敏感内容判断依赖上下文，工具只能做风险提示

## 规则文件

- [references/title-rules.md](references/title-rules.md) — 标题合规规则
- [references/image-rules.md](references/image-rules.md) — 封面图与配图规则
- [references/content-rules.md](references/content-rules.md) — 正文内容合规规则
- [references/marketing-rules.md](references/marketing-rules.md) — 营销表达与广告法规则
