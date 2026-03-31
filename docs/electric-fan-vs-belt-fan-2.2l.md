# Electric fan vs stock belt fan (2.2L S10)

## Summary

Replacing the belt-driven clutch fan on a **1999 Chevrolet S10 2.2L** with an electric puller fan can reduce crank parasitic load, simplify access in front of the engine, and allow thermostatic fan control independent of engine speed. Gains are often **modest** in seat-of-the-pants terms; the main engineering risk is **insufficient airflow** through the radiator (and A/C condenser if equipped) if the fan, shroud, or control strategy is undersized. Plan for **relay-based high-current wiring**, a **trusted coolant temperature indication**, and a **road/A/C stress test** before relying on the truck. This note is **2.2L-only**; do not assume the same pulleys, clearance, or electrical behavior as the 4.3L V6.

## 2.2L applicability

This repo assumes **GMT325 S10, 1999 model year, 2.2L inline-four (LN2 family), factory configuration**. Other years may share the same idea but can differ in **accessory drive**, **radiator/shroud**, **PCM outputs**, and **fuse/relay centers**. Anything you bolt on or wire in must be verified against **your** truck and **2.2L** service documentation.

## Goals and worst-case sizing

Before picking a fan or controller, be explicit about **why** you are doing the swap and what “good enough” looks like.

| Goal | What to plan for |
|------|------------------|
| Quieter idle / less fan roar | Fan noise vs controller cycling; shroud rattle |
| Easier belt and front accessory access | Mechanical fan and shroud removal; correct **water pump pulley** for fan delete |
| Small efficiency / parasitic reduction | Real gains are often small; don’t overpromise |
| Steadier coolant temp (with good control) | Adequate **CFM**, good **shroud seal**, sensible **turn-on** temp |

**Size the system for the worst case you actually drive:** summer traffic, long grades, idling with **A/C on**, and any towing. If that profile is demanding, bias toward **higher airflow margin**, a **well-sealed shroud**, and conservative **fan-on** temperatures. Undersized or poorly ducted e-fans are a common cause of **slow-speed overheating** after a mechanical fan delete.

## Buying / parts considerations

- **Fan style**: **Puller** fans behind the radiator are the usual choice; pushers are a fallback when puller mounting is impossible. **Single large** vs **dual** fans trade packaging vs redundancy and wiring complexity.
- **Shroud**: Air must be **pulled through the radiator core**, not around it. A loose or absent shroud hurts low-speed cooling. Budget time for **brackets**, **sealing**, and **clearance** to the engine driven accessories.
- **“Conversion kits”**: Vendor kits exist for S10-class trucks; treat marketing claims (HP, MPG) skeptically and prioritize **fitment**, **CFM**, and **build quality**.
- **Junkyard assemblies**: Some owners adapt donor fan modules (various cars). Treat forum fitment stories as **leads only**—measure your radiator, hoses, and clearance yourself.
- **Water pump side**: After removing the mechanical fan, you typically need the **correct pulley** for a fan-delete setup (often a smooth or alternate pulley—**not** guessed from a generic “S10” thread). See **Verify in factory documentation** below.

## Control path: thermostatic vs PCM integration

Pick **one** primary control strategy and design the harness once.

### Option A — Thermostatic controller (common DIY)

- **Pros**: Self-contained; no need to decode PCM fan outputs; straightforward **relay** design.
- **Cons**: Another failure point (probe, controller, relay); must mount probe and set **on/off** temps thoughtfully.
- **Typical stack**: **Fused B+** → **relay** contacts → fan ground path; **low-current trigger** from controller → relay coil; **heavy gauge** power wiring sized for fan **stall/startup** current; **solid grounds** to chassis or battery return.

### Option B — PCM or factory-style integration

- **Pros**: Can match OEM intent if your year/engine actually supports discrete fan control and you understand the outputs.
- **Cons**: **1999 2.2L** may not mirror later truck e-fan strategies; wiring diagrams and enable conditions are **manual-specific**. Do not assume wire colors or fuse numbers from unrelated engines.

### Electrical practice (either path)

