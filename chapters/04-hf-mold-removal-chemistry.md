# Chapter 4: HF Chemistry of Mold Removal

## Overview

Hydrofluoric acid dissolves silicon dioxide and leaves silicon nitride and titanium nitride nearly untouched. That one fact makes the pillar capacitor possible. This chapter develops the chemistry behind it: the species present in dilute HF, the dissolution reaction, the etch rates of every material in the structure and their temperature dependence, the transport of HF and products in 17 nm gaps, and the vapor-phase alternative.

The central result is that, in the reference structure, removal is limited by surface reaction along the longest path, not by diffusion. The dip time is set by the slowest oxide over the longest distance. The transport problems that matter in practice are wetting, trapped gas, and the condition of the surfaces the acid must enter, rather than the supply of HF.

**Learning Objectives:**
- Describe the equilibria among HF, F⁻, HF₂⁻, and (HF)₂ and their roles in oxide dissolution
- Compute the etch time along the longest path for each oxide layer
- Estimate support, stop, and TiN loss for a given dip time and temperature
- Show, with a Damköhler number, why diffusion in the gaps does not limit removal
- Explain wetting and trapped gas as the real transport risks
- Compare liquid and vapor HF and their residues

---

## 4.1 Species in Dilute HF

### 4.1.1 Equilibria

HF is a weak acid in water. In dilute solution three equilibria matter:

```
HF       ⇌  H⁺ + F⁻           K₁ ≈ 6.8 × 10⁻⁴ mol/L
HF + F⁻  ⇌  HF₂⁻              K₂ ≈ 3.9 mol⁻¹·L
2 HF     ⇌  (HF)₂             K₃ ≈ 2.7 mol⁻¹·L
```

In 5 wt% HF (about 2.6 mol/L), nearly all fluorine is undissociated HF and its dimer. The bifluoride ion HF₂⁻ is present at a few percent of total fluoride; F⁻ is much lower.

### 4.1.2 Which Species Etch

Oxide dissolution is commonly modelled with two parallel paths:

```
R = k_HF·[HF] + k_HF₂·[HF₂⁻] (+ k_dimer·[(HF)₂])

k_HF₂ / k_HF ≈ 4–5 (HF₂⁻ is the more reactive species per molecule)
```

The overall reaction is

```
SiO₂ + 6 HF → H₂SiF₆ + 2 H₂O       (net, in excess HF)
SiO₂ + 4 HF → SiF₄ + 2 H₂O         (vapor phase; Section 4.6)
```

Buffering with NH₄F raises [F⁻] and [HF₂⁻], which increases the rate per unit HF and stabilizes it as HF is consumed. Buffered HF (BHF) also etches nitride faster relative to oxide than plain dilute HF does, because nitride dissolution is more sensitive to HF₂⁻. The reference process uses unbuffered 5 wt% HF for that reason.

---

## 4.2 Etch Rates of the Structure

### 4.2.1 Reference Rates

```
5 wt% HF, 25 °C (illustrative; after the thermal history of Chapter 2):
  Material                     Rate (nm/min)   Ratio to support SiN
  ────────────────────────────────────────────────────────────────
  BPSG (lower oxide)           600             600
  PE-TEOS (upper oxide)        70              70
  Thermal SiO₂ (reference)     23              23
  Low-H PECVD SiN (supports)   1.0             1
  LPCVD SiN (bottom stop)      0.7             0.7
  TiN (CVD, oxidized surface)  ≈ 0.05          0.05
  W (landing pad, if exposed)  ≈ 0 in HF alone; dissolves if oxidant present
```

### 4.2.2 Temperature

Oxide dissolution in HF is thermally activated with an apparent activation energy near 0.35 eV for thermal oxide and somewhat lower for doped oxides:

```
d ln R / dT = E_a / (k_B T²) = 0.35 / (8.617×10⁻⁵ × 298²) = 0.046 K⁻¹

  → 4.6% per kelvin near room temperature
  → ±0.5 K bath control gives ±2.3% rate
```

Nitride dissolution has a higher activation energy (about 0.5–0.6 eV), so the oxide:nitride selectivity falls slowly as temperature rises. A warm dip-out finishes sooner but loses relatively more nitride.

### 4.2.3 Concentration

```
Rate roughly ∝ [HF]^1.1–1.3 for unbuffered dilute HF (thermal oxide)

  5.0 → 4.8 wt% (4% drop, e.g. evaporation or drag-out dilution)
  → rate falls by ≈ 5%
```

Chapter 9 shows how concentration is controlled in recirculated and single-pass systems.

---

## 4.3 The Longest Path

### 4.3.1 The Upper Oxide

The support-open column has already removed the oxide in the opening. HF enters the column and attacks the upper oxide laterally from the column wall. The farthest upper-oxide point is 27 nm from an opening edge (Chapter 1):

```
t_upper = 27 nm / 70 nm/min = 23 s
```

