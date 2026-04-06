# roast-cold-email

[中文](README.md) · [English](README_EN.md) · [SKILL_EN.md](SKILL_EN.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills Standard](https://img.shields.io/badge/AgentSkills-Standard-blue)](https://github.com/titanwings/colleague-skill)

---

你把简历投出去，等了三周，收到了已读不回。你写了一封措辞完美的感谢信，对方没有打开。你说"我对贵司充满热情"，他们选了另一个人。

You've been politely ignored long enough.

---

## 这是什么

一个 Claude Code skill，帮你用**有理有据的批评**代替空洞赞美来写 cold email。

核心逻辑：

- 有理有据的批评 > "I'm passionate about your mission"
- 公司的 gap 是靶子，收件人是你找来的**盟友**，不是攻击对象
- 最坏的结果是被 block——而你用的是小号

这个 skill 会研究目标公司的痛点，匹配合适的钩子，生成一封让对方不得不回复的邮件，通过 Gmail 小号发送。

---

## 功能

| 模式 | 说明 |
|------|------|
| **研究模式** | 用 Tavily 搜索公司最近的公开信息、招聘动态、技术债 |
| **邮件生成** | 根据公司类型匹配钩子，生成定制化邮件草稿 |
| **Gmail 小号发送** | 通过 Google OAuth + Gmail API 用小号发送，主号不沾手 |

---

## 钩子库

每封邮件只用**一个钩子**，点到为止。

| # | 钩子名 | 适用场景 | 核心句 |
|---|--------|----------|--------|
| 1 | 47% reply rate | 有招聘团队、在用 LinkedIn Premium 的公司 | "I get a 47% reply rate without LinkedIn Premium. Just thought you should know." |
| 2 | 这封邮件本身是自动化的 | 写了 AI strategy 但没落地的公司 | "This email was automated. Your onboarding program wasn't. I noticed." |
| 3 | Hive contributor | EdTech / L&D / 企业培训公司 | "I contribute to Hive (YC-backed). I've spent months building agentic pipelines while most L&D teams debate whether to use ChatGPT." |
| 4 | 简历不附（默认） | 所有邮件 | "I'll skip the resume — if a PDF could explain what I do, I wouldn't be emailing you." |
| 5 | GCP credentials 嘲讽 | 写了 AI/技术转型但明显不懂的公司 | "The job description mentions AI transformation. It also suggests no one has touched a GCP console." |

---

## 安装

```bash
cp SKILL.md ~/.claude/commands/roast-cold-email.md
```

或者复制 `SKILL_EN.md` 如果你想要英文版：

```bash
cp SKILL_EN.md ~/.claude/commands/roast-cold-email.md
```

---

## 使用方法

在 Claude Code 中输入：

```
/roast-cold-email
```

然后告诉 Claude 你要发给哪家公司，以及联系人姓名和邮箱（可选）。

**示例对话：**

```
/roast-cold-email

目标公司：AcmeLMS Inc.
联系人：Alex Johnson（Chief Revenue Officer）
邮箱：a.johnson@acmelms.example.com
背景：他们的 LMS 用了很多年没有更新 AI 层
```

Claude 会：
1. 用 Tavily 搜索公司近期信息
2. 判断最匹配的钩子
3. 给你看邮件草稿
4. 确认后用 Gmail 小号发送

---

## 技术要求

### Gmail 小号

你需要准备一个独立的 Gmail 账号用于发送（不要用主号）。

### GCP OAuth Credentials

1. 在 [GCP Console](https://console.cloud.google.com/) 创建项目
2. 启用 Gmail API
3. 创建 OAuth 2.0 客户端凭据（Desktop app）
4. 下载 `credentials.json`，放到 skill 指定路径

### Python 依赖

```bash
pip install google-auth google-auth-oauthlib google-api-python-client
```

---

## 铁律

> **一切针对公司，不针对个人。**

永远不说"你写得烂"，说"公司的 X 和 Y 之间有矛盾"。

收件人是你要拉拢的人，不是你要羞辱的人。

---

## 致谢

灵感来自 [titanwings/colleague-skill](https://github.com/titanwings/colleague-skill)。  
配套使用：[Schlaflied/hr-skill](https://github.com/Schlaflied/hr-skill) — 站HR视角，生成拒信/开人/面试话术。  
原材料来自每一个被礼貌无视过的求职者。

---

[中文](README.md) · [English](README_EN.md) · [SKILL_EN.md](SKILL_EN.md)

---

MIT License · Built by someone who got tired of being politely ignored
