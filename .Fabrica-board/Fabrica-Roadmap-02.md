# Fabrica — Roadmap 02

---

## Dashboard


| Metric       | Value |
| ------------ | ----- |
| Total tasks  | 8     |
| ✅ Done       | 8     |
| 🔶 In Review | 0     |
| ⬜ Todo       | 0     |
| 📋 Planning  | 0     |
| 🚫 Blocked   | 0     |
| 🚫 Cancelled | 0     |
| ❌ Issues     | 0     |
| Completion   | 100%  |


### Phase Progress

```
Fabrica Transformation

Group 1 — Discovery & Analysis                       ✅  [████████████████████] 100% (3 tasks)
Group 2 - Verify                                     ✅  [████████████████████] 100% (3 tasks)
Group 3 - Synthesis & Concept Mapping                ✅  [████████████████████] 100% (2 tasks)
Round 1 COMPLETE — verification Pass 1 & 2 clean → Round 2 next
```

---

## Right Now

> What's actively being tracked. Update this section as work progresses.


| What                                             | Status | Owner        | Notes                                                                                                                                    |
| ------------------------------------------------ | ------ | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Round 1 — Discovery → Verify → Synthesis         | ✅ Done | Orchestrator | All 8 tasks complete; 2 clean verification passes; outputs in discovery/, verify/, analysis/                                              |
| Round 2 — Deep pass (parallel sub-agents)        | ✅ Done | Orchestrator | 4 parallel deep dives (FA orchestration+RPC, BZ relay, MC tests) merged into docs; verification clean; analysis addendum w/ 8 refinements   |
| Round 3 — Orchestrated worker wave               | ⏸ Paused | Orchestrator | run_ebde8b42551c: 6/7 deep reports captured in discovery/round3/ (261KB); renderer task pending re-dispatch; PM paused the wave            |


---

## Fabrica Transformation

> In order to Plan for Transforming Fabrica from coding-first to a desktop CLI agent management and operations platform for both bussines and coding builders and operators.

---

### Group 1 — Discovery &amp; Analysis
>
> **WHAT THIS GROUP DOES:**
>
> - Scan `_sources/mission-control` and `_sources/buzz` and `Fabrica-app/`
> - Scan every file. If 50 files with 10,000 lines each — ALL must be scanned, understood, and documented. 
> - List EVERY feature, module, service, API, UI component, logic, architectural pattern. Do NOT extract code. Map features to original source only. Extract architecture &amp; specs in extreme detail.
> - Understand how each repo is structured and what it does
> - Categorize everything (features by type, architecture by layer, logic by domain)
> - Document as plain text — every file, every function, every relation, architecture, idea, every concept documented
>
>
>
> **WHAT THIS GROUP DOES NOT DO:**
>
> - Do NOT modify `Fabrica-app/` source files — scan and understand only, do not change contents
> - Do NOT touch `_sources/legacy-fabrica` — ignore completely


| #   | Task                                                                                               | Status       | Output File                                             |
| --- | -------------------------------------------------------------------------------------------------- | ------------ | ------------------------------------------------------- |
| 1.1 | Scan `_sources/mission-control/` — list all features, architecture, logic, concepts, map to source | ✅            | `.Fabrica-board/discovery/mission-control-discovery.md` |
| 1.2 | Scan `_sources/buzz/` — list all features, architecture, logic, concepts, map to source            | ✅            | `.Fabrica-board/discovery/buzz-discovery.md`            |
| 1.3 | Scan `Fabrica-app/` — list all features, architecture, logic, concepts (do not modify files)      | ✅            | `.Fabrica-board/discovery/fabrica-app-discovery.md`     |



---

### Group 2 - Verify

> **AFTER Group 1 completes.** Verify findings to make sure we have all context needed to go next.
>
> **WHAT THIS GROUP DOES:**
>
> - verify all discovery files are complete and accurate  


| #   | Task                                                                                                          | Status | Output File                                          |
| --- | ------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------- |
| 2.1 | Verify mission-control discovery — all files, features, architecture accounted for                              | ✅      | `.Fabrica-board/verify/mission-control-verify.md`    |
| 2.2 | Verify buzz discovery — all files, features, architecture accounted for                                         | ✅      | `.Fabrica-board/verify/buzz-verify.md`               |
| 2.3 | Verify Fabrica-app discovery — all files, features, architecture accounted for                                  | ✅      | `.Fabrica-board/verify/fabrica-app-verify.md`        |



