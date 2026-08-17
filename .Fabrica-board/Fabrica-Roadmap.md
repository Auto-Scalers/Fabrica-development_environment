# Fabrica — Roadmap

> Tactical execution plan. For the enduring vision and strategic pillars, see `Fabrica-DNA.md`.

---

## Phase 1 — Rebranding & Foundation

> Make the Orca codebase fully Fabrica.

### Done

- [x] Brand assets created
- [x] Old Fabrica aesthetic reference captured (`Fabrica-ADE/old-fabrica`)
- [x] Support email confirmed: `fabrica.studio.contact@gmail.com`
- [x] App ID confirmed: `ai.autoscalers.fabrica` (unified across all platforms)
- [x] Landing page deployed (`fabrica-ai.vercel.app`)
- [x] GitHub repo created (`Auto-Scalers/Fabrica-app`)

### In Progress

when someone look at the new Fabrica app he should not reconize that it been builded on the base of orca :

- [ ] Capture aesthetic reference from (`Fabrica-web/`)
- [ ] Visual palette migration — extract from `Fabrica-web/`, audit Orca app, apply consistently
- [ ] Clean build verification after each migration step

### Next

Look for any old reops references or names like stablyai, orca, autoskiller, Auto-Skiller, auto-skiller, AutoSkiller, Fabrica-IDE, Fabrica-ADE or similar things, the olny things we should have are : autoscalers, AutoScalers, Fabrica, Auto-Scalers/Fabrica-app, fabrica-ai.vercel.app :

- [ ] Configs migration — metadata, distribution configs, app identifiers
- [ ] Telemetry sanitization — replace `stablyai` analytics with Fabrica endpoints (`fabrica-ai.vercel.app/api/telemetry`)
- [ ] Auto-updater & releases — point to `Auto-Scalers/Fabrica-app` repo, endpoint at `fabrica-ai.vercel.app/api/update`
- [ ] Deep linking — rename `orca://` protocol handlers to `fabrica://`
- [ ] Final rebrand verification — full audit that no Orca artifacts remain

---

## Phase 2 — Business-First UI & Agentic Layer

> Transform from coding-first to business-first. Non-technical founders control everything from the UI.
notes: 
- we stricly keep all existing festures, we are auditing and adding, not making massive refactors.
- we are Reimplementing business layer and agentic driven ui without corrupting existing features.

### Planning

- [ ] UI-driven task lifecycle: Draft → Plan → Execute → Verify — no CLI required
- [ ] Agent crew definitions: Researchers, Developers, Marketers, Business Analysts
- [ ] Orchestration & supervision from the UI — assign, monitor, intervene
- [ ] Data visualization & interactive dashboards (research Power BI, Vercel Labs patterns)
- [ ] Business intelligence features

### Mission-Control Integration

Source: `Auto-Scalers/Fabrica/mission-control` (AGPL-3.0)

**License-safe approach:**
1. Agent A reads source → writes functional specs (what it does, not how)
2. Agent B (never saw source) implements from specs independently
3. Clean-room reimplementation — zero license entanglement

- [ ] Extract functional specs from mission-control
- [ ] Audit specs — add, remove, refine features

---

## Phase 3 — Ecosystem & Scale

> Plugins, skills, composability. Users build their own stacks.

### Planned

- [ ] Plugin system with Fabrica publisher (migrate from `stablyai.orca-*`)
- [ ] Skill marketplace
- [ ] Multi-agent crew templates
- [ ] Extended features: Phone, Canvas (require auth)

---

## Blocked / Deferred

> Not blocking current desktop-first work. Revisit when conditions change.

| Item | Blocker | What's Needed | Timeline |
|------|---------|---------------|----------|
| Code signing | Apple Developer Program enrollment | $99/year Apple Dev membership, Windows SignPath | Apple approval: 24-48h (first time can be longer) |
| App Store (iOS) | Same Apple Dev Program + app review | Apple Dev membership, App Store listing, review submission | Review: 1-3 days |
| Google Play | One-time $25 fee | Google Play Developer account | Instant |
| Mobile backend | Supabase auth + push notifications | Use existing Supabase project (same as landing page) | Pending mobile app scope |

---

## App ID

**Unified across all platforms:** `ai.autoscalers.fabrica`

**Backend:** Supabase (shared with landing page) — auth, push notifications, telemetry storage

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

---

## GitHub Repos

| Repo | Purpose | Status |
|------|---------|--------|
| `Auto-Scalers/Fabrica-app` | Main desktop app source | Created, empty (pre-push) |
| `fabrica-ai.vercel.app` | Landing page | Live |
| `Auto-Scalers/Fabrica-hourly` | Scheduled task runner | To create |
| `Auto-Scalers/Fabrica-daily` | Daily digest runner | To create |
| `Auto-Scalers/Fabrica-adhoc` | On-demand tasks | To create |
| `fabrica-plugins` | Plugin registry | To create |
| `fabrica-portuguese` | Portuguese localization | To create |
| `fabrica-multipass-recipes` | Multipass recipes | To create |
| `fabrica-navigation-shortcuts` | Navigation shortcuts | To create |

---

## Open Questions

- `/usr/bin/orca` — is this GNOME's screen reader (built into Linux) or from the codebase?
- Some features require login (Phone, Canvas) — what's the auth strategy?
- GNOME screen reader naming conflict — does it affect the Orca fork?
- GitHub repos — not creating yet, decide after codebase exploration

---

_Last updated: Aug 2026_
