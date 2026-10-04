---
name: simple-first-dev
description: Enforce modern, user-friendly, mobile-first product design so software stays easy to learn, demo, and sell. Use when starting a new product, designing screens or features, reviewing UI complexity, or when the user wants clean sellable tools with personalization. Triggers on simple-first, keep it simple, product first, UX simplicity, sellable UI, modern design, mobile-first, widget dashboard, learnability, anti-complexity, personalization, or Elementor-style containers.
---

# Simple-First Development

## What this skill does (read this first)

This skill forces every non-trivial design or coding task to stay simple, modern, and pleasant for the end user.
It prevents crowded menus, deep navigation, and complex flows that make a product hard to learn, hard to demo, and hard to sell.

Anyone can edit or improve this skill. The rules are written in plain language on purpose.

Core idea:
- One strong Home (or primary workspace) that covers most daily work
- Navigation that matches the real needs of the project — not an arbitrary fixed number
- Most work happens through clear cards, widgets, sheets, or modals
- Users can personalize their workspace (show, hide, rearrange)
- Design is modern, calm, and mobile-first
- New features must prove they do not make the product harder to learn or sell

## When to activate

Activate for:
- Starting a new project or major module
- Designing or changing any screen, menu, or navigation
- Adding a feature that touches the user interface
- Reviewing whether the UI is becoming too complex
- Preparing a demo or sales presentation
- Planning personalization or widget systems
- Choosing visual style, spacing, or mobile behavior

Do not skip this skill for small changes. Small additions often create the biggest clutter.

## Simulated agents

### Core six (mandatory for non-trivial tasks)

Each writes its own short proposal before critique.

1. Designer — architecture, information architecture, and modern visual structure
2. Implementer — concrete working solution
3. Security-Critic — security, secrets, data isolation
4. Performance-Critic — speed, perceived performance, and resource use
5. Code-Reviewer — maintainability and clean code
6. Product-UX Critic — simplicity, clarity, and real-user experience (most important for this skill)

After independent proposals, agents critique each other in writing.
Critiques must name specific risks to simplicity, learnability, mobile use, or sellability.

### Domain specialists (on-demand)

Activate only when the task touches that domain. Details in `references/domain-specialists.md`.

- Accounting specialist — money, invoices, P&L, profit definitions, periods
- Inventory specialist — stock movements, reorder point, units, negative stock policy
- Analytics specialist — charts, rankings, KPI widgets, aggregation, mobile series limits
- Retail / assortment specialist (optional) — top sellers vs top profit, category mix

Specialists add constraints before the Judge scores. Ignoring a required specialist concern lowers Correctness or Completeness.

## Judge rules

The Judge scores every proposal on these criteria (0-10 each):

Technical criteria:
- Correctness
- Safety
- Risk of file loss or data corruption
- Maintainability
- Completeness

Product criteria (required):
- Learnability in 60 seconds — can a new user understand the main action quickly?
- Navigation fit — is the number and naming of top-level items appropriate for this project and its users?
- Demo and sellability — can the product be shown to a customer without confusion?
- Mobile experience — does the design work well on phone and tablet?
- Clicks / steps to primary task — fewer is better (aim for a very short path from Home)

The Judge selects only one winning approach.
If the average of the product criteria is below 7, the proposal is rejected or must be simplified before any code is written.
Never proceed with a non-winning approach.

Present the Judge decision and the winning plan to the user before any file changes.

## UX-First Gate (must pass before coding)

Before any feature work starts, Designer + Product-UX Critic must answer in writing:

1. Where does this live? (prefer existing Home card, widget, sheet, or modal)
2. Does it need a new top-level menu item or a new page? Default answer is no. If yes, justify why it fits this project’s real workflow.
3. Can the same result be achieved with a simpler flow or by combining with an existing surface?
4. Will a first-time user still understand the product in under one minute?
5. How many steps from Home to complete the main related task?
6. How does this behave on a phone or tablet?

Only after this gate is passed may the Implementer write production code.

## Visual Prototype Gate (mandatory before real implementation)

After the user needs are understood (jobs, navigation intent, palette direction, key widgets), **do not jump to full product code**.

Build a **complete visual sample** the user can open and click through, then wait for explicit approval.

### What the prototype must include

- Real HTML/CSS (and light JS if needed for tabs, drawers, modals) — not only a description or wireframe text
- Main navigation as agreed for this project
- Home / primary workspace with the proposed layout and sample widgets
- At least the key secondary screens or panels (menus and windows the user will live in)
- Light and dark if a palette was chosen (or a clear single theme if not yet chosen)
- Mobile-width layout visible (responsive or a dedicated narrow view)
- Placeholder data that looks realistic for the domain (no empty shells only)

Preferred delivery: a small folder the user can open in a browser (for example `prototype/` with `index.html`, shared CSS, and pages or sections for each main area). A single solid multi-section HTML file is acceptable for very small scopes.

### Approval loop

1. Present the prototype path and a short note on what to click.
2. Ask the user explicitly: approve as-is, approve with listed tweaks, or reject.
3. If rejected or major changes requested → revise the prototype and show again. Do not start backend or production app structure yet.
4. If approved (or approved with minor tweaks) → lock the visual direction in the decision log, apply tweaks, then continue implementation matching the prototype.

