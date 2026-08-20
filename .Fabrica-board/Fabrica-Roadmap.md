# Fabrica — Roadmap

> Central command. Vision/identity → `Fabrica-DNA.md`. Execution details → sub-project task files.

---

## Dashboard


| Metric      | Value |
| ----------- | ----- |
| Total tasks | 152   |
| ✅ Done      | 125   |
| 🔶 Partial  | 2     |
| ⬜ Todo      | 25    |
| 📋 Planning | 0     |
| 🚫 Blocked  | 0     |
| ❌ Issues    | 0     |
| Completion  | 82%   |


### Phase Progress

```
Phase 1 — Rebranding & Foundation
Fabrica-app      ✅ 55 ⬜ 0                       [████████████████████] 100%
Fabrica-web      ✅ 13 ⬜ 0                       [████████████████████] 100%
Fabrica-marketing ✅ 13 ⬜ 22                      [██████░░░░░░░░░░░░░░] 37%
Fabrica-plugins  ✅ 16 ⬜ 0                        [████████████████████] 100%
Fabrica-relay    ✅ 28 🔶 1 ⬜ 1                       [████████████████████] 93%
```

---

## Right Now

> What's actively being tracked. Update this section as work progresses.


| What                                       | Status | Owner             | Notes                                                                                                                                                                |     |
| ------------------------------------------ | ------ | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| App rebranding — display identity          | ✅ Done | Fabrica-app       | App name, menu, firewall, helper, CLI, env vars, keychain, wire tokens, plugin engines, data dirs, casks, i18n, deep links                                           |     |
| API routes (W1-W7)                         | ✅ Done | Fabrica-web       | All 9 route files built, no TS errors                                                                                                                                |     |
| Plugin source study (P0a-P0f)              | ✅ Done | Fabrica-plugins   | 9 repos cloned, schemas documented                                                                                                                                   |     |
| Marketing plans (M1-M13)                   | ✅ Done | Fabrica-marketing | All 13 tasks complete                                                                                                                                                |     |
| CI workflows                               | ✅ Done | Fabrica-app       | All 8 workflows renamed stablyai → Auto-Scalers                                                                                                                      |     |
| SKILL.md files                             | ✅ Done | Fabrica-app       | All rebranded (remaining "orca" = GNOME Orca screen reader, correct)                                                                                                 |     |
| Localized READMEs                          | ✅ Done | Fabrica-app       | zh-CN, pt, ko, ja, fr, es all rebranded                                                                                                                              |     |
| CONTRIBUTING.md                            | ✅ Done | Fabrica-app       | Rebranded                                                                                                                                                            |     |
| WINDOWS_SETUP_GUIDE.md                     | ✅ Done | Fabrica-app       | Rebranded, zero orca/stablyai refs                                                                                                                                   |     |
| OAuth callback route                       | ✅ Done | Fabrica-web       | Created /api/auth/callback/route.ts                                                                                                                                  |     |
| package.json name                          | ✅ Done | Fabrica-web       | Renamed from saas-landing-page to fabrica-web                                                                                                                        |     |
| docs/reference/ files                      | ✅ Done | Fabrica-app       | Rebranded (remaining refs = historical GitHub URLs + orca-cli skill name)                                                                                            |     |
| Attribution footer                         | ✅ Done | Fabrica-app       | "Made with [FABRICA]" — verified clean                                                                                                                               |     |
| Static files (W8-W10)                      | ✅ Done | Fabrica-web       | Changelog, nudge, kill-list JSON created                                                                                                                             |     |
| Docs site (W11)                            | ✅ Done | Fabrica-web       | Layout, sidebar, content, build compiles                                                                                                                             |     |
| Landing page updates (W12-W13)             | ✅ Done | Fabrica-web       | Audit complete: no Orca refs in page copy or meta tags                                                                                                               |     |
| Plugin marketplace (P1-P10)                | ✅ Done | Fabrica-plugins   | All 10 tasks complete — marketplace index, bundled plugins, submission guidelines, schema, validation, review, kill-list, signing research, loader, update mechanism |     |
| PostHog + GitHub secrets                   | ✅ Done | Orchestrator      | Write key + build identity set                                                                                                                                       |     |
| Release repos (hourly/daily/adhoc/plugins) | ✅ Done | Orchestrator      | All 4 repos created                                                                                                                                                  |     |
| F1: Full rebrand audit                     | ✅ Done | Orchestrator      | ORCA-RELAY→FABRICA-RELAY (35 files), orca-mobile-e2ee→fabrica-mobile-e2ee (4 files), README.md rebranded, CLI type investigated                                      |     |
| README.md rebrand                          | ✅ Done | Orchestrator      | Main README.md rebranded (was missed in earlier sweeps)                                                                                                              |     |
| Marketplace filename fix                   | ✅ Done | Orchestrator      | Renamed marketplace-index.json → fabrica-marketplace.json (app looks for this name)                                                                                  |     |
| Kill list URL fix                          | ✅ Done | Orchestrator      | Changed onFABRICA.dev → fabrica-ai.vercel.app (real web domain)                                                                                                      |     |
| Categories filter removal                  | ✅ Done | Orchestrator      | Removed UNSUPPORTED_MARKETPLACE_CATEGORIES — show all plugins like Orca                                                                                              |     |
| Plugin repos created                       | ✅ Done | Orchestrator      | 8 GitHub repos created under Auto-Scalers, added as submodules in Fabrica-plugins/                                                                                   |     |
| Orca Legacy Bridge investigation           | ✅ Done | Orchestrator      | No "Orca Legacy Bridge" plugin exists — codex-session-bridge.ts is internal migration tool, not a plugin                                                             |     |
| Archive P0-P8 planning docs                | ✅ Done | Orchestrator      | Moved P0-P8 to .archive/ in all sub-project boards                                                                                                                   |     |
| Relay server repo created                  | ✅ Done | Orchestrator      | Fabrica-relay repo created with AGENTS.md, README, and 30 tasks (R1-R30)                                                                                             |     |
| Relay deployment decision                  | ✅ Done | Orchestrator      | Cloudflare Workers + Durable Objects chosen ($0/mo), stack: Hono; research archived into relay tasks file                                                            |     |
| Relay design decisions                     | ✅ Done | Orchestrator      | DB=SQLite per-host DO (no Postgres/D1); accept client reconnects on deploy; concurrency ~1K users/&lt;100 tunnels                                                    |     |


