# Chapter 8: Rinse & Drying Systems

## Overview

The forest survives the HF. It is the drying that decides whether it stands. As the last liquid leaves the gaps between pillars, menisci form between neighbours and pull on them with a pressure set by the surface tension of the liquid and the width of the gap. In a 17 nm gap filled with water, that pressure is about 8.5 MPa. If the meniscus on one side of a pillar recedes before the meniscus on the other side, the pillar is pulled sideways. Chapter 10 develops the mechanics. This chapter describes the systems that keep the force small enough: displacement of water by a low-surface-tension solvent, heated and vapor-assisted drying, surface modification, and supercritical drying, which removes the meniscus altogether.

**Learning Objectives:**
- Compute the Laplace pressure in a gap for water, IPA, and fluorinated solvents
- Explain the role of meniscus asymmetry in the lateral force on a pillar
- Design an IPA displacement step that leaves no water in the gaps
- Describe spin, Marangoni, and supercritical CO₂ drying, and their equipment
- Choose a drying method from the structure's collapse margin

---

## 8.1 The Capillary Force

### 8.1.1 Laplace Pressure in a Gap

A liquid wetting the walls of a gap of width g with contact angle θ has a meniscus whose pressure is lower than the gas above it by

```
ΔP = 2γ cos θ / g        (slit approximation)

g = 17 nm, θ = 0:
  Water (γ = 0.072 N/m)             ΔP = 8.5 MPa
  IPA, 25 °C (γ = 0.0217)            ΔP = 2.6 MPa
  IPA, 50 °C (γ = 0.0198)            ΔP = 2.3 MPa
  HFE-type solvent (γ ≈ 0.0136)      ΔP = 1.6 MPa
  Supercritical CO₂                  ΔP = 0 (no interface)
```

### 8.1.2 Asymmetry Is What Bends

A pillar wetted equally on all sides feels the same pressure from every direction and does not bend. It bends when the menisci around it are at different heights or have different curvatures, as happens whenever a drying front passes through the forest. Chapter 10 writes the unbalanced load on a pillar of diameter d as

```
q = α · ΔP · d        (force per unit length along the pillar)
```

where α is an effective fraction of the full pressure that is unbalanced, averaged over the span. α = 1 is the worst case: liquid on one side only, over the whole span. A drying front passes down the gaps, so at any moment only part of the span carries an unbalanced meniscus; observation and simulation of orderly fronts in pillar arrays suggest effective α of about 0.1–0.2. Disturbances (vibration, a jet, a droplet, a local dry spot) push α toward 1 locally.

### 8.1.3 What the Supports Allow

Chapter 10 derives the deflection of the lower free span (760 nm, clamped at both ends) and the collapse threshold. Two neighbouring pillars pulled toward each other close their gap from both sides, and the capillary force grows as the gap closes; the pair becomes unstable when the linear deflection of each pillar exceeds one-eighth of the gap (2.1 nm). The reference numbers, for the orderly-front value α = 0.15 and the full-asymmetry worst case:

```
Linear deflection of the 760 nm span (d = 28 nm, E = 400 GPa):
  Fluid             α = 0.15     α = 1        Pair margin (g/8 ÷ δ at α = 0.15)
  ──────────────────────────────────────────────────────────────────────────
  Water             2.6 nm       17.1 nm      0.83 → pairs collapse
  IPA, 25 °C        0.77 nm      5.2 nm       2.8
  IPA, 50 °C        0.70 nm      4.7 nm       3.0
  HFE solvent       0.48 nm      3.2 nm       4.4
  Supercritical     0            0            —
```

Water drying would collapse the forest even with an orderly front. IPA has a margin of about three, which disappears where the front is disturbed (α above about 0.4). The design of the drying system is the management of α and γ.

---

## 8.2 Displacing Water with IPA

### 8.2.1 Why the Displacement Must Be Complete

Water and IPA are miscible, and the surface tension of a mixture falls steeply with the first IPA added but approaches pure IPA only at high IPA content:

```
Surface tension of IPA–water mixtures, 25 °C (approximate):
  wt% IPA      0     10     30     50     70     90     100
  γ (mN/m)     72    42     30     26     24     22.5   21.7
```

