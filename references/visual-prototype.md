# Visual Prototype Delivery

Build this only after jobs, navigation intent, palette direction, and key widgets are understood.
Stop for user approval before production implementation.

## Goal

A clickable sample that shows menus, Home, and main windows so the user can say yes, yes-with-tweaks, or no.

## Suggested folder shape

```
prototype/   (or artifacts/ui-prototype/)
  index.html           # entry — login or Home
  css/
    theme.css          # tokens for the chosen (or proposed) palette
    layout.css         # shell, nav, grid
  js/
    shell.js           # nav switching, theme toggle, simple interactions only
  pages/               # optional if multi-file is clearer
    home.html
    ...
  README.md            # how to open and what to click
```

For a very small scope, one self-contained HTML file with embedded CSS is fine.

## Must show

- Top-level navigation (desktop and a mobile pattern)
- Home with sample widgets/cards using placeholder but realistic data
- Primary actions (large, obvious)
- At least one secondary screen or panel per major menu item in scope
- One example modal or sheet if those are part of the design
- Theme: light and dark if the user already picked a palette; otherwise one clear theme plus optional toggle if proposing both
- Readable RTL or LTR according to the product language

## Must not do in the prototype

- Real backend, auth, or database
- Full business logic
- Production folder structure mixed into the live app without a clear `prototype/` boundary
- Empty gray boxes with no sample content

## Handoff text to the user

Always include:

1. Where the files are
2. How to open them (e.g. open `prototype/index.html` in a browser)
3. What to click through (3–6 steps)
4. A direct question: **Approve / Approve with tweaks / Reject**

## After approval

- Log the approval and any tweaks in the decision log
- Match production UI to the prototype unless the user later changes direction
- If the user rejects, revise the prototype only — do not start the real app
