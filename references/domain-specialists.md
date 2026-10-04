# Domain specialists (on-demand agents)

In addition to the six core agents, activate the specialists below when the task touches their domain.
Each specialist writes a short note: risks, required fields, and acceptance checks.

## Accounting specialist

Activate when work involves money, invoices, payments, P&L, tax, or period reports.

Must check:
- Correct meaning of revenue, cost, profit, and discounts
- Period boundaries (day/month/fiscal) and timezone
- That charts and widgets label metrics honestly (gross vs net, with/without tax)
- Double-entry or ledger impact if the product claims full accounting
- Soft-delete and void rules for documents that affect balances

## Inventory specialist

Activate when work involves stock, purchases, sales of goods, reorder, or warehouses.

Must check:
- Unit consistency (piece, box, kg) and conversion if used
- Reorder point and suggested order quantity fields
- Stock movement direction on sale, purchase, return, adjustment
- Negative stock policy (block vs warn)
- Multi-location / multi-bin only if the product truly needs it

## Analytics specialist

Activate when work involves charts, rankings, dashboards, or KPI widgets.

Must check:
- Right chart for the question (trend vs rank vs share)
- Default time range sensible for mobile and desktop
- Maximum series visible by default (prefer 2–3)
- Aggregations match the business question (sum, margin %, quantity)
- Empty and partial-data states (no cost data → do not fake profit)

## Retail / assortment specialist (optional)

Activate for supermarket, shop, or multi-product catalog decisions.

Must check:
- Top sellers vs top profit are both available when relevant
- Category and barcode/SKU workflows stay simple
- Promotions or discounts do not break margin widgets silently

## How specialists work with the core team

1. Core six agents still produce proposals and critiques.
2. Relevant specialists add domain constraints before the Judge scores.
3. Judge may lower Completeness or Correctness if a required specialist concern is ignored.
4. Do not activate every specialist on every task — only when the feature touches that domain.
