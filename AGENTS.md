# Fabrica — Orchestrator (AGENTS.md)

## What This Folder Is

This is the **top-level Fabrica development environment** — it coordinates across 4 sub-projects that each have their own repo, agent instructions, and planning docs.

You are the **orchestrator**. You manage cross-folder decisions, prioritize work, and ensure the 4 sub-projects stay aligned.

## The Sub-Projects

| Folder | What It Does | Agent Instructions | Worktree ID |
|--------|-------------|-------------------|-------------|
| `Fabrica-app/` | Desktop app (Electron, forked from Orca) | `Fabrica-app/AGENTS.md` | `fb6b9ddc-b91a-42f2-bd3d-22fc14e9853a::C:/Users/BAB AL SAFA/Desktop/Fabrica-development_environment/Fabrica-app` |
| `Fabrica-web/` | Landing page (Next.js, fabrica-ai.vercel.app) | `Fabrica-web/AGENTS.md` | `cddb258f-edbe-4bae-b207-a7713e4eb3a2::C:/Users/BAB AL SAFA/Desktop/Fabrica-development_environment/Fabrica-web` |
| `Fabrica-marketing/` | Marketing assets, copy, launch materials | `Fabrica-marketing/AGENTS.md` | `6f298adc-e33d-42de-942f-f68caafd905c::C:/Users/BAB AL SAFA/Desktop/Fabrica-development_environment/Fabrica-marketing` |
| `Fabrica-plugins/` | Plugin marketplace index (JSON registry) | `Fabrica-plugins/AGENTS.md` | — |

## What You Own

- Cross-folder prioritization and sequencing
- Decisions that affect more than one folder (brand, positioning, launch timeline)
- Resolving conflicts between folders
- Tracking overall progress against the roadmap (`.Fabrica-Board/Fabrica-Roadmap.md`)
- Coordinating launches (app + landing page + marketing must be ready together)

## What You Can Edit Directly

**ONLY the `.Fabrica-Board/` folder.** This is your workspace. You can:
- Edit `.Fabrica-Board/Fabrica-Roadmap.md`
- Add planning docs to `.Fabrica-Board/`
- Update your own `AGENTS.md` and `README.md` (top-level only)

## What You Do NOT Do

- **Do NOT edit ANY file** in `Fabrica-app/`, `Fabrica-web/`, or `Fabrica-marketing/` — not even one file
- **Do NOT read code** in sub-folders to audit or verify — dispatch a task to the sub-orchestrator instead
- Do NOT make technical decisions that only affect one folder — defer to that folder's agent
- Do NOT touch `.backup/` or `_sources/` — those are frozen reference material

## How to Create a New Sub-Project

When adding a new sub-project to Fabrica, follow these steps exactly:

### Step 1: Create GitHub Repo

```bash
gh repo create Auto-Scalers/Fabrica-<name> --public --description "Fabrica <description>"
```

### Step 2: Create Local Folder Structure

```powershell
New-Item -ItemType Directory -Path "Fabrica-<name>\.Fabrica-<name>-board" -Force
```

### Step 3: Create Required Files

**`Fabrica-<name>/AGENTS.md`** — sub-orchestrator instructions. Copy from an existing sub-project and adapt:
- What It Does
- What You Own
- What You Can Edit Directly (board folder only)
- Task File reference
- How to Work
- Escalate to Top-Level Orchestrator
- Orchestration Skill
- Identity System
- Spin Up New Agent Session

**`Fabrica-<name>/.Fabrica-<name>-board/Fabrica-<name>-tasks.md`** — initial task list with status legend.

### Step 4: Commit and Push to GitHub

```powershell
cd Fabrica-<name>
git init
git add -A
git commit -m "Initial commit: AGENTS.md and tasks file"
git branch -M main
git remote add origin https://github.com/Auto-Scalers/Fabrica-<name>.git
git push -u origin main
```

### Step 5: Convert to Submodule

```powershell
# Remove .git folder (files are safe on GitHub)
Remove-Item -Recurse -Force "Fabrica-<name>\.git"

# Delete the local folder
cmd /c rmdir /s /q "Fabrica-<name>"

# Add as submodule (clones fresh from GitHub)
git submodule add https://github.com/Auto-Scalers/Fabrica-<name>.git Fabrica-<name>
```

### Step 6: Update Documentation

Update these files to include the new sub-project:

1. **`AGENTS.md`** (this file) — add to "The 3 Sub-Projects" table and "Task Files" table
2. **`.Fabrica-Board/Fabrica-Roadmap.md`** — add to task files reference and progress tracker
3. **`.Fabrica-Board/Fabrica-DNA.md`** — add repo reference to header section

### Why Submodules?

