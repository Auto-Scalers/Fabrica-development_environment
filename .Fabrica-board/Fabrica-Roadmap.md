# Fabrica — Roadmap

> Central command. Vision/identity → `Fabrica-DNA.md`. Execution details → sub-project task files.

---

## Dashboard


| Metric | Value |
|--------|-------|
| Total tasks | 100 |
| ✅ Done | 68 |
| 🔶 Partial | 0 |
| ⬜ Todo | 16 |
| 📋 Planning | 15 |
| 🚫 Blocked | 1 |
| ❌ Issues | 0 |
| Completion | 68% |


### Phase Progress

```
Phase 1 — Rebranding & Foundation
Fabrica-app      ✅ 35 ⬜ 20 🚫 1                   [████████████████████] 84%
Fabrica-web      ✅ 13 ⬜ 0  📋 2                 [████████████████████] 100%
Fabrica-marketing 📋 13                           [██░░░░░░░░░░░░░░░░░░] 19%
Fabrica-plugins  ✅ 13 ⬜ 3                        [████████████████░░░░] 81%

Phase 2 — Business-First UI & Agentic Layer
Fabrica-app      ⬜ 7                               [░░░░░░░░░░░░░░░░░░░░] 0%
```

---

## Right Now

> What's actively being tracked. Update this section as work progresses.


| What | Status | Owner | Notes |
|------|--------|-------|-------|
| App rebranding — display identity | ✅ Done | Fabrica-app | App name, menu, firewall, helper, CLI, env vars, keychain, wire tokens, plugin engines, data dirs, casks, i18n, deep links |
| API routes (W1-W7) | ✅ Done | Fabrica-web | All 9 route files built, no TS errors |
| Plugin source study (P0a-P0f) | ✅ Done | Fabrica-plugins | 9 repos cloned, schemas documented |
| Marketing plans (M1-M13) | 📋 Planning | Fabrica-marketing | All 13 tasks have detailed plans (696 lines) |
| CI workflows | ✅ Done | Fabrica-app | All 8 workflows renamed stablyai → Auto-Scalers |
| SKILL.md files | ✅ Done | Fabrica-app | All rebranded (remaining "orca" = GNOME Orca screen reader, correct) |
| Localized READMEs | ✅ Done | Fabrica-app | zh-CN, pt, ko, ja, fr, es all rebranded |
| CONTRIBUTING.md | ✅ Done | Fabrica-app | Rebranded |
| WINDOWS_SETUP_GUIDE.md | ✅ Done | Fabrica-app | Rebranded, zero orca/stablyai refs |
| OAuth callback route | ✅ Done | Fabrica-web | Created /api/auth/callback/route.ts |
| package.json name | ✅ Done | Fabrica-web | Renamed from saas-landing-page to fabrica-web |
| docs/reference/ files | ✅ Done | Fabrica-app | Rebranded (remaining refs = historical GitHub URLs + orca-cli skill name) |
| Attribution footer | ✅ Done | Fabrica-app | "Made with [FABRICA]" — verified clean |
| Static files (W8-W10) | ✅ Done | Fabrica-web | Changelog, nudge, kill-list JSON created |
| Docs site (W11) | ✅ Done | Fabrica-web | Layout, sidebar, content, build compiles |
| Landing page updates (W12-W13) | 📋 Planning | Fabrica-web | Audit Orca references |
| Plugin marketplace (P1-P5) | 🔶 P1 Done | Fabrica-plugins | marketplace-index.json created, P2-P5 remaining |
| PostHog + GitHub secrets                   | ✅ Done        | Orchestrator      | Write key + build identity set                                                                                             |
| Release repos (hourly/daily/adhoc/plugins) | ✅ Done        | Orchestrator      | All 4 repos created                                                                                                        |
| F1: Full rebrand audit                     | ✅ Done        | Orchestrator      | ORCA-RELAY→FABRICA-RELAY (35 files), orca-mobile-e2ee→fabrica-mobile-e2ee (4 files), README.md rebranded, CLI type investigated |
| README.md rebrand                          | ✅ Done        | Orchestrator      | Main README.md rebranded (was missed in earlier sweeps)                                                                    |
| Marketplace filename fix                    | ✅ Done        | Orchestrator      | Renamed marketplace-index.json → fabrica-marketplace.json (app looks for this name)                                        |
| Kill list URL fix                           | ✅ Done        | Orchestrator      | Changed onFABRICA.dev → fabrica-ai.vercel.app (real web domain)                                                            |
| Categories filter removal                   | ✅ Done        | Orchestrator      | Removed UNSUPPORTED_MARKETPLACE_CATEGORIES — show all plugins like Orca                                                    |
| Plugin repos created                        | ✅ Done        | Orchestrator      | 8 GitHub repos created under Auto-Scalers, added as submodules in Fabrica-plugins/                                         |


