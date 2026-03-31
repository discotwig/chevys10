# Trusted vendors for price checks

Use this list when searching for current prices. Search every vendor for each MPN unless the vendor's catalog scope clearly excludes the part category.

## Primary vendors (always search)

| Vendor | Domain | Search strategy | Catalog strengths |
|--------|--------|-----------------|-------------------|
| Summit Racing | `summitracing.com` | URL pattern: `summitracing.com/parts/{sku}` where `{sku}` is lowercase with prefix (e.g. `der-16214`). Fallback: web search `"{MPN}" site:summitracing.com`. | Performance cooling, electric fans, wiring, fuse holders, relays. Broad aftermarket catalog. |
| RockAuto | `rockauto.com` | Web search `"{MPN}" site:rockauto.com` or navigate catalog by vehicle (Chevrolet > S10 Pickup > 2.2L L4 > Cooling System). Prices render in page; look for the dollar amount near the part number row. | OEM and aftermarket replacement parts, pulleys, controllers, sensors. May not carry performance-only brands (e.g. Derale). |
| O'Reilly Auto Parts | `oreillyauto.com` | Web search `"{MPN}" site:oreillyauto.com`. O'Reilly pages sometimes block automated fetches; if the page returns no content, note "price not confirmed online" rather than inventing a number. | Hayden fans/controllers, Bussmann fuses/holders, OEM replacement. In-store price may differ from online. |
| AutoZone | `autozone.com` | Web search `"{MPN}" site:autozone.com`. Similar fetch limitations as O'Reilly. | Bussmann fuses/holders, Dorman pulleys, general electrical. May not carry performance fan brands. |

## Optional vendors (search when relevant)

| Vendor | Domain | When to include | Notes |
|--------|--------|-----------------|-------|
| Jegs | `jegs.com` | When Summit Racing does not list the MPN, or for price comparison on performance parts. | Similar catalog to Summit Racing; often identical pricing. |
| LMC Truck | `lmctruck.com` | Only for S10/GMT325-specific items (brackets, pulleys, trim) that other vendors lack. | S10-era truck specialty. Not useful for universal fans or electrical commodities. |
| Amazon | `amazon.com` | Only if the user requests it. Note that seller and fulfillment vary; not an "application tool" vendor. | Wide availability but fitment data is unreliable; use only for commodity items (fuses, wire, zip ties). |

## Search rules

1. Always quote the manufacturer part number in the search query: `"Derale 16214"`, not `Derale 16214`.
2. If a site-scoped search returns no results, try a general web search: `"{MPN}" {vendor name} price`.
3. If a vendor page loads but does not display a price (bot-blocked, login-required, or out-of-stock), record `---` with a note. Never guess.
4. Record prices in **USD**. If the page shows a foreign currency (e.g. RockAuto sometimes shows NZD/CAD depending on geo), note the currency and convert at the day's rate, or mark it `---` if USD cannot be confirmed.
5. Capture the **product page URL** for every confirmed price so the user can verify.
