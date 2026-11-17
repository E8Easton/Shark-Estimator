# AGENTS.md — read this first (Claude Code, Codex, and any other AI tool)

This file is the shared memory for every AI tool working on Shark projects.
Claude Code loads it through `CLAUDE.md`; Codex loads it directly.
**Before you change anything, read this file, `docs/PROJECT_LOG.md` (newest entries at the top) and, for any UI or brand work, `docs/brand/SHARK_BRAND_SYSTEM.md`.**
**When you finish, add an entry to the top of `docs/PROJECT_LOG.md`.**

---

## 1. Who and what

- **Owner:** Easton. Runs **Shark Exterior**: window cleaning, screens and tracks, house washing, pressure washing and gutters.
- **Goal:** be the best service company in the city, then the state, then the country. We win on **brand and experience**, not only the service. Think In-N-Out, not Subway.
- **Plan:** Shark Exterior is the flagship. More companies (Shark Electric, Shark Detail, possibly Shark Landscape) will launch on the same brand system and the same software.

## 2. Repos (GitHub: E8Easton)

| Repo | What it is | Status |
|---|---|---|
| `Shark-Exterior-Calendar-Tracker` | **The CRM.** Calendar, jobs, customers, quote tool. Live at sharkexteriorcalendar.netlify.app | Active, main product |
| `Shark-Exterior-Cleaning-Website` | Public marketing website | Active |
| `Leaf-Estimator` (this repo) | Old estimator. Retired 2026-10-26, every URL redirects to the CRM's `/quote-tool`. Now holds the **brand system** and pricing docs | Docs only |
| `Shark-Estimator` | Older estimator copy | Legacy |
| `shark-exteriors-payroll` | Payroll tool | Legacy or side tool |
| `Shark-Cleaning-Onboarding-Portal-` | Crew onboarding portal | Legacy or side tool |

Brand and pricing source of truth: `docs/brand/` and `PRICING_PLAN.md` / `QUOTING_GUIDE.md` in this repo. Copy this file and `docs/` into any repo you work in if they're missing.

## 3. Hard rules

1. **Do not change pricing numbers** (pane tiers, plan discounts, the $125 floor, the French pane × 0.4 rule) unless Easton asks for that exact change. Pricing lives in `client/src/lib/pricing.ts` here and in the CRM's price book.
2. **Do not rename the business or change brand colors** on your own. Brand decisions are in `docs/brand/SHARK_BRAND_SYSTEM.md`. Follow it.
3. **Stay on scope.** Only touch files the task needs. No drive-by refactors, no reformatting whole files, no dependency upgrades unless asked.
4. **Never commit secrets.** Supabase keys and the like go in `.env` (git-ignored) or Netlify environment variables. `.env.example` shows the names only.
5. **Work on a branch and open a PR.** Don't push straight to `main`. Easton merges.
6. **Say plainly what you did and didn't do** in the PR and in the project log, including anything you couldn't test.
7. **Mobile first.** Easton and the crew use these apps on phones in driveways. Big tap targets, readable in sunlight.

## 4. Tech stack (this repo; the CRM is similar, so check its package.json)

- Vite + React 19 + TypeScript, Tailwind CSS v4, shadcn/ui (Radix), wouter for routing, lucide-react icons
- pnpm (`pnpm install`, `pnpm dev`, `pnpm check`, `pnpm build:netlify`)
- Hosting: Netlify (static SPA). Optional cloud sync: Supabase (`supabase/migrations/`)
- Font today: Outfit. Brand target: Archivo + IBM Plex Mono (see brand system)

## 5. Brand in one paragraph

**Shark House** is one family of companies that all look alike. House constants: **Deep Water navy `#0A1628`**, **Foam white `#F3F6FA`**, the **fin mark**, Archivo type, the crew uniform, the van layout, the 7-step **Shark Service Standard** and the **Shark Club** membership. Each company swaps only **one signature color** and the line under the fin:
- Shark Exterior: **Shark Orange `#F26A1B`**, water wave
- Shark Electric: **Voltage Yellow `#FFC629`**, lightning bolt
- Shark Detail: **Lagoon Teal `#19C2B0`**, speed lines
- Open slot: **Kelp Green `#6CC24A`** (Landscape)

In code, use the tokens in `docs/brand/shark-tokens.css`. The company is chosen by `data-company="exterior|electric|detail|landscape"` on `<html>`, so one codebase can theme all the companies.

## 6. How to hand off between Claude and Codex

- Both tools work through **GitHub**. Whatever is merged to `main` is what the next tool sees, so merge or at least push the branch before switching.
- At the end of every session, add a `docs/PROJECT_LOG.md` entry: date, tool, what changed, what's unfinished, what's next.
- Starting a session in either tool, say: *"Read AGENTS.md and the latest PROJECT_LOG entry, then continue."*
- Big decisions go in `docs/DECISIONS.md`, one line each, so nobody re-argues them.
