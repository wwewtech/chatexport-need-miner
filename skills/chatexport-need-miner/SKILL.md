---
name: chatexport-need-miner
description: Mine offline Telegram Desktop chat exports (result.json, including 100MB+ multi-chat dumps) for unmet needs and product opportunities. Use when the user provides exported chat history files and asks what people are missing, what tools they wish existed, or what complaints repeat. Produces a quantified, quote-grounded ranking of need signals. Does not use live APIs, bots, or MTProto.
---

# ChatExport Need Miner

Turn offline Telegram Desktop exports into a ranked list of unmet needs with verbatim evidence.

## Input contract

- You receive one or more Telegram Desktop export files (`result.json` — a dict with `name`, `messages`, where `text` is a string or a list of strings/objects).
- Files can be huge (100MB–1GB+). NEVER load a whole file into memory. NEVER `cat` it.
- Everything runs offline. No API keys, no bots, no network. If the user wants live channels instead, stop and say this skill is the wrong tool.

## When NOT to use

- Live channel monitoring or digests — that is a different job (online fetchers).
- Personal relationship analysis ("what did we talk about") — out of scope.
- SaaS feedback suites (Zendesk/Intercom/Gong/Reddit) — different sources, different tooling.

## Method

1. **Fingerprint.** Read only the first 4KB: extract chat `name`, then stream the file in fixed-size chunks (e.g. 4MB with an overlap tail). Count characters and keyword hits per chunk. Counting rule: a match counts only if it ends past the overlap boundary, so boundary-spanning matches are counted exactly once.
2. **Need lexicon.** Case-insensitive substring search, per language of the chats. Default Russian set: `вот бы`, `не хватает`, `бесит`, `надоело`, `задолбал`, `ищу инструмент`, `ищу бот`, `есть ли бот`, `есть ли инструмент`, `посоветуйте`, `не работает`, `вручную`, `рутина`. Default English set: `i wish`, `missing`, `annoying`, `looking for a tool`, `is there a bot`, `doesn't work`, `manually`, `routine`. Extend only with user-approved phrases.
3. **Evidence capture.** For each hit keep at most N examples (default 6) per keyword per file: the nearest preceding `"date"` value plus ~200 characters of surrounding text, whitespace-collapsed. Skip `service`-type messages.
4. **Cluster, don't list.** Group hits into need themes (e.g. "manual multi-source curation", "no zero-downtime deploy guidance"). Rank themes by hit count across distinct chats. A theme seen in 3+ independent chats outranks one seen 50 times in one chat.
5. **Quote grounding.** Every theme must carry 2–5 verbatim quotes with dates. If a theme has no verbatim support, label it `unsupported` — never invent quotes, never paraphrase as quotation.

## Output

```markdown
## Need themes (ranked)
### 1. [Theme name] — [total hits] hits across [N] chats
- Evidence: "[verbatim quote]" ([date], [chat])
- Evidence: ...
- Verdict: real gap | covered by existing tools | unclear
```

End with a short `Coverage check` section: for each top theme, state which existing tools/skills already cover it (with names), or write `no known coverage found` — never claim uniqueness without a search.

## Honesty rules

- Counts are substring hits, not messages or people. Say which.
- If a file was sampled instead of fully scanned, state the method and sample size.
- If uniqueness of an opportunity cannot be verified, write exactly: `I cannot confirm this`.
