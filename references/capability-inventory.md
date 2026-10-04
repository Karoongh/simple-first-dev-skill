# Capability Inventory Gate (existing projects)

Use this gate when the workspace already contains application code, docs, or a running product — not only a blank new idea.

## Goal

Do not invent a simplified UI that silently drops real capabilities (print, Telegram, returns, payroll, backup, allergies, etc.).
First extract what exists, score strengths and weaknesses with multi-agent analysis, then let the user choose Keep / Drop / Defer.

## When it is mandatory

Run this gate **before** UX-First Gate and **before** Visual Prototype Gate if any of these are true:

- A repo or project folder is in the workspace
- Models, routes, pages, or decision docs exist
- The user says specialize, simplify, redesign, or rebuild an existing product

Skip only for greenfield products with no prior code.

## How to inventory (minimum sources)

Search and read targeted slices — do not dump entire large files:

1. Backend routes / API surface
2. Data models (entities and important enums)
3. Front panels, menus, buttons, and JS modules
4. Decision logs, README, QA / production checklists
5. Integrations (Telegram, print sheets, Excel export, backup, webhooks)

Record each capability as a short line with:

- Name (user language)
- Where it lives (route, model, UI panel, script)
- Status: Working / Partial / Placeholder / Broken
- Role impact (who uses it daily)

## Integration families (always scan)

| Family | Example signals in code |
|--------|-------------------------|
| Auth | login, logout, JWT, roles, membership |
| Print | print-sheet, window.print, PDF, چاپ |
| Messaging | telegram, bot, webhook |
| Export | excel, csv, xlsx, خروجی |
| Backup | backup, sqlite backup, restore |
| Returns | return, مرجوعی, void |
| Clinical safety | allergy, medication, interaction |
| Multi-tenant | businesses list, business_id switcher |
| Field / other verticals | mission, expense categories for field service |

## Multi-agent analysis (pair with safe-multi-agent-github-dev)

Activate at least:

- Designer — information architecture fit
- Product-UX Critic — learnability and clutter risk
- Security-Critic — auth, secrets, tenant isolation, webhooks
- Code-Reviewer — maintainability and dead code
- Domain specialists as needed (Accounting, Inventory, Analytics, Clinic/treatment)

Each writes a short note. Then Judge produces:

1. Strengths (bullet list)
2. Weaknesses / risks (bullet list)
3. Capability table for the user

## Capability table format (present to user)

| # | Capability | Status | Recommendation | User choice |
|---|------------|--------|----------------|-------------|
| 1 | … | Working / Partial / Placeholder | Keep / Drop / Defer | (blank for user) |

Recommendations are suggestions only. **User choice is required.**

Rules:

- Keep = must appear in the next prototype and later production UI
- Drop = explicitly out of scope for this product direction (document why)
- Defer = not in the next prototype, but must remain in the inventory log

Never mark Drop without user confirmation when the capability already exists in code.

## After the user answers

1. Lock the Keep set in the decision log
2. Pass only Keep (and optionally Defer as “hidden advanced”) into UX-First and Visual Prototype
3. Prototype **must surface every Keep capability** in some form (menu, settings panel, button, or progressive disclosure) — not only the happy path
4. If the user later adds a Keep item, revise the prototype before more production work

## Anti-patterns this gate prevents

- Redesigning Home while forgetting print, Telegram, returns, or settings that already ship
- “Simple” UI that is actually incomplete relative to the real product
- Agents guessing features instead of reading the codebase
- Skipping strength/weakness analysis when full project access is available
