# Chapter 10: Pillar Leaning, Bending & Collapse

## Overview

The defining failure of the mold etch is a pillar that does not stand straight. Two neighbouring pillars that touch, or come so close that the dielectric and plate cannot fill between them, become a short or a pair of low-capacitance cells. A pillar that leans without touching narrows the gap on one side and may later touch under the stress of the plate fill. Leaning defects are the main reason the supports exist, the main reason drying is engineered so carefully, and the main yield signature of the module.

This chapter builds a simple mechanical model of a supported TiN pillar, derives the collapse threshold for capillary loading, shows why collapse comes in pairs, introduces a statistical model that connects the mean drying conditions to a defect rate of one in a billion, and treats stress-driven leaning and its control.

**Learning Objectives:**
- Compute the bending stiffness of a pillar span from its diameter, length, and modulus
- Derive the deflection of a clamped span under a capillary load
- Derive the elastocapillary collapse threshold for a single pillar and for a pair
- Estimate the leaning probability from a distribution of meniscus asymmetry
- Evaluate the sensitivity of leaning to pillar diameter, span length, and fluid
- Explain why touching pillars stay stuck, and how stress and initial lean add to the problem

---

## 10.1 The Pillar as a Beam

### 10.1.1 Second Moment of Area

```
Solid circular section, diameter d:
  I = π d⁴ / 64

d = 28 nm: I = π × 28⁴ / 64 = 3.02 × 10⁴ nm⁴ = 3.02 × 10⁻³² m⁴
E (CVD TiN) = 400 GPa
EI = 1.21 × 10⁻²⁰ N·m²
```

Stiffness scales as d⁴. A pillar 1 nm thinner (27 nm) has 86% of the stiffness; 2 nm thinner, 74%.

### 10.1.2 Boundary Conditions

The pillar is anchored at four places: the landing pad and bottom stop at its foot, the middle support at 770–820 nm, and the top support at 0–120 nm. Between them it has two free spans:

```
  Top support (120 nm)  ═══╪═══   clamp
                           │      upper free span L_u = 650 nm
  Middle support (50 nm)═══╪═══   clamp
                           │      lower free span L_l = 760 nm
  Bottom stop (20 nm)   ═══╪═══   clamp
  Landing pad              ▀
```

Each support is a thin perforated plate. It restrains the pillar laterally and, to a degree, rotationally. A clamped–clamped beam is the stiff limit and a pinned–pinned beam the soft limit:

```
Maximum deflection under uniform load q over span L:
  clamped–clamped:  δ = q L⁴ / (384 EI)
  pinned–pinned:    δ = 5 q L⁴ / (384 EI)   (5× softer)
```

A 120 nm top support around a 32 nm pillar clamps well. The 50 nm middle support, perforated by openings and with a TiN collar only 50 nm tall, clamps less well. The reference model uses clamped–clamped for both spans and treats rotational compliance at the middle support as a sensitivity.

---

## 10.2 Capillary Load

From Chapter 8, the unbalanced capillary load per unit length on a pillar is

```
q = α · ΔP · d = α · (2γ cos θ / g) · d
```

For the lower span with water and α = 1:

```
q = (2 × 0.072 / 17 × 10⁻⁹) × 28 × 10⁻⁹ = 0.237 N/m
δ = q L⁴ / (384 EI) = 0.237 × (760 × 10⁻⁹)⁴ / (384 × 1.21 × 10⁻²⁰)
  = 0.237 × 3.34 × 10⁻²⁵ / 4.63 × 10⁻¹⁸ = 1.71 × 10⁻⁸ m = 17.1 nm
```

Without the middle support, the span would be the whole 1580 nm. The deflection scales as L⁴, a factor of (1580/760)⁴ = 18.7, giving 320 nm even clamped at both ends. Without any support at all, as a cantilever (δ = qL⁴/8EI), it would be about 15 µm. These numbers explain why a support lattice is not optional for a pillar this slender.

```
Linear deflection, lower span (d = 28 nm, clamped–clamped):
                  α = 1      α = 0.15
  Water           17.1 nm    2.6 nm
  IPA 25 °C       5.2 nm     0.77 nm
  Upper span (650 nm) is (650/760)⁴ = 0.53 of these values.
```

---

## 10.3 The Collapse Threshold

### 10.3.1 One Pillar, Rigid Neighbour

The capillary pressure is inversely proportional to the gap. As a pillar bends toward a neighbour, the gap on that side narrows and the pressure rises. If the neighbour is rigid and the pillar deflects by δ, the load becomes q₀·g/(g − δ). The equilibrium deflection satisfies

```
δ = δ₀ · g / (g − δ)        (δ₀ = linear deflection at the initial gap)
δ² − g δ + δ₀ g = 0
δ = [g − √(g² − 4 δ₀ g)] / 2

Real solution exists only if δ₀ ≤ g/4.
```

