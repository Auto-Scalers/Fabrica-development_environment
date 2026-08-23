# Fabrica — Roadmap

> Central command. Vision/identity → `Fabrica-DNA.md`. Execution details live ONLY in sub-project task files — this file mirrors their Rollups, never recomputes them. Canonical schema: `Fabrica-Schema.md`. Autonomous-loop instructions and current focus areas: `Heartbeat.md`.

---

## High-Level Goals (PM mandate)

> The why behind everything. Task details stay in sub-project task files — this is the direction.

1. **Finish the rebrand without losing anything.** Every old Orca/Stably word gone from Fabrica-app, every feature and custom logic intact, everything tested and reviewed.
2. **Prepare for the After-Rebrand.** Atlas keeps discovering, verifying, and synthesizing so the final version of the app is planned from evidence.
3. **Beta public launch.** When app + relay + plugins are verified working perfectly, we ship our first public Beta — immediately after, marketing starts publishing daily content aligned with the product vision.
4. **Plan the final version ("Atlas-project").** Right after Beta, figure out how the Fabrica app becomes the Atlas app — upgrading it while losing zero functionality or custom logic.
5. **Implement, then final launch.** Execute the Atlas-project plan, ship the final version, and start generating profit.

### Current Focus (what runs NOW)

| Orchestrator | Slot | Mission | Min workers |
|---|---|---|---|
| **App-orchestrator** | `Fabrica-app/` | Rebrand fully done with zero functionality loss: hunt every remaining old word (orca/stablyai/onorca), test and review everything | 5 |
| **Atlas-orchestrator** | `Fabrica-atlas/` | Continue discovery rounds preparing everything for the After-Rebrand transformation | 5 |

All other terminals were closed for a fresh start. Web / Marketing / Plugins / Relay activate only when their phase arrives.

---

## Dashboard

> Copied verbatim from each project's Rollup block on 2026-08-23.
> ⚠️ Fabrica-app is mid-reconciliation (its task file regressed during parallel work and was re-migrated; some statuses need an orchestrator ruling) — its numbers are provisional.
> Note: Fabrica-web recount corrected 2026-08-23 (was overstated by 2 DONE).

| Project | Total | ✅ DONE | 👀 VERIFY | 🔶 IN_PROGRESS | ⬜ TODO | Completion |
|---|---|---|---|---|---|---|
| Fabrica-app ⚠️ | 21 | 2 | 15 | 0 | 4 | 10% |
| Fabrica-web | 30 | 18 | 11 | 1 | 0 | 60% |
| Fabrica-marketing | 27 | 15 | 0 | 0 | 12 | 56% |
| Fabrica-plugins | 16 | 16 | 0 | 0 | 0 | 100% |
| Fabrica-relay | 32 | 30 | 0 | 2 | 0 | 94% |
| Fabrica-atlas | 9 | 8 | 0 | 0 | 1 | 89% |
| **Total** | **135** | **89** | **26** | **3** | **17** | **~66%** |

### Phase Progress

```
Phase A — Rebrand Finish & After-Rebrand Prep   ← CURRENT FOCUS
Fabrica-app      ✅2 👀15 ⬜4   [██░░░░░░░░░░░░░░░░░]  10% ⚠️ recount pending
Fabrica-atlas    ✅8 ⬜1        [██████████████████░░]  89% (R2-4.1 encoding repair pending; Rounds 1–3 done)

Phase B — Beta Public Launch
Fabrica-relay    ✅30 🔶2       [██████████████████░]  94%
Fabrica-plugins  ✅16           [████████████████████] 100%
Fabrica-web      ✅18 👀11 🔶1  [████████████░░░░░░░]  60%

Phase C — Atlas-Project Plan & Daily Content
Fabrica-marketing ✅15 ⬜12     [███████████░░░░░░░░]  56%

Phase D — Implement Final Version → Final Launch
(all projects feed this)
```

---

## Launch Phases (the big picture)

| Phase | Gate to enter | What happens |
|---|---|---|
| **A — Rebrand Finish & Prep** (now) | — | App-orchestrator closes out rebrand (APP-F1/F2/F3 audits, appId chain) with full functional review. Atlas-orchestrator runs deeper discovery rounds. |
| **B — Beta Public Launch** | Rebrand verified clean AND app + relay + plugins tested working perfectly | First public Beta release. Landing page live checks flip WEB-W1..W10 VERIFY→DONE. Marketing begins daily content publishing aligned with the product vision. |
| **C — Atlas-Project Plan** | Beta shipped | Review Beta feedback; define how Fabrica-app upgrades into the final "Atlas" app losing no functionality or custom logic (driven by Atlas synthesis outputs). Align marketing vision; scale content. |
| **D — Implement & Final Launch** | Atlas-project plan approved by PM | Implement the final version across sub-projects, verify end-to-end, ship the final launch → revenue phase. |

