# Chapter 2: The Post-Electrode Structure, Support Lattice & Support-Open Pattern

## Overview

The mold etch inherits a structure that four modules have built: the mold deposition, the hole etch, the TiN fill, and the top isolation. Every property of that structure matters to the mold etch. The density and doping of each oxide layer set how fast HF removes it. The thickness, composition, and stress of each nitride layer set how much it loses and whether it holds. The TiN fill sets the pillar's stiffness, its seam, and its surface. The top isolation sets the remaining top-support thickness and the planarity on which the support-open mask is printed.

This chapter describes the incoming structure as the mold etch sees it, then the support lattice that must survive, and the support-open pattern that will perforate it.

**Learning Objectives:**
- Describe the TiN fill, its seam, and its top isolation, and their consequences for the mold etch
- Compare the HF behaviour of the undoped upper oxide and the doped lower oxide after thermal history
- Compute the solid fraction of the top and middle supports after the support open
- Explain the choices in the support-open pattern: opening size, pitch, placement, and shape
- Estimate the effect of support-open overlay on pillar exposure

---

## 2.1 The TiN Pillar

### 2.1.1 Fill Deposition

The bottom electrode is TiN deposited by thermal CVD or pulsed CVD from TiCl₄ and NH₃ at about 550–600 °C. It is conformal: it grows inward from the hole wall at the same rate on all sides until the two fronts meet in the middle.

```
Fill (reference):
  Hole diameter        32 (top) → 24 (bottom) nm
  TiN deposited        ≈ 18 nm on the field (fills to ≥ 16 nm radius)
  Fill growth rate     ≈ 0.4 nm/cycle (pulsed CVD)
  Residual Cl          ≤ 0.5 at% in the bulk, higher at the seam
  Resistivity          ≈ 150–200 µΩ·cm
  Young's modulus      ≈ 400 GPa (dense CVD TiN; 300–450 reported)
```

Because the hole tapers, the fronts meet first at the bottom and last near the bow and top. The result is a **seam**: a plane or line in the centre of the pillar where the two growth fronts met. A well-closed seam is a grain boundary. A poorly closed seam is a void, a keyhole, or a string of voids, typically near the bow where the hole is widest.

### 2.1.2 What the Seam Means to the Mold Etch

The seam matters in three ways:

1. **Stiffness.** A hollow or partly hollow pillar has a lower second moment of area. A keyhole of 6 nm in a 28 nm pillar reduces I by (6/28)⁴ = 0.2%, negligible. A seam that is open along a plane, so the pillar is two half-cylinders weakly joined, can halve the effective bending stiffness in one direction.
2. **Chemistry.** If the seam is open at the top after CMP, HF can enter the pillar. It finds no oxide there, but liquid and Cl-rich residue in the seam later outgas during the dielectric deposition.
3. **Top loss.** The seam is weakest at the top, and the support-open plasma etches faster along it. Chapter 13 treats seam opening.

### 2.1.3 Top Isolation

After the fill, TiN covers the whole wafer. It is removed from the field by CMP (or by a blanket etch-back) to leave each pillar isolated, with its top flush with the top support:

```
Top isolation (reference):
  Top SiN deposited         140 nm
  TiN CMP stop on SiN       ≈ 15 nm SiN consumed
  Touch-up                  ≈ 5 nm
  Remaining top SiN         120 nm (± 4 nm across the wafer, 3σ)
  Pillar dishing            0–3 nm below SiN top
```

The remaining top-support thickness matters twice: it is the first film the support open must clear, and it sets the stiffness of the top tie.

---

## 2.2 The Mold Oxides

### 2.2.1 Why Two Oxides

The mold has two oxide layers for reasons that Book #29 gave in terms of the hole etch: the lower oxide is doped so that it etches faster in the fluorocarbon plasma near the bottom of the hole, where ion flux is weakest. That same doping helps the dip-out, because doped oxide etches much faster in HF:

```
HF etch rate in 5 wt% HF, 25 °C (illustrative, after 600 °C thermal history):
  Thermal SiO₂ (reference)                     23 nm/min
  PE-TEOS, undoped (upper oxide)               70 nm/min   (3.0× thermal)
  BPSG, 3.5 wt% B, 4 wt% P (lower oxide)      600 nm/min  (26× thermal)
```

### 2.2.2 Thermal History

