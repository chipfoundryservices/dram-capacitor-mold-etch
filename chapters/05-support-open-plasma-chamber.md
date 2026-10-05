# Chapter 5: Plasma Chambers for the Support Open

## Overview

The support-open etch is a dielectric etch of moderate depth and aspect ratio. It does not need the multi-kilovolt sheaths and tens of kilowatts of the capacitor hole chamber in Book #29. It does need precise control of ion energy at the exposed TiN, chemistry that can switch cleanly between nitride and oxide steps, good uniformity of landing depth across 300 mm, and enough mask selectivity to finish within a 300 nm carbon mask. This chapter describes the chamber choice, RF configuration, gas delivery, temperature control, and fleet matching for the support open.

**Learning Objectives:**
- Justify a medium-power dual-frequency CCP for the support open
- Choose frequencies and bias power to set ion energy at the TiN tops
- Describe gas delivery for a four-step nitride–oxide–nitride–landing recipe
- Explain the role of bias pulsing in TiN loss and column offset
- Estimate throughput and set matching criteria for a fleet

---

## 5.1 Choosing the Chamber

### 5.1.1 Requirements

```
Support-open etch requirements (reference):
  Films           SiN 120 nm, SiO₂ 650 nm, SiN 50 nm, BPSG ~100 nm
  Feature         50 nm column, aspect ratio ≈ 20 (26 with mask)
  Mask            300 nm ACL with SiON cap; selectivity ≥ 3 (SiN), ≥ 5 (oxide)
  TiN loss        ≤ 5 nm at the exposed crescents
  Landing depth   50–150 nm into BPSG across the wafer
  Throughput      ≥ 20 wafers/h per chamber
```

### 5.1.2 CCP or ICP

```
Option                  Strength                         Weakness
──────────────────────────────────────────────────────────────────────────
Dual-frequency CCP      Fluorocarbon dissociation suited  Edge uniformity needs
(e.g. 60 MHz + 2 MHz)   to oxide/nitride selectivity;    focus-ring tuning
                        standard dielectric platform
ICP / TCP with bias     Independent density and energy;   Over-dissociation of
                        low pressure                      C₄F₆ → poor ACL and TiN
                                                          selectivity
High-power CCP          Ample margin                      Wasted power; higher
(capacitor-hole class)                                    TiN sputter; cost
```

A medium-power dual-frequency CCP, the same platform used for contact and via etch, is the usual choice. It keeps the fluorocarbon radicals heavy (CF₂, C₂F₄ fragments) for polymer protection of TiN and ACL, and its sheath voltage of 1–1.5 kV is enough for an aspect ratio of 20.

---

## 5.2 RF Configuration

### 5.2.1 Source and Bias

```
Reference RF (illustrative):
  Source:  60 MHz, 1.5–2.5 kW (upper electrode)
  Bias:    2 MHz, 1.5–3 kW (lower electrode / ESC)
  Peak-to-peak bias voltage V_pp ≈ 1.6–2.4 kV
  Mean ion energy at the wafer E_i ≈ 0.35–0.45 × V_pp
                                   ≈ 600–900 eV (OX step)
                                   ≈ 400–600 eV (SN steps)
```

### 5.2.2 Ion Energy and TiN

TiN sputter yield rises roughly as the square root of ion energy above a threshold near 100 eV. The oxide etch rate rises nearly linearly with ion energy in the ion-limited regime. Lower ion energy therefore improves Ox:TiN selectivity, but costs aspect-ratio performance at the column bottom:

```
Effect of reducing E_i by 25% (illustrative):
  Oxide rate at A = 20:        −20%
  TiN loss rate:               −13%
  TiN loss per nm of oxide:    0.87/0.80 = 1.09 → 9% worse
```

The arithmetic shows a subtle point: if the oxide slows more than the TiN loss, lower energy is worse per unit depth even though the rate of TiN loss falls. The benefit comes only when the polymer protection improves at lower energy, which it usually does because the film on TiN thickens. In practice, the best Ox:TiN selectivity is found at moderate energy with a polymer-rich gas mix, not at the lowest energy.

### 5.2.3 Bias Pulsing

Pulsing the bias at 1–10 kHz with 30–70% duty cycle brings three benefits:

1. During the off-phase, the sheath collapses and electrons reach the column bottom, neutralizing positive charge (Chapter 3, Section 3.6).
2. Polymer deposits during the off-phase, thickening the film on TiN and on the ACL.
3. The time-averaged ion energy falls while the peak energy, which sets the aspect-ratio performance, does not.

```
Reference SN steps: bias pulsed 2 kHz, 50% duty, source continuous
Reference OX step:  bias pulsed 5 kHz, 70% duty
Observed: TiN top loss −25 to −35%; column offset −50%; time +10–15%
```

---

## 5.3 Gas Delivery and the Four-Step Recipe

### 5.3.1 Step Chemistries

```
Step    Gas (sccm, illustrative)                   Pressure   Wafer T
──────────────────────────────────────────────────────────────────────────
SN1     CH₂F₂ 40 / CF₄ 60 / O₂ 20 / Ar 300           30 mT      40 °C
OX      C₄F₆ 25 / O₂ 22 / Ar 600                      25 mT      40 °C
SN2     CH₂F₂ 40 / CF₄ 50 / O₂ 15 / Ar 300           30 mT      40 °C
LAND    C₄F₆ 25 / O₂ 18 / Ar 600                      25 mT      40 °C
```

