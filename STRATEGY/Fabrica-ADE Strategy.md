# Fabrica: Rebranding &amp; Strategic Roadmap

## 1. Product Positioning &amp; Core Architecture

**Fabrica** is a local desktop application built directly on top of the open-source MIT-licensed **Orca** (`stablyai/orca`) codebase. see `Fabrica-IDE.md` for the Product high-level Details. 

- **Brand Assets &amp; Aesthetic Alignment**:
  - **Visual Palette**: Inspired by the aesthetic of the app in `Fabrica-ADE/old-fabrica`.
  - **Core Brand Logo**: ICON located at  `Fabrica-ADE/fabrica-logo_icon.ico`, SVG lacated at `Fabrica-ADE/fabrica-logo_icon.svg`

---

## 2. Rebranding &amp; Infrastructure Foundation - Planning:

### Foundation &amp; Rebranding

#### Planning :

1. creat a new [VisualPalette-plan.md](http://VisualPalette-plan.md) and goo depeer in the old-fabrica/ and extract everything into this file.
2. rename  [VisualPalette-plan.md](http://VisualPalette-plan.md) to  [VisualPalette-migration_plan.md](http://VisualPalette-plan.md)
3. Go depeer in the orca/ app and see what need to be updated to matches, like all **Brand Asset Integration, Color Palette Alignment ..**  
and update [VisualPalette-migration_plan.md](http://VisualPalette-plan.md) with findings.
4. creat a new [configs-migration_plan.md](http://VisualPalette-plan.md) and goo depeer orca/ app and see what need to be updated to matches, like all **Metadatas &amp; Distribution Configs**

#### Exexution :

1. impliment [VisualPalette-migration_plan.md](http://VisualPalette-plan.md) then do a **Clean Build Verification.**
2. **impliment** [configs-migration_plan.md](http://VisualPalette-plan.md) then do a **Clean Build Verification.**

### Infrastructure

#### Planning : in a new Infrastructure-migartion_plan.md, plan to :

1. **Telemetry Sanitization**: replace `stablyai` upstream analytics calls with Fabrica servers.
2. **Auto-Updater &amp; Releases**: change the repo to (`Auto-Skiller/Fabrica-ADE`)
3. **Deep Linking Scheme**: Rename all `orca://` protocol handlers to `fabrica://`

### Verify if we maked all the orca app our own so we can go further ?

## 3.  Interactive Agentic UI &amp; Bussines-First Upgrade - Planning:

Currently, the app is for Coding-First, it can run some agentic tasks and busines tasks but a Founder need to have some technical backgrounds and some agentic experience, we need to turn it to something where a user can controll everything without touching the cli or writhing code, everything from the ui, where he can Draft, plan, execute, verify -- assign tasks, orchestrate and supervise,  define multi-agent crews (Researchers, Developers, Marketers, Business Analysts) on 24/7 Autonomy and Scale.



### Agentic UI &amp; Bussines layers - Planning:

- am thinking about others repos/projects like Power BI and others for **Data Visualization &amp; Interactive Dashboards**
- also we need some **Business Intelligence** projects, 
- 



&nbsp;

&nbsp;

`mission-control` **- Planning:**

in order to impliment those new features, we will get inspired by another repo `Auto-Skiller/Fabrica-ADE/mission-control` but this repo is under  [**AGPL-3.0 license]** 

1. **the only method that reliably avoids derivative-work status:**

one Agent reads the original codesource and writes multiple functional specs for all features (what it does, not how), and a separate Agent who never saw the source code implements that spec independently, Treat Mission Control as a product spec (task model, agent crew, daemon behavior) rather than a code source.

This is expensive and slow, but it's the real thing companies do (e.g., how BIOS clones were legally built in the 80s), More work up front, zero license entanglement.

2. **Reimplement the business layer:** 
then we add, ewmove, audit features form thsoe specs and figure out how we should upgrade Fabrica's business layer without corrupting any existing features and how each feature should look like, where it should be, how it interact and link with everything else ...



&nbsp;