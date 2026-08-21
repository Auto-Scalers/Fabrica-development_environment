# Fabrica — Roadmap 02

> Phase 2 execution. Vision/identity → `Fabrica-DNA.md`. Marketing Findings, Gaps & Feature QA → `Features-QA.md`.

---

## Dashboard

| Metric | Value |
|--------|-------|
| Total Phase 2 tasks | 70 |
| ✅ Done | 4 |
| 🔶 In Review | 0 |
| ⬜ Todo | 66 |
| 📋 Planning | 0 |
| 🚫 Blocked | 0 |
| ❌ Issues | 0 |
| Completion | 6% |

### Phase Progress

```
Phase 2 — Business-First Transformation

Group 0 — Strategy & Feature QA Alignment            ✅  [████████████████████] 100% (4/4 done)
Group I — Source Extraction & Licensing Isolation    ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (3 tasks) ← NEXT
Group A — Mission Control UI & Visual Lifecycle      ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (10 tasks)
Group B — Multi-Role Business Agent Crews & CLI Mgr  ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (9 tasks)
Group C — Governance: Approval Gates & Hard Budgets  ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (6 tasks)
Group D — Field Ops, n8n & 64+ Service Connectors    ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (9 tasks)
Group E — Knowledge Vault & Encrypted Credentials    ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (6 tasks)
Group F — Workflow Automation & 24/7 Runtime Daemon  ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (6 tasks)
Group G — Mobile Companion & 24/7 Remote Steering    ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (5 tasks)
Group H — Dual Onboarding (Builders/Runners) & Packs ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (7 tasks)
```

---

## Right Now

> What's actively being tracked. Update this section as work progresses.

| What | Status | Owner | Notes |
|------|--------|-------|-------|
| Extract marketing findings into `Features-QA.md` | ✅ Done | Orchestrator | Complete in `Features-QA.md` (all 9 domains & competitor gaps) |
| PM Review of `Features-QA.md` | ✅ Done | User (PM) | PM decisions, feedback, and positioning corrections received |
| Update Brand & Research from PM Feedback | ✅ Done | Orchestrator | `brand-guidelines.md`, `positioning-statement.md`, `competitor-landscape.md` updated |
| Lock in Phase 2 feature backlog | ✅ Done | Orchestrator | `Features-QA.md` and `Fabrica-Roadmap-02.md` synchronized |
| Group I: Source Study & Feature Extraction | ⬜ Next | Fabrica-app | Unblocked. Extract specs from `_sources/` (mission-control, buzz, legacy-fabrica) |

---

## Phase 2 — Business-First Transformation

> Transform Fabrica from coding-first to a desktop CLI agent management and operations platform for both builders and operators.
> All marketing research, competitor gaps, trade-offs, and options live in **[Features-QA.md](Features-QA.md)**.

### Progress by Sub-Project

| Sub-Project | ✅ Done | 🔶 In Review | ⬜ Todo | 📋 Planning | 🚫 Blocked | ❌ Issues | Task File |
| ----------- | ------ | ------------ | ------ | ----------- | ---------- | -------- | --------- |
| Strategy & QA | 4 | 0 | 0 | 0 | 0 | 0 | `.Fabrica-Board/Features-QA.md` |
| Fabrica-app | 0 | 0 | 49 | 0 | 0 | 0 | `Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md` |
| Fabrica-relay | 0 | 0 | 5 | 0 | 0 | 0 | `Fabrica-relay/.Fabrica-relay-board/Fabrica-relay-tasks.md` |
| Fabrica-web | 0 | 0 | 5 | 0 | 0 | 0 | `Fabrica-web/.Fabrica-web-board/Fabrica-web-tasks.md` |
| Fabrica-marketing | 0 | 0 | 7 | 0 | 0 | 0 | `Fabrica-marketing/.Fabrica-marketing-board/Fabrica-marketing-tasks.md` |
| **Total** | **4** | **0** | **66** | **0** | **0** | **0** | |

