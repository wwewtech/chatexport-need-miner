# Contributing to ChatExport Need Miner

We welcome contributions from developers, data analysts, and researchers working to improve offline market signal mining from Telegram community exports.

---

## Ways to Contribute

1. **Extend Seed Lexicons:** Propose new high-intent search patterns for Russian, English, or other languages that indicate customer pain points.
2. **Evaluation Benchmarks (`evals/evals.json`):** Submit real-world edge cases (e.g., malformed UTF-8, split JSON chunks, high-frequency bot spam).
3. **Stream Parsers:** Optimize chunk iteration speed and memory footprint.
4. **Export Formats:** Propose clean Markdown, CSV, or structured JSON export schemas for product management tools.

---

## Submission Guidelines

- All modifications to `SKILL.md` must maintain **single-file self-containment** and remain in **concise English**.
- Ensure byte-for-byte SHA256 symmetry between `./SKILL.md` and `./skills/chatexport-need-miner/SKILL.md`.
- Run the validation check before opening a PR:
  ```bash
  python -c "import hashlib; assert hashlib.sha256(open('SKILL.md','rb').read()).hexdigest() == hashlib.sha256(open('skills/chatexport-need-miner/SKILL.md','rb').read()).hexdigest(), 'Hash mismatch!'"
  ```
- Use conventional commits: `feat:`, `fix:`, `docs:`, `chore:`.