For δ₀ > g/4 there is no equilibrium short of contact: the pillar snaps to its neighbour. At δ₀ = g/4 the pillar has already moved g/2 before going unstable.

### 10.3.2 A Pair

In a forest, the neighbour is not rigid. Two pillars with liquid between them and drier surroundings are pulled toward each other symmetrically. The gap closes at 2δ:

```
δ = δ₀ · g / (g − 2δ)
2δ² − g δ + δ₀ g = 0
Real solution only if δ₀ ≤ g/8

g = 17 nm → pair threshold δ₀ = 2.1 nm
```

The pair threshold is half the single-pillar threshold. Pairs are the commonest collapse mode in practice; triples and larger clusters form when a pair's collapse leaves an asymmetric meniscus on a third pillar.

### 10.3.3 Margins

```
Pair margin M = (g/8) / δ₀ at α = 0.15:
  Water        0.83   (collapses)
  IPA 25 °C    2.8
  IPA 50 °C    3.0
  HFE          4.4
```

A margin of 2.8 means the effective asymmetry α must reach 0.15 × 2.8 = 0.41 before an IPA-dried pair collapses.

---

## 10.4 From Margin to Defect Rate

### 10.4.1 A Distribution of Asymmetry

No drying front is uniform at the scale of individual pillars. The effective α varies from gap to gap with local film thickness, roughness, small residues, and the exact moment each meniscus depins. A useful model treats α as lognormal:

```
ln α ~ Normal(ln 0.15, σ = 0.17)

Collapse probability per pair site:
  P = P(α > α_crit) = ½ erfc[ ln(α_crit/0.15) / (σ√2) ]
```

### 10.4.2 The Reference Result

```
IPA 25 °C:  α_crit = 0.41 → z = ln(2.76)/0.17 = 5.97 → P ≈ 1.2 × 10⁻⁹
Water:      α_crit = 0.12 → z = −1.1           → P ≈ 0.86 (nearly all)
IPA 50 °C:  α_crit = 0.45 → z = 6.46           → P ≈ 5 × 10⁻¹¹
HFE:        α_crit = 0.66 → z = 8.7            → P ≈ 10⁻¹⁸
```

The reference process sits at about one collapse per billion sites, the specification of Chapter 1. The model is crude, and σ = 0.17 is a fitting parameter, but it captures the essential behaviour: leaning sits deep in the tail of a distribution, so small changes in the mean margin produce large changes in the defect rate.

### 10.4.3 Sensitivity

```
Change                                 New margin   P (per site)    Factor
───────────────────────────────────────────────────────────────────────────
Reference (IPA, d = 28, L = 760)       2.76         1.2 × 10⁻⁹      1
Pillar 1 nm thinner, same gap          2.47         4.9 × 10⁻⁸      ≈ 40×
  (d = 27, g = 17: local TiN loss)
Pillar 1 nm thinner, same pitch        2.77         1.1 × 10⁻⁹      ≈ 1×
  (d = 27, g = 18)
Lower span 40 nm longer (L = 800)      2.25         ≈ 9 × 10⁻⁷      ≈ 800×
Gap 11.5 nm in the lower span         ≈ 1.3*       ≈ 9 × 10⁻²      —
E = 350 GPa (less dense TiN)           2.41         ≈ 1 × 10⁻⁷      ≈ 90×
IPA at 50 °C                           3.0          5 × 10⁻¹¹       ≈ 0.04×
───────────────────────────────────────────────────────────────────────────
* The bow is at 350 nm depth, in the upper span, where the span factor
  (0.53) partly compensates: g/8 falls to 1.44 nm and ΔP rises by 1.48×;
  the local upper-span margin is ≈ 1.44 / (0.77 × 0.53 × 1.48) ≈ 2.4.
  The local-gap row shows the danger if a bow of that size sat in the
  lower span instead.
```

Three lessons follow. First, the lower span is the weak point, and every ten nanometres of span length and every loss of stiffness at fixed gap matter by orders of magnitude in defect rate. Second, at fixed pitch the margin scales as d³g² = d³(a − d)², which is maximal at d = 0.6a = 27 nm: the reference pillar sits almost exactly at the mechanical optimum, so a uniformly thinner pillar costs capacitance, not stability. Third, a profile defect from the hole etch, such as a bow or a twist that narrows a gap, sets the local margin. Leaning maps often mirror hole-etch signatures.

---

## 10.5 Why Touching Pillars Stay Stuck

Once two pillars touch, the liquid between them evaporates, and the question becomes whether elastic restoring force can pull them apart against adhesion:

```
Restoring force of the lower span at mid-span contact (each pillar bent g/2):
  k (point load at centre, clamped–clamped) = 192 EI / L³
    = 192 × 1.21 × 10⁻²⁰ / (760 × 10⁻⁹)³ = 5.3 N/m
  F_el = k × g/2 = 5.3 × 8.5 × 10⁻⁹ = 45 nN

Van der Waals adhesion between two parallel cylinders at contact:
  F/ℓ = A / (8√2 D^(5/2)) × √(R/2)
  A ≈ 3 × 10⁻¹⁹ J (TiN with a thin oxide), D ≈ 0.3 nm, R = 14 nm
  F/ℓ ≈ 0.45 N/m → over a contact length ℓ:
    ℓ = 50 nm  → 22 nN (pillars may spring back)
    ℓ = 100 nm → 45 nN (balance)
    ℓ = 200 nm → 90 nN (stuck)
```