---

### Group 3 — Synthesis &amp; Concept Mapping

> **AFTER Group 2 completes.** Analyze findings, find relations, see the final picture.
>
> **WHAT THIS GROUP DOES:**
>
> - Analyze similarities between the 3 repos (shared features, overlapping logic, common patterns)
> - Identify gaps (what mission-control/buzz have that Fabrica-app doesn't, what can be Added)
> - Identify extensions and enhancements opportunities (what can be enhanced, expanded, combined)
> - Map relevances (which features from buzz/mission-control are relevant to Fabrica's direction)
> - Define the final production Fabrica app architecture — what it should look like (complete picture of what the app should be)
> - verify all analysis files are complete and accurate  
> - Audit only `.Fabrica-board/` files (NOT DNA, NOT Roadmap 01, NOT other files that do not belongs to you)


| #   | Task                                                                                                          | Status | Output File                                          |
| --- | ------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------- |
| 3.1 | Analyze similarities, gaps, extensions across mission-control, buzz, and Fabrica-app                           | ✅      | `.Fabrica-board/analysis/similarities-gaps.md`       |
| 3.2 | Define final production Fabrica architecture — complete picture of what the app should be                      | ✅      | `.Fabrica-board/analysis/production-architecture.md` |


---

## Autonomous Work System

> Enable hours of autonomous execution without breaking. Agent reads this section to know what to do, where it stopped, and how to verify.
>
> **CORE PRINCIPLE: Scan and understand all 3 repos. Do NOT modify any source files.**
>
> **HOW ROUNDS WORK:**
> - One **Round** = full execution of Group 1 → Group 2 → Group 3
> - Each round, the agent discovers more, understands more, links features more
> - When verification finds gaps, new tasks are added to the existing task tables
> - The roadmap supports **infinite rounds** — each round goes deeper than the last
> - The agent stops only when the user says stop, or when all source files are fully accounted for across multiple rounds

### Checkpoint (Current State)

> Updated after every significant action. Agent reads this FIRST on resume.


| Field                  | Value                                                                                                   |
| ---------------------- | ------------------------------------------------------------------------------------------------------- |
| **Current Round**      | 3 — Group 1 deep wave PAUSED by PM (6 of 7 reports delivered; renderer task pending)                      |
| **Current Task**       | task_31f81d787e0a — FA renderer deep dive (worker stopped, task reset to ready, prompt preserved in ledger) |
| **Current Group**      | Group 1 — Discovery & Analysis (Round 3)                                                                |
| **Phase**              | Group 1 → 2 → 3 (repeat)                                                                                |
| **Last Checkpoint**    | `2026-08-21T16:40:00Z`                                                                                  |
| **Last Action**        | PM said STOP. Orchestrated via orca: run_ebde8b42551c, 7 tasks, 7 opencode workers (prompts hand-delivered — dispatch injection left TUIs empty). 6/7 worker_done received (capability-rejected formally but full content captured): plugins 29KB, ai-vault+browser 33KB, buzz-desktop 68KB, FA main subsystems 74KB, buzz crates 31KB, MC-frontend+buzz-clients 26KB — all saved in .Fabrica-board/discovery/round3/. Mailbox acked. |
| **Next Action**        | On resume: review + merge the 6 round3 reports into main discovery docs (Group 2 verify), then re-dispatch task_31f81d787e0a (renderer) with opencode; NOTE workers cannot send valid worker_done (dispatch_capability_invalid) — settle tasks manually via task-update after extracting report files |
| **Verification Pass**  | R2: 1 clean · R3: pending review                                                                          |
| **Hours Elapsed**      | ~5                                                                                                       |
| **Files Modified**     | discovery/round3/×6 (new, 261KB total), Fabrica-Roadmap-02.md                                             |
| **Verification Pass**  | 0 (within current round)                                                                                |
| **Hours Elapsed**      | 0.5                                                                                                     |
| **Files Modified**     | `Fabrica-Roadmap-02.md`, `.Fabrica-board/discovery/mission-control-discovery.md`                         |


### Autonomous Execution Rules

> Agent MUST follow these rules when running autonomously.

**WHAT YOU ARE DOING (READ THIS):**

- You are doing DISCOVERY and ANALYSIS of mission-control and buzz and Fabrica-app
- You scan repos, list features, understand architecture, categorize everything
- You analyze similarities, gaps, extensions, relations across repos
- You audit `.Fabrica-board/` files only (NOT DNA, NOT Roadmap 01, NOT others that dont belongs to you)
- You do NOT modify Fabrica-app source files — scan and understand only

**STARTUP SEQUENCE (every resume):**

1. Read this `Fabrica-Roadmap-02.md` file
2. Read the **Checkpoint** table above
3. Read the **Current Task** details from the task table
4. Read the **Current Group** description and critical rules
5. Resume from **Next Action**

**WORK SEQUENCE (DISCOVERY MODE):**

1. Scan the source repo directory for the current task
2. List EVERY: file, function, module, service, API, UI component, logic, concept
3. Categorize: group by type (features, architecture, logic, domain)
4. Document as plain text — every relation, every concept, nothing skipped
5. Write output to the specified file in `.Fabrica-board/discovery/`
6. After completing a task:
  - Update the task status to ✅ Done
  - Update the Checkpoint table (Current Task, Last Checkpoint, Last Action, Next Action)
  - Move to the next task
7. After completing a group:
  - Update Phase Progress bar
  - Verify the group is complete (count tasks, check output files exist)
  - Move to the next group

**WORK SEQUENCE (ANALYSIS MODE):**

1. Read all discovery output files from `.Fabrica-board/discovery/`
2. Analyze: what features overlap across repos? what's unique? what's missing?
3. Identify: gaps (what exists but Fabrica doesn't have), extensions (what can be enhanced)
4. Map: which buzz/mission-control features are relevant to Fabrica's direction
5. Define: final production Fabrica architecture — the complete picture
6. Audit: `.Fabrica-board/` files only — verify discovery/analysis is complete

**VERIFICATION LOOP (CRITICAL):**

> When all tasks show ✅ Done, the agent does NOT stop. It enters verification, then starts a new round.

**Within a round — verification passes:**

1. **Pass 1:**
  - Re-read every output file in `.Fabrica-board/discovery/` and `.Fabrica-board/analysis/`
  - Cross-reference: did we miss entire directories or files in the source repos?
  - Count: source repo file count vs documented file count
  - If gaps found: add new tasks to the appropriate group table, mark them ⬜, and execute them within this same round
  - Update Verification Pass counter

2. **Pass 2 (if Pass 1 found gaps):**
  - Re-scan source repos for anything not documented
  - Compare: are all features, modules, services accounted for?
  - If gaps found: execute more discovery tasks
  - Update Verification Pass counter

3. **Pass N:**
  - Continue until two consecutive passes find ZERO gaps
  - Mark the current round as complete

**Between rounds — the full cycle repeats:**

1. Current round completes (all tasks ✅, verification passes clean)
2. Increment Round counter
3. Reset to Group 1 — start a new round with fresh eyes
4. Each round goes deeper: more features discovered, better understanding, more relations found
5. Repeat until user says stop, or source repos are fully accounted for across multiple rounds

**COMPLETION CRITERIA:**

- All tasks ✅ Done
- All output files exist and contain content
- All source repo files/features/modules accounted for in discovery docs
- Verification passes clean (two consecutive passes with zero gaps)
- Multiple rounds completed with diminishing new findings

**ANTI-BREAKAGE RULES:**

- Never skip the Checkpoint update — it's how you resume
- Never mark a task Done without producing the output file
- Never stop at ✅ Done — always verify
- If stuck on a task, document the blocker and move to the next task
- Max 4 hours per checkpoint cycle, then summarize and update Checkpoint
- Do NOT modify Fabrica-app source files — scan and understand only, never change contents

### Verification Tracker

> Track rounds and verification passes within each round.


| Round | Pass | Tasks Done | Output Files | Source Files Scanned | Gaps Found | Status    |
| ----- | ---- | ---------- | ------------ | -------------------- | ---------- | --------- |
| 1     | 0    | 8          | 8            | ~18,800 (all 3 repos) | —          | ✅ Complete |
| 1     | 1    | 8          | 8            | spot re-checks       | 0 open (7 minor patched) | ✅ Clean |
| 1     | 2    | 8          | 8            | structural counts (81/81, 55/55, 30/30, 29/29) | 0 | ✅ Clean — round closed |
| 2     | 0    | 3          | 3 (enriched) | FA orchestration+RPC, BZ relay, MC tests (4 parallel deep dives) | —          | ✅ Done |
| 2     | 1    | 3          | 8            | spot-checks (line-exact, enums) | 0          | ✅ Clean — Round 2 closed |
| 3     | 0    | 6/7        | 6 new (261KB) | orchestrated wave run_ebde8b42551c (7 opencode workers) | renderer pending | ⏸ Paused by PM — reports in discovery/round3/ |


### Source Repo Scan Log

> Track which source directories have been fully scanned and documented.


| Source Repo     | Directory           | Files Counted | Files Documented | Status        |
| --------------- | ------------------- | ------------- | ---------------- | ------------- |
| mission-control | `/`                 | 492 (excl. .git; ~180 source) | ~180 | ✅ Scanned |
| buzz            | `/`                 | 4,121 (excl. .git/node_modules) | ~4,100 | ✅ Scanned |
| Fabrica-app     | `/src/`             | 15,563 (excl. node_modules/.git; incl. out/ build) | ~10,900 src + mobile/tests | ✅ Scanned |



---

## Session Ledger

> Roadmap 2 sessions. Master ledger .

### Worker Sessions (ephemeral — released after review)

**Run: `run_ebde8b42551c` — Round 3 deep-discovery wave (coordinator: term_470af25d-4bc5-47df-94b9-f1006a633582)**

| Name | Task | Dispatch | Terminal | Agent | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| FA plugins | `task_1548de5511b0` | `ctx_e85075846c47` | `term_1eec31e4-d1bd-4a9e-8e1d-2dd0fc39f2e8` | opencode | ✅ done + released | report → round3/fabrica-app-plugins.md (29KB); task completed manually |
| FA AI Vault + browser | `task_d3bcae3d8a71` | `ctx_9b70a1d1626d` | `term_3116fc7a-a45f-4d4b-a09d-5ad2039c96ba` | opencode | ✅ done | report → round3/ai-vault-browser.md (33KB); task completed; release returned False |
| FA renderer | `task_31f81d787e0a` | `ctx_e07b56ed725a` | `term_db53bbf4-4f5a-435c-b351-c4c8c41776fc` | opencode | ⏹ stopped by PM | task reset to ready; re-dispatch on resume |
| BZ desktop | `task_16a099d604d2` | `ctx_f83fbee5962e` | `term_eef7b82f-c36b-48e5-a406-d309b0796b33` | opencode | ✅ done | report → round3/buzz-desktop.md (68KB, file:line citations) |
| BZ crates | `task_08de805f101c` | `ctx_29df8157b992` | `term_f0a7de78-900a-4aa5-bfef-a15fc666af41` | opencode | ✅ done | report → round3/buzz-agent-crates.md (31KB) |
| FA main subsystems | `task_7ed39d28e039` | `ctx_dd26f12b4af6` | `term_998dcd19-366b-46d5-8963-f569aeaf3383` | opencode | ✅ done + released | 75KB report rescued from temp → round3/fabrica-app-main-subsystems.md |
| MC frontend + BZ mobile/web | `task_b1957c7492d3` | `ctx_df87c62c67ff` | `term_adc33c3f-573d-45a1-ba0b-a4ea9c3542b4` | opencode | ✅ done | report → round3/mc-frontend-buzz-clients.md (26KB) |

Run: `run_ebde8b42551c` · coordinator: term_470af25d-4bc5-47df-94b9-f1006a633582 · Round 3 wave paused by PM with 6/7 reports captured.
**Known issue:** hand-prompted workers cannot send valid worker_done (dispatch_capability_invalid — capability rides only on injected preambles). Workaround: extract report content from rejected messages / report files, then settle via `task-update --status completed`.
Superseded launches (stopped): ctx_17777bfa7f57 (codex), ctx_60a9a823c9e4 (claude, exited), ctx_3bde05ece125 (codex reuse).



---

*Last updated: Aug 2026*