### Rules

- No production feature implementation until the Visual Prototype Gate has an explicit user approval in the current conversation.
- The prototype is throwaway-friendly but should be faithful enough that production UI follows it.
- Keep prototype code separate from production paths when the real app already exists (e.g. `prototype/` or `artifacts/ui-prototype/`).
- See `references/visual-prototype.md` for folder shape and checklist.

## Hard product rules

### Navigation (project-appropriate, not a fixed number)

- The number of top-level menu items must be justified by the actual jobs of the users of this product.
- Prefer the smallest set that still covers frequent work without hiding important actions.
- Every top-level item must earn its place: frequent use, clear label, and no good home inside another item.
- Adding a new top-level item usually requires merging, renaming, or removing something else (delete-or-merge before add).
- Role-based visibility is encouraged — different roles can see different subsets without creating extra menus for everyone.
- Record the chosen navigation structure and the reason in the decision log.

### Home / primary workspace

- One strong Home (or primary workspace) should cover the majority of daily work for the main role.
- Prefer cards, widgets, bottom sheets, and modals over new full pages.
- Design for progressive disclosure — show the simple path first, keep advanced options one step away.
- Primary actions must be obvious (large, clearly labeled, easy to reach with a thumb on mobile).

### Personalization

- From day one, design the Home as a set of widget slots / containers.
- User must be able to show, hide, and ideally rearrange widgets (full drag-and-drop can come later).
- Provide a few ready presets that match real roles in the project.
- Never hard-code a fixed Home layout that the end user cannot change.
- See `references/widget-system.md`.

### Modern design standards (current best practice)

Apply contemporary product design, not outdated dense admin panels:

- Generous whitespace and clear visual hierarchy
- Readable type scale and high contrast for text
- Consistent spacing system (e.g. 4/8 pt grid)
- Soft elevation or subtle borders instead of heavy lines
- Calm color palette with one strong accent for primary actions
- Clear empty states and helpful microcopy
- Smooth, fast feedback for every important action
- Respect reduced-motion preferences when adding animation
- Support both LTR and RTL when the product language needs it
- Support light and dark themes once the project has chosen a palette

Avoid:
- Crowded tables with no breathing room
- Tiny click targets
- Low-contrast text or icons
- Decorative complexity that does not help the task

### Color system (no fixed default)

There is **no mandatory palette**. Do not apply a color set until the user has chosen one for this project.

When color is needed (new project, theme work, or first UI build):

1. Ask the user about brand constraints, industry feel, and preference (cool/warm, bold/calm, existing logo colors).
2. Propose 2–3 complete light+dark options with short pros/cons (use `references/color-system.md` only as a catalog of ideas, not as the automatic choice).
3. Wait for the user to pick or adjust.
4. Lock the chosen tokens in the project decision log and implement only that set via semantic CSS variables (`primary`, `success`, `warning`, `danger`, chart series).
5. Status meaning must stay consistent in both themes after the choice is made.

Never silently reuse a previous project’s palette.

### Analytics and inventory containers (no fixed default set)

There is **no mandatory default widget list**. Do not install a standard dashboard until the user has chosen what matters for this project.

When Home widgets or charts are in scope:

1. Ask which decisions users make daily (profit, volume, stock, cash, appointments, etc.).
2. Propose a short menu of relevant container types (ideas live in `references/analytics-widgets.md`) with why each helps.
3. Let the user pick which widgets exist, which are on by default, and which roles see them.
4. Record the choice in the decision log.

Rules that always apply after the user chooses:
- Comparing two metrics over time (e.g. sales vs purchases) belongs on one chart with a clear legend when the user wants that comparison.
- Profit widgets must not invent cost data; if cost is missing, show revenue-only and label it clearly.
- Reorder-point style alerts are only first-class if the user confirmed inventory/reorder is in scope.
- Activate Accounting, Inventory, and Analytics specialists when building the widgets the user selected.

### Mobile-first and responsive

- Design the phone layout first, then expand to tablet and desktop.
- Touch targets must be large enough for fingers (roughly 44×44 px minimum).
- Primary actions must be reachable with the thumb on common phone sizes.
- Navigation on small screens may use a bottom bar, a clean drawer, or a combination — choose what fits the project, but keep it consistent.
- Tables and dense data must degrade gracefully (cards, horizontal scroll with care, or progressive disclosure).
- Test the main flows on a real narrow viewport before calling a feature done.

### Front-end discipline

- Keep JavaScript modular. Split files before they grow past a few hundred lines.
- Every important daily action needs one clear entry point.
- Perceived performance matters: skeleton loaders, optimistic UI where safe, and fast first paint.

## Anti-complexity checklist

Flag and usually reject any proposal that does any of the following:

- Adds a top-level menu item without a clear job-to-be-done justification for this project
- Creates a new page for something that fits in a card, sheet, or modal
- Forces a multi-step flow when a single step is enough
- Hides the main daily action behind several steps
- Ignores phone and tablet behavior
- Hard-codes a Home layout the user cannot personalize
- Uses outdated dense or cluttered visual patterns without reason