Real contacts are rarely clean: residues from the drying liquid (dissolved silicate, fluoride salts) form solid bridges as they dry, and the contact length grows as the pillars zip together. In practice, pillars that touch during drying stay touching. The defect is irreversible, which is why prevention, not repair, is the strategy.

---

## 10.6 Stress-Driven Leaning

Not all leaning comes from capillarity. A pillar can lean in a dry environment if the supports or the pillar carry unbalanced stress:

1. **Support stress gradients.** A support that is more tensile on one side of an array block than the other pulls the pillars toward the more tensile region after the oxide, which balanced the stress, is gone. Leaning appears at array edges and near large open areas in the support-open pattern.
2. **Asymmetric support-open openings.** Overlay error (Chapter 2) removes more of the support collar from one side of a pillar, so the restoring stiffness differs by direction.
3. **Pillar residual stress.** CVD TiN carries intrinsic stress (compressive or tensile depending on conditions). A stress gradient through the pillar, for example from the seam or from a surface layer oxidized during the dip-out, bends it like a bimetal.
4. **Initial lean from the hole.** A hole that twisted or tilted in the etch (Book #29) produces a pillar whose axis is already off-vertical. The gap to one neighbour is smaller before any load.

```
Effect of an initial lean δ_i toward a neighbour (pair, both leaning):
  Effective gap g' = g − 2δ_i
  Threshold scales with g' and ΔP with 1/g', so the margin scales ≈ (g'/g)²
  δ_i = 1.5 nm each → g' = 14 nm → margin × 0.68 → 2.76 → 1.87
  → P rises from ≈ 10⁻⁹ to ≈ 10⁻⁴ locally
```

---

## 10.7 Controlling Leaning

```
Lever                        Effect                          Cost
────────────────────────────────────────────────────────────────────────
Lower γ (IPA → HFE, SC-CO₂)  Margin ×1.5 to ∞                Cost, time
Orderly drying front         Lowers median α and σ           Tool design
Shorter lower span           Margin ∝ L⁻⁴                    Capacitance (support
(move middle support down)                                   area), hole etch steps
Pillar diameter at fixed     Margin ∝ d³(a − d)²; flat       Capacitance rises with d
pitch                        near optimum d = 0.6a
Third support                Halves a span: margin × ≈ 16    Capacitance, process
Denser TiN (higher E)        Margin ∝ E                      Fill conditions
Remove initial lean          Margin ∝ (g'/g)²                Hole etch twist/tilt
```

The middle-support position is the strongest design lever. Equalizing the spans (705 nm each instead of 650/760) raises the lower-span margin by (760/705)⁴ = 1.35 and lowers the upper-span margin by (650/705)⁴ = 0.72; the weaker span then has a higher margin than before.

---

## Summary and Key Takeaways

1. **The lower span is the weak point.** 760 nm of 28 nm TiN deflects 17 nm under a full water meniscus.

2. **Collapse is a snap instability.** Single pillar at δ₀ > g/4; a pair at δ₀ > g/8 = 2.1 nm.

3. **Leaning lives in the tail.** With IPA, a margin of 2.8 gives about one collapse per billion sites; 40 nm more span is a factor of about 800. At fixed pitch the pillar diameter is already near its mechanical optimum.

4. **Touching is permanent.** Adhesion over 100 nm of contact equals the elastic restoring force.

5. **Profile and stress set the local margin.** Bows, twists, overlay, and stress gradients produce leaning maps that echo upstream signatures.

---

## Study Questions

1. Compute the lower-span pair margin for d = 26 nm with IPA at 25 °C, and the collapse probability with the lognormal model.

2. The middle support is treated as pinned instead of clamped (5× softer). What happens to the margin? What does this tell you about the importance of the TiN–nitride bond at the support collar?

3. Derive the pair threshold for a row of three pillars in which the middle one is pulled equally from both sides and the outer two are pulled toward it. Is the middle pillar stable?

4. With σ = 0.17, what median α must the drying front achieve to keep P below 10⁻⁹ for a structure whose margin at α = 0.15 is 2.0?

5. Equalize the spans at 705 nm. Compute both margins and the collapse probabilities in each span with IPA.

6. A pillar with a seam open along one plane has half the stiffness in one direction. Estimate its collapse probability and explain why seam-related leaning has a preferred direction.

---

**Next Chapter:** [Chapter 11: Support Lattice Integrity](./11-support-lattice-integrity.md)

---

**Chapter 10 Development Status:** Complete  
**Version:** 1.0
