---
name: simple-first-dev
description: Enforce modern, user-friendly, mobile-first product design so software stays easy to learn, demo, and sell. On existing codebases, first inventory all real capabilities, multi-agent strengths/weaknesses, and user Keep/Drop/Defer choices before any prototype. Use when starting or redesigning a product, simplifying UI, reviewing complexity, or personalization. Triggers on simple-first, keep it simple, product first, UX simplicity, sellable UI, modern design, mobile-first, capability inventory, redesign existing app, or Elementor-style containers.
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
- On existing products, **never redesign by forgetting** real capabilities (print, Telegram, export, returns, backup, etc.)

## Ordered pipeline (do not skip steps)

Work in this order for non-trivial UI or product work:

| Step | Gate | Stop for user? |
|------|------|----------------|
| 0 | **Capability Inventory** (if code/docs exist) | Yes — Keep / Drop / Defer |
| 1 | Jobs + navigation intent + roles | Yes if unclear |
| 2 | Color / theme direction | Yes — user picks palette |
| 3 | Home widgets / containers | Yes — user picks set |
| 4 | **UX-First Gate** (written answers) | Internal + show summary |
| 5 | **Visual Prototype Gate** (clickable HTML) | Yes — Approve / Tweaks / Reject |
| 6 | **Mobile Acceptance** on the prototype | Yes if mobile is broken |
| 7 | Production implementation matching prototype | Only after approval |
| 8 | Decision log update | Always |

Skipping Capability Inventory on an existing codebase, or shipping a prototype that omits a Keep capability, is a skill failure.

## When to activate

Activate for:
- Starting a new project or major module
- Redesigning or specializing an existing product
- Designing or changing any screen, menu, or navigation
- Adding a feature that touches the user interface
- Reviewing whether the UI is becoming too complex
- Preparing a demo or sales presentation
- Planning personalization or widget systems
- Choosing visual style, spacing, or mobile behavior

Do not skip this skill for small changes. Small additions often create the biggest clutter.

## Existing-Project Capability Inventory Gate (mandatory when code exists)

When the workspace already has application code, models, routes, pages, or product docs, **do not jump to a simplified UI or prototype**.

Order of work:

1. **Inventory** — extract real capabilities from API routes, models, front panels, JS modules, decision logs, and integrations (print, Telegram, export, backup, returns, payroll, webhooks, etc.).
2. **Multi-agent analysis** — use the core agents plus safe-multi-agent-github-dev style critique; activate domain specialists when money, stock, clinic/treatment, or analytics are involved.
3. **Strengths and weaknesses** — present a short, honest list to the user.
4. **Capability table** — every found capability with Status (Working / Partial / Placeholder) and a suggested Keep / Drop / Defer.
5. **User choice** — stop and ask which capabilities to Keep, Drop, or Defer. Do not assume.
6. Only after the user answers → continue the pipeline **using the Keep set only**.

Rules:

- The next prototype must surface **every Keep** capability (button, panel, settings section, or progressive disclosure). Missing a Keep item is a failed prototype.
- Never silently Drop an existing capability. Drop requires explicit user confirmation.
- Full procedure and table format: `references/capability-inventory.md`.
- Greenfield products with no prior code may skip this gate.

### Integration completeness checklist (run during inventory)

Always search the codebase for these families and list them if present:

- Auth (login, logout, roles, membership)
- Print / PDF / sheet output
- Messaging bots (Telegram, etc.) and webhooks
- File export (Excel, CSV)
- Backup / restore
- Returns, voids, cancellations
- Notifications
- Multi-tenant or multi-business controls
- Domain-specific catalogs (allergies, medications, services, stock)

If a family exists in code and the user did not Drop it, the prototype and production UI must expose it.

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
- Clinic / treatment specialist (optional) — admission, patient record, appointments, clinical safety fields

Specialists add constraints before the Judge scores. Ignoring a required specialist concern lowers Correctness or Completeness.

## Judge rules

The Judge scores every proposal on these criteria (0-10 each):

Technical criteria:
- Correctness
- Safety
- Risk of file loss or data corruption
- Maintainability
- Completeness (includes every Keep capability from inventory)

Product criteria (required):
- Learnability in 60 seconds
- Navigation fit
- Demo and sellability
- Mobile experience
- Clicks / steps to primary task

The Judge selects only one winning approach.
If the average of the product criteria is below 7, the proposal is rejected or must be simplified before any code is written.
Never proceed with a non-winning approach.

Present the Judge decision and the winning plan to the user before any file changes.

## UX-First Gate (must pass before coding)

Before any feature work starts, Designer + Product-UX Critic must answer in writing:

1. Where does this live? (prefer existing Home card, widget, sheet, or modal)
2. Does it need a new top-level menu item or a new page? Default answer is no. If yes, justify why it fits this project real workflow.
3. Can the same result be achieved with a simpler flow or by combining with an existing surface?
4. Will a first-time user still understand the product in under one minute?
5. How many steps from Home to complete the main related task?
6. How does this behave on a phone or tablet?
7. Which Keep capabilities from inventory does this change touch, and are any at risk of being hidden?

Only after this gate is passed may the Implementer write production code.

## Visual Prototype Gate (mandatory before real implementation)

After the user needs are understood (jobs, navigation intent, palette direction, key widgets, and Keep set), **do not jump to full product code**.

Build a **complete visual sample** the user can open and click through, then wait for explicit approval.

### What the prototype must include

