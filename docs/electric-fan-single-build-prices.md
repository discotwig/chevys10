# Electric fan single-build vendor price list (2.2L S10)

## Purpose and scope

This document defines **one recommended electric fan conversion build** for a **1999 Chevrolet S10 2.2L** (mechanical fan delete, thermostatic control, relay-switched fused feed) and lists current retail prices from trusted U.S. auto-parts vendors. It accompanies [electric-fan-vs-belt-fan-2.2l.md](electric-fan-vs-belt-fan-2.2l.md), which covers the *why*, installation outline, and stress-test procedure.

**All prices are retail snapshots in USD retrieved on 2026-03-31.** Shipping and sales tax are excluded. Prices change without notice; re-check before ordering. Availability at chain stores (O'Reilly, AutoZone, NAPA) may vary by location.

## Recommended build summary

**Build in one line:** 1999 S10 2.2L, mechanical fan delete, 14-inch puller e-fan, thermostatic controller with included relay, fused battery feed, heavy-gauge power/ground.

| Line | Manufacturer part # | Description | Why chosen |
|------|---------------------|-------------|------------|
| Fan | Derale 16214 | 14 in. High-Output Single RAD fan, 2,100 CFM (high) / 1,500 CFM (low), 22 A max draw, 265 W 2-speed motor, reversible pusher/puller, ratchet mounting kit included | Provides strong airflow margin for worst-case sizing (summer traffic, A/C, grades) on the 2.2L's ~16 in. wide radiator core. Puller mounting behind radiator per parent doc. |
| Controller | Hayden 3647 | Adjustable thermostatic fan controller, 160–210 °F probe, 30 A relay capacity. Kit includes relay, wiring harness (36 in.), and A/C override relay. | Self-contained control + relay in one kit; adjustable set-point simplifies tuning. 30 A relay handles the Derale's 22 A running draw. |
| Fuse holder | Bussmann HHX | MAXI inline fuse holder, 20–60 A capacity, 6 AWG leads, with protective cover | Fuses the battery-side feed per the parent doc's electrical practice section. 6 AWG leads handle the fan's current with margin. |
| Fuse | Bussmann BP/MAX-30 | 30 A MAXI blade fuse | Sized above 22 A running draw with margin; below the 60 A holder limit and wiring capacity. |
| Wire | 10 AWG primary wire, ~20 ft | Stranded automotive primary wire for supplemental power and ground runs between battery, fuse, relay, fan, and chassis ground | 10 AWG is rated for ~30 A in a typical under-hood environment; covers the 22 A draw with headroom. Length is approximate—measure your actual routing. |
| Pulley (conditional) | GM 24576197 | Water pump pulley, 1994–2003 S10 2.2L (replaces 10141934) | **May not be required.** On the 2.2L, the mechanical fan clutch bolts to a hub on the water pump shaft; removing the fan and clutch usually leaves the existing water pump pulley and serpentine belt routing intact. **Verify against your truck and factory service manual** before ordering. Listed here for completeness. |

### Electrical sizing rationale

- **Fan draw:** 22 A running (high speed), brief inrush higher.
- **Controller relay:** Hayden 3647 relay rated 30 A — adequate for steady-state; inrush is transient.
- **Fuse:** 30 A MAXI — protects against sustained overcurrent while allowing normal startup.
- **Wire:** 10 AWG stranded (~30 A capacity at chassis-harness temps) for runs from battery to fuse holder to relay output to fan, and fan ground to chassis/battery return.
- **Fuse holder leads:** 6 AWG (Bussmann HHX) — more than adequate for a 30 A fuse.

## Price table

Prices retrieved **2026-03-31**. "—" means the vendor does not list that exact MPN or the price could not be confirmed online.

### Derale 16214 — 14 in. High-Output Single RAD Fan

| Vendor | Price | Product URL |
|--------|------:|-------------|
| Summit Racing | $234.83 | [summitracing.com/parts/der-16214](https://www.summitracing.com/parts/der-16214) |
| RockAuto | — | Not listed under Derale universal fans at time of search |
| O'Reilly | — | Not listed online at time of search |
| AutoZone | — | Not listed online at time of search |

**Note:** The Derale 16214 is a performance-catalog item sold primarily through Summit Racing, Jegs, and specialty retailers. Chain auto-parts stores generally do not stock it.

### Hayden 3647 — Adjustable Thermostatic Fan Controller Kit

| Vendor | Price | Product URL |
|--------|------:|-------------|
| RockAuto | $29.99 | [rockauto.com — Hayden 3647](https://www.rockauto.com/en/parts/hayden,3647,cooling+fan+controller,2180) |
| Summit Racing | $32.99 | [summitracing.com/parts/hda-3647](https://www.summitracing.com/parts/hda-3647) |
| O'Reilly | — | Hayden line is carried; exact 3647 price not confirmed online |
| AutoZone | — | Not listed online at time of search |

### Bussmann HHX — MAXI Inline Fuse Holder

| Vendor | Price | Product URL |
|--------|------:|-------------|
| Summit Racing | $19.99 | [summitracing.com/parts/bss-hhx](https://www.summitracing.com/parts/bss-hhx) |
| RockAuto | — | Not confirmed at time of search |
| O'Reilly | — | Bussmann fuse holders stocked in-store; price varies by location |
| AutoZone | — | Bussmann fuse holders stocked in-store; price varies by location |

### Bussmann BP/MAX-30 — 30 A MAXI Blade Fuse

| Vendor | Estimated price | Notes |
|--------|----------------:|-------|
| Any auto-parts store | $5–$8 | Commodity item; widely stocked at AutoZone, O'Reilly, NAPA, Walmart. Purchase locally. |

### 10 AWG Stranded Primary Wire (~20 ft)

| Vendor | Estimated price | Notes |
|--------|----------------:|-------|
| Any auto-parts store | $15–$25 | Sold by the foot or in 25 ft rolls. Available at AutoZone, O'Reilly, NAPA, Summit, or hardware stores. Measure your actual routing before buying. |

### GM 24576197 — Water Pump Pulley (conditional)

| Vendor | Price | Notes |
|--------|------:|-------|
| GMPartsGiant | — | Listed for 1994–2003 S10 2.2L but showed unavailable at time of search |
| RockAuto | — | Not confirmed under this GM part number at time of search |
| Dealer | Varies | Contact a GM dealer parts counter with this number or replacement 10141934 |

**This line item is conditional.** Most 2.2L fan-delete conversions do not require a separate pulley purchase. Verify by inspecting your truck: if the fan clutch hub unbolt from the existing water pump pulley and the serpentine belt routing is unchanged, no new pulley is needed.

## Estimated totals (confirmed prices only)

| Vendor | Items priced | Subtotal |
|--------|-------------|----------|
| Summit Racing | Fan + Controller + Fuse holder | $287.81 |
| RockAuto | Controller only | $29.99 |

A realistic all-in estimate using Summit Racing for the fan and fuse holder plus RockAuto for the controller, plus ~$20–$33 in commodity items (fuse + wire) locally:

**Estimated total: ~$310–$325 USD** (before shipping and tax)

## Gaps

| Component | Gap | Recommendation |
|-----------|-----|----------------|
| Derale 16214 fan | Not stocked at chain auto-parts stores (O'Reilly, AutoZone, NAPA) | Order from Summit Racing or Jegs |
| Hayden 3647 controller | O'Reilly carries Hayden but 3647 price not confirmed online | Check in-store or call; likely comparable to RockAuto's $29.99 |
| Water pump pulley GM 24576197 | Unavailable at online GM-parts retailers at time of search | Verify if needed first; if so, try a local GM dealer or salvage yard |
| MAXI fuse + primary wire | Commodity items not priced per-vendor | Buy locally at any auto-parts store |

## Sources consulted

- [Summit Racing — Derale 16214](https://www.summitracing.com/parts/der-16214) — fan specifications, pricing, and application data.
- [Derale Performance — 16214 product page](https://derale.com/product-footer/electric-fans/universal-electric-fans/high-output-single-rad/16214-detail) — manufacturer specs (CFM, amps, dimensions).
- [Summit Racing — Hayden 3647](https://www.summitracing.com/parts/hda-3647) — controller specifications and pricing.
- [RockAuto — Hayden 3647](https://www.rockauto.com/en/parts/hayden,3647,cooling+fan+controller,2180) — controller pricing.
- [RockAuto — Hayden 3690](https://www.rockauto.com/en/parts/hayden,3690,radiator+fan+assembly,2181) — alternative fan reference and pricing.
- [Summit Racing — Bussmann HHX](https://www.summitracing.com/parts/bss-hhx) — fuse holder specifications and pricing.
- [GMPartsGiant — S10 water pump pulley](https://www.gmpartsgiant.com/oem-chevrolet-s10-water_pump_pulley.html) — GM 24576197 application and availability.
- [Hayden Automotive — electric fan brochure (PDF)](https://www.haydenauto.com/media/5477/electric-fan-brochure_4-page_final.pdf) — manufacturer CFM and amp specifications for Hayden fan line.
- Parent document: [electric-fan-vs-belt-fan-2.2l.md](electric-fan-vs-belt-fan-2.2l.md) — installation outline, electrical practice, and stress-test procedure.

## Disclaimer

This document is **not** official General Motors documentation. Prices are point-in-time retail snapshots and will change. Verify **part numbers**, **fitment**, **electrical ratings**, and **procedures** against **2.2L** service information for your vehicle. The water pump pulley line item is conditional—inspect your truck before ordering. Use at your own risk.
