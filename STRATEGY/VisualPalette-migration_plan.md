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
| `STRATEGY/fabrica-logo_icon.svg` / `.ico` / `.png` | Logo mark asset                                                         |

---

## 9. `orca/` codebase — migration findings (live audit)

> Audited against the tokens in §3–§6. Orca's own `docs/STYLEGUIDE.md` describes it as **"monochrome and quiet"**: neutral grays carry the chrome, color is reserved for *state only*. Its only visible brand hues today are a **blue sidebar primary `#1447e6`** (dark theme) and a **violet AI-action accent** — neither is Fabrica Copper. Everything below must be re-pointed to the Fabrica identity.

### 9.1 Brand Asset Integration (logo + icons)

| Asset | File | Notes |
| --- | --- | --- |
| App window / sidebar / onboarding logo | `orca/resources/logo.svg` | Current Orca mark (white path, transparent). **Replace with Fabrica mark.** Imported by `src/renderer/src/App.tsx:23`, `Landing.tsx:15`, `SidebarSettingsHelpMenu.tsx:17`, `OnboardingFlow.tsx:16`, `components/settings/orca-logo-settings-icon.tsx:3`, `components/mobile/slides/HomeSlide.tsx:250` (`OrcaLogo()`), `components/stats/share-card-utils.tsx:130` (`OrcaLogo()`), `StatsShareUsageCard.tsx:111`. |
| App icon (set) | `orca/resources/icon.png`, `icon-dev.png`, `build/icon.png`, `build/icon.ico`, `build/icon.icns` | Replace with Fabrica `.icns/.ico/.png` generated from `STRATEGY/fabrica-logo_icon.*`. |
| Secondary app icons | `orca/resources/app-icons/orca-watercolor.png`, `orca-blue.png` | Rebrand or drop. |
| macOS tray template | `orca/resources/tray/orca-menu-barTemplate.png` (+`@2x`) | Rename + swap to Fabrica glyph. |
| Settings icon component | `orca/src/renderer/src/components/settings/orca-logo-settings-icon.tsx` | **Rename → `fabrica-logo-settings-icon.tsx`**; update import + usage in `useSettingsNavigationMetadata.ts:39,268`. |
| `OrcaLogo()` builders | `components/stats/share-card-utils.tsx:130`, `components/mobile/slides/HomeSlide.tsx:250` | Rename to `FabricaLogo()`. |
| Web client app name | `src/renderer/src/web/web-preload-api.ts:551` (`name: 'Orca'`) | → `'Fabrica'`. |

### 9.2 Color Palette Alignment (tokens in `main.css`)

Canonical token file: `orca/src/renderer/src/assets/main.css`. The `@theme inline` block (lines 43–120) maps `--color-*` → CSS vars; the **actual values** live in the `:root` / `.dark` blocks:

| Token | Orca light (current) | Orca dark (current) | **Fabrica target** |
| --- | --- | --- | --- |
| `--background` | `#fff` | `#0a0a0a` | light `#FAF9F6` / `#ffffff`; dark `#121214` |
| `--foreground` | `#0a0a0a` | `#fafafa` | light `#1C1C1E`; dark `#FAF9F6` |
| `--primary` | `#171717` | `#e5e5e5` | Copper `#CC7A4A` (brand) — or keep near-black primary but add copper brand layer |
| `--border` | `#e5e5e5` | `rgb(255 255 255/.07)` | light `#E2E8F0`/`#2C2C2E`-class; dark `#2C2C2E` |
| `--ring` | `#a1a1a1` | `#737373` | copper-tinted ring `rgba(204,122,74,…)` |
| `--sidebar-primary` | `#171717` | `#1447e6` (blue) | **Copper `#CC7A4A`** (this is Orca's main brand color today → swap to copper) |
| `--ai-action-accent` | `violet-500` | `violet-400` | **Copper/amber** (`#CC7A4A` / `#e59320`) to match brand accent |
| `--primary-foreground` | `#fafafa` | `#171717` | contrast text on copper = `#ffffff` |

Apply per §6 rules: flat (`--shadow:none`), sharp radius, copper as the *sole* brand accent; green/red/amber/blue/violet kept only for status semantics. The status hues already exist as `--status-success/-error/-warn` etc. — verify they match §4 (success `#10b981`, error `#ef4444`/dark `#f43f5e`, warn `#f59e0b`).

### 9.3 Typography

`main.css` defines `--app-font-family: 'Geist', …` (line 127) and loads `Geist` + `Orca Nerd Font Symbols` via `@font-face` (lines 10–25). To match Fabrica §3.3:
- Add `@font-face` for **Inter** (UI/sans), **Space Grotesk** (display), **JetBrains Mono** (mono/technical labels).
- Repoint `--app-font-family` / `--font-sans` → Inter; add `--font-display` → Space Grotesk; `--font-mono` → JetBrains Mono.
- Keep `Orca Nerd Font Symbols` (terminal icon font) but consider renaming the family reference.

### 9.4 Non-visual scope moved out

All non-visual rebrand work — **Metadata & Distribution Configs, Auto-Updater & Release Channels, Deep-Link scheme (`orca://`→`fabrica://`), Backend/Telemetry endpoints (`onorca.dev`/PostHog → Fabrica), CLI command names & data directories, CI/CD, Homebrew, and user-visible product-name strings** — is now documented in **`STRATEGY/configs-migration_plan.md`** (with deeper `orca/` findings and ordered checklist). This file stays focused on visual identity only.

---

## 10. Ordered rebrand checklist for `orca/` (visual only)

1. **Assets:** drop Fabrica logo into `resources/logo.svg` + `build/icon.{icns,ico,png}` + `tray/` + `app-icons/`; rename `orca-logo-settings-icon.tsx` → `fabrica-logo-settings-icon.tsx` and `OrcaLogo()` → `FabricaLogo()`.
2. **Color tokens:** rewrite `:root` / `.dark` in `main.css` (§9.2 table) → Fabrica copper/cream/charcoal; repoint `--sidebar-primary` and `--ai-action-accent` to copper; verify status hues match §4.
3. **Typography:** add Inter/Space Grotesk/JetBrains Mono `@font-face`; repoint `--app-font-family` / `--font-sans` / `--font-mono` / `--font-display`.
4. **Verify (visual):** `pnpm lint` + `vitest` in `orca/`; build a smoke artifact; confirm light/dark contrast (copper `#CC7A4A` on `#121214` is WCAG-safe for UI text).

> Non-visual steps (metadata, launchers/casks, deep link, backend/telemetry, display strings, CI/CD) → **`STRATEGY/configs-migration_plan.md` §10**.