---

## Phase 1 — Rebranding &amp; Foundation

> Make the Orca codebase fully Fabrica.

### Progress


| Sub-Project       | ✅ Done | 🔶 Partial | ⬜ Todo | 📋 Planning | 🚫 Blocked | ❌ Issues | Task File                                                               |
| ----------------- | ------ | ---------- | ------ | ----------- | ---------- | -------- | ----------------------------------------------------------------------- |
| Fabrica-app       | 38     | 0          | 17     | 0           | 1          | 0        | `Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md`                   |
| Fabrica-web       | 13     | 0          | 0      | 2           | 0          | 0        | `Fabrica-web/.Fabrica-web-board/Fabrica-web-tasks.md`                   |
| Fabrica-marketing | 0      | 0          | 0      | 13          | 0          | 0        | `Fabrica-marketing/.Fabrica-marketing-board/Fabrica-marketing-tasks.md` |
| Fabrica-plugins   | 15     | 0          | 1      | 0           | 0          | 0        | `Fabrica-plugins/.Fabrica-plugins-board/Fabrica-plugins-tasks.md`       |
| **Total**         | **66** | **0**      | **18** | **15**      | **1**      | **0**    |                                                                         |


---

### Fabrica-app — Source Code

> Desktop app, CLI, mobile companion, relay, plugins, build system.

```
Progress [████████████████████] 84%  ✅ 35 ⬜ 20 🚫 1
```

#### Group A — Display &amp; Visible Identity


| #   | Task                                      | Status |
| --- | ----------------------------------------- | ------ |
| A1  | App name / productName / About / app menu | ✅      |
| A2  | Firewall rule display name                | ✅      |
| A3  | Computer Use helper app name              | ✅      |


#### Group B — CLI &amp; Install Paths


| #   | Task                                           | Status |
| --- | ---------------------------------------------- | ------ |
| B1  | CLI command rename (`orca` → `fabrica`)        | ✅      |
| B2  | Install paths rename                           | ✅      |
| B3  | Environment variables (`ORCA_*` → `FABRICA_*`) | ✅      |
| B4  | Git co-author trailer                          | ✅      |


#### Group C — Runtime Identity


| #   | Task                                 | Status           |
| --- | ------------------------------------ | ---------------- |
| C1  | Wire tokens (`fabrica_server_ready`) | ✅                |
| C2  | Keychain service name                | ✅                |
| C3  | TLS certificate CN                   | ✅                |
| C4  | Data directories                     | 🚫 BLOCKED on A1 |


#### Group D — Plugin Ecosystem


| #   | Task                                                 | Status |
| --- | ---------------------------------------------------- | ------ |
| D1  | Plugin `engines.orca` → `engines.fabrica`            | ✅      |
| D2  | Plugin publisher rename (`stablyai` → `autoscalers`) | ✅      |
| D3  | Plugin marketplace repos on GitHub                   | ✅      |
| D4  | Plugin kill-list URL                                 | ✅      |
| D5  | Bundled plugin content hashes                        | ✅      |


#### Source Code Renames


| #   | Task                                                                  | Status |
| --- | --------------------------------------------------------------------- | ------ |
| 1   | GitHub org + repo refs (`stablyai/orca` → `Auto-Scalers/Fabrica-app`) | ✅      |
| 2   | `orca://` deep link → `fabrica://`                                    | ✅      |
| 3   | PostHog env vars                                                      | ✅      |
| 4   | Diagnostics env vars                                                  | ✅      |
| 5   | Build identity env var                                                | ✅      |
| 6   | Attribution footer                                                    | ✅      |
| 7   | Product URL env var                                                   | ✅      |
| 8   | Feature wall docs URLs                                                | ✅      |


#### CI/CD Workflows

> All 8 workflows renamed from stablyai → Auto-Scalers.

| #   | Task                                           | Status |
| --- | ---------------------------------------------- | ------ |
| 1   | `hourly-mac-build.yml` — rename org refs       | ✅      |
| 2   | `daily-mac-build.yml` — rename org refs        | ✅      |
| 3   | `adhoc-mac-build.yml` — rename org refs        | ✅      |
| 4   | `release-cut.yml` — rename org refs            | ✅      |
| 5   | `release-mac-build.yml` — rename org refs      | ✅      |
| 6   | `release-policy.yml` — rename org refs         | ✅      |
| 7   | `readme-downloads-badge.yml` — rename org refs | ✅      |
| 8   | `homebrew-bump.yml` — rename org refs          | ✅      |


