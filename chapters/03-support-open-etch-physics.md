# Chapter 3: Support-Open Etch Physics

## Overview

The support-open etch cuts a column 50 nm wide and about 920 nm deep through three films: the top nitride support, the upper oxide, and the middle nitride support, ending in the lower oxide. In isolation this is a moderate contact etch, well below the aspect ratio of the capacitor hole. Its difficulty comes from what it passes through. Three TiN pillars intrude into every opening. Their crescents form part of the column wall for its full depth and their tops face the plasma for the whole etch. The etch must cut nitride and oxide while leaving the TiN almost untouched, must clear every nitride sliver at the middle support, and must stop before it reaches the bottom stop, 760 nm farther down.

This chapter treats the ion and neutral physics of that column, the chemistry of selectivity to TiN, the mask budget, the landing depth, and charging on conducting pillars.

**Learning Objectives:**
- Describe the geometry of the support-open column and the TiN surfaces it exposes
- Explain why fluorocarbon chemistry etches nitride and oxide selectively to TiN
- Estimate the TiN top loss from ion energy, flux, and time
- Compute the mask budget and the aspect-ratio-dependent etch rate in the column
- Set the landing depth into the lower oxide and the overetch at the middle support

---

## 3.1 The Column

### 3.1.1 Geometry

```
Support-open column (reference):
  Film              Depth (nm)       Column CD (nm)    Wall material
  ─────────────────────────────────────────────────────────────────────────
  ACL mask          −300 → 0         50                ACL
  Top SiN           0 → 120          50 → 49           SiN + 3 TiN crescents
  Upper oxide       120 → 770        49 → 45           SiO₂ + 3 TiN crescents
  Middle SiN        770 → 820        45 → 44           SiN + 3 TiN crescents
  Landing (BPSG)    820 → 920        44 → 43           BPSG + 3 TiN crescents
  ─────────────────────────────────────────────────────────────────────────
  Aspect ratio at landing (from mask top): 1220/47 ≈ 26
  Aspect ratio in the films alone:          920/47 ≈ 20
```

Each crescent is a strip of TiN sidewall roughly 15 nm deep into the pillar at the top, becoming shallower with depth as the pillar narrows (pillar radius 16 nm at the top, 15 at 800 nm) and the column narrows. About one-third of the column perimeter is TiN at the top, falling to about a quarter at the landing.

### 3.1.2 What the Column Must Deliver

1. Clear nitride across the full opening at both supports, including the corners where the nitride meets the TiN crescents
2. Keep the column at least 40 nm wide at the middle support, so the dip-out has adequate access to the lower oxide
3. Keep TiN loss at the pillar tops below 5 nm and lateral TiN loss on the crescent walls below 2 nm
4. Land in the lower oxide, never in the bottom stop

---

## 3.2 Chemistry of Selectivity to TiN

### 3.2.1 Why Fluorocarbons Spare TiN

Titanium forms TiF₄ in fluorine plasmas. TiF₄ is a solid that sublimes at 284 °C at atmospheric pressure; at wafer temperatures of 20–60 °C and tens of millitorr its vapour pressure is low. Fluorination of TiN therefore produces a passivating TiF₄/TiNₓFᵧ layer rather than a volatile product. Removal requires ion sputtering of that layer. By contrast, chlorine forms TiCl₄, volatile at room temperature, which is why Cl-based chemistry etches TiN readily and must be avoided here.

```
Relative volatility of etch products (qualitative):
  SiF₄        very volatile (b.p. −86 °C)        → Si, SiO₂, SiN etch
  TiCl₄       volatile (b.p. 136 °C)              → TiN etches in Cl
  TiF₄        involatile (subl. 284 °C)           → TiN passivates in F
  TiOₓFᵧ      involatile                          → passivation with O
```

### 3.2.2 Polymer on TiN

Fluorocarbon polymer deposits on TiN as readily as on any other surface. On oxide, the polymer is consumed by oxygen from the substrate and the etch proceeds through a thin film. On TiN, as on silicon or nitride, there is no oxygen source except the gas, and the polymer accumulates. A steady-state film of 2–4 nm on the crescent walls and pillar tops further suppresses TiN loss. The art of the oxide step is to keep this film on the TiN while the oxide surface stays thin enough to etch.

### 3.2.3 Reference Chemistries

```
Step        Film         Chemistry (illustrative)              Selectivities
──────────────────────────────────────────────────────────────────────────────
SN1         Top SiN      CH₂F₂ / CF₄ / O₂ / Ar                 SiN:TiN ≈ 15
                                                               SiN:ACL ≈ 3
OX          Upper oxide  C₄F₆ / O₂ / Ar                        Ox:TiN ≈ 40
                                                               Ox:ACL ≈ 5
                                                               Ox:SiN ≈ 6
SN2         Middle SiN   CH₂F₂ / CF₄ / O₂ / Ar                 SiN:TiN ≈ 15
                                                               SiN:Ox ≈ 1.5
LAND        BPSG         C₄F₆ / O₂ / Ar (lower power)          Ox:TiN ≈ 40
```