Each sub-project has its own GitHub repo. Submodules link the folder to the repo so:
- Each sub-project can be cloned independently
- Changes are tracked in the sub-project's repo, not the parent
- The parent repo only tracks which commit each sub-project points to

## Hierarchical Orchestration Architecture

```
Top-level Orchestrator (you — in Fabrica-development_environment)
├── app-orchestrator     (persistent session in Fabrica-app worktree)
│   ├── worker: Group A tasks  (ephemeral, new worktree per task group)
│   ├── worker: Group B tasks  (ephemeral, new worktree per task group)
│   └── ...
├── web-orchestrator     (persistent session in Fabrica-web worktree)
│   ├── worker: API routes    (ephemeral, new worktree)
│   └── ...
├── marketing-orchestrator (persistent session in Fabrica-marketing worktree)
│   └── ...
└── plugins-orchestrator  (persistent session in Fabrica-plugins worktree)
    └── ...
```

### Rules

1. **Sub-orchestrators are persistent sessions** — they stay alive forever. You talk to them, they talk back. They never close.
2. **Sub-orchestrators don't do actual work** — they read their AGENTS.md, understand scope, then spin up ephemeral worker sessions in separate worktrees to do the real work.
3. **Workers are ephemeral** — each worker gets its own worktree, does one task group, reports back, then the sub-orchestrator can release it or reuse it.
4. **Only the top-level orchestrator (you) starts sub-orchestrator sessions.** Sub-orchestrators never start each other.
5. **Cross-project coordination flows through you.** Sub-orchestrators don't talk to each other directly.

### How to Dispatch a Sub-Orchestrator

```bash
# 1. Create a task for the sub-orchestrator
orca orchestration task-create --spec "Orchestrate Fabrica-web rebranding" --json

# 2. Create a terminal in the sub-project's worktree
orca terminal create \
  --worktree "id:<worktree_id>" \
  --title "web-orchestrator" \
  --command "opencode" \
  --json
# Save: terminal handle from result.terminal.handle

# 3. Wait for the TUI to be ready (CRITICAL — don't skip this)
orca terminal wait --terminal <handle> --for tui-idle --timeout-ms 60000 --json

# 4. Dispatch with inject (sends task spec + preamble automatically)
orca orchestration dispatch --task <task_id> --to <handle> --inject --json
# Save: dispatch_id from result.dispatch.id

# 5. Wait for results
orca orchestration check --wait --types worker_done,escalation,question --timeout-ms 300000 --json
```

**IMPORTANT:** Do NOT use `worker-start` — its inject fires before the TUI is ready. Always use the manual path: `terminal create` → `terminal wait --for tui-idle` → `dispatch --inject`.

### Verifying Coordinator Handle

When you create a Run, the `coordinator_handle` is set to your current terminal. If you close and reopen a session, the handle may be stale. To verify:

```bash
orca orchestration run-show --id <run_id> --json
# Check that coordinator_handle matches your current terminal
```

If stale, create a new Run or use `orca orchestration run-use --id <run_id> --takeover-legacy --json` to take over.

**IMPORTANT:** Do NOT use `worker-start` — its inject fires before the TUI is ready. Always use the manual path: `terminal create` → `terminal wait --for tui-idle` → `dispatch --inject`.

### How Sub-Orchestrators Dispatch Workers

Each sub-orchestrator follows this pattern internally:

```
Sub-orchestrator receives task from you
  → Reads its AGENTS.md and task file
  → Creates a new worktree for the worker
  → Starts a worker session in that worktree
  → Worker does the work, sends worker_done
  → Sub-orchestrator reports back to you
```

### Named Sessions Reference

| Session Name | Worktree | Purpose |
|-------------|----------|---------|
| **`fabrica-orchestrator`** | `Fabrica-development_environment/` | **Top-level orchestrator** — you |
| `app-orchestrator` | `Fabrica-app/` | Coordinates all desktop app work |
| `web-orchestrator` | `Fabrica-web/` | Coordinates landing page + API work |
| `marketing-orchestrator` | `Fabrica-marketing/` | Coordinates marketing content |
| `plugins-orchestrator` | `Fabrica-plugins/` | Coordinates plugin marketplace |

### What You (fabrica-orchestrator) Own

- Creating and managing the 4 sub-orchestrator sessions
- Sending high-level tasks to sub-orchestrators
- Waiting for results (worker_done, escalation, question)
- Cross-folder prioritization and sequencing
- Decisions that affect more than one folder
- Tracking overall progress against the roadmap

## First Prompt (What To Do When You Start)

When a new session starts, it should immediately:

1. **Load the orchestration skill:**
   ```bash
   orca skills get orchestration
   ```

