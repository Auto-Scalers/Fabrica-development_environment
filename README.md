# Fabrica

**Business-First, Coding-First Agentic Development Environment (Desktop application).**

For Founders, solo builders, and lean engineering teams spending dozens of hours manually running local CLI scripts, managing tracking spreadsheets, and prompting AI tools across fragmented browser tabs.

Stop prompting. Define your multi-agent crews (Researchers, Developers, Marketers, Business Analysts), control budget, approvals, security and let parallel AI coding agents work across isolated worktrees or plain disk folders on 24/7 Autonomy and Scale.

Draft, plan, execute, verify — assign tasks, orchestrate and supervise from a unified command center. With zero technical setup.

**The Next AI Exit. Operating locally or remotely.**

---

## Development Environment

This is the **Fabrica development environment** — a monorepo containing all the pieces needed to build, market, and manage the Fabrica product.

### Repos

| Folder | Repo | What It Is |
|--------|------|-----------|
| `Fabrica-app/` | `Auto-Scalers/Fabrica-app` | Desktop app (Electron, forked from Orca) |
| `Fabrica-web/` | `Auto-Scalers/Fabrica-web` | Landing page (Next.js, fabrica-ai.vercel.app) |
| `Fabrica-marketing/` | `Auto-Scalers/Fabrica-Marketing` | Marketing assets, copy, and launch materials |
| `Fabrica-plugins/` | `Auto-Scalers/Fabrica-plugins` | Plugin marketplace index (JSON registry + plugin submodules) |
| `Fabrica-relay/` | `Auto-Scalers/Fabrica-relay` | Relay server (Cloudflare Workers — phone↔desktop bridge) |
| `Fabrica-atlas/` | `Auto-Scalers/Fabrica-atlas` | Discovery & transformation planning (owns `_sources/`) |

### How It Works

```
Fabrica-development_environment/     ← You are here (top-level)
├── Fabrica-app/                     ← Desktop app source code
├── Fabrica-web/                     ← Landing page (fabrica-ai.vercel.app)
├── Fabrica-marketing/               ← Marketing assets & copy
├── Fabrica-plugins/                 ← Plugin marketplace index
├── Fabrica-relay/                   ← Relay server (phone↔desktop)
├── Fabrica-atlas/                   ← Discovery & transformation planning (_sources/)
├── .Fabrica-board/                  ← Top-level roadmap, DNA, schema, heartbeat
├── AGENTS.md                        ← Orchestrator agent instructions
└── README.md                        ← This file
```

Each folder is its own git repo with its own `AGENTS.md` (system logic / agent instructions), `README.md` (what this folder is), and `.Fabrica-{name}-board/` (task files).

### Where Things Live (role separation)

| File type | Role |
|---|---|
| `AGENTS.md` | System logic — how agents work in that folder |
| `README.md` | Project details — what the project is |
| `.Fabrica-board/Fabrica-Roadmap.md` | High-level goals + cross-project status mirror |
| `.Fabrica-{name}-board/*-tasks.md` | Task details, runs, session ledgers |
| `.Fabrica-board/Heartbeat.md` | Autonomous loop instructions + current focus areas |

### Core Value Pillars

- **Zero-Prompt Automation:** Continuous execution powered by background daemons and task queues.
- **Operational Oversight:** Eisenhower prioritization, goal tracking, and live agent activity streams.
- **Field Ops & Safety:** Human approval workflows for high-risk actions (payments, deployments, social publishing) and client-side credential vaulting.
- **Priority Matrix / Kanban workflows.**

---

## Getting Started

**For Product Manager (non-technical):**
- Read each folder's `README.md` to understand what it does
- Read each folder's `AGENTS.md` to understand what agents can/can't do there
- The top-level `AGENTS.md` explains how the orchestrator coordinates across all folders

**For Developers:**
- `Fabrica-app/` — Electron app, see its README for setup
- `Fabrica-web/` — Next.js landing page, `npm install && npm run dev`
- `Fabrica-marketing/` — Static assets, no build step
- `Fabrica-plugins/` — JSON registry, no build step
- `Fabrica-relay/` — Cloudflare Workers, see its README for setup
- `Fabrica-atlas/` — Analysis-only, read-only on sources

---

## Brand

- **Product:** Fabrica
- **Tagline:** "The Next AI Exit"
- **Voice:** Forge/foundry & command-center metaphor
- **Theme:** Obsidian dark + molten copper/amber
- **Target:** Founders, solo builders, lean engineering teams
