# Fabrica Visual Palette — Plan &amp; Extraction

> Source of truth for the Fabrica visual identity. Everything below was extracted directly from `old-fabrica/` (frontend code, CSS, Tailwind config, and the brand slide deck reference). This is the **one** palette document to implement the rebrand against.

---

## 1. Brand Theme (from `CHANGELOG.md`)

> "**Style:** blueprint/draftsman theme — cream `#f5f2eb`, charcoal `#1a1a1a`, amber `#f2a93b`, teal `#1a8c7b`, neo-brutalist thick borders, drafting-grid background, monospace technical labels, + a dark variant (theme toggle)."

**Theme name concept:** "BluePrint / Draftsman" — Fabrica is designed and built like a blueprint / engineering draft:

- Thick neo-brutalist borders
- Drafting-grid backgrounds
- Monospace technical labels (JetBrains Mono)
- Display headings in Space Grotesk

---

## 2. Brand Logo &amp; Colors

- **Logo icon:** `Fabrica-ADE/Assets/fabrica-logo_icon.ico` (SVG source at `STRATEGY/Assets/fabrica-logo_icon.svg`, PNG at `..._icon.png`, plus `fabrica-logo.jpg`). A mark drawn like a drafting/technical emblem.

### Hero Brand Colors (Tailwind config `old-fabrica/frontend-next/tailwind.config.js`)


| Token            | Value              | Use                                   |
| ---------------- | ------------------ | ------------------------------------- |
| `brand.orange`   | `#e59320`          | Brand accent (amber/orange)           |
| `brand.dark`     | `#070a13`          | Brand dark / background               |
| `*Copper accent` | `#CC7A4A` (inline) | copper hover (`Fabrica` wordmark dot) |


---

## 3. CSS Token System — Core Palette

> Canonical source: `old-fabrica/frontend-next/app/globals.css` (Dashboard Blueprint/Draftsman theme).

### 3.1 Light (default `:root`)


| Token                      | Value     | Role                                                            |
| -------------------------- | --------- | --------------------------------------------------------------- |
| `--bg`                     | `#ffffff` | Page background                                                 |
| `--surface`                | `#ffffff` | Panel / card surface                                            |
| `--surface-alt`            | `#F8FAFC` | Chips, inputs, alternate rows                                   |
| `--border`                 | `#E2E8F0` | Borders                                                         |
| `--border-soft`            | `#E2E8F0` | Soft/dashed borders                                             |
| `--text`                   | `#1C1C1E` | Primary text                                                    |
| `--muted`                  | `#7E7E86` | Secondary / labels                                              |
| `--accent`                 | `#CC7A4A` | **Fabrica Copper**                                              |
| `--accent-2`               | `#CC7A4A` | **Fabrica Copper Accent**                                       |
| `--accent-contrast`        | `#ffffff` | Text on accent                                                  |
| `--status-success`         | `#10b981` | Success                                                         |
| `--status-error`           | `#ef4444` | Error                                                           |
| `--status-warn`            | `#f59e0b` | Warning                                                         |
| `--shadow` / `--shadow-sm` | `none`    | Flat design default                                             |
| `--r`                      | `0px`     | Border radius default (sharp) individual elements add their own |


### 3.2 Dark (`[data-theme="dark"]`)


| Token              | Value     | Role                          |
| ------------------ | --------- | ----------------------------- |
| `--bg`             | `#121214` | Page background               |
| `--surface`        | `#121214` | Panel / card surface          |
| `--surface-alt`    | `#1C1C1E` | Chips, inputs, alternate rows |
| `--border`         | `#2C2C2E` | Borders                       |
| `--border-soft`    | `#2C2C2E` | Soft borders                  |
| `--text`           | `#FAF9F6` | Primary text (warm off-white) |
| `--muted`          | `#8E8E93` | Secondary / labels            |
| `--accent`         | `#CC7A4A` | **Fabrica Copper**            |
| `--accent-2`       | `#CC7A4A` | Copper Accent                 |
| `--status-success` | `#10b981` | Success                       |
| `--status-error`   | `#f43f5e` | Error (rose)                  |
| `--status-warn`    | `#f59e0b` | Warning                       |