- Real HTML/CSS (and light JS if needed for tabs, drawers, modals)
- Main navigation as agreed for this project
- Home / primary workspace with the proposed layout and sample widgets
- At least the key secondary screens or panels
- Light and dark if a palette was chosen
- Mobile-width layout that is actually usable
- Placeholder data that looks realistic for the domain
- **Every Keep capability** visible as a control or clear entry point
- Login and logout when auth is in the Keep set

Preferred delivery: a small folder (e.g. `prototype/`) the user can open in a browser.

### Approval loop

1. Present the prototype path and what to click (desktop and mobile).
2. Ask: approve as-is, approve with listed tweaks, or reject.
3. If rejected → revise prototype only. Do not start production structure yet.
4. If approved → lock visual direction in the decision log, then implement matching the prototype.

### Rules

- No production feature implementation until explicit user approval in the current conversation.
- Keep prototype code separate from production paths when the real app already exists.
- See `references/visual-prototype.md`.

## Mobile Acceptance Gate

After the visual prototype exists, verify mobile before asking for final approval:

- Primary flows work at ~375px width without horizontal page scroll (except intentional table scroll)
- Touch targets ~44x44 px for primary actions
- Navigation is a drawer, bottom bar, or equivalent
- Forms are single-column; dense line tables become cards or labeled stacks on small screens
- Tabs can scroll horizontally without crushing labels
- Input font size mobile-safe (avoid accidental iOS zoom)

If the user reports mobile is broken, fix the prototype before any production work.

## Hard product rules

### Navigation

- Top-level menu items must be justified by real user jobs.
- Prefer the smallest set that still covers frequent work.
- Delete-or-merge before add for new top-level items.
- Role-based visibility is encouraged.
- Record navigation structure in the decision log.

### Home / primary workspace

- One strong Home covers majority of daily work for the main role.
- Prefer cards, widgets, sheets, modals over new full pages.
- Progressive disclosure: simple path first.
- Primary actions large and thumb-reachable on mobile.

### Personalization

- Home is widget slots from day one.
- User can show/hide (and ideally rearrange) widgets.
- Role presets recommended.
- See `references/widget-system.md`.

### Modern design

- Generous whitespace, clear hierarchy, high contrast text
- Soft elevation or subtle borders
- Calm palette with one strong accent
- Empty states and helpful microcopy
- LTR and RTL when needed
- Light and dark after user chooses palette

Avoid crowded tables, tiny targets, low-contrast icons, decorative noise.

### Color system (no fixed default)

Do not apply a palette until the user chooses one for this project.
Propose 2-3 light+dark options; lock tokens in the decision log.
See `references/color-system.md` as a catalog of ideas only.

### Analytics / widgets (no fixed default set)

Do not install a stock dashboard until the user chooses widgets.
See `references/analytics-widgets.md` for ideas only.

### Mobile-first

Phone layout first, then tablet/desktop.
Touch targets large enough; primary actions thumb-reachable.
Tables degrade to cards or careful horizontal scroll.

### Front-end discipline

Modular JS. Clear entry point for each daily action. Fast perceived performance.

## Anti-complexity checklist

Reject proposals that:
- Add unjustified top-level menu items
- Create a page when a card/sheet/modal suffices
- Force multi-step when one step is enough
- Hide the main daily action
- Ignore phone/tablet
- Hard-code non-personalizable Home
- Use dense legacy admin patterns without reason
- Build a simple UI that omits Keep capabilities
- Skip Capability Inventory when the codebase is available

## Project bootstrap (new projects only)

1. Confirm primary users and top daily jobs.
2. Propose Home + navigation; wait for approval.
3. Propose 2-3 palettes; user chooses.
4. Propose widgets; user chooses.
5. Build visual prototype; iterate until approval (including mobile).
6. Only then production implementation.

## Existing-product redesign rule

When specializing or simplifying an existing product:

1. Run Capability Inventory Gate first.
2. Get explicit Keep / Drop / Defer.
3. Rebuild navigation and Home around the Keep set.
4. Prototype must still expose every Keep item (including integrations).
5. Do not delete backend capabilities marked Defer without a separate explicit decision.

## Decision log

Log date, decision, why, and what was rejected/deferred for navigation, palette, Keep set, widgets, and prototype approval.

## Companion skill

Use with `safe-multi-agent-github-dev` for multi-agent critique and safe GitHub operations.

## References

- `references/capability-inventory.md`
- `references/visual-prototype.md`
- `references/domain-specialists.md`
- `references/home-template.md`
- `references/widget-system.md`
- `references/modern-ui-guidelines.md`
- `references/color-system.md`
- `references/analytics-widgets.md`
- `references/demo-script-template.md`

## Refusal conditions

Refuse when:
- Capability Inventory was skipped on an existing codebase
- UX-First or Visual Prototype gates were skipped
- Judge has no single winner or product score average is below 7 without a simplification plan
- Prototype omits Keep capabilities
- Production starts before prototype approval
- Palette or widgets applied without user choice
- Mobile behavior is ignored after a mobile failure report

## Quick reference

1. Inventory existing capabilities first; user chooses Keep/Drop/Defer.
2. Match navigation to real jobs.
3. Protect one strong personalizable Home.
4. User picks palette and widgets — no silent defaults.
5. Clickable prototype must include every Keep item; wait for approval.
6. Mobile must be usable before production.
7. Document decisions.
8. Prefer cards/widgets/sheets over new pages.
