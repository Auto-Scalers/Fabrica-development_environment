# Fabrica — Roadmap

> Central command. Vision/identity → `Fabrica-DNA.md`. Execution details → sub-project task files.

---

## Dashboard

| Metric | Value |
|--------|-------|
| Total tasks | 100 |
| 🔧 Needs verification | 14 |
| 🔶 Partial | 1 |
| ⬜ Todo | 69 |
| 📋 Planning | 15 |
| 🚫 Blocked | 1 |
| ✅ Verified | 0 |
| Completion | 0% |

### Phase Progress

```
Phase 1 — Rebranding & Foundation
Fabrica-app      🔧 6  🔶 1  ⬜ 42 🚫 1   [████░░░░░░░░░░░░░░░░] 12%
Fabrica-web      🔧 4  ⬜ 11  📋 2         [███░░░░░░░░░░░░░░░░░] 24%
Fabrica-marketing 🔧 3  📋 13              [██░░░░░░░░░░░░░░░░░░] 19%
Fabrica-plugins  🔧 1  ⬜ 16               [██░░░░░░░░░░░░░░░░░░] 9%

Phase 2 — Business-First UI & Agentic Layer
Fabrica-app      ⬜ 7                       [░░░░░░░░░░░░░░░░░░░░] 0%
```

---

## Right Now

> What's actively being tracked. Update this section as work progresses.

| What | Status | Owner | Notes |
|------|--------|-------|-------|
| App rebranding (Groups A–D) | 🔶 In progress | Fabrica-app | A1 ✅, C1-C3 ✅, D3 ✅ — rest todo |
| API routes (auth, share, diagnostics) | ⬜ Not started | Fabrica-web | Client code exists, need servers |
| Landing page updates (W12-W13) | 📋 Planning | Fabrica-web | Plan and refine — not executing yet |
| Marketing (all groups) | 📋 Planning | Fabrica-marketing | All 13 tasks — plan and refine only |
| Plugin source study (P0a-P0f) | ⬜ Not started | Fabrica-plugins | Clone orca-plugins + bundled repos, study schema |
| Plugin marketplace index | ⬜ Not started | Fabrica-plugins | After P0 complete |
| PostHog + GitHub secrets | ✅ Done | Orchestrator | Write key + build identity set |
| Release repos (hourly/daily/adhoc/plugins) | ✅ Done | Orchestrator | All 4 repos created |

---

## Phase 1 — Rebranding & Foundation

> Make the Orca codebase fully Fabrica.

### Progress

| Sub-Project | 🔧 Verify | 🔶 Partial | ⬜ Todo | 📋 Planning | 🚫 Blocked | Task File |
|-------------|-----------|-----------|---------|-------------|------------|-----------|
| Fabrica-app | 6 | 1 | 42 | 0 | 1 | `Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md` |
| Fabrica-web | 4 | 0 | 11 | 2 | 0 | `Fabrica-web/.Fabrica-web-board/Fabrica-web-tasks.md` |
| Fabrica-marketing | 3 | 0 | 0 | 13 | 0 | `Fabrica-marketing/.Fabrica-marketing-board/Fabrica-marketing-tasks.md` |
| Fabrica-plugins | 1 | 0 | 16 | 0 | 0 | `Fabrica-plugins/.Fabrica-plugins-board/Fabrica-plugins-tasks.md` |
| **Total** | **14** | **1** | **69** | **15** | **1** | |

---

### Fabrica-app — Source Code

> Desktop app, CLI, mobile companion, relay, plugins, build system.

```
Progress [████░░░░░░░░░░░░░░░░] 12%  🔧 6  🔶 1  ⬜ 42 🚫 1
```

#### Group A — Display & Visible Identity

| # | Task | Status |
|---|------|--------|
| A1 | App name / productName / About / app menu | 🔧 |
| A2 | Firewall rule display name | ⬜ |
| A3 | Computer Use helper app name | 🔶 |

#### Group B — CLI & Install Paths

| # | Task | Status |
|---|------|--------|
| B1 | CLI command rename (`orca` → `fabrica`) | ⬜ |
| B2 | Install paths rename | ⬜ |
| B3 | Environment variables (`ORCA_*` → `FABRICA_*`) | 🔶 |
| B4 | Git co-author trailer | ⬜ |

#### Group C — Runtime Identity

| # | Task | Status |
|---|------|--------|
| C1 | Wire tokens (`fabrica_server_ready`) | 🔧 |
| C2 | Keychain service name | 🔧 |
| C3 | TLS certificate CN | 🔧 |
| C4 | Data directories | 🚫 BLOCKED on A1 |

#### Group D — Plugin Ecosystem

