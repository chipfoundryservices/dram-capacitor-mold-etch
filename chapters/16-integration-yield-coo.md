# Chapter 16: Post-Dip-Out Integration, Yield & Cost of Ownership

## Overview

The forest that leaves the dip-out has a short life as a free-standing structure. Within hours it is coated with a high-k dielectric, then a top electrode, then a plate fill that locks every pillar in place. Each of those steps depends on what the mold etch delivered, and each can still damage the forest. This chapter follows the wafer through the rest of the capacitor module, sets out the yield signatures that trace back to the mold etch, and builds a cost model for the module.

**Learning Objectives:**
- Describe the dielectric, top electrode, and plate fill as customers of the dip-out
- Explain how the plate fill loads the forest and where it can cause late leaning
- Translate leaning, residual oxide, and electrode defects into failed cells and die yield
- Build a cost-of-ownership model for the support open, dip-out, and drying
- Compare the cost of drying options with the value of the yield they protect

---

## 16.1 Queue Time and the Dielectric

### 16.1.1 Queue Time

Chapter 13 set a queue-time limit of about 4 h in air, 12 h in nitrogen, between dry and dielectric ALD. The limit protects the TiN surface and also the forest: a free-standing forest in humid air can adsorb enough water in the narrowest gaps to form capillary bridges by capillary condensation (Chapter 7), and pillars that are already close can be pulled together days after a perfect dry.

### 16.1.2 Dielectric ALD

```
Dielectric (reference):
  ZrO₂/Al₂O₃/ZrO₂ (ZAZ) class, total ≈ 5.5 nm physical, EOT 0.50 nm
  ALD at 250–300 °C, conformal through 17 nm gaps and 1.6 µm depth
  Gap after dielectric: 17 − 2 × 5.5 = 6 nm
```

The dielectric must nucleate uniformly on the TiN. A surface with patchy fluorine, phosphorus residue, or silicate nucleates unevenly, producing thickness variation that shows up as leakage tails. The dielectric also sees the forest at its weakest: the ALD chamber heats the wafer, which changes the TiN and support stresses, and the first cycles occur with no mechanical reinforcement.

### 16.1.3 Top Electrode and Plate

```
Top electrode: TiN ALD/CVD ≈ 3 nm → gap 0 at the reference geometry
  (6 nm gap less 2 × 3 nm); the top electrode closes the gaps
Plate fill: B-doped SiGe (LPCVD, 400–450 °C) or W above the forest
```

The top electrode fills the remaining gaps. Any pair of pillars closer than about 11 nm before the dielectric (2 × 5.5) is bridged by dielectric alone and receives no top electrode between them, losing that area. Any pair closer than about 17 nm minus tolerance receives an incomplete top electrode with seams.

---

## 16.2 The Plate Fill and Late Leaning

### 16.2.1 Loading

The plate fill deposits above and around the forest. SiGe and W films carry intrinsic stress, and their thermal expansion differs from TiN and SiN. Inside the array the loads are symmetric and the pillars, now coated and filled, are mechanically locked. At the array edge and at large openings, the fill exerts a net lateral force on the outermost pillars.

### 16.2.2 Late Leaning

Pillars that survived drying with reduced margin, for example with an initial lean from the hole etch or a loosened collar, can lean during the dielectric or plate deposition. These defects are not visible at post-dip-out inspection, so the leaning seen at the end of the module is the sum of drying collapse and late leaning:

```
Leaning budget (illustrative, events per 10⁹ pillars):
  Drying collapse                       0.8
  Late leaning (dielectric, plate)      0.3
  Total at end of capacitor module      1.1
```

Separating them needs inspection both after the dip-out and after the plate, on the same wafers.

---

## 16.3 Yield Signatures

### 16.3.1 Cell-Level Failures

```
Mold-etch-related failures per 16 Gb die (illustrative, reference process):
  Mode                         Rate (per 10⁹)    Cells per die
  ──────────────────────────────────────────────────────────────
  Leaning pairs (2.2 cells)    1.1 events        ≈ 41
  Residual oxide (low C_s)     0.3 cells         ≈ 5
  Seam / top-loss leakage      2 cells           ≈ 34
  Total                                         ≈ 80
```

A typical DRAM die has spare rows and columns to repair a few thousand random cell failures. Eighty mold-etch-related cells are well within the repair budget. The yield risk is not the random rate but the clusters.

### 16.3.2 Cluster Failures

```
Cluster sources and size (illustrative):
  Collapse cluster from a droplet or particle      10–100 cells
  Support crack along a row                         100–1000 cells
  Residual-oxide cluster (blocked columns)         10–50 cells
  Array-edge peeling                                whole edge rows
```

A cluster larger than the repair resource in its sub-array kills the die. Die yield loss from clusters follows a Poisson model on the cluster density:

```
Y_cluster = exp(−D_c · A_die)

D_c = 0.02 per cm² (fatal clusters), A_die = 0.70 cm²
  Y = exp(−0.014) = 98.6%  → 1.4% yield loss from the mold etch
```