---

### Group 0 — Strategy & Feature QA Alignment
> **COMPLETE.** Marketing intelligence extracted, PM feedback integrated, Brand & Research docs rewritten, and Phase 2 backlog locked.

| # | Task | Status | Owner | Output / Deliverable |
|---|------|--------|-------|----------------------|
| 0.1 | Extract marketing findings, gaps, and opportunities into QA file | ✅ Done | Orchestrator | `.Fabrica-Board/Features-QA.md` created with 9 domains |
| 0.2 | Review `Features-QA.md` and select desired features & options | ✅ Done | User (PM) | PM decisions on P0/P1 priorities, CLI agent framing, and ops |
| 0.3 | Update Brand, Research, and `Features-QA.md` based on PM feedback | ✅ Done | Orchestrator | Brand guidelines, positioning, and research updated |
| 0.4 | Audit & finalize `Fabrica-Roadmap-02.md` tasks from approved QA | ✅ Done | Orchestrator | Locked Phase 2 task backlog with 70 tasks |

---

### Group I — Source Study & Feature Extraction
> **UNBLOCKED — NEXT STEP.** Blocks Groups A–H. Workers extract specifications into `Fabrica-app/.Fabrica-app-board/specs/`.

| # | Task | Status | Output File |
|---|------|--------|-------------|
| I1 | Extract functional specs from `_sources/mission-control` | ⬜ | `specs/mission-control-spec.md` (AGPL-3.0 clean-room) |
| I2 | Extract architecture & code from `_sources/buzz` | ⬜ | `specs/buzz-spec.md` (Apache 2.0) |
| I3 | Extract UI components from `_sources/legacy-fabrica` | ⬜ | `specs/legacy-fabrica-spec.md` |

---

### Group A — Mission Control UI (Command Center)

| # | Task | Status | Notes |
|---|------|--------|-------|
| A1 | Design master Mission Control layout (Kanban + fleet status) | ⬜ | Wireframe from `mission-control` patterns |
| A2 | Implement Visual Kanban & Eisenhower Priority Matrix | ⬜ | `@dnd-kit` drag-and-drop |
| A3 | Implement Sources vs. Deliverables Split View | ⬜ | 50/50 split from `legacy-fabrica` |
| A4 | Implement Agent Fleet Registry Panel with Forge Pulse | ⬜ | Active cards with status, token usage & Forge Pulse animation |
| A5 | Implement Unified Decision Inbox | ⬜ | Central feed for human sign-offs |
| A6 | Implement Live App & Artifact Previewer | ⬜ | Embedded iframe sandbox |
| A7 | Implement Activity & Audit Log View | ⬜ | Searchable, timestamped execution log |
| A8 | Implement AI Context Snapshot Generator | ⬜ | Background ~650-token prompt summarizer |
| A9 | Implement Natural Language Mission Launcher | ⬜ | Objective ➔ Auto-decomposed sub-tasks |
| A10 | Implement Business Velocity & Cost Analytics | ⬜ | Time/money saved charts (D3/Recharts) |

---

### Group B — Multi-Role Business Agent Crews & CLI Management

| # | Task | Status | Notes |
|---|------|--------|-------|
| B1 | Implement Persona Engine & Role Definitions | ⬜ | Inspired by `buzz-persona` |
| B2 | Build Lead Researcher Agent Persona | ⬜ | Web search, scrape, competitor summaries |
| B3 | Build Growth Marketer Agent Persona | ⬜ | GTM copy, social threads, SEO, launch blogs |
| B4 | Build Business Data Analyst Agent Persona | ⬜ | CSV/SQL modeling, unit economics, charts |
| B5 | Build Operations Specialist Agent Persona | ⬜ | Webhooks, cron jobs, file maintenance |
| B6 | Upgrade Senior Full-Stack Engineer Agent | ⬜ | Architecture planning, tests, PR descriptions |
| B7 | Implement Crew Collaboration UI & Delegation Tree | ⬜ | Lead agent delegating to parallel worktrees |
| B8 | Implement Slack-like Agent Collaboration Channels | ⬜ | Dedicated agent discussion channels, group routing & debate |
| B9 | Implement CLI Agent Terminal Manager | ⬜ | Spawner & manager for Claude Code, Codex, Cursor, Devin, Hermes, Pi |