## Project bootstrap rule (new projects only)

When starting from zero, **ask before assuming**:

1. Identify primary users and their top 1–3 daily jobs (confirm with the user).
2. Propose — then wait for approval on — one Home structure and a short justified top-level navigation.
3. Ask about visual direction; propose 2–3 light+dark palette options; user chooses.
4. Ask which Home containers/widgets matter; propose options from the catalog; user chooses defaults and role presets.
5. **Build a complete visual prototype** (HTML folder or equivalent) covering menus, Home, and key windows — Visual Prototype Gate.
6. Iterate the prototype until the user explicitly approves.
7. Only after approval may production implementation begin.

Do not build many modules or many pages before the core user journey feels clean and modern.
Do not apply a stock palette or a stock widget set without an explicit user choice for this project.
Do not implement the real app before the visual prototype is approved.

See `references/home-template.md` for structure ideas only.
See `references/visual-prototype.md` for how to package the sample.

## Demo and sell path

Every major version must support a short demo (about 2–3 minutes) that a non-expert can follow.

The demo must:
- Start from login or Home
- Complete the main daily task on a short path
- Show personalization (at least show/hide or switch preset)
- Work convincingly on a mobile or tablet viewport as well as desktop
- Never require explaining a maze of menus

If the current design cannot support such a demo, simplify first.

See `references/demo-script-template.md`.

## Decision log requirement

Important UX and navigation decisions must be written down (date, status, reason, rejected alternatives).

Examples that must be logged:
- Why the top-level menu has its current items and count
- Which color palette (light+dark) the user chose and why alternatives were rejected
- Which Home widgets/containers the user chose as default for each role
- Why a feature lives on Home instead of a new page
- Why a multi-step flow was accepted or rejected
- Why a particular mobile navigation pattern was chosen

## Pre-change checklist (must be green)

Before applying any non-trivial change, confirm:

- [ ] Top-level navigation is still justified by real user jobs for this project
- [ ] A new user can complete the main task without training
- [ ] Path from Home to primary task remains short
- [ ] The change does not increase visual or navigational clutter
- [ ] A simpler alternative (widget / card / sheet / modal) was considered
- [ ] Home remains personalizable
- [ ] Layout and interactions work on phone and tablet
- [ ] Visual design follows modern, calm, readable standards
- [ ] Palette in use is the one the user chose for this project (not an unspoken default)
- [ ] Home widgets in use match what the user selected for this project
- [ ] Front-end files remain modular
- [ ] Important UX decisions are in the decision log
- [ ] A short demo path still works

## Relationship to other skills

This skill protects product simplicity, modern UX, and mobile experience.
For high-safety GitHub operations (branches, backups, pull requests, destructive changes) also apply the companion skill `safe-multi-agent-github-dev`.
The two skills work together — one protects the product experience, the other protects the repository.

## How to edit or upgrade this skill

This file is intentionally plain so any team member can improve it.

Common upgrades:
- Add or remove agents
- Change score thresholds (currently product average must be ≥ 7)
- Add domain-specific notes in `references/` without hard-coding them into the core rules
- Adjust mobile or visual guidelines after real user testing
- Improve the widget system guidance

Keep the language simple. Future readers should understand the rules without extra explanation.

## Refusal conditions

Refuse to proceed and explain why when:

- The UX-First Gate was skipped
- The Judge has not selected a single winner
- The average product score is below 7 and no simplification plan exists
- A new top-level menu item is added without justification for this project’s users
- Phone/tablet behavior is ignored
- The user is about to start a new project without first locking Home + justified navigation
- A palette or default widget set is applied without an explicit choice for this project
- Production implementation starts before an explicit approval of the visual prototype
- A feature is proposed without a place on the personalizable Home or justified navigation

## Quick reference

Simple-first means:
1. Match navigation to real user jobs — do not invent arbitrary menu counts.
2. Protect one strong, personalizable Home.
3. Ask the user before locking palette and default widgets; propose options, never silent defaults.
4. After understanding the need, ship a clickable visual prototype and wait for approval before real build.
5. Force every feature through a simplicity and mobile gate.
6. Use modern, calm, readable design — not dense legacy admin UI.
7. Design mobile-first.
8. Let Product-UX Critic and the Judge reject complexity.
9. Document decisions so the next person does not repeat old mistakes.
10. Prefer cards, widgets, and sheets over new pages.

## Bundled references

These files are **catalogs and ideas**, not automatic defaults. The user chooses per project.

- `references/home-template.md` — structure ideas for Home + navigation
- `references/widget-system.md` — how personalization works
- `references/demo-script-template.md` — short sellable demo outline
- `references/modern-ui-guidelines.md` — current visual and interaction standards
- `references/color-system.md` — example light/dark palettes to propose (not auto-apply)
- `references/analytics-widgets.md` — example chart and stock containers to propose (not auto-install)
- `references/domain-specialists.md` — accounting, inventory, analytics, retail specialists
- `references/visual-prototype.md` — how to build and deliver the approval prototype
