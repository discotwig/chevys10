---
name: price-check
description: >-
  Discovers price-list documents (docs/*-prices.md), reads their BOM tables,
  searches trusted U.S. auto-parts vendors for current retail prices, and
  rewrites the price tables with fresh data and today's date. Use when the user
  asks to fetch, refresh, update, or check prices for a project, or mentions
  "price check" or "vendor prices."
---

# Price check

## Default assumptions

This skill operates inside the **chevys10** repo, which documents a **1999 Chevrolet S10 2.2L inline-four**. All part searches must stay **2.2L-specific**; do not drift to 4.3L V6 or other engines. Follow the same source-citation and corroboration rules as the [s10-research skill](../s10-research/SKILL.md).

## Scope

This skill handles **price lookup and table updates only**. It does not add, remove, or change parts in the BOM. If the user wants to change which parts are listed, direct them to use the `s10-research` skill first, then re-run `price-check`.

## Workflow

### 1. Discover target documents

Glob for `docs/*-prices.md`. Depending on the result:

- **One file found** — use it automatically.
- **Multiple files found** — list them and ask the user which to refresh (or offer "all").
- **User already named a file** — use that file; skip the prompt.
- **No files found** — tell the user no price-list documents exist yet and suggest creating one with the `s10-research` skill.

### 2. Read the BOM

Open the target document and parse the **"Recommended build summary"** table. Extract each row's:

- **Line label** (e.g. "Fan", "Controller")
- **Manufacturer part #** (e.g. `Derale 16214`, `Hayden 3647`)
- **Description** (for context when searching)

This list is the shopping list for the vendor search loop. Also note any rows marked **"conditional"** — still price them but keep the conditional flag.

### 3. Classify each line

- **MPN-searchable** — has a specific manufacturer part number (e.g. `Derale 16214`). Search vendors.
- **Commodity** — generic items described by spec rather than MPN (e.g. "10 AWG primary wire, ~20 ft", "30 A MAXI blade fuse"). Do **not** web-search these. Keep the existing estimated price range and append "(not re-priced; commodity item)".

### 4. Vendor search loop

Read [vendors.md](vendors.md) for the full vendor list and search rules.

For each **MPN-searchable** line, for each **primary vendor**:

1. **Search**: web-search `"{MPN}" site:{vendor domain}` or `"{MPN}" {vendor name} price`.
2. **Fetch**: if a product page URL is found, fetch it and extract the **USD retail price**.
3. **Record**:
   - **Found**: vendor name, price (USD), product page URL.
   - **Not found**: `---` with a short note (e.g. "Not listed online at time of search").
4. **Never invent a price.** If the page loads but the price is hidden, blocked, or in a non-USD currency that cannot be confirmed, record `---`.

Run searches for **optional vendors** only when a primary vendor misses the MPN or when the user requests broader coverage.

### 5. Update the price tables

Edit the target document **in place**:

1. **Date banner** — update the retrieval date in the "Purpose and scope" section to today's ISO date (e.g. `2026-03-31`).
2. **Per-component tables** — rewrite each component's vendor/price/URL table with the fresh data. Keep the same markdown table structure:
   ```
   | Vendor | Price | Product URL |
   |--------|------:|-------------|
   ```
3. **Commodity tables** — leave estimated-price ranges unchanged. Add "(not re-priced; commodity item)" if not already present.
4. **Notes below tables** — preserve existing notes (e.g. "performance-catalog item") unless the new data contradicts them.

### 6. Recalculate totals

Update the **"Estimated totals"** section:

- Recompute the per-vendor subtotals from confirmed prices.
- Update the mixed-vendor "realistic all-in estimate" by summing the cheapest confirmed price for each MPN-searchable item plus the commodity estimate range.

### 7. Update gaps

Rebuild the **"Gaps"** table:

- A row for every component/vendor combination that returned `---`.
- Keep the recommendation column actionable (e.g. "Order from Summit Racing", "Check in-store").

### 8. Leave untouched

Do **not** edit these sections unless the user explicitly asks:

- Recommended build summary (BOM)
- Electrical sizing rationale
- Sources consulted (add new vendor URLs only if they weren't already listed)
- Disclaimer

## Output rules

- All prices in **USD**, excluding shipping and tax.
- Every confirmed price must have a **clickable product URL**.
- Retrieval date appears **once** in the header banner; do not repeat per row.
- Do not invent prices. Do not round or estimate confirmed prices.
- Do not substitute a different MPN without flagging it to the user.
- Do not silently drop a vendor that appeared in the previous version of the table.

## Anti-patterns

- Guessing prices from forum posts or unrelated listings.
- Substituting a different part number and calling it equivalent without asking.
- Dropping a vendor row because no price was found (keep it with `---`).
- Drifting into 4.3L or generic "S10" part numbers.
- Editing the BOM table (add/remove/change parts) during a price refresh.