---

### Group C — Governance: Approval Gates & Budget Controls

| # | Task | Status | Notes |
|---|------|--------|-------|
| C1 | Visual One-Click Approval Modal | ⬜ | Shows visual diffs, cost estimate, risk level |
| C2 | Hard Financial Budgeting Engine | ⬜ | Strict per-mission spend cap with auto-halt |
| C3 | 3-Tier Risk Classification Engine | ⬜ | Tier 1 (Auto) / Tier 2 (Desktop) / Tier 3 (Gate) |
| C4 | Granular Autonomy Sliders | ⬜ | Manual ➔ Supervised ➔ Autonomous |
| C5 | Real-Time Quota & Spend Tracker | ⬜ | Live counter for supported CLI agents (Claude Code, Codex, OpenCode) |
| C6 | Global Emergency Circuit Breaker | ⬜ | Floating instant-kill button for all workers |

---

### Group D — Field Ops, n8n & 64+ Service Connectors

| # | Task | Status | Notes |
|---|------|--------|-------|
| D0 | Implement Native n8n Capability Plugin | ⬜ | Bidirectional bridge connecting agent workflows to 400+ SaaS apps |
| D1 | Build Field Ops Execution State Machine | ⬜ | Clean-room implementation |
| D2 | Build Service Adapter Interface | ⬜ | Extensible TypeScript adapter standard |
| D3 | Core Connectors (Batch 1: Dev/Ops) | ⬜ | GitHub, Slack, Email (SMTP/Resend), Supabase |
| D4 | Core Connectors (Batch 2: Growth) | ⬜ | Twitter/X, LinkedIn, Stripe, Notion |
| D5 | 64-Service Visual Catalog & Setup Wizard | ⬜ | Interactive service directory |
| D6 | Dry-Run Sandbox Preview Mode | ⬜ | Simulates external API calls before approval |
| D7 | Per-Service Action Throttling | ⬜ | Rate limits and spend caps per integration |
| D8 | Field Ops Audit Trail & CSV Export | ⬜ | Compliance log with approving user timestamps |

---

### Group E — Knowledge Vault & Encrypted Credentials

| # | Task | Status | Notes |
|---|------|--------|-------|
| E1 | Implement AES-256-GCM Vault Engine | ⬜ | Derived via Argon2id / OS Keychain |
| E2 | Build Zero-Knowledge BYOK Settings UI | ⬜ | Store keys for Anthropic, OpenAI, Google, etc. |
| E3 | Implement Least-Privilege Key Scoping | ⬜ | Memory-only injection per sub-task |
| E4 | Vault Auto-Lock & Session Timeout | ⬜ | Configurable lock requiring master password |
| E5 | Implement Emergency Panic Wipe | ⬜ | Secure shredder purging all cached secrets |
| E6 | Build Central Knowledge Vault (Document Drop) | ⬜ | Local folder watcher & semantic context provider for all agents |

---

### Group F — Workflow Automation & 24/7 Runtime Daemon

| # | Task | Status | Notes |
|---|------|--------|-------|
| F1 | Build YAML Workflow Blueprint Engine | ⬜ | Adapted from `buzz-workflow` (Apache 2.0) |
| F2 | Implement Persistent Background Daemon | ⬜ | Node runner with `node-cron` support |
| F3 | Build Visual Workflow Builder | ⬜ | Node graph / clean YAML editor |
| F4 | Build Loop & Stall Watchdog Engine | ⬜ | Auto-detects stuck processes and escalates |
| F5 | Implement Session Checkpointing & Resilience | ⬜ | Resumes crashed missions without data loss |
| F6 | Create 24/7 Turnkey Operational Recipes | ⬜ | Customer Support Triage, Ecommerce Bot, Content Pipeline, HR Intake |