| # | Task | Status |
|---|------|--------|
| D1 | Plugin `engines.orca` → `engines.fabrica` | ⬜ |
| D2 | Plugin publisher rename (`stablyai` → `autoscalers`) | ⬜ |
| D3 | Plugin marketplace repos on GitHub | 🔧 |
| D4 | Plugin kill-list URL | ⬜ |
| D5 | Bundled plugin content hashes | ⬜ |

#### Source Code Renames

| # | Task | Status |
|---|------|--------|
| 1 | GitHub org + repo refs (`stablyai/orca` → `Auto-Scalers/Fabrica-app`) | 🔶 |
| 2 | `orca://` deep link → `fabrica://` | ⬜ |
| 3 | PostHog env vars | ⬜ |
| 4 | Diagnostics env vars | ⬜ |
| 5 | Build identity env var | ⬜ |
| 6 | Attribution footer | ⬜ |
| 7 | Product URL env var | ⬜ |
| 8 | Feature wall docs URLs | 🔧 |

#### CI/CD Workflows

| # | Task | Status |
|---|------|--------|
| 1 | `hourly-mac-build.yml` | ⬜ |
| 2 | `daily-mac-build.yml` | ⬜ |
| 3 | `adhoc-mac-build.yml` | ⬜ |
| 4 | `release-cut.yml` | ⬜ |
| 5 | `release-mac-build.yml` | ⬜ |
| 6 | `release-policy.yml` | ⬜ |
| 7 | `readme-downloads-badge.yml` | ⬜ |
| 8 | `homebrew-bump.yml` | ⬜ |

#### Localized READMEs

| # | Task | Status |
|---|------|--------|
| 1 | `README.zh-CN.md` | ⬜ |
| 2 | `README.pt.md` | ⬜ |
| 3 | `README.ko.md` | ⬜ |
| 4 | `README.ja.md` | ⬜ |
| 5 | `README.fr.md` | ⬜ |
| 6 | `.github/CONTRIBUTING.md` | ⬜ |
| 7 | `WINDOWS_SETUP_GUIDE.md` | ⬜ |

#### i18n & Homebrew

| # | Task | Status |
|---|------|--------|
| 1 | `en.json` — 621 "Orca" occurrences | ⬜ |
| 2 | All other locales (ko, ja, zh, es) | ⬜ |
| 3 | `Casks/fabrica.rb` | ⬜ |
| 4 | `Casks/fabrica@rc.rb` | ⬜ |

#### Visual, Configs, Relay

| # | Task | Status |
|---|------|--------|
| 1 | Capture aesthetic reference from Fabrica-web | ⬜ |
| 2 | Apply palette to app | ⬜ |
| 3 | Clean build verification | ⬜ |
| 4 | Configs migration | ⬜ |
| 5 | Auto-updater | ⬜ |
| 6 | Deep linking (`orca://` → `fabrica://`) | ⬜ |
| 7 | Build relay server | ⬜ |
| 8 | Deploy to Fly.io | ⬜ |

#### Final Verification

| # | Task | Status |
|---|------|--------|
| 1 | Full rebrand audit | ⬜ |
| 2 | Clean build on all platforms | ⬜ |
| 3 | Lint + test pass | ⬜ |

---

### Fabrica-web — Landing Page + API Routes

```
Progress [███░░░░░░░░░░░░░░░░░] 24%  🔧 4  ⬜ 11  📋 2
```

#### API Routes

| # | Endpoint | Status |
|---|----------|--------|
| W1 | `/api/auth/authorize` (OAuth PKCE) | ⬜ |
| W2 | `/api/auth/session` | ⬜ |
| W3 | `/api/auth/refresh` | ⬜ |
| W4 | `/api/auth/logout` | ⬜ |
| W5 | `/api/share/*` (Artifact sharing) | ⬜ |
| W6 | `/api/diagnostics/*` (Crash/feedback) | ⬜ |
| W7 | `/api/telemetry` (Analytics fallback) | ⬜ |

#### Static Files & Docs

| # | Task | Status |
|---|------|--------|
| W8 | `/whats-new/changelog.json` | ⬜ |
| W9 | `/whats-new/nudge.json` | ⬜ |
| W10 | `/plugins/kill-list.json` | ⬜ |
| W11 | `/docs/*` (migrate from onorca.dev) | ⬜ |

#### Landing Page Updates

> **PLANNING MODE** — Plan and refine only.

| # | Task | Status |
|---|------|--------|
| W12 | Audit Orca references in page copy | 📋 |
| W13 | Update meta tags / OG images | 📋 |

---

### Fabrica-marketing — Brand + Launch

```
Progress [██░░░░░░░░░░░░░░░░░░] 19%  🔧 3  📋 13
```

#### Brand & Positioning

> **PLANNING MODE** — Plan and refine only.