The TiN fill at 550–600 °C and any anneals after it densify the oxides. BPSG is particularly sensitive: its HF rate depends on its boron and phosphorus contents and on how far it has relaxed and outgassed. As-deposited BPSG may etch 1.5–2× faster than BPSG that has seen 600 °C for an hour. A change in fill temperature or a long queue at temperature shows up as a change in dip-out time.

```
Approximate dependence of BPSG HF rate (illustrative):
  +1 wt% B           → ×1.4
  +1 wt% P           → ×1.3
  +50 °C anneal      → ×0.85
```

### 2.2.3 Interfaces and Seams in the Oxide

The upper oxide is deposited on the middle support and the top support on the upper oxide. Any weak interface, such as a moisture-rich layer at the bottom of the PE-TEOS or a boron-rich skin on the BPSG, etches faster than the bulk. That is harmless. A dense skin, such as a nitrided or carbon-rich layer at an interface, etches slower and can leave a residual film on the support. Chapter 12 shows that the last oxide to go is usually at interfaces and in corners.

---

## 2.3 The Support Lattice

### 2.3.1 Support Films

```
Support films (reference):
                    Top support     Middle support    Bottom stop
  Thickness         120 nm          50 nm             20 nm
  Deposition        PECVD (low-H)   PECVD (low-H)     LPCVD
  Si/N ratio        ≈ 0.80          ≈ 0.80            0.75
  H content         ≈ 8 at%         ≈ 8 at%           ≈ 3 at%
  Stress            +250 MPa (T)    +250 MPa (T)      +1.0 GPa (T)
  HF rate (5%)      1.0 nm/min      1.0 nm/min        0.7 nm/min
  Young's modulus   ≈ 220 GPa       ≈ 220 GPa         ≈ 250 GPa
```

The supports are chosen for low HF etch rate first. Hydrogen-rich PECVD nitride etches several times faster in HF than LPCVD nitride. Low-H PECVD films (high RF power, low NH₃, or N₂-based chemistries) approach LPCVD behaviour at temperatures the TiN-free mold can tolerate.

### 2.3.2 Why Tensile

A support lattice in mild tension pulls itself flat and keeps the pillars straight. A lattice in compression, once released from the oxide that held it, can buckle out of plane, carrying pillars with it. The stress also must not be so tensile that the perforated lattice cracks at its narrowest ligaments. Chapter 11 develops the limits; +150 to +400 MPa is a common window.

### 2.3.3 The Solid Fraction

After the support open, each support is a perforated sheet with two kinds of holes: the pillars that pass through it and the support-open openings. The solid fraction is what holds the structure together:

```
Top support, per opening cell (90 nm hex, area 7015 nm², 4.05 pillars):
  Pillar area (d = 32 nm)          4.05 × 804 = 3256 nm²
  Opening area (d = 50 nm)         1963 nm²
  Overlap (3 crescents × 317 nm²)  951 nm²
  Union of holes                   3256 + 1963 − 951 = 4268 nm²
  Solid nitride                    7015 − 4268 = 2747 nm²  → 39%

Middle support (pillar d ≈ 30 nm, opening d ≈ 44 nm at that depth):
  Solid nitride                    ≈ 46%
```

Only about 40% of the top support is nitride after the support open, and the pillars passing through it are bonded to it only by adhesion and by the TiN deposited against the nitride hole wall. The lattice must carry the bending loads that drying applies to every pillar.

### 2.3.4 The Bottom Stop

The bottom stop is a 20 nm LPCVD-class nitride on the landing-pad level. Each pillar passes through it onto a tungsten landing pad. Between the pads lies the inter-pad oxide. If the dip-out penetrates the bottom stop anywhere, HF reaches that oxide and undercuts the pads. The bottom stop is therefore the most important barrier in the module: thin, uncovered by the support open, and exposed to HF for the longest time after the lower oxide is gone.

---

## 2.4 The Support-Open Pattern

### 2.4.1 Purpose and Constraints

The support-open pattern has three jobs:

1. Give HF access to every part of both oxide layers
2. Leave enough solid support to hold the pillars
3. Avoid weakening any pillar, and avoid exposing it more than necessary to the plasma

It also has two convenient freedoms. It is printed at a relaxed pitch, about twice the pillar pitch, so it is a single ArF-immersion exposure rather than a double self-aligned pattern. And it does not have to define the capacitor; it only has to perforate the lattice.

### 2.4.2 Reference Layout