The SN steps use hydrofluorocarbons whose hydrogen scavenges fluorine and forms HCN-type products with nitrogen from the film; this gives nitride a selectivity advantage over oxide that the OX step does not need. The SiN:TiN selectivity is lower than Ox:TiN because the SN chemistry is leaner (less polymer) and the TiN gets less protection.

---

## 3.3 TiN Top Loss

### 3.3.1 An Estimate

The pillar tops in the crescents see the full ion flux for the whole etch. A simple sputter model gives the loss:

```
Ion flux Γ_i            ≈ 5 × 10¹⁵ cm⁻² s⁻¹ (medium-power CCP)
Mean ion energy E_i     ≈ 600 eV (OX step), 400 eV (SN steps)
Sputter yield of TiN under fluorocarbon film, Y_eff:
                        ≈ 0.004 atoms/ion at 600 eV (polymer-covered)
                        ≈ 0.008 at 400 eV (leaner SN chemistry)
TiN atomic density      ≈ 1.05 × 10²³ cm⁻³ (Ti+N pairs ≈ 5.3 × 10²²)

Loss rate (OX):  Γ_i · Y_eff / n_TiN
              = 5×10¹⁵ × 0.004 / 5.3×10²² cm/s = 3.8 × 10⁻¹⁰ cm/s
              ≈ 0.23 nm/min from sputtering alone
              × ≈ 5 for ion-enhanced fluorination → ≈ 1.1 nm/min
Loss rate (SN):  ≈ 2.5 nm/min (leaner chemistry, higher effective yield)

Time:  SN1 40 s, OX 110 s, SN2 20 s, LAND 25 s
Loss:  2.5×(40+20)/60 + 1.1×(110+25)/60 = 2.5 + 2.5 = 5.0 nm
```

The estimate lands at the specification limit, and the SN steps contribute half the loss in a third of the time. Leaner nitride chemistry is the main threat to the pillar tops.

### 3.3.2 Where the Loss Concentrates

The loss is not uniform across the crescent. The pillar edge adjacent to the column wall sees ions reflected from the ACL facet and from the column wall, in addition to the direct flux. The edge rounds by more than the centre of the crescent loses. A seam that reaches the top (Chapter 2) etches faster than the surrounding TiN and can open into a slot. Chapter 13 treats the consequences for the dielectric.

---

## 3.4 Transport and Rate in the Column

### 3.4.1 ARDE

The column reaches an aspect ratio of about 20 in the films and 26 including the remaining mask. With the linear ARDE form of Book #29:

```
ER/ER₀ = 1/(1 + k·A), k ≈ 0.02 (fluorocarbon oxide etch)

A = 10  →  0.83
A = 20  →  0.71
A = 26  →  0.66
```

The column etches about a third slower at the landing than at the top. This is mild compared with the capacitor hole, but it matters for SN2: the middle nitride must clear at A ≈ 17 in leaner chemistry, and any nitride residue there blocks HF access to the lower oxide below that opening.

### 3.4.2 Step Times

```
Step   Thickness   ER₀ (nm/min)   Mean A   ER (nm/min)   Time (s)   +OE
────────────────────────────────────────────────────────────────────────
SN1    120         240            2–4      ≈ 225         32         40 s (25%)
OX     650         450            4–16     ≈ 370         105        110 s
SN2    50          200            16–17    ≈ 150         20         20 s (incl. OE
                                                                   from SN1 margin)
LAND   100         400 (BPSG)     17–19    ≈ 290         21         25 s
────────────────────────────────────────────────────────────────────────
Total etch time                                                     ≈ 195 s
```

### 3.4.3 Mask Budget

```
ACL consumed:
  SN1:  120 × 1.25 / 3   = 50 nm
  OX:   650 / 5          = 130 nm
  SN2:  50 × 1.4 / 3     = 23 nm
  LAND: 100 / 5          = 20 nm
  Facet / corner allowance ≈ 30 nm
  Total ≈ 253 nm of 300 nm → 47 nm remaining at the thinnest
```

The margin is thin. If the ACL runs out over the top support, the remaining LAND and SN2 time etches the top support itself, which is permanent loss of the top tie. The ACL thickness, not the etch rate, sets the latest point at which the etch can stop.

---

## 3.5 Landing in the Lower Oxide

### 3.5.1 Why Land in Oxide

The column must break fully through the middle support so that the opening there is at least 40 nm wide. Overetching into the BPSG ensures this across the wafer despite variations in SN2 rate and middle-support thickness. The column then extends 50–150 nm into the lower oxide.

