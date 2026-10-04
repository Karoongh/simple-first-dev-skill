# Color System Catalog (examples to propose — not auto-default)

**Do not apply these automatically.** When a project needs a palette, ask the user about brand and feel, then propose 2–3 options (this file can supply candidates). The user chooses; lock the choice in the project decision log.

Values are hex. After a choice, implement only via semantic names (`--color-primary`, `--color-danger`, …).

## Design intent (for any candidate you propose)

- Trust and clarity first when the product handles money or stock
- One strong accent for primary actions
- Status colors only for meaning (profit, loss, low stock, overdue)
- Dark mode is a first-class theme, not an afterthought
- Charts must remain readable in both themes

---

## Light mode

| Token | Hex | Use |
|-------|-----|-----|
| background | `#F7F8FA` | Page background |
| surface | `#FFFFFF` | Cards, panels, modals |
| surface-muted | `#EEF1F5` | Secondary strips, table header |
| border | `#E2E6EC` | Dividers, card edges |
| text | `#1A1D23` | Primary text |
| text-muted | `#5C6570` | Secondary labels, hints |
| text-faint | `#8B93A0` | Placeholders, disabled |
| primary | `#2F6FED` | Main buttons, links, focus |
| primary-hover | `#1F5AD6` | Hover / pressed primary |
| primary-soft | `#E8F0FE` | Soft primary backgrounds |
| success | `#1B9E5A` | Profit, paid, in stock OK |
| success-soft | `#E6F7EE` | Soft success background |
| warning | `#D97706` | Reorder point near, attention |
| warning-soft | `#FEF3C7` | Soft warning background |
| danger | `#DC2626` | Loss, overdue, critical low stock |
| danger-soft | `#FEE2E2` | Soft danger background |
| chart-1 | `#2F6FED` | Primary series (e.g. sales) |
| chart-2 | `#0D9488` | Secondary series (e.g. purchases) |
| chart-3 | `#7C3AED` | Third series / services |
| chart-4 | `#EA580C` | Fourth series / comparison |
| chart-grid | `#E8ECF1` | Chart grid lines |
| chart-axis | `#8B93A0` | Axis labels |

Accent rationale: blue reads as professional and neutral for money software; teal and violet give clear series separation on charts without looking playful.

---

## Dark mode

| Token | Hex | Use |
|-------|-----|-----|
| background | `#0F1218` | Page background |
| surface | `#1A1F2A` | Cards, panels, modals |
| surface-muted | `#242B38` | Secondary strips, table header |
| border | `#2E3645` | Dividers, card edges |
| text | `#F0F2F5` | Primary text |
| text-muted | `#A0A8B5` | Secondary labels, hints |
| text-faint | `#6B7382` | Placeholders, disabled |
| primary | `#5B8FF9` | Main buttons, links, focus |
| primary-hover | `#7AA4FB` | Hover / pressed primary |
| primary-soft | `#1A2A4A` | Soft primary backgrounds |
| success | `#34D399` | Profit, paid, in stock OK |
| success-soft | `#0F2E22` | Soft success background |
| warning | `#FBBF24` | Reorder point near, attention |
| warning-soft | `#3A2E0A` | Soft warning background |
| danger | `#F87171` | Loss, overdue, critical low stock |
| danger-soft | `#3B1515` | Soft danger background |
| chart-1 | `#5B8FF9` | Primary series (e.g. sales) |
| chart-2 | `#2DD4BF` | Secondary series (e.g. purchases) |
| chart-3 | `#A78BFA` | Third series / services |
| chart-4 | `#FB923C` | Fourth series / comparison |
| chart-grid | `#2A3140` | Chart grid lines |
| chart-axis | `#8B93A0` | Axis labels |

Dark surfaces stay slightly blue-gray so pure black fatigue is avoided and cards still separate from the page.

---

## Chart color rules

- Sales vs purchases on one chart: use `chart-1` (sales) and `chart-2` (purchases)
- Profit highlight: `success`; loss highlight: `danger`
- Never rely on color alone — always pair with labels, patterns, or icons when status matters
- On mobile, prefer at most 2–3 series visible by default; extra series behind a toggle

## CSS variable sketch

```css
:root {
  --bg: #F7F8FA;
  --surface: #FFFFFF;
  --text: #1A1D23;
  --primary: #2F6FED;
  --success: #1B9E5A;
  --warning: #D97706;
  --danger: #DC2626;
  /* …map the rest from the tables above */
}

[data-theme="dark"] {
  --bg: #0F1218;
  --surface: #1A1F2A;
  --text: #F0F2F5;
  --primary: #5B8FF9;
  --success: #34D399;
  --warning: #FBBF24;
  --danger: #F87171;
}
```

## Optional alternate accent

If the brand needs a warmer feel (food retail, lifestyle):
- Light primary: `#0F766E` (teal)
- Dark primary: `#2DD4BF`

Keep status colors unchanged so profit/loss/reorder meaning stays consistent.
