# Chapter 13: Electrode Integrity — TiN Oxidation, Fluorine Uptake, Top Recess & Seams

## Overview

The mold etch hands the dielectric ALD a surface. That surface is the outer few ångströms of every TiN pillar, and it becomes the bottom interface of the capacitor. A titanium oxide or oxyfluoride layer on the TiN changes the effective EOT, the work function, the leakage, and the nucleation of the high-k film. A pillar top eroded in the support-open etch or a seam opened by it changes the geometry and the local field. This chapter treats what the module does to the electrode and how to limit it.

**Learning Objectives:**
- Describe the oxidation and fluorination of TiN in plasma strip, HF, water, and air
- Relate a TiOₓ or TiOₓFᵧ interfacial layer to EOT, leakage, and capacitance
- Quantify pillar-top loss from the support open and its consequences
- Explain how seams open and what they do to the capacitor
- Set queue-time and surface-preparation limits before the dielectric

---

## 13.1 TiN Surface Chemistry

### 13.1.1 Native Oxide

TiN exposed to air forms a native oxide of TiO₂ and TiOₓNᵧ, about 1–2 nm thick, within minutes to hours. Inside the mold, the TiN outer surface has been in contact with oxide since the fill, with a thin Ti–O–Si interfacial layer (Chapter 12). The dip-out removes the SiO₂ but not most of the titanium oxide.

### 13.1.2 In HF

HF dissolves TiO₂ slowly compared with SiO₂. In 5% HF, TiO₂ from oxidized TiN etches at a fraction of a nanometre per minute, and the surface becomes partly fluorinated:

```
TiN surface after 105 s of 5% HF (illustrative, XPS):
  Ti–N            dominant
  Ti–O / Ti–O–N   ≈ 0.5–0.8 nm equivalent
  Ti–F            3–6 at% in the top 2 nm
  Si              ≤ 0.5 at% (residual silicate)
```

The HF step thins the oxide that was there, but it leaves fluorine behind. Fluorine is not entirely harmful: a small amount at the interface passivates traps in the subsequent high-k. Large amounts produce volatile TiF₄ during the dielectric deposition, roughen the interface, and raise leakage.

### 13.1.3 In Water

The DIW rinse that follows the HF contains dissolved oxygen unless degassed (Chapter 6). TiN oxidizes in water:

```
TiN oxidation in rinse water, 45 s (illustrative):
  Air-saturated DIW (8 ppm O₂)   +0.3–0.5 nm TiOₓ
  Degassed DIW (≤ 5 ppb O₂)      +0.05–0.1 nm
```

### 13.1.4 In IPA and Air

IPA displaces water and dries the surface; it causes little oxidation itself. After drying, the TiN is exposed to clean-room air until the wafer reaches the ALD chamber. Oxidation in air is logarithmic in time: most of it occurs in the first hour.

```
Queue-time oxidation (air, 22 °C, 45% RH, illustrative):
  1 h      +0.3 nm
  4 h      +0.5 nm
  24 h     +0.8 nm
```

---

## 13.2 What the Interface Costs

### 13.2.1 EOT

A TiO₂-like interfacial layer has a dielectric constant of 30–80 depending on crystallinity and stoichiometry, much higher than SiO₂. In isolation it would barely affect EOT. But the interfacial oxide on TiN is substoichiometric, nitrogen-containing, and partly conducting. It behaves as a lossy layer that affects leakage more than capacitance:

```
Effect of TiOₓ interfacial layer (illustrative):
  EOT contribution     ≈ t_TiOₓ × 3.9/40 → 1 nm adds ≈ 0.1 nm EOT
  ΔC_s at EOT 0.50     ≈ −16% per nm of TiOₓ (if fully insulating)
  Observed ΔC_s        ≈ −2 to −6% per nm (partly conducting layer)
  Leakage              rises with Ti³⁺ and oxygen vacancies at the interface
```

### 13.2.2 Work Function and Leakage

The leakage of a ZrO₂-based capacitor is set largely by the conduction-band offset between the electrode and the dielectric. TiN has a work function near 4.5–4.7 eV. An oxidized surface shifts it, and a fluorinated one shifts it further. Trap-assisted conduction through defects in a TiOₓ layer adds a path. Both effects appear as an increase in the leakage tail of the retention distribution rather than in the median.

### 13.2.3 Specification

```
TiN surface before dielectric ALD (reference):
  TiOₓ (XPS, equivalent thickness)    ≤ 1.0 nm
  F at surface (XPS)                  ≤ 3 at%
  Si at surface (XPS)                 ≤ 0.5 at%
  C at surface (XPS)                  ≤ 5 at%
  Queue time dip-out → ALD            ≤ 4 h (in N₂ stocker ≤ 12 h)
```

---

## 13.3 Pillar-Top Loss

### 13.3.1 Where It Comes From

Chapter 3 estimated the support-open etch removes about 5 nm of TiN from the crescents exposed in each opening. The ACL strip then oxidizes them. Three in four pillars have a crescent; the remaining quarter are untouched. The result is a population of pillar tops with three shapes: intact, one crescent eroded, or (with overlay error) two crescents eroded.

