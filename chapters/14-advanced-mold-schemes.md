# Chapter 14: Advanced Schemes — Taller Molds, Three Supports, Silicon Molds, 4F² & 3D DRAM

## Overview

Every DRAM generation asks the capacitor for the same charge on a smaller footprint. The pillar must grow taller, or thinner, or both, and every step in that direction is a step toward the collapse threshold of Chapter 10. This chapter looks at the schemes that extend the mold etch: taller molds with a third support, sequential removal that dries the forest in stages, molds made of materials other than oxide, and the very different mold-removal problems of 4F² vertical-channel and 3D DRAM.

**Learning Objectives:**
- Compute the collapse margin of a taller mold with two and three supports
- Explain sequential (two-dip) mold removal and its trade-offs
- Compare silicon and carbon molds removed by dry etch with oxide molds removed by HF
- Describe how mold removal changes for 4F² capacitors and for lateral capacitors in 3D DRAM

---

## 14.1 Taller Molds

### 14.1.1 The Capacitance Case

```
Capacitance gain from height (d = 28 nm, EOT 0.50 nm, supports 190 nm):
  Mold 1.60 µm → H_eff 1.41 µm → 8.6 fF
  Mold 2.00 µm → H_eff 1.81 µm → 11.0 fF (+28%)
  Mold 2.00 µm with a third 50 nm support → H_eff 1.76 µm → 10.7 fF
```

Alternatively, the taller mold holds the capacitance constant while the pillar shrinks with the pitch at the next node.

### 14.1.2 The Mechanics

```
2.0 µm mold, two supports (middle support placed for equal spans):
  spans ≈ (2000 − 120 − 50 − 20) / 2 = 905 nm each
  margin relative to reference: (760/905)⁴ = 0.50 → IPA pair margin 1.38
  P (lognormal model) ≈ 3 × 10⁻²  → unusable with IPA

2.0 µm mold, three supports (two middle supports, 50 nm each):
  spans ≈ (2000 − 120 − 100 − 20) / 3 = 587 nm each
  margin: (760/587)⁴ = 2.81 → IPA pair margin 7.8 → P ≈ 0

2.0 µm mold, two supports, supercritical drying:
  no capillary load; stress and van der Waals only
```