- Use **automotive relays** rated for the fan load; avoid running high current through the controller’s small terminals except as designed by the manufacturer.
- **Fuse** the fan circuit at the battery (or appropriate distribution point) per your design; do not rely on fragile taps into unrelated circuits.
- Route wires **away from exhaust and moving parts**; support harnesses so connectors do not chafe.

**Relay/fuse/wire sizing**: Use the fan manufacturer’s **current draw** (inrush and running) and standard automotive wiring tables; round up on **wire gauge** for long runs and under-hood heat. Final numbers belong in **your** build notes once parts are chosen.

## Verify in factory documentation (not forum-only)

The following must come from **Helm / factory service manual** or equivalent **2.2L** sections—not from uncorroborated posts:

- **Mechanical fan and clutch removal** procedure and **tool sizes** (large hex / spanner requirements appear often in community threads; still confirm for your year).
- **Water pump pulley** part numbers and **torque** for pulley bolts and pump fasteners if the pulley is changed.
- **Serpentine belt routing** and **belt tensioner** handling after the accessory drive changes.
- Any **ground**, **fusing**, or **PCM output** you intend to use for fan control.

Community threads are useful for **tips and pitfalls** (for example, holding the pulley while breaking the fan nut loose); they are not a substitute for **torque specs** and **official diagrams**.

## Installation outline

1. **Baseline cooling system**: Confirm **thermostat**, **pressure cap**, **hoses**, **coolant level**, and a **temperature gauge you trust** *before* removing the mechanical fan. Fix existing problems first.
2. **Design on paper**: Fan + shroud + controller + **relay diagram** (coil trigger, fused B+, grounds, fan connections).
3. **Mechanical**: Remove **clutch fan / mechanical fan** per manual. Install the **correct water pump pulley** for running **without** a mechanical fan if required. Reinstall **drive belt** per diagram; verify **alignment** and **tension**.
4. **Mount e-fan**: Secure **shroud/fan** with good seal to the radiator; confirm **clearance** to engine and steering at full lock.
5. **Electrical**: Install **relay(s)**, **fuses**, and **power/ground** runs; terminate with strain relief and **labeled** circuits where helpful.
6. **Initial checkout**: At idle, confirm **fan operation** at the expected temperature and that **current draw** does not sag supply voltage dangerously.

## Stress test before daily trust

After installation, **prove** cooling under load:

- **Idle** with the engine fully warm; confirm **fan cycles** or runs as designed and **temperature stabilizes**.
- **Road load**: sustained cruise, then **grade** or hard acceleration segments that heat-soak the cooling system.
- **A/C**: if equipped, repeat **idle and low-speed** conditions with **A/C on**; the **condenser** needs airflow through the stack.

Watch for **creep past normal**, **boil-over**, or **rapid temperature rise** in traffic. If any occur, fix **airflow** (fan, shroud, seal) or **control** (turn-on earlier, higher duty cycle, dual fans) before relying on the truck.

## Sources consulted

- [S-10 Forum — water pump pulley removal](https://www.s10forum.com/threads/water-pump-pulley-removal.851265/) — community techniques for holding the pulley while servicing the front drive.
- [S-10 Forum — remove clutch fan](https://www.s10forum.com/threads/remove-clutch-fan.851497/) — discussion of mechanical fan removal (confirm tool sizes in your manual).
- [Grassroots Motorsports — converting an S10 to an e-fan](https://grassrootsmotorsports.com/forum/grm/converting-an-02-s10-to-an-e-fan-queations/66851/page1/) — general e-fan conversion discussion (thread mixes contexts; filter for applicability to your year/engine).
- [S-10 Forum — eliminating stock fan / electric fan threads](https://www.s10forum.com/threads/eliminating-stock-fan-adding-electric-horsepower.858170/) — community experience on motivation and expectations.
- **Manuals**: Chevrolet S10 **2.2L** factory service manual (Helm) and/or Haynes/Chilton — use for **torque, wire diagrams, and routing**; cross-check critical values when possible.

## Disclaimer

This document is **not** official General Motors documentation. Verify **part numbers**, **torques**, **wire colors**, and **procedures** against **2.2L** service information for your vehicle. Use at your own risk.