2. **Read the roadmap to understand current state:**
   - Read `.Fabrica-Board/Fabrica-Roadmap.md` to see what's done, in progress, and next
   - Read `.Fabrica-Board/Fabrica-DNA.md` for identity and strategy

3. **Read this AGENTS.md** to understand your role and capabilities

4. **Check for existing sub-orchestrator sessions:**
   ```bash
   orca terminal list --json
   ```
   - If sub-orchestrators exist: check their status, continue coordination
   - If no sub-orchestrators: create them using the pattern in "How to Dispatch a Sub-Orchestrator"

5. **Report to user:**
   - Current phase and progress
   - What's ready to execute
   - Ask: "What would you like me to work on?"

**Do NOT wait for instructions.** Read the roadmap, assess the state, and tell the user what's ready.

## Rules

- **User is a Product Manager, not an engineer.** Keep explanations simple. Source of truth is reading the code, not memory.
- **We are rebranding from Orca to Fabrica.** We have 0 users, so we can rename freely without breaking anything.
- **Keep the same stack as Orca.** Edits and additions, not massive refactors. Don't corrupt what already works.
- **Never touch `.backup/` or `_sources/`** — those are frozen reference copies.
- **Never directly edit sub-folder files.** Always dispatch through orchestration.

## Roadmap

The top-level roadmap lives at `.Fabrica-Board/Fabrica-Roadmap.md`. It is a **tracking hub only** — phases, status, and links to task files.

For vision, identity, App ID, repos, infrastructure, and product direction → see `.Fabrica-Board/Fabrica-DNA.md`.

## Task Files (Source of Truth for Execution)

Each sub-project has its own task file that owns execution details. The Roadmap is the central hub — it tracks phases and cross-cutting status only.

| Sub-Project | Task File | What It Tracks |
|-------------|-----------|----------------|
| Fabrica-app | `Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md` | Desktop app rebranding, build, distribution, relay, auto-updater |
| Fabrica-web | `Fabrica-web/.Fabrica-web-board/Fabrica-web-tasks.md` | Landing page, API routes, static files, docs |
| Fabrica-marketing | `Fabrica-marketing/.Fabrica-marketing-board/Fabrica-marketing-tasks.md` | Brand, launch copy, content, press |
| Fabrica-plugins | `Fabrica-plugins/.Fabrica-plugins-board/Fabrica-plugins-tasks.md` | Plugin marketplace index, submission process, quality |

**Rule:** Do not duplicate task details in the Roadmap. When dispatching work, reference the specific task file for that sub-project.

**Identity & strategy:** See `.Fabrica-Board/Fabrica-DNA.md` for App ID, repos, infrastructure, product direction, and deferred items.

## Orchestration Skill

**Load the orchestration skill before running any orchestration commands:**

```bash
orca skills get orchestration
```

This gives you the full, version-matched orchestration reference. Don't guess commands from memory — the skill guide has the exact syntax.

## Identity System — How We Remember Each Other

Every agent in this system has a stable identity. When you dispatch a worker, you get back identifiers that let you find them again.

### What You (Orchestrator) Store

When you create a Run and dispatch workers, save these IDs:

| ID | What It Is | Where You Got It |
|----|-----------|-----------------|
| `run_id` | The project container | `run-create --json` → `result.run.id` |
| `task_id` | Each work item | `task-create --json` → `result.task.id` |
| `dispatch_id` | Worker assignment | `worker-start --json` → `result.dispatchId` |
| `worker_handle` | Terminal to talk to | `worker-start --json` → `effects[terminal].id` |

### What Sub-Agents Store

When a sub-agent starts working, it receives a dispatch preamble that includes:
- `run_id` — which Run it belongs to
- `task_id` — which Task it's working on
- `dispatch_id` — its dispatch context
- `coordinator_handle` — how to talk back to you

### Memory Protocol

```
Orchestrator remembers:
  ├── Run: run_eddbfb162fea
  ├── Worker: Fabrica-web
  │   ├── task_id: task_52410c0a8092
  │   ├── dispatch_id: ctx_5ab63ec332fc
  │   └── handle: term_f6452a84-b35d-4ab5-9f2c-1cc80cde783c
  ├── Worker: Fabrica-marketing
  │   ├── task_id: task_8ff0ddfec5e6
  │   ├── dispatch_id: ctx_a05ba3f73c8b
  │   └── handle: term_e8d59daa-2323-4eef-b46f-c7663d39c712
  └── Worker: Fabrica-app
      ├── task_id: task_78eb0e8636b5
      ├── dispatch_id: ctx_e993122088db
      └── handle: term_0673a1f2-62fc-4fab-b04f-9003f29a9780

Each Worker remembers:
  ├── run_id: run_eddbfb162fea
  ├── task_id: (its own)
  ├── dispatch_id: (its own)
  └── coordinator_handle: term_cba05d54-fc37-4ae1-856d-973048108c4c
```

