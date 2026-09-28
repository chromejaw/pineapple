# Data-Dense Interfaces: Dashboards, Tables & Admin Tools

Apple's desktop guidance (more content in fewer levels, comfortable density, precise selection, keyboard-first work) and its charting guidance applied to dashboards, data tables, and internal tools — where "simplicity" means *fast scanning and zero ambiguity*, not whitespace.

---

## 1. Principles

- **Purpose first:** every dashboard answers a small set of questions for a specific person ("Is anything on fire? What changed since yesterday?"). Write those questions down; anything that doesn't answer one goes.
- **Summarize, then detail** (progressive disclosure): headline numbers → trend → breakdown → raw rows. One click deeper at each level.
- **Density is a feature, clutter is not.** Tight spacing is fine; decoration, borders on every cell, and competing colors are not.
- **Color means something or it's neutral.** Reserve saturated color for status and the single action tint; charts use a deliberate categorical palette; everything else is grayscale.
- **Solid chrome.** No glass or translucency over data; use solid bars and hard scroll edges for pinned headers (see [Materials › When not to use glass](./materials-and-glass.md)).

## 2. Layout

- Desktop body text **13–14 px**, rows **28–32 px** (compact) to **40–44 px** (comfortable, touch). Offer a density toggle.
- Grid of cards for KPIs at the top: label (footnote/caption style), value (title style, tabular figures), delta with direction icon and sign ("+4.2% vs last week"), optional sparkline.
- Align to a strict grid; left-align text, **right-align numbers**, align decimal points; use `font-variant-numeric: tabular-nums` everywhere numbers change.
- Keep filters, date range, and scope visible at the top — people must always know *what data they're looking at*.
- Show **data freshness** ("Updated 2 min ago") and timezone.

## 3. KPI & Number Formatting

- Round for the reader: 1,234,567 → **1.23M** in cards, full precision in tables and tooltips.
- Always show units and the comparison baseline; don't show a delta without "vs what."
- Direction ≠ good/bad: color deltas by *meaning* (costs going up can be bad), and pair color with an arrow and sign.
- Handle zero, null, and "no data" distinctly ("—" for no data, "0" for zero).

## 4. Charts (see [Patterns › Charting data](./patterns.md) and [Components › Charts](./components.md))

- Choose the simplest chart that answers the question: bar for comparison, line for trend over time, stacked only when the parts sum to a meaningful whole, tables when people need exact values. Avoid pie charts beyond ~5 slices and never 3D.
- Title each chart with the takeaway ("Sign-ups doubled after launch"), not just the metric name.
- Label axes and units; start bar charts at zero; keep consistent scales across charts compared side by side.
- Interaction reveals detail (hover/scrub tooltips) but **never hides critical information** behind interaction.
- Accessibility: text summary of each chart, per-point accessible labels, don't rely on color (use patterns/shapes/direct labels), respect reduced motion.

## 5. Data Tables

- **Sticky header** (hard scroll edge), sticky first column for wide tables, horizontal scroll inside the table — never the page.
- **Sort** by clicking headers (show direction; secondary sort stable), **filter** per column or with tokens, **search** across the table.
- **Resizable, reorderable, hideable columns** for power users; remember their layout.
- **Selection:** checkbox column + shift-click range + select-all (with "select all 2,340 matching" for filtered sets); a contextual action bar appears on selection.
- **Row actions:** primary action on row click/Enter; secondary in a trailing "more" menu and the context menu (right-click); destructive actions last and red.
- **Pagination vs. virtual scroll:** paginate when people need stable positions or counts; virtualize long scrolling lists, but keep keyboard navigation and screen-reader row counts correct (`aria-rowcount`, `aria-rowindex`).
- **Inline editing:** clear edit affordance, Enter to save, Esc to cancel, validation inline, undo available.
- **Empty, loading, and error states** for the whole table and for individual cells (skeleton rows; "No results for 'acme' — clear filters").
- **Keyboard:** arrow keys move between cells, Space selects, Enter opens, Cmd/Ctrl-A selects all, `/` focuses search. Visible focus on the active cell/row.

## 6. Admin & Internal Tools

- Consistency over creativity: one table component, one form layout, one set of statuses used everywhere.
- Status badges: short word + color + icon ("● Active", "⚠ Failing"); define every status in one place.
- Bulk actions show a preview of affected items and a count; irreversible bulk actions require typing a confirmation or offer undo.
- Audit trail visible where changes happen ("Edited by Ana · 2h ago").
- Command palette (Cmd/Ctrl-K) for navigation and actions; keyboard shortcuts for frequent tasks.