---

## Right Now

> What's actively being tracked. Historical log — newest entries at the bottom.

| What | Status | Owner | Notes |
|---|---|---|---|
| App rebranding — display identity | ✅ Done | Fabrica-app | App name, menu, firewall, helper, CLI, env vars, keychain, wire tokens, plugin engines, data dirs, casks, i18n, deep links |
| API routes (W1–W7) | ✅ Done | Fabrica-web | All 9 route files built, no TS errors |
| Plugin source study (P0a–P0f) | ✅ Done | Fabrica-plugins | 9 repos cloned, schemas documented |
| Marketing plans (M1–M13) | ✅ Done | Fabrica-marketing | All 13 tasks complete |
| Marketing review (M14–M18) | ✅ Done | Fabrica-marketing | Internal files reviewed and updated; external files pending |
| CI workflows | ✅ Done | Fabrica-app | All 8 workflows renamed stablyai → Auto-Scalers |
| SKILL.md files | ✅ Done | Fabrica-app | All rebranded (remaining "orca" = GNOME Orca screen reader, correct) |
| Localized READMEs | ✅ Done | Fabrica-app | zh-CN, pt, ko, ja, fr, es all rebranded |
| CONTRIBUTING.md | ✅ Done | Fabrica-app | Rebranded |
| WINDOWS_SETUP_GUIDE.md | ✅ Done | Fabrica-app | Rebranded, zero orca/stablyai refs |
| OAuth callback route | ✅ Done | Fabrica-web | Created /api/auth/callback/route.ts |
| package.json name | ✅ Done | Fabrica-web | Renamed from saas-landing-page to fabrica-web |
| docs/reference/ files | ✅ Done | Fabrica-app | Rebranded (remaining refs = historical GitHub URLs + orca-cli skill name) |
| Attribution footer | ✅ Done | Fabrica-app | "Made with [FABRICA]" — verified clean |
| Static files (W8–W10) | ✅ Done | Fabrica-web | Changelog, nudge, kill-list JSON created |
| Docs site (W11) | ✅ Done | Fabrica-web | Layout, sidebar, content, build compiles |
| Landing page updates (W12–W13) | ✅ Done | Fabrica-web | Audit complete: no Orca refs in page copy or meta tags |
| Landing page enhancement (W14–W17) | ✅ Done | Fabrica-web | Carousel images, standalone images, bottom bg, full copy rewrite from marketing docs |
| Pricing tiers (W13b) | ✅ Done | Fabrica-web | Renamed: Power User, One-Person Company, Agency & Teams. 14-day free trial CTAs. Updated en/fr/ar.json |
| FR/AR localization (W18) | ✅ Done | Fabrica-web | fr.json and ar.json fully updated to match new en.json |
| Mobile audit (W19) | ✅ Done | Fabrica-web | Fixed carousel nav, touch targets, background scaling, gate toggles |
| Plugin marketplace (P1–P10) | ✅ Done | Fabrica-plugins | All 10 tasks complete |
| PostHog + GitHub secrets | ✅ Done | Orchestrator | Write key + build identity set |
| Release repos (hourly/daily/adhoc/plugins) | ✅ Done | Orchestrator | All 4 repos created |
| F1: Full rebrand audit | ✅ Done | Orchestrator | ORCA-RELAY→FABRICA-RELAY (35 files), orca-mobile-e2ee→fabrica-mobile-e2ee (4 files), README.md rebranded, CLI type investigated |
| README.md rebrand | ✅ Done | Orchestrator | Main README.md rebranded (was missed in earlier sweeps) |
| Marketplace filename fix | ✅ Done | Orchestrator | Renamed marketplace-index.json → fabrica-marketplace.json |
| Kill list URL fix | ✅ Done | Orchestrator | Changed onFABRICA.dev → fabrica-ai.vercel.app |
| Categories filter removal | ✅ Done | Orchestrator | Removed UNSUPPORTED_MARKETPLACE_CATEGORIES — show all plugins like Orca |
| Plugin repos created | ✅ Done | Orchestrator | 8 GitHub repos created under Auto-Scalers, added as submodules in Fabrica-plugins/ |
| Orca Legacy Bridge investigation | ✅ Done | Orchestrator | No "Orca Legacy Bridge" plugin exists — codex-session-bridge.ts is internal migration tool |
| Archive P0–P8 planning docs | ✅ Done | Orchestrator | Moved P0–P8 to .archive/ in all sub-project boards |
| Relay server repo created | ✅ Done | Orchestrator | Fabrica-relay repo created with AGENTS.md, README, and 30 tasks (R1–R30) |
| Relay deployment decision | ✅ Done | Orchestrator | Cloudflare Workers + Durable Objects chosen ($0/mo), stack: Hono; research archived into relay tasks file |
| Relay design decisions | ✅ Done | Orchestrator | DB=SQLite per-host DO (no Postgres/D1); accept client reconnects on deploy; concurrency ~1K users/<100 tunnels |
| R16+R22 miniflare integration tests | ✅ Done | Fabrica-relay | 37 tests passing (24 unit + 13 integration), orchestrator-verified. Found 5 real server bugs — fixes committed `17401bf`, pushed, REDEPLOYED live Aug 23; /v1/assign responding correctly |
| Fabrica-atlas migration complete | ✅ Done | Orchestrator | Roadmap 02 → Fabrica-atlas sub-project (repo Auto-Scalers/Fabrica-atlas): _sources/ moved, tasks file + 15 discovery/verify/analysis docs migrated; Rounds 1–3 complete |
| I18N locale rebrand (en/ko/ja/zh/es) | ✅ Done | Fabrica-app | All locales rebranded; 0 Orca occurrences left in en.json (verified on disk) |
| Localized READMEs + CONTRIBUTING re-sweep | ✅ Done | Fabrica-app | 5 READMEs + CONTRIBUTING.md fixed (10 replacements) |
| CI workflows + Homebrew casks verification | ✅ Done | Fabrica-app | grep clean for orca/stablyai across .github/workflows + Casks (verified) |
| Supabase login UI + packaged env wiring | 🔶 In progress | Fabrica-app | electron-vite env wiring + IPC supabase-auth.ts + SupabaseAccountSignInCard.tsx created; worker finishing end-to-end wiring |
| F3: Lint + test pass | 🔶 In progress | Fabrica-app | Resumed after hung/dead workers; ~203 files changed in tree, final verification running |
| Tracking Schema v1 rollout | ✅ Done | Orchestrator | `Fabrica-Schema.md` created; all task files migrated to new files, verified loss-free, originals archived in `.archive/*-pre-schema-v1.md`; Parallelism policy embedded in all AGENTS.md + tracking files |
| Fresh-start reset (2026-08-23) | ✅ Done | Orchestrator | PM ordered all terminals closed. New fleet: App-orchestrator + Atlas-orchestrator at root level, min 5 workers each. Focus: finish rebrand (app) + After-Rebrand prep (atlas). Heartbeat registry rewritten accordingly |