#### Localized READMEs & Docs

> All rebranded. Remaining "orca" refs = historical GitHub URLs + orca-cli skill name (correct).

| #   | Task                                           | Status |
| --- | ---------------------------------------------- | ------ |
| 1   | `README.zh-CN.md` — full rebrand               | ✅      |
| 2   | `README.pt.md` — full rebrand                  | ✅      |
| 3   | `README.ko.md` — full rebrand                  | ✅      |
| 4   | `README.ja.md` — full rebrand                  | ✅      |
| 5   | `README.fr.md` — full rebrand                  | ✅      |
| 6   | `.github/CONTRIBUTING.md` — full rebrand       | ✅      |
| 7   | `WINDOWS_SETUP_GUIDE.md` — full rebrand         | ✅      |
| 8   | `docs/STYLEGUIDE.md` — full rebrand            | ✅      |


#### i18n &amp; Homebrew


| #   | Task                               | Status |
| --- | ---------------------------------- | ------ |
| 1   | `en.json` — 621 "Orca" occurrences | ✅      |
| 2   | All other locales (ko, ja, zh, es) | ✅      |
| 3   | `Casks/fabrica.rb`                 | ✅      |
| 4   | `Casks/fabrica@rc.rb`              | ✅      |


#### Visual, Configs, Relay


| #   | Task                                         | Status |
| --- | -------------------------------------------- | ------ |
| 1   | Capture aesthetic reference from Fabrica-web | ✅      |
| 2   | Apply palette to app                         | ✅      |
| 3   | Clean build verification                     | ✅      |
| 4   | Configs migration                            | ✅      |
| 5   | Auto-updater                                 | ✅      |
| 6   | Deep linking (`orca://` → `fabrica://`)      | ✅      |
| 7   | Build relay server                           | ⬜      |
| 8   | Deploy to Fly.io                             | ⬜      |


#### Skill Files

> All 8 SKILL.md files verified clean. Remaining "orca" refs = GNOME Orca screen reader (correct).

| #   | Task                                                                            | Status |
| --- | ------------------------------------------------------------------------------- | ------ |
| 1   | `skills/fabrica-cli/SKILL.md` — fixed incorrect over-rebrand                    | ✅      |
| 2   | `skills/orchestration/SKILL.md` — verified clean                                | ✅      |
| 3   | `skills/computer-use/SKILL.md` — verified clean                                 | ✅      |
| 4   | `skills/fabrica-linear/SKILL.md` — verified clean                               | ✅      |


#### Documentation

> All rebranded. Remaining "orca" refs = historical GitHub URLs + orca-cli skill name (correct).

| #   | Task                                                | Status |
| --- | --------------------------------------------------- | ------ |
| 1   | `docs/STYLEGUIDE.md` — full rebrand                 | ✅      |
| 2   | `config/i18n-translation-source.md` — rebranded     | ✅      |
| 3   | `config/localization-audit.md` — rebranded          | ✅      |
| 4   | `docs/reference/*.md` — all 7 files rebranded       | ✅      |
| 5   | Test README files — rebranded                       | ✅      |


#### Final Verification


| #   | Task                         | Status |
| --- | ---------------------------- | ------ |
| 1   | Full rebrand audit | ✅      |
| 2   | Clean build on all platforms | ⬜      |
| 3   | Lint + test pass             | ⬜      |


---

### Fabrica-web — Landing Page + API Routes

```
Progress [████████████████████] 100%  ✅ 13 ⬜ 0  📋 2
```

#### API Routes


| #     | Endpoint                              | Status |
| ----- | ------------------------------------- | ------ |
| W1    | `/api/auth/authorize` (OAuth PKCE)    | ✅      |
| W2    | `/api/auth/session`                   | ✅      |
| W3    | `/api/auth/refresh`                   | ✅      |
| W4    | `/api/auth/logout`                    | ✅      |
| W5    | `/api/share/*` (Artifact sharing)     | ✅      |
| W6    | `/api/diagnostics/*` (Crash/feedback) | ✅      |
| W7    | `/api/telemetry` (Analytics fallback) | ✅      |
| W8    | `/api/auth/callback` (OAuth callback) | ✅      |


#### Static Files &amp; Docs