A gap that still holds 30% water dries at γ ≈ 24–30 mN/m instead of 21.7, and more importantly, as the IPA evaporates first (it is more volatile), the last liquid in the gap becomes water-rich. Drying a gap with 10% residual water ends with a water-rich meniscus near 40–60 mN/m.

### 8.2.2 Displacement Kinetics

Exchange of water by IPA in the gaps is limited by the film above the wafer, as for the rinse (Chapter 6). Diffusion in the gaps is fast (milliseconds), but the film must reach a low water content:

```
Target: < 1% water in the film at the start of drying
Film exchange time at 0.8 L/min IPA ≈ 0.25 s
Needed exchanges (well-mixed): ln(100) ≈ 5 → ≈ 1.3 s ideal
Practical: 20–40 s, because of recirculation, bevel, back-side,
           and the transition from rinse (DIW must not re-enter)
```

### 8.2.3 Heated IPA

Heating IPA to 50–70 °C lowers γ by 10–15% and lowers viscosity, which improves displacement. It also raises evaporation and the risk of a drying front forming early at the edge, and in a chamber that also handles HF it raises fire risk. Most dip-out chambers run IPA at 25–50 °C.

---

## 8.3 Spin Drying

After displacement, the wafer is accelerated (for example 300 → 1500 rpm) with an N₂ flow, sometimes carrying IPA vapor, over the surface. The film thins under centrifugal flow and evaporation until it breaks. The breakup front then moves from the centre to the edge.

```
Spin-dry front design points:
  - Start the front at the centre with an N₂ jet so that it moves
    outward in one direction (a single orderly front, α small)
  - Move the N₂ nozzle outward behind the front at a rate matched to
    the front speed (≈ 2–5 mm/s)
  - Supply IPA vapor ahead of the front to suppress early breakup
    in the outer region
  - Avoid droplets left behind the front: each droplet dries alone,
    with α near 1 at its perimeter
```

The most damaging events in spin drying are droplets and secondary fronts: a film that breaks in two places at once creates a region of liquid surrounded by drying forest, which dries inward with the full asymmetry at its boundary.

---

## 8.4 Marangoni Drying

Marangoni drying exploits the surface-tension gradient created when IPA vapor dissolves into the water meniscus. The meniscus at the drying line becomes IPA-rich and has lower surface tension than the bulk water, which pulls liquid back from the drying line into the bulk and leaves the surface nearly dry as it emerges.

```
Marangoni drying:
  Vertical withdrawal from DIW at ≈ 1–2 mm/s
  IPA vapor in N₂ over the meniscus
  Water film left behind ≈ nm-scale (evaporates)
```

In a pillar forest, Marangoni drying still forms menisci in the gaps as the wafer emerges; their composition is IPA-enriched water rather than pure IPA, so γ is higher than in an IPA-displaced spin dry. The front, however, is very orderly (low α). Marangoni dryers are used in batch tools (Chapter 6) and some single-wafer tools with a horizontal equivalent.

---

## 8.5 Surface Modification

Since ΔP ∝ cos θ, making the surfaces less wettable reduces the force. Silylating agents (for example HMDS-type or chlorosilane chemistries) render oxide and nitride hydrophobic (θ ≈ 70–90°), cutting cos θ to 0.0–0.3. Three obstacles limit this in DRAM:

1. **TiN.** The pillar is TiN, whose surface hydroxyls are fewer and less reactive than on oxide; silylation coverage is partial.
2. **Removal.** The modifying layer must be removed before the dielectric ALD, which needs a clean, hydroxylated TiN surface for nucleation. Removal by UV-ozone or plasma oxidizes the TiN.
3. **Particles and residues.** Silylation by-products in nanometre gaps are hard to rinse.

Surface modification is used in some flows as an enhancement to IPA drying, with careful removal; it is not a substitute for low γ.

---

## 8.6 Supercritical CO₂ Drying

### 8.6.1 Principle

Above its critical point (31.0 °C, 7.38 MPa), CO₂ is a single fluid phase with no liquid–gas interface. A structure filled with supercritical CO₂ can be dried by venting it without ever forming a meniscus.