---

### Group G — Mobile Companion & Remote Steering

| # | Task | Status | Notes |
|---|------|--------|-------|
| G1 | Build Mobile Push Notification Dispatcher | ⬜ | Alerts on approval gates & budget warnings |
| G2 | Build One-Tap Mobile Decision & Diff Review | ⬜ | Inspect diffs and approve via Fabrica-relay |
| G3 | Build Live Mobile Mission Feed | ⬜ | Real-time progress and token consumption |
| G4 | Remote Natural Language Steering | ⬜ | Send chat instructions to running agents |
| G5 | Remote Emergency Mission Pause | ⬜ | 1-tap mobile kill-switch |

---

### Group H — Dual Onboarding (Builders/Runners) & Starter Packs

| # | Task | Status | Notes |
|---|------|--------|-------|
| H1 | Build 3-Step Guided Dual Onboarding Wizard | ⬜ | Builder vs Runner path ➔ Connect Agent/Key ➔ Launch Demo |
| H2 | Full UI Terminology De-Jargonization | ⬜ | Replace dev jargon with founder/operator language |
| H3 | Create Turnkey Business Starter Packs | ⬜ | SaaS Dev, E-Commerce Ops, Agency Multi-Client, HR & Content |
| H4 | Build Contextual In-App Guidance | ⬜ | Interactive feature walkthroughs |
| H5 | Action-Oriented Empty States | ⬜ | Illustrative graphics with clear CTAs |
| H6 | Humanized Error Explanations | ⬜ | Plain English diagnosis with 1-click fix |
| H7 | Build Interactive Demo Mission Sandbox | ⬜ | Zero-cost pre-cached simulation |

---

## What We Keep From Fabrica (Orca Base) — Never Replace

| Feature | Current State | Phase 2 Enhancement |
|---------|---------------|---------------------|
| Parallel worktrees | CLI-driven git worktrees | Visual Workspace Tabs in Mission Control (A1) |
| Approval gates | Terminal confirmation prompts | Rich GUI modal with visual diffs and risk tags (C1) |
| Mobile companion relay | Terminal mirror | Dedicated mobile approval UI with push alerts (G1-G5) |
| Plugin ecosystem | Developer plugin loader | Foundation for Field Ops & n8n integration (D0, D3-D5) |
| Multi-model BYOK | Environment variables | Encrypted client-side Vault with live token counter (E1-E3) |
| Skills framework | Markdown skill files | Reusable Knowledge Modules assignable visually (B1) |
| CLI engine | `fabrica` CLI commands | Retained for developers, automated under GUI |

---

> **Reference** (App ID, Infrastructure, Deferred Items) → see [Fabrica-DNA.md](Fabrica-DNA.md)

---

## Session Ledger

> Phase 2 sessions. Master ledger → `Fabrica-Roadmap.md`.

### Worker Sessions (ephemeral — released after review)

| Name | Session | Parent Orchestrator | Task | Status | Worktree Merged |
|------|---------|-------------------|------|--------|----------------|
| Marketing QA Alignment | `term_orchestrator` | Orchestrator | Group 0: Feature QA Alignment | **complete** | ✅ |

### Rules

- **Workers are released after review.** Once work is approved, release the worker and merge the worktree.
- **Group 0 (QA Review & Alignment) is complete.**
- **Group I (Source Extraction) must complete before Groups A–H dispatch.**
- **One orchestration session per task file.** No duplicates.
- **Merge worktrees immediately.** Never leave branches unmerged after review.
- **Update this ledger** when sessions are created, released, or worktrees merged.

---

*Last updated: Aug 2026*
