# Chapter 1: The Pillar Capacitor & Why the Mold Must Go

## Overview

A DRAM cell stores a bit as charge on a capacitor. In a modern 6F² array, that capacitor is a tall, thin conductor standing on a landing pad, covered by a high-k dielectric and wrapped in a top electrode. In the reference process of this book, the bottom electrode is a solid titanium nitride pillar 1.6 µm tall and 28 nm wide on average. It is formed by filling the capacitor hole of Book #29 with TiN. At that moment the pillar is still buried in the oxide mold that the hole was cut into. The capacitor does not yet exist, because its area, the outer surface of the pillar, is covered.

The mold etch removes the mold. This chapter explains why the outer surface is the capacitor, describes the geometry of the pillar forest that results, shows where the mold etch sits in the process flow, and sets out the specification sheet that the rest of the book works against.

**Learning Objectives:**
- Compute the sense signal and the capacitance needed from the cell
- Explain why a single-sided pillar capacitor needs its mold removed
- Compute the capacitance of the reference pillar from its exposed area
- Describe the pillar forest: height, diameter, gap, slenderness, and pillar count
- List the steps of the mold etch module and the specification each must meet

---

## 1.1 The Cell and Its Charge

### 1.1.1 The Sense Signal

When a word line opens the access transistor, the storage capacitor C_s shares its charge with the bit line, which has capacitance C_BL and is precharged to half the array voltage. The bit-line voltage moves by

```
ΔV_BL = (V_core/2) · C_s / (C_s + C_BL)

Reference: V_core = 1.10 V, C_BL = 40 fF, C_s = 8.6 fF
  ΔV_BL = 0.55 × 8.6 / 48.6 = 97 mV
```

The sense amplifier needs a margin over its offset, the coupling noise, and the charge lost to leakage before refresh. In practice the cell must deliver ΔV_BL above about 80–90 mV at the end of the retention period, which sets a floor on C_s near 8 fF for the reference bit-line loading.

### 1.1.2 Capacitance Has Not Shrunk

The cell footprint has shrunk roughly as F² for three decades. The bit line has become shorter, but not by enough to let C_s fall in proportion. The capacitor has kept its 8–10 fF by growing upward. The 6F² cell in the reference process has a footprint of 1734 nm², about the area of a square 42 nm on a side, and yet carries about 1.2 × 10⁵ nm² of capacitor area. The capacitor area is seventy times the footprint, all of it vertical.

---

## 1.2 From Hole to Pillar

### 1.2.1 Two Ways to Use a Hole

The capacitor hole can become a capacitor in two ways:

```
Cylinder (inner surface)                 Pillar (outer surface)
─────────────────────────                ────────────────────────
TiN lines the hole (≈ 5 nm)              TiN fills the hole
Dielectric and plate inside the liner    Mold removed; dielectric and
                                         plate wrapped around outside
Area ≈ π (d − 2t_TiN) H                  Area ≈ π d H
Mold may stay (one-sided cylinder)       Mold must go
or be removed (double-sided cylinder)
```

At large pitch, the cylinder was the obvious choice: line the hole, then form the dielectric and plate inside. At the reference 28 nm average diameter, a cylinder with a 5 nm TiN liner leaves an 18 nm opening to fill with 5–6 nm of dielectric and a plate from both sides; the inside is nearly gone. The pillar uses the whole outer diameter instead. It gives up the inside but gains the outside, which is larger.

### 1.2.2 The Outer Surface

For a pillar, the capacitor is the outer surface of the TiN after the mold has gone. The parts of that surface still clamped by nitride supports, or still covered by residual oxide, do not count:

```
Exposed height:
  H_eff = H_mold − t_top − t_mid − t_bottom
        = 1600 − 120 − 50 − 20 = 1410 nm

Exposed area (average diameter):
  A = π · d_avg · H_eff = π × 28 × 1410 = 1.240 × 10⁵ nm²

Capacitance:
  C_s = ε₀ · 3.9 · A / EOT
      = 8.854×10⁻¹² × 3.9 × 1.240×10⁻¹³ / 0.50×10⁻⁹
      = 8.6 fF
```

The supports cover 13% of the pillar height. The openings in the top and middle supports uncover a little of that, which Chapter 2 treats; it is ignored here.

### 1.2.3 What Covered Area Costs

A residual film of oxide on part of a pillar does not just lose that area: it puts a thick low-k layer in series with the high-k dielectric. For a film of thickness t_ox on a fraction f of the area:

