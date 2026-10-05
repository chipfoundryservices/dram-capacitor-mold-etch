# Chapter 7: Vapor-HF Mold Removal Reactors

## Overview

A vapor-HF reactor removes oxide without ever wetting the forest. The pillars see no liquid meniscus, so there is no capillary force to bend them. In exchange, the reactor must hold a thin adsorbed layer on the surface, thick enough to catalyse the reaction and thin enough never to condense, while removing the gaseous products and dealing with the residues that do not leave as gas. Vapor HF has long been the standard release etch for MEMS. In DRAM it is used for the weakest forests, as a finishing step after a partial liquid dip, and as a research path for molds beyond 2 µm.

This chapter describes the vapor-HF reaction regime, the reactor hardware, the control of condensation, the handling of byproducts and residue, and the throughput and cost that limit its use.

**Learning Objectives:**
- Explain the adsorbed-layer mechanism and the condensation limit of vapor HF
- Choose pressure, temperature, and catalyst partial pressure for a given etch rate
- Describe reactor hardware for single-wafer vapor HF
- Identify vapor-HF residues from BPSG and nitride, and how to remove them
- Compare vapor and liquid dip-out on throughput, cost, and leaning

---

## 7.1 The Reaction Regime

### 7.1.1 The Adsorbed Layer

Chapter 4 introduced the mechanism: HF ionizes in an adsorbed layer of water or alcohol and attacks the oxide; the reaction releases water, which feeds the layer. The etch rate depends on the thickness of that layer, which depends on the partial pressures of HF, catalyst, and water and on the wafer temperature.

```
Vapor-HF regimes (qualitative):
  Layer < ~1 monolayer      etch incubates or stops
  1–5 monolayers            steady etch, rate ∝ p_HF·p_cat (roughly)
  approaching condensation  rate rises steeply; water accumulates
  condensed film            liquid etch with capillary forces and
                            uncontrolled, spotty removal
```

### 7.1.2 Staying Below Condensation

The adsorbed layer condenses when the combined partial pressure of water and catalyst approaches their saturation pressure at the wafer temperature. Two knobs keep the process below that point:

1. **Wafer temperature above ambient.** At 40–50 °C, the saturation pressure of water (7.4 kPa at 40 °C, 12.3 kPa at 50 °C) is several times that at 20 °C (2.3 kPa).
2. **Low total pressure.** Operating at 5–20 kPa with HF and alcohol diluted in N₂ keeps the water product partial pressure low as it is pumped away.

```
Reference vapor-HF conditions (illustrative):
  Total pressure       10 kPa (75 Torr)
  Wafer temperature    45 °C
  HF partial pressure  2.5 kPa
  Ethanol              0.6 kPa
  N₂ balance
  Rates:  BPSG ≈ 150 nm/min; PE-TEOS ≈ 25 nm/min; thermal ≈ 8 nm/min
          Support SiN ≈ 0.3 nm/min; TiN ≈ 0
```

The oxide:nitride selectivity is higher than in liquid HF, because nitride requires more water at the surface to dissolve.

### 7.1.3 Incubation

On a dry, clean oxide surface, vapor HF does not start immediately. The adsorbed layer must first build up, which takes 5–60 s depending on the surface. Doped oxides, which are more hygroscopic, start sooner. A non-uniform incubation produces a non-uniform start, and on a structure as deep as the mold, where the vapor must reach the bottom of the column before etching there can begin, a long incubation adds directly to process time.

---

## 7.2 Transport in the Vapor

Gas-phase diffusion is fast compared with the reaction, even in the Knudsen regime of a 17 nm gap:

```
Knudsen diffusivity in a gap of width w:
  D_K ≈ (w/3) · v̄,  v̄(HF, 318 K) ≈ 580 m/s
  w = 17 nm → D_K ≈ 3.3 × 10⁻⁶ m²/s (≈ 2000× liquid D)
```

Supply into the gaps is therefore not limiting. The limit is the removal of the products SiF₄ and H₂O. Water that cannot leave the bottom of a deep gap accumulates there, thickening the adsorbed layer locally and accelerating the etch at the bottom relative to the top. In the extreme it condenses in the gap even when the open surface is dry, because the gap's narrowness lowers the condensation pressure (Kelvin effect):

```
Kelvin equation for capillary condensation in a slit of width w:
  ln(p/p_sat) ≈ −γV_m cos θ / (R T · w/2)
  (a cylindrical pore has twice the curvature, and condenses earlier)

Water, 318 K, w = 17 nm, θ = 0:
  γ = 0.069 N/m, V_m = 1.8 × 10⁻⁵ m³/mol
  ln(p/p_sat) ≈ −0.069 × 1.8×10⁻⁵ / (8.314 × 318 × 8.5×10⁻⁹) = −0.055
  → condensation at 95% of saturation in a 17 nm slit
  w = 5 nm (narrowest point near a touching pair) → 83% of saturation
```

Condensation in the gaps between pillars starts a few percent below bulk saturation. The process must run well below saturation, typically at less than 50% relative humidity equivalent at the wafer.

---

## 7.3 Reactor Hardware

### 7.3.1 Single-Wafer Reactor

```
Vapor-HF chamber (schematic):
  ┌────────────────────────────────────┐
  │  showerhead (heated, 60 °C)        │ ← HF, alcohol, N₂ (premixed or
  │  ════════════ wafer ═════════════  │   separate injection)
  │  heated pedestal, 45 °C ± 0.5 °C   │
  │  pump port, throttle valve         │ → to scrubber
  └────────────────────────────────────┘
  Materials: nickel-plated or Monel body, PTFE- or Ni-coated lines,
  heated gas lines to prevent HF/alcohol condensation
```