### 16.3.3 Retention Tails

Electrode surface defects (fluorine, TiOₓ, top loss) widen the distribution of cell leakage. They do not cause hard fails at test, but they increase the number of weak cells that need a shorter refresh interval or must be repaired after retention screening. A shift in the 10⁻⁶ tail of the retention distribution is often the first sign of a TiN surface problem.

---

## 16.4 Cost of Ownership

### 16.4.1 Support Open

```
Support-open etch (reference, per wafer):
  Tool: 4-chamber CCP platform, $6.0 M, 39 wafers/h, 85% uptime
    wafers/year = 39 × 8760 × 0.85 ≈ 290,000
    depreciation (5 years) = $6.0 M / 5 / 290,000 ≈ $4.1
  Consumables (electrode, ring, liners)               $1.5
  Gases, power, facilities                            $0.8
  Support-open mask (ACL, SiON, litho, mask open, strip) $18 (counted
    separately in litho/carbon modules; listed for reference)
  Etch subtotal                                       ≈ $6.4
```

### 16.4.2 Dip-Out and Dry

```
Single-wafer wet with IPA dry (reference, per wafer):
  Tool: 12-chamber platform, $8.0 M, 120 wafers/h, 85% uptime
    wafers/year ≈ 890,000 → depreciation ≈ $1.8
  HF (single pass, 2.6 L at $3/L)                     $7.8
  IPA (0.5 L at $5/L, partly reclaimed)               $1.5
  DIW, N₂, exhaust, waste treatment                   $1.2
  Subtotal                                            ≈ $12.3
  With HF reclaim (0.4 L net + $0.30 handling)        ≈ $6.0

Supercritical CO₂ drying (additional, per wafer):
  Tool: $5.0 M per 40 wafers/h → depreciation ≈ $3.4
  CO₂, power                                          $0.8
  Additional                                          ≈ $4.2

Vapor HF (instead of liquid, per wafer):
  Tool: $7.0 M, 35 wafers/h → depreciation ≈ $5.4
  Anhydrous HF, alcohol, abatement                    $6.0
  Residue bake                                        $0.8
  Subtotal                                            ≈ $12.2
```

### 16.4.3 Module Total

```
Module (support open + dip-out, IPA dry, HF reclaim):  ≈ $12 per wafer
  + supercritical drying                               ≈ $16 per wafer
  sequential (two-dip) scheme                          ≈ $24 per wafer
```

### 16.4.4 The Value of Yield

```
Value of a 16 Gb DRAM wafer (illustrative):
  ≈ 900 gross dies × 90% yield × $8 per die ≈ $6,500
  1% die yield ≈ $65 per wafer
```

The entire mold-etch module costs about a fifth of one percent of yield. A drying upgrade costing $4 per wafer pays for itself if it saves 0.06% of die yield. This is why fabs adopt supercritical drying as soon as the collapse margin approaches 2, and why the module's engineering effort is driven by defect density rather than by cost per wafer.

---

## 16.5 Putting It Together

```
Mold etch module: what each chapter controls
  Support open (Ch. 3, 5)     → TiN top loss, opening, landing
  Dip-out (Ch. 4, 6, 7, 9)    → complete removal, low nitride loss
  Drying (Ch. 8)              → collapse margin usage (α)
  Structure (Ch. 2, 10, 11)   → collapse margin itself, lattice strength
  Surface (Ch. 13)            → interface for the dielectric
  Metrology (Ch. 15)          → seeing all of the above
```

---

## Summary and Key Takeaways

1. **The forest is free for hours.** Queue time protects both the TiN surface and the pillars from capillary condensation.

2. **The dielectric and top electrode close the gaps.** Pairs closer than about 11 nm get no top electrode between them.

3. **Random fails are repairable; clusters are not.** About 80 mold-etch cells per die are within repair; fatal clusters cost about 1.4% yield.

4. **The module costs about $12–16 per wafer.** Chemicals dominate the liquid dip-out; depreciation dominates the plasma and supercritical steps.

5. **Yield dominates cost.** 1% die yield is worth about five times the module cost.

---

## Study Questions

1. A pair of pillars is 9 nm apart after the dip-out. Describe what the dielectric and top electrode do between them, and estimate the capacitance lost by each cell.

2. Late leaning doubles after a change in plate-fill stress. Using the leaning budget, what is the new end-of-module rate, and is it still within the 1 per 10⁹ target?

3. Compute the die yield loss for a fatal cluster density of 0.05 cm⁻² on a 0.70 cm² die. What value per wafer does it represent?

4. Using the cost model, find the break-even yield gain for replacing IPA drying by supercritical drying, and for replacing a two-support mold with a three-support mold (assume the third support costs $8 per wafer in deposition and etch).

5. A retention-tail shift appears with no change in hard fails. Which mold-etch parameters would you check first, and with which metrology?

---

**Back to:** [README](../README.md) | [INDEX](../INDEX.md)

---

**Chapter 16 Development Status:** Complete  
**Version:** 1.0
