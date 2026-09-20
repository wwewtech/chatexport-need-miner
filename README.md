# chatexport-need-miner

Mine offline Telegram Desktop chat exports for unmet needs, product opportunities, and repeated complaints with quote-grounded evidence.

```bash
npx skills add wwewtech/chatexport-need-miner
```

## Links
- [Live Showcase](https://wwew.tech/chatexport-need-miner)
- [skills.sh](https://skills.sh/wwewtech/chatexport-need-miner)
- [SKILL.md](./SKILL.md)

## Why?
Product research often requires sifting through hundreds of megabytes of chat history to find pain points and feature requests. Loading these directly into LLMs fails due to context limits, and manual review is impossible. This skill provides an agentic protocol for streaming huge JSON exports, fingerprinting them, and clustering exact-match evidence around unmet needs and frustrations without blowing up memory.

## Quick Installation

### 1. Via `skills.sh` / Vercel Skills CLI
```bash
npx skills add wwewtech/chatexport-need-miner
```

### 2. Via Claude Code
```bash
claude skills add https://github.com/wwewtech/chatexport-need-miner
```

### 3. For Google Antigravity
Clone or copy `SKILL.md` directly into your Antigravity skills directory:
```bash
# Windows
mkdir -p "$HOME\.gemini\config\skills\chatexport-need-miner"
curl -sL https://raw.githubusercontent.com/wwewtech/chatexport-need-miner/main/SKILL.md -o "$HOME\.gemini\config\skills\chatexport-need-miner\SKILL.md"

# macOS / Linux
mkdir -p ~/.gemini/config/skills/chatexport-need-miner
curl -sL https://raw.githubusercontent.com/wwewtech/chatexport-need-miner/main/SKILL.md -o ~/.gemini/config/skills/chatexport-need-miner/SKILL.md
```

### 4. For Cursor & Windsurf
Add `SKILL.md` to your workspace prompt context:
```bash
mkdir -p .cursor/skills/chatexport-need-miner
curl -sL https://raw.githubusercontent.com/wwewtech/chatexport-need-miner/main/SKILL.md -o .cursor/skills/chatexport-need-miner/SKILL.md
```


## Core Concepts
- **Offline Only:** Works purely on local `result.json` Telegram exports.
- **Chunked Streaming:** Processes files in 4MB chunks to handle 100MB+ dumps safely.
- **Need Lexicon:** Uses precise substring search (e.g. "i wish", "missing", "не хватает") to find intent.
- **Quote Grounding:** Forces AI to cite verbatim evidence, preventing hallucinations.

## License
MIT © 2026 wwewtech