### 7.3.2 Key Design Points

- **Heated lines and walls.** HF and alcohol condense on cold surfaces and later evaporate in bursts. All wetted surfaces run above the wafer temperature.
- **Pedestal uniformity.** At 4–5% per kelvin in rate and a strong condensation sensitivity, the pedestal must hold ±0.5 K.
- **Cyclic operation.** Many reactors alternate etch and pump-out phases (for example, 20 s etch, 10 s pump) to purge water from the gaps and prevent its build-up.
- **HF delivery.** Anhydrous HF from a cylinder via a heated MFC, or HF vapor from an azeotrope with controlled water content.

---

## 7.4 Byproducts and Residues

### 7.4.1 From BPSG

The boron in BPSG leaves as BF₃. The phosphorus forms oxyfluorides and phosphoric acid, which are not volatile at 45 °C:

```
P content of BPSG (4 wt%) in the array per µm²:
  0.49 µm³ of BPSG per µm² of array (760 nm × 0.645)
  × 2.25 g/cm³ × 0.04 → 4.4 × 10⁻¹⁴ g of P per µm²
  If 10% stays as residue, spread over the exposed surfaces
  (577 pillars × 1.24 × 10⁵ nm² + supports ≈ 74 µm² per µm² of array):
  4.4 × 10⁻¹⁵ g of P → 1.4 × 10⁻¹⁴ g H₃PO₄ → 7.4 × 10⁻¹⁵ cm³
  ≈ 0.1 nm average, concentrated at the gap bottoms where the
  last BPSG was removed (locally ≈ 0.5–1 nm)
```

A phosphoric film of a fraction of a nanometre, thicker at the bottom, is enough to change the nucleation of the ALD dielectric. The post-treatments are:

```
Post-treatment              Effect                         Cost
──────────────────────────────────────────────────────────────────────
Vacuum bake 150–200 °C      volatilizes part of P residue  TiN oxidation if O₂
                                                           present; time
Short DIW rinse + IPA dry   dissolves residue              reintroduces capillary
                                                           force (weaker: no HF,
                                                           short, after partial
                                                           support relaxation)
Dilute-acid rinse           more complete removal          same as above
```

### 7.4.2 From Nitride

Silicon nitride under vapor HF forms ammonium fluorosilicate, (NH₄)₂SiF₆, a white solid that sublimes above about 100 °C under vacuum. On the supports it forms a thin crust. It is removed by the same bake. If left, it decomposes during the dielectric deposition and releases NH₃ and SiF₄ into the ALD chamber.

---

## 7.5 Hybrid Schemes

The most common production use of vapor HF in DRAM is hybrid:

```
Hybrid A: liquid HF removes the upper oxide and most of the lower;
          a vapor HF step finishes the last 100–200 nm at the bottom
          after a solvent-exchanged dry.
Hybrid B: liquid HF removes all oxide; supercritical dry (Chapter 8);
          vapor HF touch-up removes residual oxide found at the
          bottom corners and at interfaces.
```

Both use the liquid process for speed and the vapor process where a meniscus would be most dangerous or where the last oxide is hardest to reach.

---

## 7.6 Throughput and Cost

```
Vapor-HF dip-out, full mold (reference structure):
  Path-limited time (lower oxide, 662 nm at 150 nm/min)   265 s
  Upper oxide (47 nm at 25 nm/min, in parallel)            115 s
  Incubation + cycling overhead                            +90 s
  Overetch (40%)                                           +110 s
  Bake                                                     60 s
  Total                                                    ≈ 525 s
  Chambers per platform 6 → ≈ 35 wafers/h

Compared with liquid single-wafer (Chapter 6): ≈ 120 wafers/h
```

Vapor HF is about three times slower per chamber, uses expensive anhydrous HF with large abatement load, and requires a residue treatment. It wins only where liquid drying cannot hold the forest.

---

## Summary and Key Takeaways

1. **No liquid, no meniscus.** Vapor HF removes the capillary force entirely.

2. **The adsorbed layer is the catalyst and the risk.** Too thin, no etch; too thick, condensation and collapse.

3. **Gaps condense early.** In a 17 nm slit water condenses at 95% of saturation; run well below.

4. **Phosphorus stays behind.** BPSG leaves a sub-nanometre phosphoric residue; nitride leaves ammonium fluorosilicate. Both need treatment.

5. **Slow and costly.** About 35 wafers/h; used for weak forests and hybrid finishing steps.

---

## Study Questions

1. Using the Kelvin equation, at what relative humidity does water condense in a 10 nm slit at 45 °C?

2. If the BPSG phosphorus content is reduced from 4 to 2 wt%, how does the estimated residue thickness change? What happens to the BPSG etch rate in liquid HF, and so to the dip time?

3. Explain why vapor HF has higher oxide:nitride selectivity than liquid HF.

4. Design a cycle (etch and pump-out times) that removes water from a 1.6 µm deep gap between etch pulses. Estimate the gas-phase diffusion time out of the gap.

5. For a hybrid process in which liquid HF removes all but the bottom 150 nm of the lower oxide, estimate the vapor step time and the total throughput if both steps run on one platform with 8 liquid and 4 vapor chambers.

---

**Next Chapter:** [Chapter 8: Rinse & Drying Systems](./08-rinse-drying-systems.md)

---

**Chapter 7 Development Status:** Complete  
**Version:** 1.0
