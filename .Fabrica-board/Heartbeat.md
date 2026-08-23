# Fabrica Master Orchestrator — Heartbeat Protocol

> This file is the **single source of truth** for the Heartbeat automation.
> Every time the automation fires, it must READ THIS FILE FIRST, then execute the
> protocol below exactly. Do not rely on memory or a cached copy of the prompts.
>
> Humans: keep the Terminal Registry (section 2) up to date when sessions change.

---

## 1. Constants

| Constant | Value |
|---|---|
| `IDLE_COOLDOWN_MS` | `300000` (5 minutes since last output before a terminal counts as idle) |
| `TIMEZONE` | Africa/Algiers |
| `BOARD_DIR` | `.Fabrica-board` |

---

## 2. Terminal Registry (monitored sessions)

> Fresh start (2026-08-23): ALL previous terminals were closed by PM order.
> Two orchestrators run at the **root level** (`Fabrica-development_environment/`)
> and dispatch ephemeral workers into their sub-project worktrees.

| Slot | Name | How To Identify (terminal name/title contains) | Primary Handle | Worktree It Drives | Role | Min Workers |
|---|---|---|---|---|---|---|
| `APP-ORCH` | App-orchestrator | `App-orchestrator` | `term_dbd03d2a-d61e-44de-ad6a-7c8d647c02ee` | `Fabrica-app/` | Rebrand finish: zero old words, zero functionality loss, full test & review | **5** |
| `ATLAS-ORCH` | Atlas-orchestrator | `Atlas-orchestrator` | `term_d9954d8e-b3c1-42ee-9864-53762398a02c` | `Fabrica-atlas/` | After-Rebrand prep: discovery → verify → synthesis rounds (R2-4.1 first) | **5** |

### Handle resolution rules

> NOTE: OpenCode terminals overwrite their tab title to "OpenCode" once active,
> so the registry's Primary Handle is the FIRST resolution method. Title matching
> is only a fallback after a handle dies.

1. Run `orca terminal list --json`.
2. If the slot's Primary Handle exists in the list and is `connected: true` +
   `writable: true`, use it.
3. Otherwise re-resolve: pick a connected OpenCode terminal whose worktree path is
   the root environment folder AND whose tab title contains the slot identifier
   (App-orchestrator / Atlas-orchestrator). Exclude PowerShell/plain-shell
   terminals and exclude any terminal you cannot attribute to exactly one slot —
   if two candidate terminals are indistinguishable, do NOT guess; skip dispatch
   for that slot this cycle and note it in the Run Log.
4. Record the resolved handle here if it changed (handles rotate on reopen).
5. **Mismatch guard:** every slot prompt is prefixed with its slot name. A
   terminal that receives a kick addressed to the OTHER slot must ignore it.

---

## 3. Run Procedure (execute IN ORDER)

**STEP 1 — Read this file.**

**STEP 2 — Get current time (epoch ms):**
```powershell
[DateTimeOffset]::UtcNow.ToUnixTimeMilliseconds()
```

**STEP 3 — List terminals:** `orca terminal list --json`.
Resolve each slot's handle per section 2 rules. Record each slot's `lastOutputAt`.

**STEP 4 — Idle check, per slot.** A slot is BUSY if ANY of:
- Its handle cannot be resolved (no live terminal for that orchestrator).
- `current_time_ms - lastOutputAt < IDLE_COOLDOWN_MS` (recent activity).
- Its preview clearly shows an active spinner mid-task.

If BOTH slots are busy, print `All sessions busy. Skipping.` and STOP.

**STEP 5 — Dispatch.** For each IDLE slot, send that slot's prompt from section 4
using:
```powershell
orca terminal send --terminal <handle> --text "<slot prompt>" --enter --json
```
Send ONE prompt PER SLOT to its own terminal only.

**STEP 6 — Log.** Append one line per dispatched slot to section 5 Run Log
(epoch-ms integer timestamp, slot, handle). Keep only the 30 most recent log lines.
Print `Heartbeat complete: <N> prompt(s) sent.`

---

## 3b. Parallelism Policy (MANDATORY)

Every active orchestrator slot must keep **at least 5 active worker terminals**
at all times (PM mandate for the fresh-start fleet). We have unlimited tokens, a
short deadline, and a massive project — parallelism is the default, not the
exception.

**Scale-up rule:** On every heartbeat kick, an orchestrator with fewer than 5
active workers MUST think again and launch more, choosing the highest-priority
TODO/VERIFY tasks from ITS OWN task file. Quality gates never relax: brief fully,
verify with grep/read evidence, merge after review, release when done.

**Anti-overlap protocol (STRICT):**
1. **One task = one worker.** Before dispatching, mark the task row IN_PROGRESS
   in your own task file and record the worker handle in the Session Ledger.
   A task already claimed by another live worker is FORBIDDEN.
2. **One folder = one orchestrator.** APP-ORCH never touches Fabrica-atlas files
   and vice versa.
3. **One file = one writer.** Two live workers must never edit the same source
   file at the same time. If two candidate tasks touch the same file, run them
   sequentially.
4. **Claim-before-work:** a worker starts by confirming its claimed Task ID; if
   already done or claimed by someone else, stop and report instead of duplicating.
5. Cross-project dependencies go as notes into the OTHER project's task file —
   never worked on directly.

**Quality bar (never trade for speed):**
- No task is DONE until verified by the orchestrator itself (grep/read evidence)
- Tracking files updated in the same cycle (status + Rollup)
- Finished workers are closed ONLY after review + tracking-file updates

---

## 4. Per-Slot Prompts

