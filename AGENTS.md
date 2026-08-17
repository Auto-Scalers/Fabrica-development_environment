# Fabrica — Orchestrator (AGENTS.md)

## What This Folder Is

This is the **top-level Fabrica development environment** — it coordinates across 3 sub-projects that each have their own repo, agent instructions, and planning docs.

You are the **orchestrator**. You manage cross-folder decisions, prioritize work, and ensure the 3 sub-projects stay aligned.

## The 3 Sub-Projects

| Folder | What It Does | Agent Instructions | Worktree ID |
|--------|-------------|-------------------|-------------|
| `Fabrica-app/` | Desktop app (Electron, forked from Orca) | `Fabrica-app/AGENTS.md` | `fb6b9ddc-b91a-42f2-bd3d-22fc14e9853a::C:/Users/BAB AL SAFA/Desktop/Fabrica-development_environment/Fabrica-app` |
| `Fabrica-web/` | Landing page (Next.js, fabrica-ai.vercel.app) | `Fabrica-web/AGENTS.md` | `cddb258f-edbe-4bae-b207-a7713e4eb3a2::C:/Users/BAB AL SAFA/Desktop/Fabrica-development_environment/Fabrica-web` |
| `Fabrica-marketing/` | Marketing assets, copy, launch materials | `Fabrica-marketing/AGENTS.md` | `6f298adc-e33d-42de-942f-f68caafd905c::C:/Users/BAB AL SAFA/Desktop/Fabrica-development_environment/Fabrica-marketing` |

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

## How to Work With Sub-Folders

You never directly touch sub-folder files. Instead:

1. **Dispatch a task** to the sub-orchestrator via orchestration
2. **Wait for results** (worker_done, escalation, question)
3. **Process the result** and decide next steps
4. **Repeat** until all work is done

Each sub-orchestrator reads its own `AGENTS.md` to understand its scope, then dispatches work to agents within its project.

## Rules

- **User is a Product Manager, not an engineer.** Keep explanations simple. Source of truth is reading the code, not memory.
- **We are rebranding from Orca to Fabrica.** We have 0 users, so we can rename freely without breaking anything.
- **Keep the same stack as Orca.** Edits and additions, not massive refactors. Don't corrupt what already works.
- **Never touch `.backup/` or `_sources/`** — those are frozen reference copies.
- **Never directly edit sub-folder files.** Always dispatch through orchestration.

## Roadmap

The top-level roadmap lives at `.Fabrica-Board/Fabrica-Roadmap.md`. It tracks:
- Product positioning and architecture
- Rebranding progress (Orca → Fabrica)
- What's been done, what's in progress, what's blocked

Read it to understand current priorities before making cross-folder decisions.

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
