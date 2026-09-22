# ChatExport Need Miner — Global Launch & Distribution Kit

This kit contains high-engagement announcement templates to publish and distribute `chatexport-need-miner` across major developer communities, product management forums, and AI agent registries.

---

## 1. Twitter / X Viral Launch Thread

### Post 1 (Hook + Banner):
> Community chats are goldmines for customer discovery, but nobody has time to read 30,000 Telegram messages.
>
> If you dump a raw JSON export into standard LLMs, you get hallucinated summaries and generic fluff.
>
> Today we're open-sourcing **ChatExport Need Miner**: a specialized agent skill that turns messy Telegram exports into prioritized, quantified product specs 🧵👇
>
> `npx skills add wwewtech/chatexport-need-miner`
> [Attach: assets/chatexport-banner.svg]

### Post 2 (The 5-Class Taxonomy):
> Raw chat text contains 90% noise (stickers, crypto spam, greetings, bot logs).
>
> ChatExport Need Miner classifies every meaningful utterance into 5 strict buckets:
> 1. Explicit Pain (broken workflows, unfulfilled expectations)
> 2. Hacks & Workarounds (tools duct-taped together)
> 3. Buying Intent & Willingness to Pay ("I'd pay $50/mo if someone built X")
> 4. Feature Friction (confusing UX, missing filters)
> 5. Churn & Frustration Signals (users abandoning existing tools)

### Post 3 (Quantified Evidence):
> No more vague claims. Every extracted opportunity includes:
> • Verbatim quotes with message ID and timestamp citations
> • Frequency and user-cluster counts
> • Severity rating (1 to 5)
> • Synthesized Jobs-To-Be-Done (JTBD) statement

### Post 4 (Install & Run):
> Works in Claude Code, Cursor, Antigravity, and Windsurf:
>
> 📦 skills.sh: https://skills.sh/wwewtech/chatexport-need-miner
> ⭐ GitHub: https://github.com/wwewtech/chatexport-need-miner
> 🌐 Web Demo: https://wwewtech.github.io/chatexport-need-miner/
>
> Star the repo and start mining your communities for real product gold! 🛠️

---

## 2. Reddit (`r/Entrepreneur`, `r/SaaS`, `r/ProductManagement`, `r/ClaudeAI`)

### Title:
> **We built an open-source agent skill that extracts validated SaaS pain points from 50k+ Telegram chat exports**

### Body:
> Hey everyone,
>
> When doing customer discovery, public and private Telegram/Discord groups are full of unfiltered customer feedback. But analyzing a 50,000-message export JSON is painful:
> - Manually scrolling takes days.
> - Feeding chunks into ChatGPT produces hand-waving generalities and loses context.
>
> We built **ChatExport Need Miner** (https://github.com/wwewtech/chatexport-need-miner), a single-file agent skill (`SKILL.md`) following the open Agent Skills standard.
>
> **What it does:**
> 1. Pre-processes Telegram export `result.json` (strips service messages, bot logs, sticker spam).
> 2. Detects implicit workarounds ("I currently copy-paste this into Excel and run a macro...").
> 3. Maps complaints to the JTBD framework (Situation -> Barrier -> Current Workaround -> Desired Outcome).
> 4. Computes a Severity Index (1-5) and attaches exact quote timestamps.
>
> **1-Click Install:**
> ```bash
> npx skills add wwewtech/chatexport-need-miner
> ```
> Or for Claude Code:
> ```bash
> claude skills add https://github.com/wwewtech/chatexport-need-miner
> ```
>
> GitHub: https://github.com/wwewtech/chatexport-need-miner
> Web Inspector: https://wwewtech.github.io/chatexport-need-miner/
>
> Would love your feedback on the extraction taxonomy!

---

## 3. Pull Request Submission Template

```markdown
## Summary
Adds the `chatexport-need-miner` skill to `skills/chatexport-need-miner/SKILL.md`.

### Overview
`chatexport-need-miner` empowers autonomous agents to systematically mine Telegram chat export JSON files for qualitative customer insights, unmet user needs, workarounds, and product opportunities using structured JTBD methodologies.

### Features
- 5-class qualitative need taxonomy (Explicit Pain, Workaround, Buying Intent, Feature Friction, Churn Signal)
- Zero-hallucination quote and timestamp citation requirement
- Impact vs. Frequency prioritization matrix
- Noise elimination filters for bot commands, sticker spam, and social chit-chat

### Validation
Passes all CI checks with 0 errors and 0 warnings. Verified against canonical evaluation testcases.
```