```
Local EOT with residue = EOT + t_ox
Capacitance of that area falls by factor EOT/(EOT + t_ox)

Example: t_ox = 2 nm, EOT = 0.5 nm → factor 0.20 (80% lost there)
  Residue on 5% of the area → C_s falls by 0.05 × 0.80 = 4%
                            → 8.6 fF → 8.26 fF
```

A 4% loss is roughly what a whole generation of dielectric work buys back. Residual oxide is therefore a capacitance defect, not a cosmetic one. Chapter 12 treats where it forms.

---

## 1.3 The Pillar Forest

### 1.3.1 Geometry

```
Reference pillar and array:
  Lattice                  hexagonal, pitch a = 45 nm
  Cells per µm²            1/1734 nm² = 577
  Pillar diameter          32 (top) / 28 (avg) / 24 (bottom) nm
  Pillar height            1600 nm (top of top support to top of pad)
  Gap to neighbour         45 − 28 = 17 nm (average)
                           45 − 32 = 13 nm (top)
                           45 − 33.5 = 11.5 nm (at the bow, 350 nm depth)
  Slenderness H/d_avg      57
  Pillar area fraction     π(14)²/1734 = 0.355
```

Each pillar has six nearest neighbours at 45 nm. The 17 nm average gap is filled with oxide before the mold etch and with dielectric, plate TiN, and fill afterwards. During the few seconds of drying in between, it is filled with liquid and then with gas.

### 1.3.2 How Much Oxide

```
Oxide per µm² of array (both oxide layers):
  thickness   = 650 + 760 = 1410 nm
  fraction    = 1 − 0.355 = 0.645
  volume      = 1.41 µm × 0.645 = 0.91 µm³ per µm² of array

Per 300 mm wafer, array area ≈ 55% of 700 cm² ≈ 385 cm²:
  volume ≈ 0.91 × 10⁻⁴ cm × 385 cm² = 0.035 cm³ ≈ 80 mg of SiO₂
```

Eighty milligrams of oxide is trivial for an HF bath. The challenge is not the quantity but the geometry: the oxide fills a connected network of 17 nm gaps, and HF must reach all of it through openings in two nitride sheets.

### 1.3.3 Why the Pillar Cannot Stand Alone

A solid TiN pillar 28 nm wide and 1.6 µm tall is an extremely slender cantilever. Chapter 10 shows that a water meniscus pulling on one side would bend an unsupported pillar by micrometres, far beyond the 17 nm gap. Even the van der Waals and electrostatic forces present in a dry environment are enough to bend it into contact. The supports exist because the pillar would not otherwise survive the removal of the mold.

```
Pillar spans (reference):
  Bottom: clamped in the 20 nm bottom stop and the pad
  Lower free span:  760 nm (bottom-stop top to middle-support bottom)
  Middle support:   50 nm
  Upper free span:  650 nm (middle-support top to top-support bottom)
  Top support:      120 nm
```

Chapter 10 models each free span as a beam clamped at both ends. Stiffness against a lateral load scales as d⁴/L⁴. The lower span, at 760 nm, is the weakest.

---

## 1.4 Where the Mold Etch Sits

### 1.4.1 The Capacitor Module

```
Capacitor module flow (reference):
  1. Mold deposition (SiN / BPSG / SiN / PE-TEOS / SiN)          (Book #29)
  2. ACL hard mask, honeycomb patterning, mask open               (Book #29)
  3. Capacitor hole etch                                          (Book #29)
  4. Strip, clean
  5. TiN bottom electrode CVD (fill)
  6. Top isolation: TiN CMP or etch-back to the top support
  ─────────────────────── this book ───────────────────────
  7. Support-open mask: ACL + SiON, patterning, mask open
  8. Support-open plasma etch: top SiN → upper oxide → middle SiN
  9. Mask strip (O₂ plasma), post-etch clean
 10. Mold dip-out: HF, rinse, IPA, dry
  ──────────────────────────────────────────────────────────
 11. High-k dielectric ALD (ZrO₂/Al₂O₃/ZrO₂ class)
 12. TiN top electrode, plate fill (SiGe or W), plate pattern
```

### 1.4.2 The Support-Open Step

The support-open mask defines a lattice of openings, each 50 nm wide, on a 90 nm hexagonal pitch. Each opening is centred on an interstitial site of the pillar lattice. The nearest three pillars are 26 nm from the opening centre, so each opening uncovers a crescent at the edge of three pillar tops. The plasma etches through the top SiN (120 nm), the upper oxide (650 nm), and the middle SiN (50 nm), stopping about 50–100 nm into the lower oxide. The pillar crescents exposed in the opening see the full etch.

### 1.4.3 The Dip-Out

HF enters through the openings and removes the upper oxide around them, then the lower oxide below the middle support. The farthest point of oxide from an opening edge is

