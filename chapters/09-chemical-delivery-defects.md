# Chapter 9: Chemical Delivery, Filtration, Particles & Defects

## Overview

The dip-out removes oxide with a chemical whose rate changes by about 5% per kelvin and by about 1.2% per 1% change in concentration. It removes that oxide from a structure with 17 nm gaps that can trap a particle permanently, and it dries with a meniscus that a single particle can disturb. Behind every dip-out chamber is a chemical system that must deliver HF, water, and solvent at fixed concentration and temperature, free of particles and metals, and that must keep doing so for thousands of wafers. This chapter covers blending and concentration control, recirculation and bath life, filtration, particles and watermarks, metal contamination, and the maintenance and matching of the fleet.

**Learning Objectives:**
- Describe HF blending and in-line concentration control for single-pass and recirculated systems
- Estimate the effect of concentration and temperature drift on the dip-out
- Compute bath life from silicate loading
- Explain how particles and watermarks become leaning and residual-oxide defects
- Set contamination limits for metals in the dip-out chemicals

---

## 9.1 HF Supply and Blending

### 9.1.1 From Bulk to Point of Use

```
HF chain (reference):
  49 wt% electronic-grade HF (bulk tank, sub-fab)
  → blending unit: 49% HF + UPW → 5.00 wt% (in-line conductivity or
    NIR/refractive concentration monitor)
  → day tank (optional)
  → point-of-use heat exchanger (25.0 ± 0.2 °C)
  → 0.01–0.02 µm filter
  → dispense valve and nozzle
```

### 9.1.2 Concentration Control

```
Target 5.00 wt%; control band ± 0.05 wt% (± 1%)
Effect on BPSG rate (rate ∝ c^1.2): ± 1.2%
Effect on dip time margin: negligible against 60% overetch
Effect on support loss at fixed time: ± 1.2% of 1.75 nm ≈ ± 0.02 nm
```

Concentration is not a tight constraint for the oxide removal itself, because the overetch is large. It matters more for nitride loss in tight processes and for the matching of chambers that share a blend.

### 9.1.3 Single-Pass versus Recirculation

```
Mode            HF use per wafer       Stability            Contamination
─────────────────────────────────────────────────────────────────────────
Single-pass     ≈ 2.6 L (1.5 L/min,    Constant; every      Lowest; nothing
                105 s)                  wafer sees fresh     carried over
Reclaim/        ≈ 0.2–0.5 L net         Drifts with          Silicate, B, P,
recirculate     (make-up only)          loading; needs       particles build up
                                        spiking
```

Many fabs reclaim the HF from the dip-out cup, filter it, measure it, spike it back to target, and reuse it for a fixed number of wafers or a fixed silicate load before draining. The savings are large; the risks are silicate saturation and particle build-up.

---

## 9.2 Bath Life

### 9.2.1 Silicate Loading

Each wafer dissolves about 80 mg of SiO₂ from the array (Chapter 1), plus the field oxide removed on the periphery and the scribe, which may double it. In a recirculated bath of volume V:

```
SiO₂ per wafer          ≈ 160 mg (array + periphery, illustrative)
HF consumed per wafer   ≈ 6 × 160/60 mmol = 16 mmol ≈ 0.32 g HF
Recirculated volume     40 L of 5% HF (≈ 2.0 kg HF, ≈ 100 mol)
Wafers to consume 5% of the HF: 0.05 × 100 mol / 0.016 mol ≈ 310
H₂SiF₆ accumulated after 310 wafers ≈ 2.7 mmol/wafer × 310 ≈ 0.83 mol (≈ 21 mmol/L)
```

Fluorosilicic acid at tens of millimolar is soluble, but it slows oxide etching slightly and changes the ratio of HF to HF₂⁻. Boron and phosphorus from the BPSG accumulate in proportion. A bath-life limit of 300–500 wafers, or a silicate-equivalent concentration limit, with continuous spiking of HF, is typical.

### 9.2.2 Monitoring

- **Concentration:** in-line conductivity (HF is weakly ionized; conductivity responds to HF and to silicate) combined with NIR spectroscopy to separate them
- **Etch rate:** daily monitor wafer of BPSG and PE-TEOS on a blanket film
- **Nitride rate:** weekly monitor of support-equivalent SiN; a rising nitride rate signals a change in HF/HF₂⁻ balance

---

## 9.3 Filtration and Particles

### 9.3.1 Why Particles Matter More Here

A particle in an ordinary wet clean either washes away or stays on the surface. In the dip-out it can do three worse things:

1. **Lodge in a support-open column** and block HF from four pillars' worth of oxide, which then stays as residual oxide (Chapter 12).
2. **Lodge between pillars** after the oxide is gone, and act as a bridge. A 15 nm particle wedged in a 17 nm gap is a short after the plate deposition.
3. **Pin the drying meniscus.** A particle on the surface at the drying front holds liquid behind it; the liquid then dries as an isolated droplet with α near 1 at its edge. The result is a ring of leaning pillars around the particle site, a characteristic "flower" defect.