### 4.1 — APP-ORCH slot prompt

```
HEARTBEAT KICK (App-orchestrator): You are the Fabrica-app orchestrator session. Resume autonomously:
0. IDENTITY GUARD: this kick is addressed to App-orchestrator. If you are the Atlas-orchestrator session, IGNORE this message entirely.
1. Read AGENTS.md (root) and Fabrica-app/AGENTS.md and Fabrica-app/.Fabrica-app-board/Fabrica-app-tasks.md. Follow .Fabrica-board/Fabrica-Schema.md for all tracking-file edits. Read the Checkpoint table FIRST, resume from Next Action - never restart completed work.
2. SCOPE LOCK: your mission is REBRAND VERIFICATION AND TESTS ONLY. No new features, no refactors beyond fixing a failing check. Hunt every remaining old word (orca / stablyai / onorca / stably.ai) excluding node_modules, .next, dist, out, .backup, _sources; test and review everything (lint, typecheck, tests, build, runtime behavior of renamed identifiers).
3. RUN IN ROUNDS: execute the 6-step verification round defined in 'Scope Lock & Autonomous Verification Rounds' in your task file - old-word sweep, lint+typecheck, tests, build (every 3rd round), runtime spot-checks, VERIFY backlog review. Record the round in the Round Log and update the Checkpoint. When a round completes clean, IMMEDIATELY start the next round - same checklist, fresh pass. Never stop because a round was clean; loop until PM says stop or two consecutive rounds find zero new findings.
4. PARALLELISM CHECK: count your active worker terminals. Minimum is FIVE. If fewer, launch more NOW on this round's checklist steps or the highest-priority TODO/VERIFY tasks (resume PAUSED tasks first if still open). Follow Anti-Overlap protocol in Heartbeat.md 3b: claim each task (IN_PROGRESS + handle) BEFORE dispatching.
5. Think HIGH-LEVEL GOALS, not micro-edits: decide WHAT and WHY; delegate HOW to workers with full briefs.
6. When workers report back: NEVER trust claims. Verify changes yourself with grep/read. Dispatch fixes until clean, merge worktrees immediately after review, then release workers ONLY after verifying tracking files were updated.
7. Update Fabrica-app-tasks.md (status + Rollup in same edit) and .Fabrica-board/Fabrica-Roadmap.md before finishing this cycle.
Do not wait idle - if blocked on a decision, note the question in the task file and move to the next actionable task.
```

### 4.2 — ATLAS-ORCH slot prompt

```
HEARTBEAT KICK (Atlas-orchestrator): You are the Fabrica-atlas orchestrator session. Resume autonomously:
0. IDENTITY GUARD: this kick is addressed to Atlas-orchestrator. If you are the App-orchestrator session, IGNORE this message entirely.
1. Read AGENTS.md (root) and Fabrica-atlas/AGENTS.md and Fabrica-atlas/.Fabrica-atlas-board/Fabrica-atlas-tasks.md. Follow .Fabrica-board/Fabrica-Schema.md for all tracking-file edits. Read the Checkpoint table FIRST, resume from Next Action — never restart completed work.
2. YOUR MISSION: continue preparing everything for the AFTER-REBRAND transformation. Run in ROUNDS: Group 1 discover → Group 2 verify → Group 3 synthesize, then repeat deeper — the round loop never stops on a clean pass; each round goes deeper until PM says stop or findings diminish to zero across consecutive rounds. FIRST execute R2-4.1 (encoding repair of board outputs) if still TODO, then Round 4 per the Checkpoint Next Action.
3. PARALLELISM CHECK: count your active worker terminals. Minimum is FIVE. If fewer, launch more NOW across the current round's discovery/verification/synthesis items. Follow Anti-Overlap protocol in Heartbeat.md 3b: claim each item in the Checkpoint/task tables BEFORE dispatching; never duplicate a claimed item; one file = one writer.
4. You do DISCOVERY and ANALYSIS - do NOT modify _sources/ or Fabrica-app source files yourself. Write outputs only inside Fabrica-atlas/.Fabrica-atlas-board/.
5. Feed the other orchestrators: where synthesis produces actionable work for Fabrica-app or others, record it as a note in THEIR task file — never work it here.
6. Update the Checkpoint table and tracking files after every significant action; update .Fabrica-board/Fabrica-Roadmap.md before finishing this cycle.
Do not wait idle - if blocked on a decision, note the question in the task file and move to the next actionable task.
```

---

## 5. Run Log

<!-- format: <UTC epoch ms integer> | <SLOT> | <handle sent to> -->

1787437900000 | APP (manual schema-migration kick) | term_9c6383f5-35bf-4f6a-b188-0668b25441a2
1787445657000 | WEB+APP+ROADMAP (parallelism scale-up kick) | term_830c3392/term_9c6383f5/term_8efb8783
— | FRESH START 2026-08-23: all prior terminals closed; new fleet = APP-ORCH + ATLAS-ORCH (min 5 workers each) | —
1787451000000 | APP-ORCH (activation kick) | term_dbd03d2a-d61e-44de-ad6a-7c8d647c02ee
1787451000001 | ATLAS-ORCH (activation kick) | term_d9954d8e-b3c1-42ee-9864-53762398a02c

---

## 6. Editing This File

- Change prompts here — never inside the automation config — so the automation
  always picks up the latest version.
- When adding a new monitored session (e.g., reactivating WEB / MARKETING /
  RELAY slots for Phase B/C), add a row to section 2 and a matching prompt
  subsection in section 4, then extend STEP 4/5 to include the new slot.