---

## Parallelism & Anti-Overlap Policy

> Real 24/7 multi-terminal orchestration across all slots. Canonical text:
> `Fabrica-Schema.md` §9. Operational checks: `Heartbeat.md` §3b.

- Policy floor: every active orchestrator slot keeps **at least 3 active worker
  terminals**. **Current operational mandate: APP and ATLAS run ≥ 5 workers each**
  (see High-Level Goals above).
- One task = one worker (claim IN_PROGRESS + handle in the Session Ledger before
  starting). One folder = one orchestrator. One file = one writer.
- Claim-before-work; never duplicate claimed or completed work.
- Cross-project dependencies go as notes into the other project's task file.
- Quality bar unchanged: no DONE without verified evidence; Rollup updated in the
  same edit as any status change.

---

## Sub-Project Index

| Sub-Project | Role | Task File (source of truth) |
|---|---|---|
| Fabrica-app | Desktop app (Electron, forked from Orca) | `Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md` |
| Fabrica-web | Landing page (Next.js, fabrica-ai.vercel.app) | `Fabrica-web/.Fabrica-web-board/Fabrica-web-tasks.md` |
| Fabrica-marketing | Brand, launch copy, content, press | `Fabrica-marketing/.Fabrica-marketing-board/Fabrica-marketing-tasks.md` |
| Fabrica-plugins | Plugin marketplace index | `Fabrica-plugins/.Fabrica-plugins-board/Fabrica-plugins-tasks.md` |
| Fabrica-relay | Relay server (WebSocket bridge phone↔desktop) | `Fabrica-relay/.Fabrica-relay-board/Fabrica-relay-tasks.md` |
| Fabrica-atlas | Discovery & transformation planning (ex-Roadmap 02; owns `_sources/`) | `Fabrica-atlas/.Fabrica-atlas-board/Fabrica-atlas-tasks.md` |

