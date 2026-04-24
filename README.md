# skills-il/design-systems

Curated [DESIGN.md](https://github.com/google-labs-code/design.md) systems for Israeli teams. Every system ships:

- A single `DESIGN.md` file (Google Labs spec) tuned with Hebrew-first font stacks and an RTL-aware `## Localization` section.
- A `metadata.json` with directory metadata (display name, tagline, mood, fonts used).

## Browse

Live preview, install, and download at <https://agentskills.co.il/design>.

## Install

The fastest way to drop a design system into your project:

```bash
npx skills-il add-design <slug>
# example
npx skills-il add-design baniyan
```

This writes `DESIGN.md` to your project root. Point your coding agent (Claude Code, Cursor, Windsurf, GitHub Copilot, Codex, OpenCode, Antigravity, Gemini CLI) at the file and it will follow the system on every UI change.

To refresh later:

```bash
npx skills-il update-design <slug>
```

## Layout

```
systems/
  <slug>/
    DESIGN.md      ← the single source of truth, served verbatim
    metadata.json  ← directory metadata (consumed by the agentskills.co.il sync)
```

## Adding a system

PRs welcome. A submission must:

1. Include a `DESIGN.md` that passes `npx @google/design.md lint`.
2. Lead every `fontFamily` stack with a Hebrew-capable family (Heebo, Rubik, Assistant, Alef, Frank Ruhl Libre, Noto Sans Hebrew).
3. Include a `## Localization` section covering RTL rules, digit direction, nikkud handling, and quote style.
4. Provide a `metadata.json` with `slug`, `name_he` / `name_en`, `tagline_he` / `tagline_en`, `mood`, `fonts_used`, `version`, `author.github`.

## License

MIT — see [LICENSE](./LICENSE).