```
Supercritical drying sequence (reference):
  1. Wet transfer: wafer arrives covered in IPA (never dry)
  2. Load into the high-pressure vessel; close
  3. Fill with liquid or supercritical CO₂ to ≈ 10–15 MPa at 35–60 °C
  4. Flush: CO₂ replaces IPA (IPA is miscible with SC-CO₂)
     until IPA in the vessel < 0.1–1%
  5. Vent slowly while above the critical temperature
     (the fluid expands to gas without crossing the liquid line)
  6. Unload dry
  Cycle ≈ 3–6 min per wafer
```

### 8.6.2 What Can Go Wrong

- **Incomplete IPA removal.** If IPA remains in the gaps when the vessel is vented, the residual IPA–CO₂ mixture can cross the two-phase region and form menisci. The flush must reduce IPA in the gaps, not only in the vessel.
- **Temperature drop during venting.** Expansion cools the fluid; if it falls below the critical temperature at a pressure above the vapor curve, liquid CO₂ condenses. Venting is rate-limited and heated.
- **IPA drying before loading.** The transfer from the wet chamber to the supercritical vessel must keep the wafer under a puddle of IPA. Any dry spot at the edge dries with an IPA meniscus.
- **Particles and extracted contamination.** SC-CO₂ dissolves organics and some residues; they redeposit if the flush is too short.

### 8.6.3 Equipment

Single-wafer supercritical dryers are integrated on the wet platform: the wet chamber performs HF, rinse, and IPA, and a robot transfers the IPA-covered wafer to the vessel. A high-pressure vessel holds 15–20 MPa and has a small free volume (≈ 100–300 mL) to keep CO₂ use and flush time low. Throughput is lower than spin drying, so platforms carry one supercritical vessel per one to two wet chambers.

---

## 8.7 Choosing the Drying Method

```
Pair collapse margin (g/8 ÷ linear deflection at α = 0.15, IPA 25 °C)
  > 4      IPA spin dry, standard
  2–4      IPA spin dry with N₂/IPA-vapor front control; heated IPA
  1–2      Supercritical CO₂, or HFE-solvent displacement + spin dry
  < 1      Supercritical CO₂ mandatory; vapor-HF finishing (Chapter 7)

Reference structure: margin 2.8 → IPA spin dry with front control
A 2.0 µm mold with a 1000 nm lower span: margin ≈ 0.9 → supercritical
```

---

## Summary and Key Takeaways

1. **Water would collapse the forest.** 8.5 MPa in a 17 nm gap; 2.6 nm deflection even with an orderly front, beyond the 2.1 nm pair threshold.

2. **IPA gives a margin of about three.** It is consumed by disturbances that push α toward 1.

3. **Displacement must be complete.** Residual water makes the last meniscus water-rich.

4. **One orderly front.** Droplets and secondary fronts dry with full asymmetry.

5. **Supercritical CO₂ removes the meniscus.** At a cost in time, equipment, and care with IPA removal and venting.

---

## Study Questions

1. Compute ΔP for a gap that narrows to 12 nm at the bow for water and for IPA. How does the bow change the collapse margin?

2. A film breaks at the edge before the centre front reaches it, leaving a ring 5 mm wide of liquid between two fronts. What α would you expect at the inner and outer boundaries? Why are edge rings common?

3. The IPA film still contains 5% water at the start of drying. Estimate the composition and surface tension of the last 10% of the liquid to evaporate, given that IPA evaporates preferentially.

4. A supercritical dryer vents from 12 MPa to 0.1 MPa. Sketch the path on the CO₂ phase diagram that avoids liquid formation, and estimate the heat that must be supplied to keep the fluid above 31 °C.

5. Using the table in Section 8.1.3, at what α does IPA at 25 °C reach the collapse threshold? What physical events could produce such an α?

---

**Next Chapter:** [Chapter 9: Chemical Delivery, Filtration, Particles & Defects](./09-chemical-delivery-defects.md)

---

**Chapter 8 Development Status:** Complete  
**Version:** 1.0