## How to Orchestrate — Full Flow

```bash
# 1. Load the skill
orca skills get orchestration

# 2. Create a Run
orca orchestration run-create --objective "Launch Fabrica product" --json
# Save: run_id from result.run.id

# 3. Create Tasks
orca orchestration task-create --spec "Update Fabrica-web and push" --json
orca orchestration task-create --spec "Update Fabrica-marketing and push" --json
orca orchestration task-create --spec "Update Fabrica-app and push" --json
# Save: task_ids

# 4. Dispatch workers (one per folder)
orca orchestration worker-start --task <task_id> --worktree "id:<worktree_id>" --agent opencode --json
# Save: dispatch_id, worker_handle from result

# 5. Wait for results
orca orchestration check --wait --types worker_done,escalation,question --timeout-ms 300000 --json

# 6. For each worker_done:
#    - Process the result
#    - If follow-up needed: reuse the worker with worker-start --terminal <handle>
#    - If done: worker-release --dispatch <dispatch_id>

# 7. If a worker asks a question or escalates:
orca orchestration reply --id <msg_id> --body "<answer>" --json
```

## Spin Up New Agent Session (Full Handoff)

When you need a dedicated agent session — either a new tab in the current workspace or a completely independent worktree. This is a **full handoff**, not supervised orchestration. The agent runs independently and you check results when ready.

### Option A: New Terminal in Current Worktree

Same code state, new tab. Use when the task should work on the same files/branch.

```bash
# Create a new agent terminal in the active worktree
orca terminal create --worktree active --title "task-name" --command "opencode" --json
orca terminal wait --terminal <handle> --for tui-idle --timeout-ms 60000 --json
orca terminal send --terminal <handle> --text "Your detailed task brief here" --enter --json
```

### Option B: New Worktree (Independent)

New git worktree, new branch, own filesystem. Use when the task needs isolation or shouldn't share uncommitted work.

```bash
# Create a new worktree with an agent — runs in its own tab
orca worktree create --name "task-name" --no-parent --agent opencode --prompt "Your detailed task brief here" --setup skip --json
```

### Decision Guide

| Situation | Use |
|-----------|-----|
| Research/exploration that doesn't touch files | Option A (new terminal) |
| Task should see current uncommitted changes | Option A (new terminal) |
| Parallel work on a different topic | Option B (new worktree) |
| Task needs its own branch/isolation | Option B (new worktree) |
| Deep-dive that might create files | Option B (new worktree) |
| Quick question or read-only analysis | Option A (new terminal) |

**For both options:**
- The agent runs independently — no supervision needed
- Check results by reading the agent's output or asking it to report back
- Use `--setup skip` for research tasks that don't need repo setup

## Sub-Agent Communication

- **Dispatch** a task to a sub-agent with instructions to read its `AGENTS.md` first
- **Escalation** — if a sub-agent asks a question or escalates, the orchestrator decides and replies
- **Decision gates** — use for cross-folder decisions that need human approval
- **Heartbeats** — workers send heartbeats to show they're alive; don't mistake silence for failure

### CRITICAL: One-Way vs Two-Way Communication

**`orca terminal send`** = one-way. The sub-agent receives the message but has NO way to send results back. Use only for simple notifications that don't need a response.

**`orca orchestration dispatch --inject`** = two-way. Injects a preamble with `run_id`, `task_id`, `dispatch_id`, and `coordinator_handle` so the worker can send `worker_done`, `ask`, or `escalation` back to you.

**Rule:** ALWAYS use `orca orchestration dispatch --inject` when you need a response. NEVER use `orca terminal send` for tasks that require results.

```bash
# WRONG — one-way, no reply possible
orca terminal send --terminal <handle> --text "Push your changes" --enter --json

# CORRECT — two-way, worker can reply
orca orchestration task-create --spec "Push changes" --json
orca orchestration dispatch --task <task_id> --to <handle> --inject --json
orca orchestration check --wait --types worker_done,escalation,question --timeout-ms 300000 --json
```

## What Each Sub-Orchestrator Should Do

1. Read its own `AGENTS.md` to understand scope
2. Read the task spec from the orchestrator (via dispatch preamble)
3. Dispatch work to agents within its project (via orchestration)
4. Send `worker_done` with outcome and files modified:
   ```bash
   orca orchestration send --type worker_done --subject "Done" --body "Summary" \
     --task-id <task_id> --dispatch-id <dispatch_id> --outcome succeeded \
     --files-modified "path/a,path/b" --json
   ```
5. Escalate if the task goes beyond its scope:
   ```bash
   orca orchestration ask --question "I need help with X" --options "yes,no" --json
   ```