### 3.3 Typography / Fonts


| Token            | Stack                                                                          |
| ---------------- | ------------------------------------------------------------------------------ |
| `--mono`         | `"JetBrains Mono", ui-monospace, "SFMono-Regular", Menlo, Consolas, monospace` |
| `--sans`         | `"Inter", system-ui, -apple-system, Segoe UI, Roboto, sans-serif`              |
| `--font-display` | `"Space Grotesk", var(--sans)` (headings h1–h5)                                |


**Fluid type rule:** `html { font-size: clamp(10px, 0.75vw + 7.5px, 15.5px) }`. Everything (padding, gaps, radius, font) is `clamp()` — scales continuously, never clips.

---

## 4. Semantic / State Colors (extracted throughout globals.css)


| Area                               | Value(s)                                                       | Meaning                   |
| ---------------------------------- | -------------------------------------------------------------- | ------------------------- |
| Priority crit                      | `#ef4444`                                                      | Critical card left border |
| Priority high                      | `#f59e0b`                                                      | High card left border     |
| Priority low                       | `#94a3b8`                                                      | Low card left border      |
| Priority draft                     | `#8a8f98`                                                      | Draft                     |
| Mission dots standard              | `#6b7280` gray                                                 |                           |
| Mission dots research              | `#3b82f6` blue                                                 |                           |
| Mission dots analytics             | `#8b5cf6` violet                                               |                           |
| Mission dots evolution             | `#f59e0b` amber                                                |                           |
| Discovery tier                     | `#8a7fd6` violet                                               | pre-raw pipeline stage    |
| Analysing tier                     | `#d6a13b` amber                                                | pipeline stage            |
| Danger button                      | `#a32424` bg / `#c73a3a` border                                |                           |
| Alert banner                       | `#b34d00` bg / `#ff7a18` border / white text                   |                           |
| Save status saved                  | `#1f7a3d` / white                                              |                           |
| Save status unsaved                | `#b8860b` / white                                              |                           |
| Save status error                  | `#a32424` / white                                              |                           |
| Move tag                           | `#6a8cff` blue                                                 |                           |
| Maturity stub                      | `--border-soft`                                                |                           |
| Maturity functional                | `#10b981`                                                      |                           |
| Maturity hardened                  | `#f59e0b`                                                      |                           |
| Maturity tested                    | `#a855f7` purple                                               |                           |
| Progress gradient (accent-2→green) | `linear-gradient(90deg, var(--accent-2), #059669)`             |                           |
| Agent FAB gradient                 | `linear-gradient(135deg, #10b981, #059669)`                    |                           |
| Modal overlay                      | `rgba(15, 23, 42, 0.6)` + `backdrop-filter: blur(8px)`         |                           |
| Floating window shadow             | `0 20px 50px rgba(0,0,0,0.3)` / `0 20px 60px rgba(0,0,0,0.35)` |                           |
| Boot log bg                        | `#0f172a` (dark slate) w/ copper text                          |                           |


### Interaction / hover language

- Hover accent: mostly `var(--accent)` copper borders + subtle `translateY(-1px)` lift.
- Active: `translateY(0)` scale-down.
- Interactions tinted with `color-mix(in srgb, var(--accent) N%, ...)` (never hard-coded shades).
- Focus ring: `box-shadow: 0 0 0 3px rgba(242,169,59,0.18)` (copper glow).

---

## 5. Landing Page Palette (extracted from `frontend-next/app/page.tsx`)

Used for marketing/landing tier of the same identity:

- Background cream: `#FAF9F6` (light) / `#0E1117` (dark panels)
- Charcoal text: `#1C1C1E`
- **Copper CTA gradient:** `from-[#CC7A4A] to-[#b2693e]`, hover `to-[#96552f]`
- Dark chrome panels: `#0E1117`, `#141824`, `#131722`, `#11141D`, `#0D101A`, `#0A0D14`, `#1C2233` (hover)
- Borders: `slate-700/80`, `slate-800/90`, `slate-800`
- Online status dot: `emerald-400`
- Input focus: `amber-500/60`
- Text accents: charcoal-to-slate gradients `from-[#1C1C1E] to-slate-900`
- Wordmark dot: `#CC7A4A` ("Fabrica" + copper `.`)

### Copper scale (derived from gradients)


| Value     | Usage                             |
| --------- | --------------------------------- |
| `#96552f` | deepest copper (end hover)        |
| `#b2693e` | mid copper                        |
| `#CC7A4A` | **signature copper**              |
| `#f2a93b` | amber brand (slide-deck heritage) |
| `#e59320` | tailwind brand orange             |


---

## 6. Visual Personality &amp; Rules (how the palette must be applied)

1. **Flat + technical:** no shadows by default (`--shadow: none`, `--r: 0px`); radius only where individual components need it. Feels like an engineering drawing / mission-control console.
2. **Neo-brutalist / drafting grid:** thick (1.5–2px+) borders, dashed "empty/suggested" slots, uppercase letter-spaced micro-labels in mono.
3. **Copper = single brand accent.** It must stay the sole "brand" color; everything else (green/red/amber/blue/violet) is reserved for **status &amp; category semantics only**.
4. **Light &amp; dark both supported** via `data-theme="dark"`. Dark never uses pure black — `#121214` bg, `#2C2C2E` borders so panels stay distinguishable.
5. **Both codebases must converge on this:** the old-fabrica palette (this doc) is the design north star; the Orca-based Fabrica UI must adopt these tokens instead of inventing new colors.

---

## 7. Implementation Plan (to apply during rebrand)

- [ ] 1. Map Orca's current design tokens (see Orca `docs/STYLEGUIDE.md` + `src/renderer/src/assets/main.css`) to the Fabrica tokens above.
- [ ] 2. Replace brand accent → **Fabrica Copper `#CC7A4A`** (primary CTA / active states), secondary → **amber `#e59320`** (warnings/accents).
- [ ] 3. Set backgrounds: light `#FAF9F6` / `#ffffff` surfaces; dark `#121214` + `#1C1C1E` surfaces, `#2C2C2E` borders, `#FAF9F6` text.
- [ ] 4. Adopt typography: `Inter` (UI), `Space Grotesk` (display/headings), `JetBrains Mono` (technical labels/slugs).
- [ ] 5. Apply flat/sharp look: kill default shadows, `--r: 0`, rely on 1–2px borders + hover lifts for depth.
- [ ] 6. Keep status/semantic set intact: success `#10b981`, error `#ef4444`/dark `#f43f5e`, warn `#f59e0b`, plus the mission-dot/category hues.
- [ ] 7. Swap brand iconography: `fabrica-logo_icon.svg` in window chrome, tray, taskbar.
- [ ] 8. Verify both light/dark themes against contrast (copper `#CC7A4A` on `#1C1C1E` gives ~WCAG-safe contrast for UI text).

---

## 8. Source files inventory (where each token came from)


| File                                               | What it contributes                                                         |
| -------------------------------------------------- | --------------------------------------------------------------------------- |
| `old-fabrica/frontend-next/app/globals.css`        | Canonical token system, status colors, component looks                      |
| `old-fabrica/frontend-next/tailwind.config.js`     | `brand.orange` `#e59320`, `brand.dark` `#070a13`                            |
| `old-fabrica/frontend-next/app/page.tsx`           | Landing-page copper palette + dark chrome                                   |
| `old-fabrica/CHANGELOG.md`                         | Theme description + original slide-deck palette (cream/charcoal/amber/teal) |
| `old-fabrica/README.md` + `metadata.json`          | Product positioning ("Your Next AI EXIT")                                   |
| `STRATEGY/fabrica-logo_icon.svg` / `.ico` / `.png` | Logo mark asset                                                             |