```
Support-open layout (reference):
  Lattice           hexagonal, pitch 90 nm (2 × pillar pitch)
  Opening           circular, 50 nm at the top-support top
  Placement         centred on an interstitial (triangle centroid) site
  Distance to the three nearest pillars   26 nm (centre to pillar axis)
  Overlap depth into each of three pillars   25 + 16 − 26 = 15 nm (at top)
  Openings per pillar   1/4.05
  Open-area fraction    1963/7015 = 28%
```

```
Plan view (schematic, one opening cell):

        ○       ○       ○
            ○       ○
        ○     ( ◐◑ )     ○        ( ) opening, 50 nm
            ○   ◒   ○             ◐◑◒ crescents of three pillars
        ○       ○       ○             exposed in the opening
```

### 2.4.3 Alternatives

```
Pattern choice          Benefit                       Cost
─────────────────────────────────────────────────────────────────────────
Circles on interstitials Small TiN exposure; strong    Long lateral paths at
(reference)              lattice                       higher pitch
Elongated slots         Shorter lateral paths;        Weaker lattice along
(between rows)          faster dip-out                the slot direction
Openings centred        Simple overlay target         Exposes a whole pillar
on pillars                                            top; large TiN loss
Larger openings,        Fewer, faster openings        More TiN exposure; less
larger pitch                                          solid support
```

### 2.4.4 Overlay

The opening is placed relative to the pillar lattice, which was itself formed by a double-patterned honeycomb. An overlay error δ moves the opening closer to one or two of its three pillars:

```
Overlap depth into the nearest pillar = 15 + δ (nm)

δ = 0       15 nm (reference crescent, 317 nm²)
δ = +4 nm   19 nm (crescent ≈ 440 nm²)
δ = +8 nm   23 nm (crescent ≈ 570 nm², 70% of the pillar top)
```

A large crescent exposes more TiN to the plasma (Chapter 3, Chapter 13) and removes nitride from one side of the pillar's support collar, weakening the tie on that side. A support-open overlay budget of about ±5 nm (mean + 3σ) is typical.

---

## 2.5 The Support-Open Mask

```
Support-open mask stack (reference):
  ACL (amorphous carbon)     300 nm
  SiON cap                   25 nm
  BARC + resist              ArF immersion, single exposure
  Mask open                  SiON (CF₄/CHF₃), ACL (O₂/COS or N₂/H₂)
  ACL CD after open          50 nm (target), ±2.5 nm 3σ
```

The ACL is deposited at ≤ 450 °C on top of the isolated pillars. Its thickness is set by the support-open etch: about 820 nm of nitride and oxide at a selectivity to ACL of about 4 for the oxide step, plus margin. Chapter 3 works out the mask budget.

---

## Summary and Key Takeaways

1. **The pillar has a seam.** It costs little stiffness when closed, but it opens under plasma and holds residue when not.

2. **The lower oxide is fast.** BPSG etches 26× faster than thermal oxide in HF, 8.6× faster than the upper PE-TEOS. Its thermal history sets its rate.

3. **The supports are 39–46% solid after the open.** The lattice is a perforated sheet that must hold every pillar.

4. **The bottom stop is the critical barrier.** 20 nm of nitride, exposed longest, over the oxide around the landing pads.

5. **The support-open pattern is relaxed but placed.** 50 nm openings on a 90 nm lattice, 28% open; overlay moves the TiN crescent from 15 nm toward most of a pillar top.

---

## Study Questions

1. Using the HF rates in Section 2.2.1, how long does it take to remove 760 nm of BPSG and 650 nm of PE-TEOS vertically, if the etch could proceed at the blanket rate? Why is this not the dip-out time?

2. An extra hour at 600 °C reduces the BPSG HF rate by 15%. How much longer does the lower-oxide removal take, and how much additional support loss does it cause at 1.0 nm/min?

3. Recompute the solid fraction of the top support for 56 nm openings on the same 90 nm lattice.

4. With an overlay error of +6 nm toward one pillar, what is the overlap depth into that pillar and into the other two (assume the error is along the line to one pillar)?

5. A pillar seam opens fully along one plane through the axis. Estimate the bending stiffness in the direction perpendicular to that plane relative to a solid pillar. (Hint: treat the pillar as two half-discs bending independently.)

6. Why is a compressive support lattice more dangerous after the dip-out than before it?

---

**Next Chapter:** [Chapter 3: Support-Open Etch Physics](./03-support-open-etch-physics.md)

---

**Chapter 2 Development Status:** Complete  
**Version:** 1.0