> Reference (App ID, Infrastructure, Deferred Items) → see [Fabrica-DNA.md](Fabrica-DNA.md)

---

## Session Ledger (Master)

> Central view of orchestration slots. Detailed ledgers live in each task file.

### Standing Orchestrator Slots (fresh start, 2026-08-23)

All previous terminals were closed by PM order. Handles are assigned when the new
orchestrators launch; Heartbeat.md resolves by worktree path first, handle second.

| Slot | Orchestrator | Worktree | Task File | Status |
|---|---|---|---|---|
| APP | App-orchestrator (root level) | `Fabrica-app/` | `Fabrica-app-tasks.md` | **launching fresh** — min 5 workers |
| ATLAS | Atlas-orchestrator (root level) | `Fabrica-atlas/` | `Fabrica-atlas-tasks.md` | **launching fresh** — min 5 workers |
| WEB | *(dormant until Phase B)* | `Fabrica-web/` | `Fabrica-web-tasks.md` | dormant |
| MARKETING | *(dormant until Phase C)* | `Fabrica-marketing/` | `Fabrica-marketing-tasks.md` | dormant |
| PLUGINS | *(dormant)* | `Fabrica-plugins/` | `Fabrica-plugins-tasks.md` | dormant (100% done) |
| RELAY | *(dormant until Phase B)* | `Fabrica-relay/` | `Fabrica-relay-tasks.md` | dormant (94%, 2 tasks open) |

### Worker Sessions (ephemeral — released after review)

Historical record. Live worker tracking happens in each task file's own ledger.

| Name | Session | Parent | Task | Status |
|---|---|---|---|---|
| P9 Plugin loader | `term_8274ea16…` | app-orchestrator | P9: Plugin loader | released |
| P10 Plugin updates | `term_4a73d6e4…` | app-orchestrator | P10: Plugin updates | released |
| Docs rebrand | `term_b9293715…` | app-orchestrator | Docs rebrand | released |
| SKILL.md rebrand | `term_1dfdcd8e…` | app-orchestrator | SKILL.md rebrand | released |
| CI workflows rebrand | `term_f77a5a04…` | app-orchestrator | CI workflows rebrand | released |
| F2 Build verification | `term_2d281364…` | orchestrator | F2: Build verification | done |
| F3 Lint+test | `term_626fd308…` | orchestrator | F3: Lint + test | superseded by app ledger |
| Relay deploy research | `term_0e49225d…` | orchestrator | Relay deployment alternatives | released |
| R-TESTS miniflare | `term_59b66903…` | orchestrator | R16+R22 integration tests | released (found 5 prod bugs; fixed+redeployed) |

### Abandoned Worktrees (removed)

| Worktree | Branch | Status | Lost Work |
|---|---|---|---|
| `rename-e2ee-2` | `Auto-Scalers/rename-e2ee-2` | removed | None (0 unique commits) |
| `rename-relay-2` | `Auto-Scalers/rename-relay-2` | removed | None (0 unique commits) |

### Rules

- **Orchestration sessions never close.** They stay alive and handle new tasks.
- **Workers are released after review.**
- **One orchestration session per task file.** No duplicates.
- **Merge worktrees immediately** after review.
- **Update this ledger** when slots change.

---

## Migration Notes

- This file was rewritten to Tracking Schema v1 on 2026-08-23. The previous
  version (including its per-project detail tables, which were stale duplicates of
  the task files and suffered UTF-8 encoding corruption) is preserved intact at
  `.archive/Fabrica-Roadmap-pre-schema-v1.md`. Nothing was deleted.
- Known follow-up: **Fabrica-app status reconciliation** — its task file regressed
  during parallel work (statuses reverted, ledger rows lost); re-migrated 2026-08-23
  with a gap list produced against `.archive/Fabrica-app-tasks-pre-schema-v1.md`.
  The App orchestrator must rule on the flagged contradictions (APP-C4, APP-F2,
  APP-F3) and restore lost ledger history from the archive copy.
- 2026-08-23 PM reset: High-Level Goals section added; launch phases A–D defined;
  dashboard resynced (web recount corrected); fleet reset to 2 root orchestrators.

---

_Last updated: 2026-08-23_
