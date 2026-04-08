# 微信公众号合规检测工具

一个基于 Claude Code Skill 的微信公众号文章发布前合规自检工具，帮助内容运营者规避删文、限流、封号风险。

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

## 安装

将整个仓库克隆到 Claude Code 的 skills 目录：

```bash
# macOS / Linux
git clone https://github.com/luoianun/wechat-compliance-checker \
  ~/.claude/skills/wechat-compliance-checker

# Windows
git clone https://github.com/luoianun/wechat-compliance-checker \
  %USERPROFILE%\.claude\skills\wechat-compliance-checker
```

## 使用方法

在 Claude Code 中，将文章内容发送给 Claude，并触发 `/wechat-compliance-checker` skill：

```
/wechat-compliance-checker

标题：震惊！这个方法让你月入过万

正文：
大家好，今天给大家分享一个绝对有效的赚钱秘诀……
（粘贴文章正文）
```

也可以附带封面图描述或正文配图描述一并检测：

```
/wechat-compliance-checker

标题：XXX
封面图：一张展示产品的横幅图，图上叠加了"全国最好"的文字
正文：（文章内容）
```

### 输入格式

可提供以下任意组合：

- **文章标题**（必填，如需检测标题）
- **封面图描述**（可选）
- **正文内容**（全文或片段）
- **配图描述**（可选）

### 输出示例

```
## 标题检测
**检测结果**：🔴 高风险
**问题清单**：
- "震惊"属于标题党夸大词
**风险说明**：平台可能降低文章推荐权重或拒绝发布
**优化建议**：
- 直接说明文章核心内容，去掉情绪化词汇
**改写方案**：
> 这个副业方法让我额外月增收入，实测可行

---

## 综合风险评级
**整体评级**：高风险
**核心风险点**：标题党、极限词"绝对有效"
**发布建议**：强烈建议修改后发布
```

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
