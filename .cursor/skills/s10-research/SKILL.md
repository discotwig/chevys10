---
name: s10-research
description: >-
  Researches Chevrolet S10 topics for the 2.2L I4 (four-cylinder) only: parts,
  mods, maintenance, wiring, cooling, and install guidance, using web search and
  public pages, then synthesizes buying considerations and step-by-step outlines
  with citations. Assumes 1999 S10 2.2L in factory configuration per the chevys10
  repo; does not default to 4.3L V6 or other engines. Use when the user asks about
  their truck, S10 GMT325 2.2L, maintenance, upgrades (e.g. electric fan, belt fan
  delete), torque specs, or forum-sourced how-tos.
---

# S10 documentation research (2.2L only)

## Default assumption

This repository documents a **1999 Chevrolet S10** with the **2.2L inline-four** in stock configuration. Unless the user clearly states otherwise, treat every question about **the truck** or **S10** as referring to **this engine only**.

**Do not** default to **4.3L V6**, **Vortec 4.3**, **V8 swaps**, or other powertrains. **Do not** generalize procedures or part numbers to “any S10” when the four-cylinder differs.

If the user **explicitly** asks about another engine or a swap, answer that narrow question and add a short note that this repo’s truck is **2.2L** and that cross-engine notes are for comparison or planning only.

## Local context first

If this repo contains a `docs/` or similar markdown how-tos folder, **glob or search it first** for existing 2.2L notes before heavy web research.

## Research workflow

1. **Restate the goal** in one line, always naming **2.2L / four-cylinder** (e.g. “electric cooling fan replacing mechanical fan on a 2.2L S10”).
2. **Search** with **2.2L-biased** queries: include `2.2`, `2.2L`, `four cylinder`, `4 cyl`, or `LN2` when accurate, plus `S10` or `GMT325` as needed.
3. **Prefer** sources that specify the four-cylinder. If a thread or article mixes engines, **filter** to 2.2L applicability and state that plainly (e.g. “thread mixes 4.3 and 2.2; below is 2.2L-only”).
4. **Corroborate** non-trivial claims when possible (e.g. two forum threads plus a vendor fitment note)—not one random post as sole authority.
5. **Official / safety-critical specs** (torque, fluids, wire colors, fuse numbers): **cite** a manual, TSB, or labeled diagram; if unavailable, say **verify in 2.2L service documentation**—never invent numbers.
6. **Fetch** public URLs when snippets are insufficient. Do not reproduce paywalled or copyrighted manual text at length; cite and summarize.
7. **Attribute** sources: link or name + short context (thread title, section). Summarize; do not copy large blocks verbatim.

For a curated list of community and manual starting points, see [reference.md](reference.md).

## Output template

Use this structure unless the user asks for something narrower:

```markdown
## Summary

[Decision-oriented paragraph for 2.2L S10.]

## 2.2L applicability

[Year/cab/transmission nuances only if sources support them; not “choose your engine.”]

## Buying / parts considerations

[Options, tradeoffs, fitment notes; avoid fake precision on price.]

## Installation outline

[Ordered steps, tools, pitfalls; torque/fluid only with cited source or “verify in manual.”]

## Sources consulted

- [Bullet list with links or identifiable titles]

## Disclaimer

Not official GM documentation. Use at your own risk; verify part numbers and procedures against your own 2.2L sources.
```

## Anti-patterns

- Drifting into **4.3L** or “typical S10” answers when the user did not ask for another engine.
- **GMT325** advice without checking **2.2L**-specific differences (accessory drive, cooling, electrical load).
- **Inventing** torque, wiring colors, or fuse IDs without a cited source.
- Treating one unsourced forum reply as definitive.