| #   | Task                                | Status |
| --- | ----------------------------------- | ------ |
| W8  | `/whats-new/changelog.json`         | ✅      |
| W9  | `/whats-new/nudge.json`             | ✅      |
| W10 | `/plugins/kill-list.json`           | ✅      |
| W11 | `/docs/*` (migrate from onorca.dev) | ✅      |


#### Landing Page Updates

> **PLANNING MODE** — Plan and refine only.


| #   | Task                               | Status |
| --- | ---------------------------------- | ------ |
| W12 | Audit Orca references in page copy | 📋     |
| W13 | Update meta tags / OG images       | 📋     |


---

### Fabrica-marketing — Brand + Launch

```
Progress [██░░░░░░░░░░░░░░░░░░] 19%  📋 13
```

#### Brand &amp; Positioning

> **PLANNING MODE** — Plan and refine only.


| #   | Task                              | Status |
| --- | --------------------------------- | ------ |
| M1  | Finalize brand guidelines         | 📋     |
| M2  | Competitor landscape doc          | 📋     |
| M3  | Positioning statement / one-pager | 📋     |


#### Launch Materials

> **PLANNING MODE** — Plan and refine only.


| #   | Task                          | Status |
| --- | ----------------------------- | ------ |
| M4  | Launch blog post              | 📋     |
| M5  | Product Hunt listing + assets | 📋     |
| M6  | Hacker News "Show HN" post    | 📋     |
| M7  | Press kit                     | 📋     |
| M8  | Email launch sequence         | 📋     |


#### Content &amp; Early Access

> **PLANNING MODE** — Plan and refine only.


| #   | Task                          | Status |
| --- | ----------------------------- | ------ |
| M9  | Social media content calendar | 📋     |
| M10 | Twitter/X thread templates    | 📋     |
| M11 | Founder story / origin post   | 📋     |
| M12 | Early access nurture emails   | 📋     |
| M13 | Waitlist page copy            | 📋     |


---

### Fabrica-plugins — Plugin Marketplace

```
Progress [███████████████████░] 94%  ✅ 15 ⬜ 1
```

#### Orca Source Study

> Clone and study original Orca plugin repos before building Fabrica equivalents.


| #   | Task                                            | Status |
| --- | ----------------------------------------------- | ------ |
| P0a | Clone `stablyai/orca-plugins` into `_sources/`  | ✅      |
| P0b | Clone bundled plugin repos into `_sources/`     | ✅      |
| P0c | Clone theme/skill plugin repos into `_sources/` | ✅      |
| P0d | Study marketplace index format                  | ✅      |
| P0e | Study bundled plugin manifest format            | ✅      |
| P0f | Document rename strategy                        | ✅      |


#### Marketplace &amp; Schema


| #   | Task                              | Status |
| --- | --------------------------------- | ------ |
| P1  | Initialize marketplace index JSON | ✅      |
| P2  | Add bundled plugins to index      | ✅      |
| P3  | Plugin submission guidelines      | ✅      |
| P4  | Define plugin manifest schema     | ✅      |
| P5  | Plugin validation rules           | ✅      |


#### Quality &amp; Integration


| #   | Task                                 | Status |
| --- | ------------------------------------ | ------ |
| P6  | Plugin review process                | ✅      |
| P7  | Kill-list management                 | ✅      |
| P8  | Plugin signing (future)              | ⬜      |
| P9  | Plugin loader reads from marketplace | ✅      |
| P10 | Plugin update mechanism | ✅      |


---

## Phase 2 — Business-First UI &amp; Agentic Layer

> Transform from coding-first to business-first. Non-technical founders control everything from the UI.
new repo to take from : https://github.com/block/buzz, but check the icence first.

```
Progress [░░░░░░░░░░░░░░░░░░░░] 0%  ⬜ 7
```

### Features


| #   | Task                                                       | Status |
| --- | ---------------------------------------------------------- | ------ |
| 1   | UI-driven task lifecycle (Draft → Plan → Execute → Verify) | ⬜      |
| 2   | Agent crew definitions                                     | ⬜      |
| 3   | Orchestration &amp; supervision from UI                    | ⬜      |
| 4   | Data visualization &amp; dashboards                        | ⬜      |
| 5   | Business intelligence features                             | ⬜      |
|     | Ralph and gsd + the aready orcastrations systems we have   |        |


### Mission-Control Integration

> Source: `Auto-Scalers/Fabrica/mission-control` (AGPL-3.0). License-safe clean-room reimplementation.


