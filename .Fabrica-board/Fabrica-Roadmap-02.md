# Fabrica — Roadmap 02

---

## Dashboard


| Metric       | Value |
| ------------ | ----- |
| Total tasks  | 8     |
| ✅ Done       | 0     |
| 🔶 In Review | 0     |
| ⬜ Todo       | 8     |
| 📋 Planning  | 0     |
| 🚫 Blocked   | 0     |
| 🚫 Cancelled | 0     |
| ❌ Issues     | 0     |
| Completion   | 0%    |


### Phase Progress

```
Fabrica Transformation

Group 1 — Discovery & Analysis                       ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (3 tasks) ← NEXT
Group 2 - Verify                                     ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (3 tasks)
Group 3 - Synthesis & Concept Mapping                ⬜  [░░░░░░░░░░░░░░░░░░░░] 0% (2 tasks)
```

---

## Right Now

> What's actively being tracked. Update this section as work progresses.


| What                                             | Status | Owner        | Notes                                                                                                                                    |
| ------------------------------------------------ | ------ | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Group 1: Discovery &amp; Analysis                | ⬜ Next | Orchestrator | Scan mission-control, buzz, Fabrica-app. List features, architecture, logic. Do NOT modify files. Output → `.Fabrica-board/discovery/`  |


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
| 1.1 | Scan `_sources/mission-control/` — list all features, architecture, logic, concepts, map to source | ⬜            | `.Fabrica-board/discovery/mission-control-discovery.md` |
| 1.2 | Scan `_sources/buzz/` — list all features, architecture, logic, concepts, map to source            | ⬜            | `.Fabrica-board/discovery/buzz-discovery.md`            |
| 1.3 | Scan `Fabrica-app/` — list all features, architecture, logic, concepts (do not modify files)      | ⬜            | `.Fabrica-board/discovery/fabrica-app-discovery.md`     |



---

### Group 2 - Verify

> **AFTER Group 1 completes.** Verify findings to make sure we have all context needed to go next.
>
> **WHAT THIS GROUP DOES:**
>
> - verify all discovery files are complete and accurate  


| #   | Task                                                                                                          | Status | Output File                                          |
| --- | ------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------------- |
| 2.1 | Verify mission-control discovery — all files, features, architecture accounted for                              | ⬜      | `.Fabrica-board/verify/mission-control-verify.md`    |
| 2.2 | Verify buzz discovery — all files, features, architecture accounted for                                         | ⬜      | `.Fabrica-board/verify/buzz-verify.md`               |
| 2.3 | Verify Fabrica-app discovery — all files, features, architecture accounted for                                  | ⬜      | `.Fabrica-board/verify/fabrica-app-verify.md`        |



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
| 3.1 | Analyze similarities, gaps, extensions across mission-control, buzz, and Fabrica-app                           | ⬜      | `.Fabrica-board/analysis/similarities-gaps.md`       |
| 3.2 | Define final production Fabrica architecture — complete picture of what the app should be                      | ⬜      | `.Fabrica-board/analysis/production-architecture.md` |


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
| **Current Round**      | 1                                                                                                       |
| **Current Task**       | 1.1 — Scan mission-control                                                                              |
| **Current Group**      | Group 1 — Discovery & Analysis                                                                          |
| **Phase**              | Group 1 → 2 → 3 (repeat)                                                                                |
| **Last Checkpoint**    | `2026-08-21T00:00:00Z` (initial)                                                                        |
| **Last Action**        | Roadmap updated, tasks defined                                                                           |
| **Next Action**        | Begin 1.1 — scan `_sources/mission-control/` directory structure, list ALL features, architecture, logic |
| **Verification Pass**  | 0 (within current round)                                                                                |
| **Hours Elapsed**      | 0                                                                                                       |
| **Files Modified**     | `Fabrica-Roadmap-02.md`                                                                                 |


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
| 1     | 0    | 0          | 0            | 0                    | —          | Pre-start |
| 1     | 1    | —          | —            | —                    | —          | Pending   |
| 1     | 2    | —          | —            | —                    | —          | Pending   |


### Source Repo Scan Log

> Track which source directories have been fully scanned and documented.


| Source Repo     | Directory           | Files Counted | Files Documented | Status        |
| --------------- | ------------------- | ------------- | ---------------- | ------------- |
| mission-control | `/`                 | —             | —                | ⬜ Not started |
| buzz            | `/`                 | —             | —                | ⬜ Not started |
| Fabrica-app     | `/src/`             | —             | —                | ⬜ Not started |



---

## Session Ledger

> Roadmap 2 sessions. Master ledger .

### Worker Sessions (ephemeral — released after review)


| Name                   | Session             | Parent Orchestrator | Task                          | Status       | Worktree Merged |
| ---------------------- | ------------------- | ------------------- | ----------------------------- | ------------ | --------------- |



---

*Last updated: Aug 2026*