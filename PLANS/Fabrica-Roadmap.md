# Fabrica: Rebranding &amp; Strategic Roadmap

## 1. Product Positioning &amp; Core Architecture

**Fabrica** is a local desktop application built directly on top of the open-source MIT-licensed **Orca** (`stablyai/orca`) codebase. see `Fabrica.md` for the Product high-level Details. 

- **Brand Assets &amp; Aesthetic Alignment**:
  - **Visual Palette**: Inspired by the aesthetic of the app in `Fabrica-ADE/old-fabrica`.
  - **Core Brand Logo**: ICON located at  `Fabrica-ADE/fabrica-logo_icon.ico`, SVG lacated at `Fabrica-ADE/fabrica-logo_icon.svg`

---

## 2. Rebranding &amp; Infrastructure Foundation - Planning:

### Foundation &amp; Rebranding

#### Planning :

1. creat a new [VisualPalette-plan.md](http://VisualPalette-plan.md) and goo depeer in the old-fabrica/ and extract everything into this file.
2. rename  [VisualPalette-plan.md](http://VisualPalette-plan.md) to  [VisualPalette-migration_plan.md](http://VisualPalette-plan.md)
3. Go depeer in the orca/ app and see what need to be updated to matches, like allÂ **Brand Asset Integration,Â Color Palette Alignment ..**  
and update [VisualPalette-migration_plan.md](http://VisualPalette-plan.md) with findings.
4. creat a new [configs-migration_plan.md](http://VisualPalette-plan.md) and goo depeerÂ orca/ app and see what need to be updated to matches, like allÂ **Metadatas &amp; Distribution Configs**

#### Exexution :

1. implimentÂ [VisualPalette-migration_plan.md](http://VisualPalette-plan.md)Â then do aÂ **Clean Build Verification.**
2. **impliment**Â [configs-migration_plan.md](http://VisualPalette-plan.md)Â then do aÂ **Clean Build Verification.**

### Infrastructure

#### Planning : in a new Infrastructure-migartion_plan.md, plan to :

1. **Telemetry Sanitization**: replace `stablyai` upstream analytics calls with Fabrica servers.
2. **Auto-Updater &amp; Releases**: change the repo to (`Auto-Scalers/Fabrica`)
3. **Deep Linking Scheme**:Â Rename allÂ `orca://` protocol handlers toÂ `fabrica://`

### Verify if we maked all the orca app our own so we can go further ?

## 3.  Interactive Agentic UI &amp; Bussines-First Upgrade - Planning:

Currently, the app is for Coding-First, it can run some agentic tasks and busines tasks but a Founder need to have some technical backgrounds and some agentic experience, we need to turn it to something where a user can controll everything without touching the cli or writhing code, everything from the ui, where he canÂ Draft, plan, execute, verify -- assign tasks, orchestrate and supervise,Â  define multi-agent crews (Researchers, Developers, Marketers, Business Analysts)Â on 24/7 Autonomy and Scale.



### Agentic UI &amp; Bussines layers - Planning:

- am thinking about others repos/projects like Power BI and others forÂ **Data Visualization &amp; Interactive Dashboards**
- also we need someÂ **Business Intelligence**Â projects,Â 
- 



&nbsp;

&nbsp;

`mission-control`Â **- Planning:**

in order to impliment those new features, we will get inspired by another repo `Auto-Scalers/Fabrica/mission-control` but this repo is under  [**AGPL-3.0 license]** 

1. **the only method that reliably avoids derivative-work status:**

one AgentÂ reads the original codesource and writes multiple functional specs for all features (what it does, not how), and a separate Agent who never saw the source code implements that spec independently, Treat Mission Control as a product spec (task model, agent crew, daemon behavior) rather than a code source.

This is expensive and slow, but it's the real thing companies do (e.g., how BIOS clones were legally built in the 80s), More work up front, zero license entanglement.

2. **Reimplement the business layer:** 
then we add, ewmove, audit features form thsoe specs and figure out how we should upgrade Fabrica's business layer without corrupting any existing features and how each feature should look like, where it should be, how it interact and link with everything else ...

we can check [https://github.com/vercel-labs/](https://github.com/vercel-labs/)

---

## Open blockers / follow-ups — revisit later (Aug 2026)

Carried over from `STRATEGY/infra-migration_plan.md` §11.6. Nothing here blocks the current desktop-first planning:

1. **Domain/website** — `fabrica.dev` (and `api.`, `relay.`, `update.`, `share.`, `login.` subdomains) NOT yet acquired. Until owned, Fabrica telemetry/diagnostics/docs endpoints must stay on `onorca.dev` or a placeholder.
2. **Code signing** — new Apple Developer ID + notarization cert (macOS) and Windows SignPath `orca`→`fabrica` slug. Longest lead time (Apple approval takes days); start early, in parallel.
3. **GitHub repos to create (instant)** — `Auto-Scalers/Fabrica-hourly`, `-daily`, `-adhoc`, `fabrica-plugins`, `fabrica-portuguese`, `fabrica-multipass-recipes`, `fabrica-navigation-shortcuts`.
4. **App Store / distribution** — new iOS App Store record + Android channel (current ones belong to stablyai). Out of desktop-first scope.
5. **Plugin publisher migration** — re-sign `stablyai.orca-*` plugins under Fabrica publisher (§11.1 / identifier-rename item 03).
6. **Mobile backend** — Firebase/push ownership, only if the mobile app is in scope.
7. the needed Fabrica support email/URL from [06-git-coauthor-trailer.md](http://06-git-coauthor-trailer.md)
8. the needed appId from 07-app-name-and-menu



&nbsp;

- actualy we changed the repo to : '[https://github.com/Auto-Scalers/Fabrica-app](https://github.com/Auto-Scalers/Fabrica-app)' (where we will have the Fabrica source code - it empty we didnt push yet), and the landing page is aready live in '[https://fabrica-ai.vercel.app/](https://fabrica-ai.vercel.app/)'.

  See what need to be updated across all the sourcecode (we should not lose any fonctionalities).
- 
- continue implementing the remaining items
- 
- what about that  /usr/bin/orca GNOME's screen reader, what is it, is it comes build in with the linux, it it from the codebase, is it an external thing ?
- some features need a login , like the phone and canvas
- making sure everyhting ok, the rebranding is fully done
- 
- github repos, Fabrica-app / Fabrica-web / Fabrica-DE and links those 2
- 
- UI/UX Layer - Business first with 
- agents, skills and plugins



&nbsp;