---

## Phase 1 — Rebranding &amp; Foundation

> Make the Orca codebase fully Fabrica.

### Progress


| Sub-Project       | ✅ Done | 🔶 Partial | ⬜ Todo | 📋 Planning | 🚫 Blocked | ❌ Issues | Task File                                                               |
| ----------------- | ------ | ---------- | ------ | ----------- | ---------- | -------- | ----------------------------------------------------------------------- |
| Fabrica-app       | 55     | 0          | 0      | 0           | 0          | 0        | `Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md`                   |
| Fabrica-web       | 13     | 0          | 0      | 0           | 0          | 0        | `Fabrica-web/.Fabrica-web-board/Fabrica-web-tasks.md`                   |
| Fabrica-marketing | 13     | 0          | 22     | 0           | 0          | 0        | `Fabrica-marketing/.Fabrica-marketing-board/Fabrica-marketing-tasks.md` |
| Fabrica-plugins   | 16     | 0          | 0      | 0           | 0          | 0        | `Fabrica-plugins/.Fabrica-plugins-board/Fabrica-plugins-tasks.md`       |
| Fabrica-relay    | 28     | 1          | 1      | 0           | 0          | 0        | `Fabrica-relay/.Fabrica-relay-board/Fabrica-relay-tasks.md`             |
| **Total**         | **125** | **2**      | **25** | **0**       | **0**      | **0**    |                                                                         |