### 9.3.2 Filtration

```
Filtration (reference):
  HF point of use:   PTFE membrane, 10–20 nm rating
  UPW point of use:  10 nm ultrafilter
  IPA point of use:  PTFE, 10–20 nm, low-extractable
Particle specification at the nozzle:
  ≤ 10 particles/mL ≥ 20 nm (HF, IPA)
```

### 9.3.3 Particle Sources Inside the Chamber

- **Splash-back from the cup** onto the wafer during spin-down
- **Chuck pins** contacting the bevel; worn pins shed fluoropolymer
- **Crystallized residues** on the nozzle or arm (dried HF/silicate, IPA residue) falling during arm motion
- **Bubbles** in the dispense line, which carry particles and also cause local dry spots on impact

---

## 9.4 Watermarks and Drying Residues

A watermark is the residue left by a droplet that dries on the surface. On a pillar forest it is both a residue and a leaning defect:

```
Droplet drying on the forest:
  Droplet carries dissolved silicate, HF, or IPA impurities
  Drying from the perimeter inward → α ≈ 1 at the edge → leaning ring
  Dissolved solids deposit at the last point → residue in gaps
```

Watermarks come from incomplete IPA displacement, from droplets splashed back during drying, from condensation on a cold wafer after the dry, and from water in the IPA. The IPA supply must be dry (≤ 100 ppm water) and the chamber atmosphere below about 30% RH during the dry.

---

## 9.5 Metals and Anions

### 9.5.1 Metals

```
Metal contamination limits at point of use (reference):
  Fe, Ni, Cu, Cr, Zn, Na, K, Ca, Al   ≤ 10 ppt each (HF, IPA)
  UPW                                 ≤ 1 ppt each
```

Copper is the most dangerous in HF. HF dissolves the native oxide of any exposed silicon (none is exposed in the array, but periphery and bevel may expose some), and Cu²⁺ in solution plates onto silicon by galvanic exchange. On TiN, noble-metal ions can deposit as well. Metals deposited on the pillar surface sit at the interface with the capacitor dielectric and raise leakage.

### 9.5.2 Anions

Chloride in the HF or water attacks the TiN surface more aggressively than fluoride, especially in the presence of oxygen. Chloride limits are in the low-ppb range. Residual chlorine from the TiCl₄-based fill (Chapter 2) can also be leached by the dip-out and redeposited.

---

## 9.6 Preventive Maintenance and Matching

```
Wet platform PM items (reference intervals, illustrative):
  Filters (HF, IPA, UPW)              3–6 months or ΔP limit
  Chuck pins                          by contact count
  Cup and chamber wash                weekly
  Nozzle and arm inspection           weekly
  Heat exchanger calibration          quarterly
  Concentration monitor calibration   monthly (against titration)
```

Chamber matching criteria:

```
  BPSG rate (monitor)                  ± 2%
  Support SiN loss (structure wafer)   ± 0.3 nm
  Leaning density (inspection)         within 1.5× fleet median
  Particle adders (≥ 30 nm)            ≤ 10 per wafer
  Residual-oxide defects               0 clusters per wafer
```

Leaning density is the most sensitive matching metric. A chamber can match on every chemical and particle metric and still lean more because its N₂ nozzle is misaligned or its drying speed ramp differs.

---

## Summary and Key Takeaways

1. **Concentration control is easy; temperature control matters more.** ±1% concentration is ±1.2% rate; ±0.5 K is ±2.3%.

2. **Reclaim saves acid and adds risk.** Bath life of a few hundred wafers is set by silicate, boron, and phosphorus build-up.

3. **Particles become structural defects.** Blocked columns, bridged gaps, and pinned menisci with leaning rings.

4. **Watermarks are leaning defects.** Droplets dry with full asymmetry at their edge.

5. **Metals and chloride go to the dielectric interface.** Limits at ppt for metals, low ppb for chloride.

---

## Study Questions

1. A recirculated bath of 40 L is spiked to hold 5.00% HF. After 400 wafers, estimate the H₂SiF₆ concentration and the fraction of fluorine tied up as fluorosilicate.

2. Single-pass HF costs $3/L at 5%. Reclaim reduces use to 0.4 L/wafer but adds $0.30/wafer in monitoring and disposal. What is the saving per 100,000 wafers?

3. A "flower" defect shows a ring of 40 leaning pillars around a central site. Estimate the radius of the droplet that caused it on the 45 nm lattice.

4. Why is chloride more dangerous than fluoride to the TiN surface in the presence of dissolved oxygen?

5. A chamber matches the fleet on every chemical metric but leans 3× more. List four drying-related causes in order of likelihood.

---

**Next Chapter:** [Chapter 10: Pillar Leaning, Bending & Collapse](./10-pillar-leaning-collapse.md)

---

**Chapter 9 Development Status:** Complete  
**Version:** 1.0