```
r_far = a_SO/√3 − d_SO/2 = 90/√3 − 25 = 52 − 25 = 27 nm (laterally)
```

so the lateral distance is short. But that oxide may be up to 760 nm below the middle-support opening, in gaps 17 nm wide. Chapter 4 shows that, perhaps surprisingly, diffusion through those gaps is fast; the dip time is set by the etch rate along the longest path, and the real transport risks are wetting and trapped gas.

### 1.4.4 Rinse and Dry

The acid is displaced by water, the water by isopropyl alcohol, and the wafer is spun dry. The drying front passes through the forest once. Chapter 8 and Chapter 10 treat the forces it applies.

---

## 1.5 The Specification Sheet

```
Mold etch module specification (reference, illustrative):

Support-open etch
  Opening CD at top-support top         50 ± 3 nm
  Opening CD at middle-support bottom   ≥ 40 nm on every opening
  Nitride residue in openings           none (0 slivers per 10⁹ openings)
  Landing depth into lower oxide        50–150 nm
  TiN top loss in exposed crescents     ≤ 5 nm
  Top-support remaining thickness       ≥ 100 nm (after mask strip)

Dip-out
  Residual oxide                        none detectable; ≤ 0.3 nm average
  Support SiN loss (each exposed face)  ≤ 3 nm
  Bottom SiN stop remaining             ≥ 15 nm everywhere
  TiN surface oxide after dry           ≤ 1.0 nm TiOₓ equivalent
  Fluorine on TiN surface               ≤ 3 at% (XPS)

Drying / structure
  Leaning pillars                       ≤ 1 per 10⁹ pillars (≈ 17 per 16 Gb die)
  Support cracks / released regions     0 per wafer
  Particles added (> 30 nm)             ≤ 10 per wafer

Electrical (after dielectric and plate)
  C_s                                   ≥ 8.3 fF (mean 8.6 fF)
  Pillar-to-pillar shorts               within repair budget
  Leakage at 1.0 V                      ≤ 1 fA per cell (median)
```

Each line corresponds to a chapter. The leaning specification deserves emphasis: with about 1.7 × 10¹⁰ pillars per die and redundancy for a few thousand failed cells, the module must keep leaning pairs to tens per die, or about one pillar in a billion.

---

## 1.6 What Makes This Module Different

1. **Structural yield.** The module can be chemically perfect and still fail mechanically.
2. **Two etch regimes in sequence.** A plasma etch with ion-driven selectivity and a wet etch with transport-limited removal.
3. **Removal must be complete, and loss must be near zero.** Both residual oxide and nitride loss are measured in single nanometres.
4. **The surface becomes the device.** The TiN surface the dip-out leaves is the interface of the capacitor dielectric.

---

## Summary and Key Takeaways

1. **The capacitor is the outside of the pillar.** C_s ≈ 8.6 fF from 1.24 × 10⁵ nm² of exposed TiN, 1410 nm of exposed height.

2. **Residual oxide is lost capacitance.** 2 nm of oxide on 5% of the area costs 4% of C_s.

3. **The pillar is slender.** H/d = 57, gap 17 nm, 577 pillars per µm². It cannot stand without supports.

4. **The module has three parts.** Support open (plasma), dip-out (HF), and drying. Each has its own specification.

5. **Leaning must be about one in a billion.** That is the number that sets the drying and the support design.

---

## Study Questions

1. Compute ΔV_BL for C_s = 8.0 fF and for C_s = 9.2 fF with C_BL = 40 fF and V_core = 1.10 V. What change in exposed height gives the same ΔV_BL improvement as raising C_s from 8.0 to 9.2 fF?

2. If the middle support were removed entirely (and the pillar somehow stood), how much would C_s increase? What does the support cost in capacitance as a fraction?

3. Residual oxide 1 nm thick covers the bottom 100 nm of every pillar. Estimate the loss of C_s.

4. Compare the capacitor area of a cylinder with a 5 nm TiN liner (inner surface only) and a solid pillar, both in a 28 nm average hole with H_eff = 1410 nm. Which is larger, and by how much?

5. The support-open pattern is changed to 56 nm openings on a 90 nm lattice. What is the new open-area fraction and the new farthest lateral distance to oxide?

6. With 1.7 × 10¹⁰ pillars per die and a budget of 40 repairable failed cells from leaning, what leaning probability per pillar is allowed if every leaning event involves a pair?

---

**Next Chapter:** [Chapter 2: The Post-Electrode Structure, Support Lattice & Support-Open Pattern](./02-post-electrode-structure-support-lattice.md)

---

**Chapter 1 Development Status:** Complete  
**Version:** 1.0