The etch proceeds isotropically from the column wall. Because pillars stand in the way, the front moves along the 17 nm gaps between them rather than in a straight line. The actual path around a pillar is longer than 27 nm, by roughly the half-circumference of a pillar at worst (π × 14 ≈ 44 nm):

```
Worst path in the upper oxide ≈ 27 + 20 ≈ 47 nm  →  t ≈ 40 s
```

### 4.3.2 The Lower Oxide

The column has landed about 100 nm into the BPSG. HF etches downward from the column bottom and outward from the column wall, isotropically:

```
Distance from column bottom (920 nm) to bottom stop (1580 nm):  660 nm
Lateral offset to the farthest corner:                          ≈ 27–47 nm
Path ≈ √(660² + 47²) ≈ 662 nm

t_lower = 662 / 600 nm/min = 66 s
```

### 4.3.3 Dip Time

The two layers etch in parallel. The lower oxide, despite its fast rate, has the longer path:

```
Path-limited time         66 s
Overetch (≈ 60%)          + 39 s  (rate variation, BPSG doping, wetting delay)
Reference HF time         105 s
```

### 4.3.4 Losses

```
Support SiN (each exposed face), exposed ≈ 105 s:
  1.0 × 105/60 = 1.75 nm per face
  Top support:     top face + column wall + underside (exposed after
                   the upper oxide clears, ≈ 80 s) → ≈ 1.8 nm top, 1.3 nm under
  Middle support:  both faces ≈ 1.3–1.8 nm
Bottom stop, exposed from ≈ 66 s to 105 s (39 s):
  0.7 × 39/60 = 0.45 nm (on average; first-exposed sites ≈ 0.8 nm)
TiN, exposed 105 s:
  0.05 × 105/60 < 0.1 nm of TiN dissolved; surface chemistry changes
  more than thickness (Chapter 13)
```

These losses are comfortably within the specification sheet of Chapter 1, which is the reason dilute HF is the reference: at oxide:nitride selectivity of 70 (PE-TEOS) to 600 (BPSG), the losses are small. The bottom stop is in less danger from uniform etching than from local defects in it, such as pinholes, seams at pillar collars, or thin spots where the hole etch gouged it. Chapter 12 develops that risk.

---

## 4.4 Transport in the Gaps

### 4.4.1 A Damköhler Number

Compare the speed at which the etch front advances with the speed at which diffusion can supply HF over the path length:

```
D (HF in water, 25 °C)       ≈ 1.5 × 10⁻⁹ m²/s
Hindrance in a 17 nm gap     ≈ ×0.7 (molecule ≈ 0.3 nm, walls charged)
D_eff                        ≈ 1.0 × 10⁻⁹ m²/s
Path L                       660 nm

Diffusion velocity D/L       ≈ 1.5 × 10⁻³ m/s = 1.5 × 10⁶ nm/s
Front velocity (BPSG)        600 nm/min = 10 nm/s

Da = v_front / (D/L) ≈ 7 × 10⁻⁶ ≪ 1
```

The etch is overwhelmingly reaction-limited. HF concentration at the front is essentially the bulk concentration.

### 4.4.2 Consumption

Each mole of SiO₂ consumes six moles of HF. The molar density of the mold oxide is about 3.7 × 10⁴ mol/m³, and 5 wt% HF is about 2.6 × 10³ mol/m³, so

```
Volume of 5% HF consumed per volume of oxide = 6 × 3.7×10⁴ / 2.6×10³ ≈ 85
```

Locally, the gap volume opened by the etch is about one oxide volume, so the liquid in the gap would be exhausted 85 times over if it were not replenished by diffusion. Replenishment is fast (above), so the gap stays near bulk concentration. At wafer scale, the oxide in the array (0.91 µm³ per µm²) consumes the HF in a liquid layer about 77 µm thick. A spin processor with a 20–50 µm boundary layer must keep exchanging it, which it does easily at normal flow, but a stagnant puddle of 1 mm would lose about 8% of its HF over the array. Chapter 6 uses this to set dispense flow.

### 4.4.3 Products

H₂SiF₆, H₃BO₃ (and fluoroborate), and phosphoric species from the BPSG diffuse out as fast as HF diffuses in. They are soluble at these concentrations. Near the front in a long narrow gap the local fluorosilicate concentration rises to perhaps a few percent of the bulk HF equivalent; no precipitate forms unless cations such as K⁺ or Na⁺ are present at high concentration.

---

## 4.5 The Real Transport Risks: Wetting and Trapped Gas

### 4.5.1 Entering the Column

Before the dip-out, the support-open columns are open holes filled with air. When the HF arrives, the liquid must enter each column and then the gaps it creates. A clean oxide column is hydrophilic; liquid enters spontaneously. But the column walls after the support-open etch and strip may carry fluorocarbon residue, which is hydrophobic, and the TiN crescents may be partly fluorinated.