### 5.3.2 Transitions

Each transition between nitride and oxide chemistry takes 2–4 s to purge the previous gas through the chamber volume at the operating pressure. During the transition the plasma may be held at reduced bias to avoid an uncontrolled mixed-chemistry etch. Two transitions matter most:

- **SN1 → OX:** if the OX polymer arrives late, the TiN crescents see a few seconds of lean, high-energy etch at the top of the column.
- **OX → SN2:** the middle support must clear in leaner chemistry at the bottom of a 16:1 column. A slow transition leaves polymer on the middle nitride and delays its breakthrough.

### 5.3.3 Center–Edge Gas

Landing depth uniformity depends mainly on the OX and SN2 rates across the wafer. A two- or three-zone gas distribution plate, with independent C₄F₆ and O₂ splits, tunes the radial profile of the OX rate. Typical reference uniformity:

```
OX rate radial range (≤ 147 mm):     ± 3%
SN2 rate radial range:                ± 5%
Landing depth range:                  60–130 nm (within the 50–150 window)
```

---

## 5.4 Temperature Control

The electrostatic chuck holds the wafer at 30–50 °C. Polymer deposition and therefore TiN and ACL protection fall as temperature rises; nitride and oxide rates change little. The chuck typically has two to four radial zones, used to flatten the edge rate where the focus ring and gas flow differ from the centre. The heat load from 2–3 kW of bias is modest compared with the capacitor hole chamber, and helium backside cooling with standard pressure (10–20 Torr) suffices.

---

## 5.5 Consumables and Drift

The upper electrode (silicon) and focus ring (silicon or SiC) wear with RF hours. Electrode wear changes the fluorine scavenging and therefore the polymer balance, which drifts the TiN loss before it drifts the etch rate. Focus-ring wear lowers the sheath at the wafer edge and tilts the columns outward, which moves the column bottom toward the outer pillars of each opening-cell. The landing at the edge also shallows.

```
Drift indicators (reference):
  Electrode RF hours    0 → 600 h: TiN loss +0.8 nm; OX rate −2%
  Focus ring RF hours   0 → 400 h: edge tilt 0 → 0.4°; edge landing −15 nm
```

Chapter 15 describes the feedback that compensates these drifts with step time and edge gas offsets.

---

## 5.6 Endpoint

The nitride steps have usable optical emission endpoints: CN (387 nm) and N₂ (337 nm) emission fall when the nitride clears. The open area is low (28% of the array, about 15% of the wafer), so the signal is weak but measurable. SN1 endpoint is reliable; SN2 endpoint, at the bottom of a 16:1 column, is noisy and is usually run by time with SN1 endpoint as a feed-forward. The landing depth is time-controlled. Chapter 15 treats endpoint algorithms.

---

## 5.7 Throughput and Fleet

```
Chamber cycle (reference):
  Transfer and chuck          30 s
  Stabilize                   15 s
  Etch (four steps + purges)  205 s
  Dechuck and dry clean       60 s (waferless clean every wafer)
  Total                       ≈ 310 s → 11.6 wafers/h per chamber
  With 4 chambers per platform ≈ 46 wafers/h (≈ 85% availability → 39)
```

A DRAM fab running 100,000 wafer starts per month needs about 100,000/(30 × 24 × 39 × 0.9) ≈ 4 platforms for the support open. Matching criteria for a fleet are landing depth (±15 nm chamber to chamber), TiN top loss (±0.7 nm), and column CD at the middle support (±1.5 nm).

---

## Summary and Key Takeaways

1. **A contact-class CCP is enough.** 60 MHz source, 2 MHz bias, V_pp ≈ 2 kV.

2. **Polymer, not low energy, protects TiN.** Lower energy alone can be worse per unit depth.

3. **Bias pulsing pays.** It relaxes charge, thickens polymer on TiN, and cuts TiN loss by about a third.

4. **Transitions matter.** Nitride-to-oxide changes must not expose TiN to lean chemistry at full bias.

5. **Consumables drift TiN loss first.** Electrode wear changes polymer before it changes rate.

---

## Study Questions

1. Using the 25% energy example, find the condition on polymer thickening (as a fractional reduction in TiN yield) under which lower energy improves TiN loss per unit oxide depth.

2. A chamber shows edge landing 40 nm shallower than centre. Which two knobs would you try first, and what is the risk of each?

3. Estimate the number of support-open platforms for 160,000 wafer starts per month at the reference throughput.

4. Why is SN2 endpoint harder to detect than SN1? Estimate the relative signal using open area and aspect ratio.

5. Bias pulsing adds 12% to etch time. How much does it change throughput, and is it worth it if it reduces TiN loss from 5.0 to 3.5 nm?

---

**Next Chapter:** [Chapter 6: Single-Wafer Wet Processors & Batch Benches](./06-single-wafer-wet-batch.md)

---

**Chapter 5 Development Status:** Complete  
**Version:** 1.0