A third support is the mechanical answer; supercritical drying is the process answer. Each has costs. The third support takes 50 nm of capacitor height, adds a step to the hole etch (Book #29), and adds a second middle-support breakthrough to the support open, at a greater depth and aspect ratio. Supercritical drying adds tool cost and time.

### 14.1.3 The Support Open at Greater Depth

With two middle supports, the support-open column must reach through the top support, the upper oxide, the first middle support, a second oxide, and the second middle support. At 50 nm opening CD and a depth near 1.4 µm, the aspect ratio approaches 30, and the second middle-support breakthrough happens in lean chemistry deep in the column, with TiN crescents exposed for the whole time. TiN top loss rises toward 7–8 nm unless the opening is widened, which reduces the solid fraction of every support.

---

## 14.2 Sequential (Two-Dip) Removal

### 14.2.1 The Idea

Instead of opening both supports and removing all oxide at once, remove the mold in two stages:

```
Sequential scheme:
  1. Support open through the top support only
  2. Dip 1: HF removes the upper oxide down to the middle support
  3. Dry (the forest is still embedded in the lower oxide below
     the middle support; only the upper span is free)
  4. Support open through the middle support (a second plasma etch,
     through the openings of the top support, now in a free forest)
  5. Dip 2: HF removes the lower oxide
  6. Dry (full forest free)
```

### 14.2.2 Benefits

- During dip 1, the lower half of each pillar is embedded: the upper span is a short, well-supported beam
- Each plasma step is shallower, with lower TiN loss per step
- The middle-support breakthrough can be optimized separately

### 14.2.3 Costs

- Two dips, two dries, two plasma etches: roughly twice the module cost
- The second plasma etch runs through a free-standing upper forest: ions and charging act on free pillars, and polymer deposits on their now-exposed outer surfaces
- The second dip re-wets the upper forest, so the upper span is dried twice

Sequential removal is used where a single dip cannot be dried safely and supercritical drying is not available, or as a development path toward three-support molds.

---

## 14.3 Silicon and Carbon Molds

### 14.3.1 Why Change the Mold Material

An oxide mold forces an HF dip and a liquid dry. A mold that can be removed by a dry, isotropic etch removes the capillary problem altogether, as vapor HF does, but without vapor HF's residues.

```
Mold material options:
  Material       Removal                    Selectivity to TiN, SiN    Issue
  ──────────────────────────────────────────────────────────────────────────
  SiO₂ (ref.)    Liquid / vapor HF          Very high                  Drying
  Poly-Si/a-Si   Remote F radicals (NF₃),   High to TiN (TiF₄ involatile),  Hole etch in Si
                 XeF₂, or TMAH (wet)        moderate to SiN             is harder; F
                                                                         attacks SiN
  Amorphous C    Remote O₂ or H₂/N₂ plasma  High to SiN; O₂ oxidizes    Carbon hole etch;
                                            TiN → use H₂/N₂             thermal budget
                                                                         for TiN fill
  SiGe           Selective vapor/wet etch   High to Si; to TiN good     Integration
```

### 14.3.2 Silicon Mold

A silicon mold is etched with Cl₂/HBr-type chemistry in the hole etch (with very different ARDE and selectivity from Book #29), filled with TiN, and removed by remote fluorine radicals:

```
Remote NF₃ removal of a-Si (illustrative):
  a-Si rate ≈ 1–3 µm/min (isotropic, radical-limited)
  SiN rate ≈ 1–5 nm/min (needs a resistant support material, e.g. SiCN)
  TiN rate ≈ 0.1–0.5 nm/min (TiF₄ passivation)
  No liquid; no capillary force
```

The obstacles are upstream: etching a 50:1 hole in silicon, at 45 nm hexagonal pitch, with straight walls, is a different and in some respects harder problem than in oxide; and the TiN fill on a silicon wall can form TiSiₓ at the interface.

### 14.3.3 Carbon Mold

A carbon mold is etched with O₂-based chemistry, filled at a temperature compatible with the carbon, and removed with a reducing plasma. It avoids fluorine at the TiN surface. It is limited by the thermal budget (carbon films change at the TiN fill temperature) and by mechanical strength of the mold during the hole etch.

---

## 14.4 4F² Vertical-Channel DRAM

In a 4F² cell with a vertical channel transistor, the storage node sits directly above the channel on a square or near-square lattice of pitch 2F. At F = 15 nm, the pitch is 30 nm and the cell area 900 nm², about half the 6F² reference:

```
4F² capacitor (illustrative):
  Pitch 30 nm (square), pillar 18 nm, gap 12 nm
  For C_s = 8 fF at EOT 0.45 nm: area 1.04 × 10⁵ nm² → H_eff ≈ 1.84 µm
  Slenderness ≈ 100 (mold ≈ 2.1 µm)
  Stiffness ∝ d⁴: (18/28)⁴ = 0.17 of the reference
  Load ∝ d/g: (18/12)/(28/17) = 0.91 of the reference
  g/8 threshold: 1.5 nm (vs 2.1)
  For equal margin, spans must shrink by [0.17 × 1.5/2.1 / 0.91]^(1/4) = 0.61
  → spans ≈ 460 nm → four spans, three middle supports, in a 2.1 µm mold
```

4F² capacitors therefore need either more supports, supercritical drying as standard, or a different capacitor form, such as a capacitor-over-channel with a wider bottom electrode or a stacked multi-tier mold where each tier is removed and dried separately.

---

## 14.5 3D DRAM

In 3D DRAM, the cell array is stacked in tiers, and the capacitor lies horizontally in each tier rather than standing vertically. The "mold" becomes a stack of sacrificial layers, often Si or SiGe alternating with Si or oxide, cut by vertical slits:

```
3D DRAM lateral capacitor (schematic):
  Tier n:   transistor ─── capacitor (horizontal) ─── plate
  Mold:     sacrificial layer between active layers
  Removal:  lateral recess from a slit, hundreds of nanometres deep,
            in every tier at once
```

The mold etch becomes a lateral, highly selective recess (for example, SiGe selective to Si, or oxide selective to Si) through tens of tiers. The structures that must not collapse are now horizontal beams and plates, not vertical pillars: a released silicon layer 10–20 nm thick and hundreds of nanometres long can sag onto the layer below under capillary force exactly as a pillar bends onto its neighbour. The same elastocapillary analysis applies, with the plate span and thickness in place of pillar length and diameter, and the same remedies: supports (anchors in the stack), low-γ fluids, supercritical drying, and dry removal.

---

## Summary and Key Takeaways

1. **Taller molds need a third support or no meniscus.** A 2.0 µm mold with two supports has an IPA margin of about 1.4; with three supports, about 7.8.

2. **Sequential removal trades cost for safety.** Two dips, two dries, two plasma etches.

3. **Dry-removable molds abolish drying.** Silicon and carbon molds move the difficulty upstream into the hole etch and fill.

4. **4F² pillars are about six times more flexible.** Spans must shrink to about 460 nm, three middle supports in a 2.1 µm mold.

5. **3D DRAM turns pillars into plates.** The same elastocapillary rules apply to lateral releases in stacked tiers.

---

## Study Questions

1. For a 2.0 µm mold with two supports, find the middle-support position and the IPA pair margin. What collapse probability does the lognormal model give?

2. Compare the module cost of (a) a three-support mold with IPA drying and (b) a two-support mold with supercritical drying, using the cost elements of Chapter 16.

3. Why does remote NF₃ etch amorphous silicon much faster than TiN? What support material would you choose for a silicon mold?

4. Derive the span needed for a 4F² pillar of 18 nm diameter at 30 nm pitch to match the reference IPA margin.

5. A released 15 nm silicon plate in a 3D DRAM tier spans 400 nm between anchors with a 20 nm gap below. Using plate bending under a uniform IPA meniscus load, estimate its deflection and compare it with the gap.

---

**Next Chapter:** [Chapter 15: Metrology, Inspection & Advanced Process Control](./15-metrology-inspection-apc.md)

---

**Chapter 14 Development Status:** Complete  
**Version:** 1.0