```
Spontaneous filling of a column requires cos θ > 0 on its walls.
Polymer residue: θ ≈ 90–110° → the column may not fill at all.
Air trapped in a column: every pillar it serves keeps its oxide.
```

A pocket of air 50 nm wide and 900 nm deep must dissolve into the surrounding liquid before HF can etch beneath it. The dissolution time, for an air pocket at a Laplace pressure of a few MPa, is seconds to tens of seconds. A short dip can therefore leave whole opening-cells of oxide intact: about four pillars buried per trapped column.

### 4.5.2 Defences

1. **Clean post-etch surfaces.** The post-etch strip and clean must remove fluorocarbon from the column walls (Chapter 3).
2. **Pre-wet.** A short DIW or dilute HF pre-wet (5–10 s) before the full-strength dip fills the columns first; the pre-wet liquid is then displaced by HF through diffusion.
3. **Surfactant or low-surface-tension pre-wet.** A pre-wet with a small fraction of IPA lowers the contact angle on mildly hydrophobic surfaces.
4. **Dispense pressure and spin.** Higher impact pressure and slower spin during the first seconds help the liquid enter.

Chapter 12 shows that trapped gas is the leading source of clustered residual-oxide defects.

---

## 4.6 Vapor-Phase HF

### 4.6.1 Mechanism

Anhydrous HF gas does not etch dry oxide appreciably. Etching starts when a thin adsorbed layer of water or alcohol forms on the surface and ionizes HF:

```
2 HF + H₂O (ads) → HF₂⁻ + H₃O⁺
SiO₂ + 2 HF₂⁻ + 2 H₃O⁺ → SiF₄ ↑ + 4 H₂O
```

Water is a product, so the reaction is autocatalytic: the adsorbed layer grows as etching proceeds. If it grows too much, it condenses into liquid, and liquid brings back capillary forces. Vapor HF processes use alcohol (methanol, ethanol, IPA) as the catalyst and keep temperature and pressure so that the adsorbed layer stays at a few monolayers.

### 4.6.2 Residues

```
Product                     Volatility
──────────────────────────────────────────────────────
SiF₄                        volatile (gas)
BF₃ (from B in BPSG)        volatile
POF₃ / HPO₂F₂ / H₃PO₄ (P)   partly involatile → phosphorus-rich residue
(NH₄)₂SiF₆ (if N-H present) solid; sublimes ≈ 100 °C under vacuum
```

The phosphorus in BPSG is the main residue problem for vapor HF. A post-treatment (heated vacuum bake, short water rinse, or a dilute-acid rinse) removes it, but each brings back part of what vapor HF was chosen to avoid. Chapter 7 treats the reactor design and Chapter 14 the trade-off.

### 4.6.3 Why Vapor at All

Vapor HF has no liquid to dry, so it applies no capillary force to the pillars. It is used where the forest is too weak for liquid drying, such as molds taller than 2 µm or pillars thinner than 24 nm, or as a final step after a liquid dip has removed most of the oxide while the supports were still strong.

---

## Summary and Key Takeaways

1. **Dilute HF etches oxide, not nitride or TiN.** BPSG 600, PE-TEOS 70, support SiN 1.0, TiN ≈ 0.05 nm/min at 5%, 25 °C.

2. **The lower oxide sets the time.** 660 nm path at 600 nm/min ≈ 66 s; reference dip 105 s with overetch.

3. **Losses are small.** About 1.8 nm per support face and under 1 nm of bottom stop.

4. **Diffusion is not the limit.** Da ≈ 10⁻⁵. The gap stays at bulk concentration.

5. **Wetting is the limit.** Hydrophobic residue and trapped air leave whole opening-cells unetched.

6. **Vapor HF trades capillary force for residue.** Phosphorus from BPSG is the main residue.

---

## Study Questions

1. Compute the dip time path for the lower oxide if BPSG is replaced by undoped PE-TEOS (70 nm/min). How much support loss would the new dip time cause?

2. The bath runs 1.5 K warm. Using E_a = 0.35 eV for oxide and 0.55 eV for nitride, what are the new oxide and nitride rates, and the new support loss for a fixed 105 s dip?

3. Show that the HF consumed by the array of one wafer (oxide volume from Chapter 1) is a negligible fraction of a 2 L dispense, but not of a 100 µm stagnant film.

4. A support-open column has a 95° contact angle on its upper walls because of polymer. Estimate the pressure needed to force liquid into a 47 nm column against this angle (γ = 0.072 N/m).

5. In vapor HF, why does too little alcohol catalyst stop the etch, and too much cause pillar collapse?

6. Estimate Da for the upper oxide path (47 nm at 70 nm/min). What does the result tell you about adding agitation to speed up the dip?

---

**Next Chapter:** [Chapter 5: Plasma Chambers for the Support Open](./05-support-open-plasma-chamber.md)

---

**Chapter 4 Development Status:** Complete  
**Version:** 1.0