### 13.3.2 Consequences

```
Top-loss consequences (illustrative):
  Capacitance: the pillar top is above the top support and contributes
    little area; loss of 5 nm of height on a crescent ≈ negligible
  Field concentration: a sharp eroded edge raises the local field in
    the dielectric at the pillar top by 10–30% → leakage hot spot
  Top support clamp: an eroded crescent reduces the TiN–SiN contact
    height on that side by 5 nm of 120 nm (≈ 4%)
  Plate contact: the plate wraps over the top; roughness there raises
    plate-to-node leakage
```

The field concentration at the pillar top is the main reason TiN top loss is specified. A rounded crescent edge is far less harmful than a sharp one. Bias pulsing and polymer-rich nitride chemistry (Chapter 5) reduce both the loss and the sharpness.

---

## 13.4 Seams

### 13.4.1 Seam Opening

The pillar's central seam (Chapter 2) reaches the top surface after CMP. In the support-open etch, the plasma attacks the seam faster than the surrounding TiN for those pillars whose tops are exposed in an opening:

```
Seam behaviour in the support open (illustrative):
  Closed seam (grain boundary):   etches ≈ 1.5× faster → shallow groove
  Partly open seam (voids):       plasma enters → groove 20–60 nm deep
  Open keyhole near the top:      plasma and polymer enter the keyhole
```

### 13.4.2 Consequences for the Dip-Out

An open seam is a slot in the pillar. During the dip-out, HF, water, and IPA enter it. They do not etch the TiN, but the seam is a capillary: it holds liquid after the outer surface has dried and releases it slowly. Liquid drying inside a seam can leave residues (silicate, fluoride) that outgas in the ALD chamber. A pillar whose seam has opened along a plane through its axis also has reduced bending stiffness in one direction (Chapter 10), which makes it more likely to lean, and in a preferred direction.

### 13.4.3 Consequences for the Capacitor

The dielectric and plate cannot fill a seam narrower than about 10 nm. An open seam at the top of the pillar is therefore a void covered by the dielectric. It does not short, but it adds a sharp re-entrant corner in the dielectric at the seam lip, another field hot spot.

### 13.4.4 Control

- **Fill.** Deposition conditions that close the seam (slower final growth, higher temperature at the end of the fill)
- **Top isolation.** CMP that does not open the seam (low-pressure finish, selective slurry)
- **Support-open placement.** Openings that intrude less into the pillar tops (Chapter 2) expose fewer seams

---

## 13.5 Surface Preparation Before the Dielectric

Some flows add a treatment between the dip-out and the dielectric ALD to reset the TiN surface:

```
Pre-ALD treatments (illustrative):
  Treatment                     Effect                          Risk
  ───────────────────────────────────────────────────────────────────────
  In-situ NH₃ anneal (350 °C)   Reduces TiOₓ, removes F         Pillar stress change;
                                                                 slight leaning
  H₂ plasma (remote)            Reduces oxide; removes C         Ti hydride; damage
  In-situ ALD-chamber pre-dose  Nucleation layer on TiN          None significant
  (e.g. Al₂O₃ or TMA pulse)
  Vapor HF touch-up             Removes residual silicate        F uptake; P residue
```

The most robust approach is to minimize what the dip-out leaves: degassed rinse, short and controlled HF, rapid drying, and a short, inert queue to the ALD chamber.

---

## Summary and Key Takeaways

1. **The dip-out hands the dielectric a surface.** About 0.5–0.8 nm of TiOₓ and a few percent fluorine after HF.

2. **Water and air add oxide.** Air-saturated rinse adds 0.3–0.5 nm; a 4 h queue adds 0.5 nm.

3. **The interface affects leakage more than capacitance.** A partly conducting TiOₓ costs a few percent of C_s but widens the leakage tail.

4. **Pillar-top loss matters at the edge.** A sharp eroded crescent is a field hot spot.

5. **Seams open in the support open.** Open seams trap liquid, soften pillars in one direction, and leave voids under the dielectric.

---

## Study Questions

1. A wafer waits 20 h between dip-out and ALD in air. Estimate the TiOₓ added and its effect on C_s using the observed −2 to −6% per nm.

2. Compare the oxidation in a 45 s rinse with air-saturated and degassed DIW. How much does degassing buy relative to the queue-time limit?

3. Estimate the field enhancement at a crescent edge with a radius of curvature of 2 nm relative to a flat surface, for a 5 nm dielectric. (Use the field at a cylinder of radius r surrounded by a coaxial layer.)

4. Why does fluorine at the interface in small amounts reduce leakage, while in large amounts it raises it?

5. A seam opens 40 nm deep in 10% of the pillars exposed in openings. Estimate the number of pillars per die affected, and propose two process changes to reduce it.

---

**Next Chapter:** [Chapter 14: Advanced Schemes — Taller Molds, Three Supports, Silicon Molds, 4F² & 3D DRAM](./14-advanced-mold-schemes.md)

---

**Chapter 13 Development Status:** Complete  
**Version:** 1.0
