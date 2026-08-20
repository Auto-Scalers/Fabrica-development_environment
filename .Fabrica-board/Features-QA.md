# Fabrica — Features & Marketing Q&A (Features-QA.md)

> **Deep-Dive Focus: `Fabrica-marketing/research/` & `Fabrica-marketing/brand/`**
> Comprehensive extraction of all competitive intelligence, market gaps, positioning plays, design tokens, voice frameworks, and product implications.

---

## Table of Contents
1. [Executive Readout & The Defensible Wedge](#1-executive-readout--the-defensible-wedge)
2. [Research Deep-Dive: Competitor Matrix & Exact Vulnerabilities](#2-research-deep-dive-competitor-matrix--exact-vulnerabilities)
3. [Research Deep-Dive: The 4 Market Gaps & Strategic Implications](#3-research-deep-dive-the-4-market-gaps--strategic-implications)
4. [Research Deep-Dive: Structural Pricing & The BYOK Economic Contrast](#4-research-deep-dive-structural-pricing--the-byok-economic-contrast)
5. [Brand Deep-Dive: The Digital Foundry & Command Center Metaphor](#5-brand-deep-dive-the-digital-foundry--command-center-metaphor)
6. [Brand Deep-Dive: Exact Visual Design Tokens & UI Rules](#6-brand-deep-dive-exact-visual-design-tokens--ui-rules)
7. [Brand Deep-Dive: Typography, UI Microcopy & Word Bank](#7-brand-deep-dive-typography-ui-microcopy--word-bank)
8. [Brand Deep-Dive: Messaging Hierarchy & Value Proposition Pillars](#8-brand-deep-dive-messaging-hierarchy--value-proposition-pillars)
9. [Product Translation: Core Features Derived from Research & Brand](#9-product-translation-core-features-derived-from-research--brand)
10. [Master Decision Matrix: Options, Suggestions & Priorities](#10-master-decision-matrix-options-suggestions--priorities)

---

## 1. Executive Readout & The Defensible Wedge
*(From `research/competitor-landscape.md` §Executive Readout & `brand/positioning-statement.md`)*

Fabrica will not win a generic "best AI coding assistant" contest against Cursor, Copilot, or Claude Code, nor an opaque "autonomous prompt-to-app" race against Manus or Replit.

### The Winning Territory
**"The Founder's Agent Command Center"**: A business-first, coding-capable desktop operating environment that turns a plain-language objective into a supervised crew of **Researcher, Developer, Marketer, and Analyst** agents running in isolated local workspaces, governed by hard budget caps, and verified through human approval gates.

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                               THE 3 STRATEGIC PILLARS                                   │
├──────────────────────────┬───────────────────────────┬──────────────────────────────────┤
│ 1. CONTROL WORK & BILL   │ 2. OPERATE THE BUSINESS   │ 3. PREDICTABLE ECONOMICS         │
│ Hard spend limits, auto- │ Coordinate research, GTM, │ Zero-markup BYOK: customer pays  │
│ stop conditions, visible │ marketing & BI alongside  │ providers for fuel, Fabrica for  │
│ worktrees & diff gates.  │ software engineering.     │ the factory. No token resale.    │
└──────────────────────────┴───────────────────────────┴──────────────────────────────────┘
```

---

## 2. Research Deep-Dive: Competitor Matrix & Exact Vulnerabilities
*(Extracted strictly from `research/competitor-landscape.md` §2)*

### Direct Competitors Analysis

| Competitor | Their Positioning | Core Strengths | Material Vulnerability (Fabrica Opening) |
| :--- | :--- | :--- | :--- |
| **Orca** *(Base)* | "AI Orchestrator for 100x builders" | Mature worktree engine, desktop/remote CLI, multi-agent foundations. | **Developer/CLI-first framing.** Fabrica wraps this engine in a visual, founder-friendly command center with business roles. |
| **Manus** | General-purpose autonomous browser agent | Easy "delegate and wait" prompt UX; high non-technical appeal. | **Black-box cloud execution.** No local code worktrees; credit-based usage hides true total costs; cannot inspect intermediate state. |
| **Devin** *(Cognition)* | Autonomous software engineer | Engineering benchmarks, cloud sandbox execution. | **Narrow software focus.** Lacks business operations context; "assign and wait" lacks visible step-by-step human steering. |
| **GitHub Copilot** | AI coding inside GitHub ecosystem | Massive distribution, PR/repo context, ecosystem integration. | **GitHub/developer-centric.** Does not offer a founder home screen with budget limits, business agents, or multi-role crews. |
| **Cursor / Windsurf** | AI code editor / IDE | Fast developer ergonomics, frontier model choice, editor polish. | **Code editor first.** Optimizes typing speed; does not organize business work or provide plain-language approval gates. |
| **Replit / Bolt / v0 / Lovable** | Prompt-to-web-app / vibe coding | Fast path from prompt to demo; instant cloud hosting. | **Prototype-bound with token meters.** Usage-metered credits escalate quickly; lack ongoing multi-role business operations. |
| **n8n / Zapier / Make** | Business workflow automation | Deep SaaS integrations, repeatable deterministic data pipelines. | **Lacks agentic coding engine.** Automates static pipelines rather than supervising autonomous agents working in codebases. |

---

## 3. Research Deep-Dive: The 4 Market Gaps & Strategic Implications
*(From `research/competitor-landscape.md` §3 & §4, referencing Stack Overflow 2025 Survey)*

### The 4 Unmet Market Gaps
1. **The Trust and Accountability Gap:**
   * *Data:* **84%** adoption, but **only 3%** highly trust AI output; **87%** have accuracy concerns, and **81%** have security/privacy concerns.
   * *Opportunity:* Make human approvals, visual diff inspections, and local client-side credential vaults the standard happy path.
2. **The Business-Role Gap:**
   * *Reality:* Developers know what code to write; founders need help discovering, prioritizing, building, marketing, and analyzing.
   * *Opportunity:* Pre-package multi-role agent crews (Researcher, Marketer, Analyst, Developer, Operations) in a shared context.
3. **The Cost-Governance Gap:**
   * *Reality:* Credit pools, effort multipliers, and hidden token allowances cause unexpected monthly bills.
   * *Opportunity:* Explicit pre-authorization of dollar budgets and hard auto-stops when spend reaches 100%.
4. **The Coordination Gap:**
   * *Data:* **54%** of builders use 6+ disconnected tools daily.
   * *Opportunity:* A unified command center replacing scattered tabs, spreadsheets, and chat windows.

### The 4 Strategic Imperatives for Product Development
1. **Demonstrate Controls Before Autonomy:** A visible approval gate and budget-stop workflow is more differentiated and trustworthy than an inflated benchmark claim.
2. **Provide Outcome-Driven Templates:** Templates should be business outcomes (*"Research competitor pricing, build landing page, draft launch sequence"*) rather than raw code prompts.
3. **Model Optionality (BYOK) as Insurance:** Users bring their own API keys; Fabrica is model-agnostic and never resells tokens.
4. **Design for 3 Core Buyer Segments:**
   * *Solo Founders:* Need capacity to run multiple lanes at once without getting stuck.
   * *Lean Teams:* Need to scale engineering and GTM throughput without losing code review quality.
   * *Agencies / Studios:* Need to manage isolated workspaces for multiple clients with strict budget partitioning.

---

## 4. Research Deep-Dive: Structural Pricing & The BYOK Economic Contrast
*(From `research/competitor-landscape.md` §2 & `brand/positioning-statement.md`)*

### The Pricing Model Comparison

| Product | Published Model | How Compute/Inference is Charged | The Fabrica Contrast |
| :--- | :--- | :--- | :--- |
| **Fabrica** | Solo (Free), Pro Studio, Agency/Team | **100% BYOK.** Customer supplies model keys; pays providers directly. | **Zero markup on inference.** Subscription pays for the desktop command center and controls. |
| Manus | Free / $20 / $40 / $200+ | Opaque credits | Fabrica gives exact USD cost visibility per task. |
| Cursor | Free / $20 / $40 / usage pools | Included pools + overage requests | Fabrica lets user connect any model directly (OpenRouter, DeepSeek, Local). |
| Replit | Free / $20 / $95/mo | Monthly credits + pay-as-you-go | Fabrica executes locally with zero cloud compute markups. |
| Bolt / v0 | Free / $25–$30 / Team tiers | Token allowances & credits | Fabrica enforces hard dollar caps without token throttling. |

> **Approved Pricing Punchline:** *"Fabrica does not mark up or bundle your model usage. Bring your own keys; set the budget; keep the control."*
> **Strictly Avoid:** *"No AI costs"*, *"Unlimited free agents"*, or unapproved tier price points.

---

## 5. Brand Deep-Dive: The Digital Foundry & Command Center Metaphor
*(Extracted strictly from `brand/brand-guidelines.md` §1 & §2.4)*

### The Core Metaphors
* **The Digital Foundry:** Communicates craftsmanship, raw material transforming into finished deliverables, momentum, and heat. *(Visual texture: dark slate, graphite, subtle grain, warm light source).*
* **The Command Center:** Communicates precision, situational awareness, visible state, and authority. *(Visual structure: status chips, routing diagrams, approval queues).*
* **What We Avoid:** No literal flames, anvils, steampunk gears, glowing humanoid AI brains, or neon sci-fi blobs.

### Brand Promise & Tagline
* **Tagline:** **"The Next AI Exit"** *(Defined as the operational exit: the moment a founder stops doing every task themselves and begins directing the work).*
* **Brand Promise:** **"Your business, automated. Your judgment, still in the loop."**

---

## 6. Brand Deep-Dive: Exact Visual Design Tokens & UI Rules
*(Extracted strictly from `brand/brand-guidelines.md` §2.2)*

### The Official Design Token Palette

| Token Name | Hex Value | RGB | UI Hierarchy & Usage Rule |
| :--- | :--- | :--- | :--- |
| **Forge Dark** | `#16171A` | `22 23 26` | **Dominant Background** (70–80% of UI frame). Deep obsidian dark. |
| **Forge Surface** | `#22242A` | `34 36 42` | **Panel & Card Canvas.** Task cards, modal bodies, navigation sidebars. |
| **Forge Edge** | `#343842` | `52 56 66` | **Structural Dividers.** Restrained borders, column separators, inactive strokes. |
| **Molten Orange** | `#E8590C` | `232 89 12` | **Primary Accent.** Single primary CTA per decision point, active progress bar. |
| **Molten Light** | `#FF8A3D` | `255 138 61` | **Highlight State.** Gradient start (`#FF8A3D ➔ #E8590C`), hover states, chart accents. |
| **Molten Ember** | `#B94308` | `185 67 8` | **Pressed/Active State.** Active button clicks, high-urgency alerts. |
| **Steel Gray** | `#8F939E` | `143 147 158` | **Secondary Metadata.** Timestamps, elapsed duration, token counts, model names. |
| **Steel Light** | `#C2C6CC` | `194 198 204` | **Subheaders & Quiet Text.** Card titles, body copy on dark, inactive tab labels. |
| **Steel Deep** | `#5E636D` | `94 99 109` | Inactive icons, subtle framing. |
| **Paper** | `#FAF7F0` | `250 247 240` | Exported documents, PDF reports, light-mode previews. |
| **Ink** | `#292725` | `41 39 37` | Text on Paper canvas. |

### Strict UI Color Rules
1. **The Single Orange Rule:** Molten Orange must appear **only once per decision point**. A screen with multiple orange buttons has no clear hierarchy.
2. **Text Contrast Rule:** On Forge Dark, body copy must be White or Steel Light—**never Molten Orange**.
3. **Contrast Standard:** Must pass WCAG AA contrast on all interactive elements.

---

## 7. Brand Deep-Dive: Typography, UI Microcopy & Word Bank
*(Extracted strictly from `brand/brand-guidelines.md` §2.3 & §3)*

### Typography System
* **Display / Headlines:** `Geist` (Bold 700–800), compact, declarative, sentence case.
* **Subheads & Navigation:** `Geist` (SemiBold 600).
* **Body Copy:** `Geist` (Regular 400–500), 16–18px equivalent, line length 45–75 characters.
* **Technical Evidence & Code:** `Geist Mono` (Regular 400–500) for paths, diff previews, shell outputs, and budget numbers.
* *Fallbacks:* `Arial, Helvetica, sans-serif` for Geist; `Consolas, monospace` for Geist Mono.

### Tone Spectrum by Context
* **Product / UI Tone:** Brief, calm, decisive (`"3 tasks need review."`, `"Growth audit is ready for review. Approve the plan to start the run."`).
* **Support Tone:** Patient, specific, accountable (`"That job paused at the approval gate. Here's how to resume it."`).
* **Docs Tone:** Exact, neutral, transparent (`"Each agent runs in an isolated worktree."`).

### Official Word Bank vs. Blacklist
```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  APPROVED WORD BANK (Use Freely)                                                       │
│  Direct, command center, crew, build, ship, run, review, approve, route,               │
│  visible work, workflow, worktree, guardrail, budget, checkpoint, brief,               │
│  output, momentum, capacity, operating system, founder, builder, control.               │
├────────────────────────────────────────────────────────────────────────────────────────┤
│  STRICT BLACKLIST (NEVER Use in UI or Marketing)                                       │
│  ❌ "AI-powered"    ❌ "revolutionary"    ❌ "game-changing"    ❌ "magic"              │
│  ❌ "seamless"      ❌ "effortless"       ❌ "set it & forget it" ❌ "10x faster"          │
│  ❌ "replace your team"                                                                │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 8. Brand Deep-Dive: Messaging Hierarchy & Value Proposition Pillars
*(Extracted strictly from `brand/positioning-statement.md` §Messaging Hierarchy)*

### The 5 Value Proposition Pillars
1. **More Capacity:** Put several focused jobs in motion simultaneously without serializing through one chat window.
2. **Visible Control:** See what is running, waiting, and ready for review organized as cards and deliverables, not buried in chat logs.
3. **Safer Delegation:** Human authority is structural; set approval gates, diff inspections, and budget ceilings on consequential work.
4. **Better Handoffs:** Context travels with the task brief (`Job + Constraints + Definition of Done`), preventing re-explanation.
5. **Built for Builders:** Keep deep technical detail (diffs, worktrees, git commits) available without forcing non-technical users to write code.

### The Universal Elevator Pitches
* **10 Words:** *"Fabrica lets founders direct agent crews and keep control."*
* **30 Words:** *"Fabrica is a command center for founders who need work moving in parallel—without losing visibility, approval, or control over what their agents do."*
* **60 Words:** *"Fabrica gives founders a practical way to direct specialized agents across business and coding work. Assign a clear brief, keep tasks visible, set approval gates and budgets, then review real output before it moves forward. It is built for people who want more capacity without handing over judgment—or spending their day stitching tools, chats, and spreadsheets together."*

---

## 9. Product Translation: Core Features Derived from Research & Brand

### Feature Mapping: Turning Brand & Research into Code Requirements

```
  MARKETING FINDING / BRAND RULE               PRODUCT FEATURE REQUIREMENT
  ──────────────────────────────               ───────────────────────────
  • "Direct a crew, not a chat"          ──►   Multi-Role Agent Fleet Panel (Researcher, Marketer, Analyst, Dev)
  • "Approval gates as a default"        ──►   3-Tier Automated Risk Modal (Diff + Estimated Cost + Approve CTA)
  • "Single orange decision point"       ──►   UI highlights only the single active blocking decision in Molten Orange
  • "Zero token markup BYOK"             ──►   Encrypted Client-Side Vault with real-time USD provider rate calculation
  • "Parallel work without collisions"   ──►   Auto-provisioned git worktrees per agent task
  • "Geist Mono for technical proof"     ──►   Diff viewer, shell logs, and budget lines rendered strictly in Geist Mono
  • "Stop being the coordination queue"  ──►   Visual Kanban + Eisenhower matrix with drag-and-drop state transitions
  • "Continuous work without babysitting"──►   Low-footprint local Node daemon supporting scheduled cron workflows
```

---

## 10. Master Decision Matrix: Options, Suggestions & Priorities

| Priority | Feature / Module | Exact Research / Brand Origin | Implementation Suggestion | Roadmap Group |
| :---: | :--- | :--- | :--- | :---: |
| **P0** | **Visual Mission Control UI** | `brand/brand-guidelines.md` §2<br>`research/competitor-landscape.md` §1 | Forge Dark (`#16171A`) base, Kanban board, `@dnd-kit`, 50/50 Sources/Deliverables split. | **Group A** |
| **P0** | **Multi-Role Agent Personas** | `positioning-statement.md` §2<br>`competitor-landscape.md` §2 | Specialized system prompts & tool whitelists for Researcher, Marketer, Analyst, Coder, Ops. | **Group B** |
| **P0** | **Visual Approval Gates & Diffs** | `brand-guidelines.md` §5<br>`research/competitor-landscape.md` §3 | Modal displaying Geist Mono diffs, risk tier (1–3), and single Molten Orange `#E8590C` CTA. | **Group C** |
| **P0** | **Hard Budget Caps & Live Tracker** | `positioning-statement.md` §3<br>`research/competitor-landscape.md` §2 | Real-time USD spend monitor against provider rates; auto-halts process at 100% cap. | **Group C & E** |
| **P0** | **Client-Side Encrypted BYOK Vault** | `research/competitor-landscape.md` §4 | AES-256-GCM vault with Argon2id; memory-only key injection; zero cloud storage. | **Group E** |
| **P0** | **3-Minute Non-Technical Onboarding** | `positioning-statement.md` §4 | Connect 1 key ➔ Select starter objective ➔ Launch visual demo mission. | **Group H** |
| **P1** | **Field Ops 64+ Service Connectors** | `competitor-landscape.md` §2 | Extensible TypeScript adapter framework (GitHub, Slack, Email, X, Stripe, Supabase). | **Group D** |
| **P1** | **YAML Blueprints & Background Daemon**| `research/competitor-landscape.md` §1 | Persistent Node runner with `node-cron` triggers for recurring daily/weekly briefs. | **Group F** |
| **P1** | **Mobile Companion via Relay** | `research/competitor-landscape.md` §1 | Web-based mobile oversight for push approval gates and budget alerts. | **Group G** |
| **P1** | **Watchdog Loop & Stall Detector** | `competitor-landscape.md` §3 | Heuristic monitor detecting repetitive tool errors; auto-escalates to inbox. | **Group C & F** |
| **P2** | **Business Velocity Analytics** | `brand/brand-guidelines.md` §5 | Charts (D3/Recharts) showing agent hours utilized, task completion velocity, and ROI. | **Group A** |
| **P2** | **Turnkey Starter Pack Library** | `brand/positioning-statement.md` §4 | Pre-configured workspace bundles (SaaS, E-Commerce, Agency, Newsletter). | **Group H** |
| **Anti-Goal** | ❌ **No Token Markup / Resale** | `research/competitor-landscape.md` §2 | Never resell compute; customer maintains direct provider relationship. | — |
| **Anti-Goal** | ❌ **No Cloud DB Secret Leakage** | `research/competitor-landscape.md` §4 | Always maintain local-first data isolation. | — |
| **Anti-Goal** | ❌ **No AGPL Code Copying** | Licensing Safeguards | Clean-room reimplementation of all `mission-control` concepts. | — |