| #   | Task                                          | Status |
| --- | --------------------------------------------- | ------ |
| 1   | Extract functional specs from mission-control | ⬜      |
| 2   | Audit specs                                   | ⬜      |


---

## Reference

### App ID

**Unified across all platforms:** `ai.autoscalers.fabrica`


| Platform                 | Value                                 |
| ------------------------ | ------------------------------------- |
| electron-builder appId   | `ai.autoscalers.fabrica`              |
| macOS CFBundleIdentifier | `ai.autoscalers.fabrica`              |
| macOS helper             | `ai.autoscalers.fabrica.computer-use` |
| Windows AUMID            | `ai.autoscalers.fabrica`              |
| Windows/Linux            | `ai.autoscalers.fabrica`              |
| Deep link protocol       | `fabrica://`                          |
| Future iOS bundle ID     | `ai.autoscalers.fabrica`              |
| Future Android package   | `ai.autoscalers.fabrica`              |


### Infrastructure


| Service            | Where                     | Owner           |
| ------------------ | ------------------------- | --------------- |
| Landing page       | Vercel                    | Fabrica-web     |
| Backend API        | Vercel (API routes)       | Fabrica-web     |
| Auth               | Supabase (shared project) | Fabrica-web     |
| Telemetry          | PostHog                   | Fabrica-app     |
| Relay              | Fly.io                    | Fabrica-app     |
| Auto-updater       | GitHub Releases           | Fabrica-app     |
| Plugin marketplace | GitHub repo               | Fabrica-plugins |


### Deferred Items


| Item            | Blocker                    | What's Needed                        |
| --------------- | -------------------------- | ------------------------------------ |
| Code signing    | Apple Developer Program    | $99/year Apple Dev, Windows SignPath |
| App Store (iOS) | Apple Dev Program + review | Dev membership, listing, review      |
| Google Play     | $25 fee                    | Google Play Developer account        |


---

## Session Ledger (Master)

> Central view of all orchestration sessions across sub-projects. Each sub-project's task file contains its own detailed ledger.

### Sub-Orchestrator Sessions (permanent, 24/7)

| Session | Worktree | Task File | Status |
|---------|----------|-----------|--------|
| `term_905a82bc-8472-4451-91d5-4fe8a3c9c67b` | `Fabrica-app/` | `Fabrica-app-tasks.md` | **active** |
| `term_0adb1b43-ceeb-47c7-ad47-f65f6df17d3e` | `Fabrica-web/` | `Fabrica-web-tasks.md` | **active** |
| `term_f667dbf4-72e5-44c5-87af-d8519f90f3e9` | `Fabrica-marketing/` | `Fabrica-marketing-tasks.md` | **active** |
| `term_24ff1a27-8b86-43f8-9206-73367917448f` | `Fabrica-plugins/` | `Fabrica-plugins-tasks.md` | **active** |

### Worker Sessions (ephemeral — released after review)

| Session | Parent Orchestrator | Task | Status | Worktree Merged |
|---------|-------------------|------|--------|----------------|
| `term_8274ea16-fd28-4b9a-9d9e-7fa10cb6d650` | app-orchestrator | P9: Plugin loader | **released** | ✅ |
| `term_4a73d6e4-0033-4910-a2b8-9af3e1dfc841` | app-orchestrator | P10: Plugin updates | **released** | ✅ |
| `term_b9293715-3f95-42f3-b041-d6b12117d5e1` | app-orchestrator | Docs rebrand | **released** | ✅ |
| `term_1dfdcd8e-5f99-4589-b08a-5754d93d9049` | app-orchestrator | SKILL.md rebrand | **released** | ✅ |
| `term_f77a5a04-5949-46a1-954f-b6252a12ca4b` | app-orchestrator | CI workflows rebrand | **released** | ✅ |

### Abandoned Worktrees (removed)

| Worktree | Branch | Status | Lost Work |
|----------|--------|--------|-----------|
| `rename-e2ee-2` | `Auto-Scalers/rename-e2ee-2` | **removed** | None (0 unique commits) |
| `rename-relay-2` | `Auto-Scalers/rename-relay-2` | **removed** | None (0 unique commits) |

### Rules

- **Orchestration sessions never close.** They stay alive and handle new tasks as they arrive.
- **Workers are released after review.** Once work is approved, release the worker and merge the worktree.
- **One orchestration session per task file.** No duplicates.
- **Merge worktrees immediately.** Never leave branches unmerged after review.
- **Update this ledger** when sessions are created, released, or worktrees merged.

---

*Last updated: Aug 2026*