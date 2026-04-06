# roast-cold-email

[中文](README.md) · [English](README_EN.md) · [SKILL_EN.md](SKILL_EN.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)
[![AgentSkills Standard](https://img.shields.io/badge/AgentSkills-Standard-blue)](https://github.com/titanwings/colleague-skill)

---

You've been politely ignored long enough.

You sent your resume. Three weeks later, you got nothing. You wrote a perfectly worded thank-you email. They didn't open it. You said "I'm deeply passionate about your mission." They hired someone else.

Here's the thing: they didn't ignore you because you weren't qualified. They ignored you because you sounded like everyone else.

---

## What This Is

A Claude Code skill that helps you write cold emails that actually get replies — not by being nicer, but by being **right about something the company got wrong**.

The logic:

- A specific, accurate critique > "I'm passionate about your mission"
- The company's gap is your opener. The recipient is your **potential ally**, not your target.
- Worst case? You get blocked. On a burner account. Who cares.

This skill researches your target company, matches the right hook, writes a draft you can be proud of, and sends it from a Gmail burner through proper OAuth. No LinkedIn Premium required.

---

## Features

| Mode | What it does |
|------|--------------|
| **Research mode** | Searches company pain points, hiring trends, and technical debt via Tavily |
| **Email generation** | Matches company type to hook, generates a sharp, targeted draft |
| **Gmail burner sending** | Sends via Google OAuth + Gmail API — your main account stays clean |

---

## The Hook Library

One hook per email. That's the rule. Hit and step back.

| # | Hook name | Best for | The line |
|---|-----------|----------|----------|
| 1 | 47% reply rate | Companies with recruiting teams who swear by LinkedIn Premium | "I get a 47% reply rate without LinkedIn Premium. Just thought you should know." |
| 2 | This email was automated | Companies that published an AI strategy deck and did nothing | "This email was automated. Your onboarding program wasn't. I noticed." |
| 3 | Hive contributor | EdTech / L&D / corporate training companies | "I contribute to Hive (YC-backed). I've spent months building agentic pipelines while most L&D teams debate whether to use ChatGPT." |
| 4 | No resume attached (default) | Every single email | "I'll skip the resume — if a PDF could explain what I do, I wouldn't be emailing you." |
| 5 | GCP credentials jab | Companies whose job descriptions mention "AI transformation" and nothing else | "The job description mentions AI transformation. It also suggests no one has touched a GCP console." |

---

## Installation

```bash
cp SKILL_EN.md ~/.claude/commands/roast-cold-email.md
```

Want the Chinese version instead?

```bash
cp SKILL.md ~/.claude/commands/roast-cold-email.md
```

---

## Usage

In Claude Code:

```
/roast-cold-email
```

Tell Claude the company you're targeting, the contact name, and their email.

**Example:**

```
/roast-cold-email

Target: AcmeLMS Inc.
Contact: Alex Johnson (Chief Revenue Officer)
Email: a.johnson@acmelms.example.com
Context: Their LMS AI layer hasn't been touched in years
```

Claude will:
1. Search the company via Tavily
2. Pick the sharpest hook
3. Show you a draft
4. Send it from your burner once you confirm

---

## Requirements

### Gmail burner account

Set up a separate Gmail account for sending. Do not use your main account. This is not negotiable.

### GCP OAuth credentials

1. Create a project in [GCP Console](https://console.cloud.google.com/)
2. Enable the Gmail API
3. Create an OAuth 2.0 client (Desktop app type)
4. Download `credentials.json` and place it at the path specified in the skill

### Python dependencies

```bash
pip install google-auth google-auth-oauthlib google-api-python-client
```

---

## The One Rule

> **Critique the company. Never the person.**

You're not here to tell someone their job description is embarrassing. You're here to tell them their company has a gap — and you know how to close it.

The person reading your email is not the company. They might even agree with you.

---

## Credits

Inspired by [titanwings/colleague-skill](https://github.com/titanwings/colleague-skill).  
Companion project: [Schlaflied/hr-skill](https://github.com/Schlaflied/hr-skill) — the HR side: generate rejections, layoff scripts, interview scripts.  
Raw material provided by everyone who has ever been politely ignored.

---

[中文](README.md) · [English](README_EN.md) · [SKILL_EN.md](SKILL_EN.md)

---

MIT License · Built by someone who got tired of being politely ignored