---

### Fabrica-app — Source Code

> Desktop app, CLI, mobile companion, relay, plugins, build system.

```
Progress [████████████████████] 100%  ✅ 55 ⬜ 0 🚫 0
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


| #   | Task                                 | Status |
| --- | ------------------------------------ | ------ |
| C1  | Wire tokens (`fabrica_server_ready`) | ✅      |
| C2  | Keychain service name                | ✅      |
| C3  | TLS certificate CN                   | ✅      |
| C4  | Data directories                     | ✅ Done |


#### Group D — Plugin Ecosystem


| #   | Task                                                 | Status |
| --- | ---------------------------------------------------- | ------ |
| D1  | Plugin `engines.orca` → `engines.fabrica`            | ✅      |
| D2  | Plugin publisher rename (`stablyai` → `autoscalers`) | ✅      |
| D3  | Plugin marketplace repos on GitHub                   | ✅      |
| D4  | Plugin kill-list URL                                 | ✅      |
| D5  | Bundled plugin content hashes                        | ✅      |
| D6  | Plugin loader reads from marketplace                 | ✅      |
| D7  | Plugin update mechanism                              | ✅      |


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


#### Localized READMEs &amp; Docs

> All rebranded. Remaining "orca" refs = historical GitHub URLs + orca-cli skill name (correct).


| #   | Task                                     | Status |
| --- | ---------------------------------------- | ------ |
| 1   | `README.zh-CN.md` — full rebrand         | ✅      |
| 2   | `README.pt.md` — full rebrand            | ✅      |
| 3   | `README.ko.md` — full rebrand            | ✅      |
| 4   | `README.ja.md` — full rebrand            | ✅      |
| 5   | `README.fr.md` — full rebrand            | ✅      |
| 6   | `.github/CONTRIBUTING.md` — full rebrand | ✅      |
| 7   | `WINDOWS_SETUP_GUIDE.md` — full rebrand  | ✅      |
| 8   | `docs/STYLEGUIDE.md` — full rebrand      | ✅      |


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
| 7   | Build relay server                           | ✅      |
| 8   | Deploy relay server (Cloudflare)             | 🚫     |


#### Skill Files

> All 8 SKILL.md files verified clean. Remaining "orca" refs = GNOME Orca screen reader (correct).


| #   | Task                                                         | Status |
| --- | ------------------------------------------------------------ | ------ |
| 1   | `skills/fabrica-cli/SKILL.md` — fixed incorrect over-rebrand | ✅      |
| 2   | `skills/orchestration/SKILL.md` — verified clean             | ✅      |
| 3   | `skills/computer-use/SKILL.md` — verified clean              | ✅      |
| 4   | `skills/fabrica-linear/SKILL.md` — verified clean            | ✅      |


#### Documentation

> All rebranded. Remaining "orca" refs = historical GitHub URLs + orca-cli skill name (correct).


| #   | Task                                            | Status |
| --- | ----------------------------------------------- | ------ |
| 1   | `docs/STYLEGUIDE.md` — full rebrand             | ✅      |
| 2   | `config/i18n-translation-source.md` — rebranded | ✅      |
| 3   | `config/localization-audit.md` — rebranded      | ✅      |
| 4   | `docs/reference/*.md` — all 7 files rebranded   | ✅      |
| 5   | Test README files — rebranded                   | ✅      |


#### Final Verification


| #   | Task                         | Status |
| --- | ---------------------------- | ------ |
| 1   | Full rebrand audit           | ⬜      |
| 2   | Clean build on all platforms | ✅      |
| 3   | Lint + test pass             | 🔶     |


---

### Fabrica-web — Landing Page + API Routes

```
Progress [████████████████████] 100%  ✅ 13 ⬜ 0  📋 2
```

#### API Routes


| #   | Endpoint                              | Status |
| --- | ------------------------------------- | ------ |
| W1  | `/api/auth/authorize` (OAuth PKCE)    | ✅      |
| W2  | `/api/auth/session`                   | ✅      |
| W3  | `/api/auth/refresh`                   | ✅      |
| W4  | `/api/auth/logout`                    | ✅      |
| W5  | `/api/share/*` (Artifact sharing)     | ✅      |
| W6  | `/api/diagnostics/*` (Crash/feedback) | ✅      |
| W7  | `/api/telemetry` (Analytics fallback) | ✅      |
| W8  | `/api/auth/callback` (OAuth callback) | ✅      |


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
| W12 | Audit Orca references in page copy | ✅      |
| W13 | Update meta tags / OG images       | ✅      |


---

### Fabrica-marketing — Brand + Launch

```
Progress [██████░░░░░░░░░░░░░░] 37%  ✅ 13 ⬜ 22
```

#### Phases Overview


| Phase                             | Tasks      | Status |
| --------------------------------- | ---------- | ------ |
| Phase 1: Foundation               | M1-M3      | ✅ DONE |
| Phase 2: Launch Assets            | M4-M8, M13 | ✅ DONE |
| Phase 3: Launch Content           | M4, M6, M8 | ✅ DONE |
| Phase 4: Ongoing Content          | M9-M12     | ✅ DONE |
| Phase 5: Review &amp; Audit       | M14-M18    | ⬜ TODO |
| Phase 6: Landing Page Enhancement | M19-M26    | ⬜ TODO |
| Phase 7: Social Launch Campaign   | M27-M35    | ⬜ TODO |


#### Brand &amp; Positioning


| #   | Task                              | Status |
| --- | --------------------------------- | ------ |
| M1  | Finalize brand guidelines         | ✅      |
| M2  | Competitor landscape doc          | ✅      |
| M3  | Positioning statement / one-pager | ✅      |


#### Launch Materials


| #   | Task                          | Status |
| --- | ----------------------------- | ------ |
| M4  | Launch blog post              | ✅      |
| M5  | Product Hunt listing + assets | ✅      |
| M6  | Hacker News "Show HN" post    | ✅      |
| M7  | Press kit                     | ✅      |
| M8  | Email launch sequence         | ✅      |


#### Content &amp; Early Access


| #   | Task                          | Status |
| --- | ----------------------------- | ------ |
| M9  | Social media content calendar | ✅      |
| M10 | Twitter/X thread templates    | ✅      |
| M11 | Founder story / origin post   | ✅      |
| M12 | Early access nurture emails   | ✅      |
| M13 | Waitlist page copy            | ✅      |


#### Phase 5 — Review &amp; Audit

> Review all marketing work from Phases 1-4, audit for consistency, fix gaps.


| #   | Task                                                         | Status |
| --- | ------------------------------------------------------------ | ------ |
| M14 | Brand consistency audit across all M1-M13 deliverables       | ⬜      |
| M15 | Visual asset review — check all generated images             | ⬜      |
| M16 | Copy audit — proofread all launch copy, emails, social       | ⬜      |
| M17 | Competitor positioning refresh — update M2 if market shifted | ⬜      |
| M18 | Final sign-off — PM approves all marketing materials         | ⬜      |


#### Phase 6 — Landing Page Enhancement

> Enhance Fabrica-web landing page using insights from marketing materials.


| #   | Task                                                      | Status |
| --- | --------------------------------------------------------- | ------ |
| M19 | Update hero section with final positioning from M3        | ⬜      |
| M20 | Integrate competitor differentiation into landing page    | ⬜      |
| M21 | Add social proof section — waitlist count, testimonials   | ⬜      |
| M22 | Embed PH gallery images into landing page feature section | ⬜      |
| M23 | Add founder quote / origin story snippet                  | ⬜      |
| M24 | Update email capture CTA with M13 waitlist copy           | ⬜      |
| M25 | Mobile responsiveness audit                               | ⬜      |
| M26 | SEO meta tags — update title, description, OG tags        | ⬜      |


#### Phase 7 — Social Launch Campaign

> Execute social media posting strategy to acquire early access customers.


| #   | Task                                                       | Status |
| --- | ---------------------------------------------------------- | ------ |
| M27 | Schedule Week 1 posts from M9 content calendar             | ⬜      |
| M28 | Prepare launch day thread (M10 template)                   | ⬜      |
| M29 | Set up Twitter/X analytics tracking                        | ⬜      |
| M30 | Prepare Product Hunt launch day social blitz               | ⬜      |
| M31 | Schedule HN "Show HN" post (M6)                            | ⬜      |
| M32 | Prepare LinkedIn launch post (founder story version)       | ⬜      |
| M33 | Set up waitlist conversion tracking (UTM params)           | ⬜      |
| M34 | Week 1 daily monitoring — respond to all comments/mentions | ⬜      |
| M35 | Week 1 metrics report — impressions, signups, engagement   | ⬜      |


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
| P8  | Plugin signing (future)              | ✅      |
| P9  | Plugin loader reads from marketplace | ✅      |
| P10 | Plugin update mechanism              | ✅      |


---

### Fabrica-relay — Relay Server

```
Progress [██░░░░░░░░░░░░░░░░░░] 3%  🔶 1 ⬜ 29
```

#### Phase 1 — Scaffold &amp; Core


| #   | Task                                                       | Status |
| --- | ---------------------------------------------------------- | ------ |
| R1  | Initialize repo (package.json, tsconfig, vitest)           | 🔶     |
| R2  | Create shared types (protocol messages, IDs, timestamps)   | ⬜      |
| R3  | Implement Director: relay JWT validation                   | ⬜      |
| R4  | Implement Director: `POST /v1/assign` + `POST /v1/resolve` | ⬜      |
| R5  | Implement Cell: WebSocket server setup                     | ⬜      |
| R6  | Implement Cell: Host challenge-response                    | ⬜      |
| R7  | Implement Cell: Host activation flow                       | ⬜      |
| R8  | Implement Cell: Ping/pong keepalive                        | ⬜      |
| R9  | Implement Cell: Phone relay-auth/relay-hello               | ⬜      |
| R10 | Unit tests for Director                                    | ⬜      |
| R11 | Unit tests for Cell                                        | ⬜      |


#### Phase 2 — Connection Tunneling


| #   | Task                                    | Status |
| --- | --------------------------------------- | ------ |
| R12 | Implement Cell: conn-open notification  | ⬜      |
| R13 | Implement Cell: Data channel per connId | ⬜      |
| R14 | Implement Cell: Data tunneling          | ⬜      |
| R15 | Implement Cell: Connection cleanup      | ⬜      |
| R16 | Integration tests for data tunneling    | ⬜      |


#### Phase 3 — Device Management


| #   | Task                                    | Status |
| --- | --------------------------------------- | ------ |
| R17 | Implement invite-create RPC             | ⬜      |
| R18 | Implement device-credential-install RPC | ⬜      |
| R19 | Implement device-credential-status RPC  | ⬜      |
| R20 | Implement device-revoke RPC             | ⬜      |
| R21 | Implement device-resume-confirm RPC     | ⬜      |
| R22 | Device management tests                 | ⬜      |


#### Phase 4 — Production Readiness


| #   | Task                                                  | Status |
| --- | ----------------------------------------------------- | ------ |
| R23 | Create wrangler config + build setup                  | ⬜      |
| R24 | Add database (SQLite-backed Durable Objects per host) | ⬜      |
| R25 | Add graceful reconnect/drain handling                 | ⬜      |
| R26 | Add structured logging                                | ⬜      |
| R27 | Add health check endpoint                             | ⬜      |
| R28 | Add rate limiting                                     | ⬜      |
| R29 | Deploy to Cloudflare                                  | ⬜      |
| R30 | Update Fabrica-app task file                          | ⬜      |



> **Reference** (App ID, Infrastructure, Deferred Items) → see [Fabrica-DNA.md](Fabrica-DNA.md)

---


## Session Ledger (Master)

> Central view of all orchestration sessions across sub-projects. Each sub-project's task file contains its own detailed ledger.

### Sub-Orchestrator Sessions (permanent, 24/7)


| Session                                     | Worktree             | Task File                    | Status      |
| ------------------------------------------- | -------------------- | ---------------------------- | ----------- |
| `term_905a82bc-8472-4451-91d5-4fe8a3c9c67b` | `Fabrica-app/`       | `Fabrica-app-tasks.md`       | **active**  |
| `term_0adb1b43-ceeb-47c7-ad47-f65f6df17d3e` | `Fabrica-web/`       | `Fabrica-web-tasks.md`       | **active**  |
| `term_f667dbf4-72e5-44c5-87af-d8519f90f3e9` | `Fabrica-marketing/` | `Fabrica-marketing-tasks.md` | **active**  |
| `term_24ff1a27-8b86-43f8-9206-73367917448f` | `Fabrica-plugins/`   | `Fabrica-plugins-tasks.md`   | **active**  |
| `pending`                                   | `Fabrica-relay/`     | `Fabrica-relay-tasks.md`     | **pending** |


### Worker Sessions (ephemeral — released after review)


| Name                  | Session                                     | Parent Orchestrator | Task                          | Status       | Worktree Merged                           |
| --------------------- | ------------------------------------------- | ------------------- | ----------------------------- | ------------ | ----------------------------------------- |
| P9 Plugin loader      | `term_8274ea16-fd28-4b9a-9d9e-7fa10cb6d650` | app-orchestrator    | P9: Plugin loader             | **released** | ✅                                         |
| P10 Plugin updates    | `term_4a73d6e4-0033-4910-a2b8-9af3e1dfc841` | app-orchestrator    | P10: Plugin updates           | **released** | ✅                                         |
| Docs rebrand          | `term_b9293715-3f95-42f3-b041-d6b12117d5e1` | app-orchestrator    | Docs rebrand                  | **released** | ✅                                         |
| SKILL.md rebrand      | `term_1dfdcd8e-5f99-4589-b08a-5754d93d9049` | app-orchestrator    | SKILL.md rebrand              | **released** | ✅                                         |
| CI workflows rebrand  | `term_f77a5a04-5949-46a1-954f-b6252a12ca4b` | app-orchestrator    | CI workflows rebrand          | **released** | ✅                                         |
| F2 Build verification | `term_2d281364-f08e-428d-b4d7-e86ef6d95f7f` | orchestrator        | F2: Build verification        | **running**  | —                                         |
| F3 Lint+test          | `term_626fd308-bb95-46df-a539-b54f3082f683` | orchestrator        | F3: Lint + test               | **running**  | —                                         |
| Relay deploy research | `term_0e49225d-9814-4f64-986d-81a1d55ed2ec` | orchestrator        | Relay deployment alternatives | **released** | ✅ research archived into relay tasks file |


### Abandoned Worktrees (removed)


| Worktree         | Branch                        | Status      | Lost Work               |
| ---------------- | ----------------------------- | ----------- | ----------------------- |
| `rename-e2ee-2`  | `Auto-Scalers/rename-e2ee-2`  | **removed** | None (0 unique commits) |
| `rename-relay-2` | `Auto-Scalers/rename-relay-2` | **removed** | None (0 unique commits) |


### Rules

- **Orchestration sessions never close.** They stay alive and handle new tasks as they arrive.
- **Workers are released after review.** Once work is approved, release the worker and merge the worktree.
- **One orchestration session per task file.** No duplicates.
- **Merge worktrees immediately.** Never leave branches unmerged after review.
- **Update this ledger** when sessions are created, released, or worktrees merged.

---

*Last updated: Aug 2026*