| # | Task | Status |
|---|------|--------|
| M1 | Finalize brand guidelines | 📋 |
| M2 | Competitor landscape doc | 📋 |
| M3 | Positioning statement / one-pager | 📋 |

#### Launch Materials

> **PLANNING MODE** — Plan and refine only.

| # | Task | Status |
|---|------|--------|
| M4 | Launch blog post | 📋 |
| M5 | Product Hunt listing + assets | 📋 |
| M6 | Hacker News "Show HN" post | 📋 |
| M7 | Press kit | 📋 |
| M8 | Email launch sequence | 📋 |

#### Content & Early Access

> **PLANNING MODE** — Plan and refine only.

| # | Task | Status |
|---|------|--------|
| M9 | Social media content calendar | 📋 |
| M10 | Twitter/X thread templates | 📋 |
| M11 | Founder story / origin post | 📋 |
| M12 | Early access nurture emails | 📋 |
| M13 | Waitlist page copy | 📋 |

---

### Fabrica-plugins — Plugin Marketplace

```
Progress [█░░░░░░░░░░░░░░░░░░░] 9%  🔧 1  ⬜ 10  📋 0
```

#### Orca Source Study

> Clone and study original Orca plugin repos before building Fabrica equivalents.

| # | Task | Status |
|---|------|--------|
| P0a | Clone `stablyai/orca-plugins` into `_sources/` | ⬜ |
| P0b | Clone bundled plugin repos into `_sources/` | ⬜ |
| P0c | Clone theme/skill plugin repos into `_sources/` | ⬜ |
| P0d | Study marketplace index format | ⬜ |
| P0e | Study bundled plugin manifest format | ⬜ |
| P0f | Document rename strategy | ⬜ |

#### Marketplace & Schema

| # | Task | Status |
|---|------|--------|
| P1 | Initialize marketplace index JSON | ⬜ |
| P2 | Add bundled plugins to index | ⬜ |
| P3 | Plugin submission guidelines | ⬜ |
| P4 | Define plugin manifest schema | ⬜ |
| P5 | Plugin validation rules | ⬜ |

#### Quality & Integration

| # | Task | Status |
|---|------|--------|
| P6 | Plugin review process | ⬜ |
| P7 | Kill-list management | ⬜ |
| P8 | Plugin signing (future) | ⬜ |
| P9 | Plugin loader reads from marketplace | ⬜ |
| P10 | Plugin update mechanism | ⬜ |

---

## Phase 2 — Business-First UI & Agentic Layer

> Transform from coding-first to business-first. Non-technical founders control everything from the UI.

```
Progress [░░░░░░░░░░░░░░░░░░░░] 0%  ⬜ 7
```

### Features

| # | Task | Status |
|---|------|--------|
| 1 | UI-driven task lifecycle (Draft → Plan → Execute → Verify) | ⬜ |
| 2 | Agent crew definitions | ⬜ |
| 3 | Orchestration & supervision from UI | ⬜ |
| 4 | Data visualization & dashboards | ⬜ |
| 5 | Business intelligence features | ⬜ |

### Mission-Control Integration

> Source: `Auto-Scalers/Fabrica/mission-control` (AGPL-3.0). License-safe clean-room reimplementation.

| # | Task | Status |
|---|------|--------|
| 1 | Extract functional specs from mission-control | ⬜ |
| 2 | Audit specs | ⬜ |

---

## Reference

### App ID

**Unified across all platforms:** `ai.autoscalers.fabrica`

| Platform | Value |
|----------|-------|
| electron-builder appId | `ai.autoscalers.fabrica` |
| macOS CFBundleIdentifier | `ai.autoscalers.fabrica` |
| macOS helper | `ai.autoscalers.fabrica.computer-use` |
| Windows AUMID | `ai.autoscalers.fabrica` |
| Windows/Linux | `ai.autoscalers.fabrica` |
| Deep link protocol | `fabrica://` |
| Future iOS bundle ID | `ai.autoscalers.fabrica` |
| Future Android package | `ai.autoscalers.fabrica` |

### Infrastructure

| Service | Where | Owner |
|---------|-------|-------|
| Landing page | Vercel | Fabrica-web |
| Backend API | Vercel (API routes) | Fabrica-web |
| Auth | Supabase (shared project) | Fabrica-web |
| Telemetry | PostHog | Fabrica-app |
| Relay | Fly.io | Fabrica-app |
| Auto-updater | GitHub Releases | Fabrica-app |
| Plugin marketplace | GitHub repo | Fabrica-plugins |

### Deferred Items

| Item | Blocker | What's Needed |
|------|---------|---------------|
| Code signing | Apple Developer Program | $99/year Apple Dev, Windows SignPath |
| App Store (iOS) | Apple Dev Program + review | Dev membership, listing, review |
| Google Play | $25 fee | Google Play Developer account |

---

_Last updated: Aug 2026_
