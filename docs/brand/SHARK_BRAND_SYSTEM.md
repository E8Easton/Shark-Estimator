# Shark House — Brand System v1

Visual version: `docs/brand/brand-book.html`. Code tokens: `docs/brand/shark-tokens.css`.

## The idea

One family of companies that all look alike. The service changes; the look, the uniform, the van and the way we treat customers don't. A Shark Electric van parked next to a Shark Exterior van should read as the same team before anyone reads a word.

Three things we take from In-N-Out:
1. **A fixed look**, recognizable from 200 feet.
2. **A uniform people remember**, a little unusual on purpose.
3. **The same ritual every visit**, so the experience is the product.

## House constants (no company changes these)

| Element | Rule |
|---|---|
| Name | `SHARK` + one word. Wide, heavy wordmark; the service word in small spaced caps between two dashes. |
| Mark | The same fin, always. The line under it shows the trade. |
| Base colors | Deep Water navy `#0A1628`, Foam white `#F3F6FA`. Panels `#10213A`, lines `#1A3152`, muted text `#9DB0C8`. |
| Type | **Archivo Expanded** (width 125, weight 800–900) for headlines. **Archivo** for body text. **IBM Plex Mono** for tickets, job numbers and labels. All free on Google Fonts. |
| Uniform | Navy snap-front crew shirt, signature-color yoke across the shoulders with a thin white piping line, oval white name patch (first name), fin patch on the left sleeve, 4-segment rank bar on the chest. Navy cap with the fin. White shoe covers whenever inside. |
| Vehicle | White body, navy lower band, signature-color stripe above it, the lockup on the doors, a big fin on the back doors, crew number on the bumper. |
| Service | The Shark Service Standard (below), the Fin Check card, a photo report within an hour. |
| Membership | Shark Club, honored by every company. |
| Voice | Short, confident, friendly. Sharks never stop moving: we're on time and we finish. House promise: **"Sharp work. On time. Every time."** |

Signature color is for **accents only**: stripes, the yoke, buttons, highlights. Backgrounds stay navy or white.

## The companies

### Shark Exterior (flagship, launching now)
- Signature: **Shark Orange `#F26A1B`** · line: **water wave**
- Tagline: **"Glass so clear it disappears."**
- Services: windows inside and out, screens and tracks, house and soft washing, concrete, gutters
- Signature move, **The Glass Test:** on the Final Fin Check the tech hands the customer a microfiber cloth to wipe any window. If it streaks, it gets redone on the spot.

### Shark Electric (ready to open)
- Signature: **Voltage Yellow `#FFC629`** · line: **lightning bolt**
- Tagline: **"Wired right the first time."**
- Services: panel upgrades, EV chargers, lighting and fans, outlets and code fixes, generators and surge protection
- Signature move, **The Panel Map:** every job ends with a labeled, laminated circuit map taped inside the panel door, branded with the crew number.
- Needs a licensed master electrician on the license.

### Shark Detail (ready to open)
- Signature: **Lagoon Teal `#19C2B0`** · line: **speed lines**
- Tagline: **"Showroom, in your driveway."**
- Services: interior and exterior details, paint correction, ceramic coating, fleet washes, all mobile
- Signature move, **The Showroom Reveal:** the car stays under a branded cover until the customer walks out, then it comes off together. A fin-shaped air freshener goes on the mirror.

### Open slot
- **Kelp Green `#6CC24A`**, held for Shark Landscape or the next trade. Pick a new line under the fin (for example a grass blade).

## The Shark Service Standard (every visit, every company)

1. **"Fin's up" text, 30 minutes out:** tech photo, first name, rank, van. *(CRM automation)*
2. **Arrival:** knock, intro, shoe covers on, hand over the Fin Check card.
3. **Walkaround:** two minutes walking the job together, before photos.
4. **Work:** drop cloths, tools on a mat, leave the area cleaner than you found it.
5. **Final Fin Check:** walk it again and tick the card together. Fix anything on the spot.
6. **Photo report within one hour:** before and after photos plus the checklist. *(CRM automation)*
7. **Next day:** thank-you, one-tap review link, Shark Club invite. *(CRM automation)*

## Crew ranks (shown by the chest rank bar; carry across companies)

| Rank | Bar | Meaning |
|---|---|---|
| Pup | 1 of 4 | In training, always paired with a Hammerhead |
| Fin | 2 of 4 | Certified, runs jobs solo, passed a Fin Check audit |
| Hammerhead | 3 of 4 | Crew lead, trains Pups, closes on-site upsells, owns a van |
| Great White | 4 of 4 | Runs a company or territory |

## Shark Club

Recurring plans become a membership that every Shark company honors: priority booking, locked pricing, a member rate on the first job with a sister company, a member card and window decal, and one customer record across companies. Each new company opens with customers already waiting.

Existing plan pricing stays exactly as it is (see `PRICING_PLAN.md`). Only the names and packaging change.

## Rules for software (CRM, quote tool, website)

- Import `shark-tokens.css`. Set `data-company="exterior"` (or `electric`, `detail`, `landscape`) on `<html>`. Use `var(--sig)` for the accent; never hard-code the orange.
- Use the dark navy theme by default (`--bg`, `--panel`, `--line`, `--text`, `--muted`). Customer-facing documents (quotes, invoices, photo reports) use Foam white with navy text and a signature-color stripe.
- Buttons: signature color fill, navy text on Electric (yellow) and Detail (teal), white text on Exterior (orange). The `--sig-ink` token handles this.
- Headlines use `--font-display` with `font-stretch: 125%`.
- Job numbers, crew numbers and prices in tables use `--font-mono` with `tabular-nums`.

## Rollout for Shark Exterior

**Now (first 30 days):** finalize the lockup · 3–5 crew shirts, name patches, navy caps · van magnets and back-door fin decal · restyle the CRM and quote tool · print Fin Check cards, stock shoe covers.
**Next (days 30–90):** CRM automations for steps 1, 6 and 7 · rename plans to Shark Club tiers · 48-hour yard sign after every job · restyle the website · Pup and Fin training checklist.
**Later (6+ months):** multi-company CRM with a switcher · promote a Great White to run Exterior · open the next company on the same kit.