### 3.5.2 Why Not Too Deep

Landing deeper does no harm to the dip-out, which will remove the BPSG anyway. But every second of LAND costs mask and TiN, and a landing far into the BPSG brings the plasma closer to the bottom stop. More subtly, a deep column with fluorocarbon polymer on its walls must be cleaned before the dip-out; polymer left on BPSG slows its removal locally.

```
Landing depth window (reference):
  Minimum 50 nm: ensures middle SiN cleared on the slowest site
  Maximum 150 nm: mask, TiN, and polymer limits
  Bottom stop at 1580 nm: never approached (≥ 600 nm away)
```

---

## 3.6 Charging and Conducting Pillars

### 3.6.1 The Pillars Are Floating

Each TiN pillar is connected through its landing pad and storage-node contact to a cell junction. With the access transistor off and the junction reverse-biased by positive charge, each pillar is effectively an isolated conductor with a capacitance of order 10⁻¹⁵ F to the substrate, through a junction that leaks only slowly.

### 3.6.2 Consequences

During the etch, electrons reach the pillar tops more easily than ions reach the column bottom, as in any high-aspect-ratio feature. The pillar tops charge negative relative to the column bottom; the oxide column bottom charges positive. Because each pillar is an equipotential conductor along its whole height, the crescent wall is not a charged insulator but a conducting strip at the pillar potential. Ions passing a crescent are attracted toward it if it is negative, which slightly enhances TiN loss on the crescent walls near the top and can bend the column toward the pillar with the largest crescent. The effect is small at A ≈ 20 but is the reason the column bottom is often slightly off-centre toward its pillars.

```
Estimate of lateral deflection:
  Differential potential between pillar and column centre ≈ 5–10 V
  Ion energy ≈ 600 eV, column length ≈ 900 nm, half-width ≈ 23 nm
  Upper bound, fully transverse field:
    θ ≈ ΔV/(2E_i) × (L/w) ≈ 7.5/1200 × 39 ≈ 0.24 rad
  Screening by the conducting walls cuts the effective field ≈ 10×:
    θ ≈ 0.024 rad ≈ 1.4°  →  ≈ 20 nm over 900 nm (still an overestimate)
```

This order-of-magnitude estimate overstates the effect; measured columns are offset by a few nanometres. It explains why bias pulsing (Chapter 5) that lets charge relax between pulses reduces column offset and crescent attack.

---

## 3.7 Polymer and Post-Etch Treatment

The column walls and pillar tops leave the etch covered by 2–4 nm of fluorocarbon polymer. The ACL is then stripped. An O₂ plasma strip removes the ACL quickly but oxidizes the exposed TiN crescents to TiO₂ by 1–2 nm. A reducing strip in N₂/H₂ or a low-temperature O₂ strip followed by a wet clean keeps TiN oxidation lower at the cost of strip time. The polymer on the column walls must also go: fluorocarbon on BPSG and PE-TEOS is not removed by HF and would leave a skin of oxide behind it.

---

## Summary and Key Takeaways

1. **The column contains metal.** Three TiN crescents form a third of its wall at the top; every opening exposes three pillar tops.

2. **Fluorine passivates TiN.** TiF₄ is involatile; TiN loss is ion-driven. Avoid chlorine.

3. **TiN top loss is about 5 nm.** The leaner nitride steps cause half of it in a third of the time.

4. **The mask is the clock.** About 250 nm of a 300 nm ACL is consumed. Running past the mask etches the top support permanently.

5. **Land 50–150 nm into BPSG.** Enough to clear the middle support everywhere; far from the bottom stop.

---

## Study Questions

1. Using the step table, compute the TiN top loss if SN1 and SN2 are run with 50% more polymer (SiN:TiN = 25) at the cost of 20% lower rate. Does the ACL budget still close?

2. The middle support is 55 nm instead of 50 nm on one lot. With unchanged SN2 time, what landing depth results at the slowest site, assuming the ARDE values above?

3. Estimate the column CD at the middle support if the column tapers by 0.3° per side from 50 nm at the top. Does it meet the 40 nm minimum?

4. Why does an O₂ plasma ACL strip affect only the crescents and not the rest of the pillar surface? What happens to the rest of the pillar surface later?

5. Explain why a Cl₂-containing nitride chemistry, used successfully elsewhere for nitride selectivity, is unacceptable here.

6. If bias pulsing at 50% duty reduces the effective ion energy on TiN by 25% and the TiN yield scales as E_i^1/2, what is the new top loss for the same etch depth if the oxide rate falls by 15%?

---

**Next Chapter:** [Chapter 4: HF Chemistry of Mold Removal](./04-hf-mold-removal-chemistry.md)

---

**Chapter 3 Development Status:** Complete  
**Version:** 1.0
