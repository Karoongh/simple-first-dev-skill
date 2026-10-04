# Analytics & Inventory Widgets Catalog (examples to propose — not auto-default)

**Do not install a fixed dashboard automatically.** Ask which decisions matter for this project, then propose a short list from the ideas below. The product owner chooses which containers exist, which are on by default, and which roles see them.

Each chosen item should be a self-contained Home container the end user can show, hide, or rearrange.

## Core chart widgets

### 1. Sales vs Purchases over time
- One chart, two series (sales amount, purchase amount)
- Time range: today / week / month / custom
- Mobile: default to last 7 or 30 days; allow expand
- Tooltip shows both values + difference

### 2. Top profitable products or services
- Ranked list or horizontal bar chart
- Metric options: gross profit, margin %, quantity sold
- Filter by category, period, branch
- Tap row → product detail or stock movement

### 3. Top selling products (by quantity or revenue)
- Separate from pure profit when volume matters (e.g. supermarket)
- Optional toggle: quantity ↔ revenue

### 4. Worst margin / loss-making items
- Same layout as top profitable, opposite sort
- Useful for pricing and assortment decisions

### 5. Category mix
- Pie or stacked bar: share of sales or profit by category
- Keep categories limited on mobile (group “Other”)

## Inventory & reorder widgets

### 6. Reorder point alerts
- List of items at or below reorder point
- Show: on-hand, reorder point, suggested order qty, supplier
- Primary action: create purchase order or mark as ordered
- This is a first-class accounting/ops widget, not a buried report

### 7. Stock health summary
- Counts: OK / near reorder / out of stock
- Optional value of inventory at cost

### 8. Slow movers
- Items with low sales velocity over a period
- Helps purchasing and promotion decisions

## Money widgets

### 9. Today / period P&L snapshot
- Revenue, COGS, gross profit, expenses (as available)
- Big numbers + small trend vs previous period

### 10. Receivables / payables attention
- Overdue counts and amounts
- Only if the product tracks credit sales or supplier terms

## Container rules

- Every widget above is optional on Home; defaults depend on role (cashier vs owner vs buyer)
- Charts that compare two metrics (sales vs purchases) stay on **one** chart with a clear legend
- Dense tables belong one click deeper; Home shows summary + alert + trend
- Reorder point logic needs product fields: reorder_point, reorder_qty (or formula), lead time optional
- Profit widgets need cost and sell price (or last cost) — if cost is missing, show revenue-only and label it honestly

## Specialist involvement

When building or changing these widgets, involve:
- Accounting specialist — definitions of profit, COGS, period boundaries
- Inventory specialist — reorder point, safety stock, unit consistency
- Analytics specialist — chart type, aggregation, mobile series limits
