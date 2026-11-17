# Project log

Newest first. Every AI session (Claude, Codex, anything else) adds an entry when it finishes.

Template:

```
## YYYY-MM-DD · <tool> · <branch>
**Did:** …
**Not done / blocked:** …
**Next:** …
```

---

## 2026-11-17 · Claude Code · claude/eager-pascal-a6e1yw
**Did:**
- Created the Shark House brand system: `docs/brand/SHARK_BRAND_SYSTEM.md`, the visual brand book `docs/brand/brand-book.html`, and design tokens `docs/brand/shark-tokens.css`.
- Designed three sibling brands on that system: Shark Exterior (orange, flagship), Shark Electric (yellow), Shark Detail (teal).
- Added `AGENTS.md` (shared AI instructions), `CLAUDE.md` (imports AGENTS.md), `docs/DECISIONS.md` and this log so Claude and Codex share context.

**Not done / blocked:**
- The CRM (`Shark-Exterior-Calendar-Tracker`) wasn't restyled yet. This session couldn't attach that repo without Easton's approval.

**Next:**
1. Easton answers the open questions in `docs/DECISIONS.md`.
2. Copy `AGENTS.md`, `CLAUDE.md` and `docs/` into the CRM repo.
3. Restyle the CRM with `shark-tokens.css` (Exterior theme), then add the Shark Service Standard automations (Fin's up text, photo report, review ask).
4. Restyle the website to match.
