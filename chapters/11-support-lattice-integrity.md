# Chapter 11: Support Lattice Integrity

## Overview

The supports are what make a 57:1 pillar possible. After the dip-out they are two perforated nitride sheets, about 40% and 46% solid, holding up a forest of seventeen billion pillars and themselves held up only by those pillars and by the array edge. A support that thins too much, cracks at a ligament, sags under its own stress, or peels at the array boundary releases the pillars it was holding. Unlike a single leaning pair, a support failure takes out a region: tens to thousands of cells.

This chapter treats the four ways the lattice fails: chemical thinning in HF, ligament fracture, out-of-plane deformation, and edge peeling. It ends with design rules for the supports.

**Learning Objectives:**
- Compute support thinning from HF exposure and its effect on stiffness and strength
- Estimate stress concentration and fracture risk at the narrowest ligaments
- Explain how support stress and the loss of the oxide change the lattice shape
- Describe edge peeling and the array-boundary design that prevents it
- State design rules for support thickness, stress, and open fraction

---

## 11.1 Thinning in HF

### 11.1.1 The Loss Budget

From Chapter 4, the reference dip-out removes about 1.75 nm per exposed face of support nitride. The faces exposed, and for how long, differ:

```
Support nitride loss (reference, 105 s HF at 1.0 nm/min):
  Top support      top face      1.75 nm (exposed whole dip)
                   underside     ≈ 1.3 nm (after upper oxide clears, ≈ 80 s)
                   column wall   ≈ 1.75 nm (lateral, widens openings)
  Middle support   top face      ≈ 1.3 nm
                   underside     ≈ 0.7 nm (after lower oxide clears locally)
                   column wall   ≈ 1.75 nm
  Thickness after dip-out:  top ≈ 117 nm; middle ≈ 48 nm
  Opening CD growth:        ≈ +3.5 nm (both sides)
```

The thickness loss matters little. The lateral loss matters more: it widens every opening and narrows every ligament between an opening and its neighbouring pillars.

### 11.1.2 Where Thinning Is Faster

Nitride etches faster in HF where it is less dense or richer in hydrogen. The support films are not uniform:

- **Near the pillar collar.** The nitride adjacent to the TiN was the wall of the capacitor hole. The hole etch modified it: fluorine and ion damage in the top few nanometres, and sometimes a thin oxidized layer from the post-etch strip. The collar etches faster than the bulk and can open a gap around the pillar, loosening its clamp.
- **At the column wall.** The support-open plasma damages the nitride at the column wall in the same way.
- **Seams in the support film.** A PECVD nitride deposited over topography forms weak seams; the supports are deposited on a flat mold, so seams are rare, but particles embedded in the film create local weak spots.

```
Illustrative HF rates:
  Bulk support nitride         1.0 nm/min
  Plasma-damaged surface       3–5 nm/min (first 1–2 nm)
  Collar after hole-etch strip 2–3 nm/min (first 1–3 nm)
```

A collar that loses 4 nm instead of 1.75 nm turns a tight clamp into a loose one. Chapter 10 showed that a pinned span is five times softer than a clamped one.

---

## 11.2 Ligament Fracture

### 11.2.1 The Narrowest Ligament

The solid nitride of the top support is a network of ligaments between pillar holes and opening holes. The narrowest are between an opening and its three intruding pillars, where the opening has cut away part of the pillar collar (Chapter 2), and between adjacent pillars away from openings.

```
Ligament widths, top support (reference, after dip-out):
  Pillar to pillar (no opening):      45 − 32 = 13 nm
  Pillar to next opening (not its own): ≈ 90/√3 − 25 − 16 − 1.75 ≈ 9 nm
  At a crescent: the opening cuts into the pillar; the collar remains
    on ≈ 60% of the pillar perimeter
```

### 11.2.2 Stress Concentration

A tensile membrane stress σ₀ in a perforated plate is concentrated at the edges of the holes. For a single circular hole in an infinite plate the factor is 3. For a dense lattice of holes with narrow ligaments it is set by the ligament fraction. A rough estimate uses the net-section stress:

```
Net-section stress across a row:
  σ_net ≈ σ₀ × (row pitch / solid width along the row)
  Top support, along a row through openings:
    solid fraction along the line ≈ 0.35 → σ_net ≈ 2.9 σ₀
  Local peak at a hole edge ≈ 2 × σ_net ≈ 6 σ₀

σ₀ = +250 MPa → local peak ≈ 1.5 GPa
```

Thin PECVD nitride films have fracture strengths in the range of 3–6 GPa when defect-free. A peak of 1.5 GPa leaves a safety factor of about 2–4, which is consumed by defects: a nano-crack from the support-open etch, a particle inclusion, or a notch where a collar has been etched back.

### 11.2.3 Fracture Patterns

```
Observed crack signatures:
  Straight cracks along lattice rows    → net-section failure; stress too
                                           high or support too thin
  Cracks radiating from one opening      → local defect (particle, notch)
  Cracks at the array edge               → stress discontinuity (11.4)
  Cracks after drying only               → capillary loading of the lattice
                                           itself (liquid on the support)
```

A crack through the top support releases the clamp on the pillars along it. Those pillars become effectively cantilevered from the middle support, with a free length of 770 nm above it, and lean in groups. A cracked middle support is worse: the lower span becomes 1580 nm long.

---

## 11.3 Out-of-Plane Deformation

### 11.3.1 Sag and Bulge

Before the dip-out, the supports are embedded in oxide and their stress is balanced by it. After the dip-out, each support is a membrane suspended on the pillars. A tensile membrane stays flat. A compressive one can buckle if its compressive stress exceeds the critical buckling stress for its span between anchors:

```
Buckling of a clamped plate strip of width b and thickness t:
  σ_cr ≈ (π² E / (3(1 − ν²))) × (t/b)²

The relevant span is between pillars (≈ 45 nm), with t = 50 nm (middle):
  σ_cr far exceeds any film stress → no local buckling between pillars
Across a large unsupported region (e.g., a missing pillar block, b ≈ 1 µm):
  σ_cr ≈ (π² × 220 GPa / 2.7) × (0.05)² ≈ 2.0 GPa
  → buckling needs a compressive stress near 2 GPa, or a region
    several µm wide
```

The pillars support the lattice densely, so the lattice itself rarely buckles in the array. What does happen is global deformation of a whole array block when the supports and the pillars carry different stresses.

### 11.3.2 Pillar–Support Stress Mismatch

The pillars bridge the top support, the middle support, and the bottom stop. If the top support is more tensile than the middle, it pulls the pillar tops inward toward the block centre more than the middle support pulls the middle. The pillars tilt, by an amount set by the stiffness of the lattice relative to the pillar bending. The effect is largest at the block edge, where the stress is unbalanced on one side.

```
Edge tilt estimate (illustrative):
  Top support tensile 250 MPa, 120 nm → force per unit edge length
    F = σ t = 250 MPa × 120 nm = 30 N/m
  Shared among the pillars in the outer rows; if ≈ 10 rows take the load
  at 39 nm per row (row spacing):
    force per pillar ≈ 30 N/m × 45 nm / 10 = 1.35 × 10⁻⁷ N (135 nN)
  Pillar top as a cantilever from the middle support (770 nm, end load):
    δ = F L³ / (3 EI) = 1.35×10⁻⁷ × (770×10⁻⁹)³ / (3 × 1.21×10⁻²⁰)
      ≈ 1.7 µm
  This is impossible; it means the pillars cannot carry the load at all.
  The top support carries its own stress in-plane, and the pillars see
  only the small residual imbalance.
```

The arithmetic shows that the support stress cannot be carried by pillar bending at all. It is carried in-plane by the lattice and transferred to the periphery at the array edge. That transfer, at the edge, is the vulnerable point.

---

## 11.4 The Array Edge

### 11.4.1 The Boundary

At the edge of the cell array, the supports continue into the periphery, where the mold is not perforated by capacitor holes. Typically, the periphery mold is protected from the dip-out by keeping the support-open pattern inside the array, so the periphery oxide stays and the supports are anchored on it. The array edge is therefore where a free-standing lattice meets an embedded one.

```
Array edge (cross-section, schematic):
  periphery: support on oxide        array: support on pillars
  ══════════════════════╗           ═══╪═══╪═══╪═══
  oxide (remains)       ║ HF front     │   │   │
  ══════════════════════╣ stops here ══╪═══╪═══╪═══
  oxide                 ║              │   │   │
```

### 11.4.2 The Edge Undercut

HF does not stop exactly at the last opening. It continues laterally under the support into the periphery oxide, as far as it can etch in the dip time:

```
Undercut into the periphery (reference):
  Upper oxide (PE-TEOS): 70 nm/min × ≈ 80 s ≈ 95 nm
  Lower oxide (BPSG):    600 nm/min × ≈ 40 s ≈ 400 nm  (after the front
                         reaches the edge)
```

The lower-oxide undercut is large. A ledge of support nitride 400 nm wide, unsupported by pillars, forms at the array edge. It is a cantilever plate, and its stress acts on its root. A tensile support curls up; a compressive one curls down. Either loads the anchor and can peel the support from the periphery oxide.

### 11.4.3 Edge Design

1. **Dummy pillars.** Several rows of dummy capacitor pillars outside the active array support the ledge region.
2. **Guard ring.** A continuous nitride or TiN wall around the array, formed in a trench through the mold, stops the lateral HF front.
3. **Support-open pattern taper.** Openings near the edge are smaller or absent, so the lower oxide near the edge is removed later and the undercut is shorter.
4. **Periphery oxide doping.** An undoped periphery lower oxide etches slower and limits the undercut.

---

## 11.5 Design Rules for the Supports

```
Support design guide (reference class, illustrative):
                              Top            Middle          Bottom stop
  Thickness                   100–140 nm     40–60 nm        15–30 nm
  Stress                      +150 to +400 MPa (tensile)     ≤ +1.2 GPa
  HF rate (5%, 25 °C)         ≤ 1.2 nm/min   ≤ 1.2 nm/min    ≤ 0.8 nm/min
  Solid fraction after open   ≥ 35%          ≥ 40%           100%
  Collar loss in dip-out      ≤ 3 nm         ≤ 3 nm          —
  Edge protection             guard ring or ≥ 5 dummy rows
```

The middle support is the hardest to design. It must be thin to minimize capacitance loss and hole-etch difficulty, thick enough to clamp the pillars and to survive the dip-out, and placed so that the spans are balanced (Chapter 10).

---

## Summary and Key Takeaways

1. **Thickness loss is small; lateral loss matters.** About 1.75 nm per face, but openings widen by 3.5 nm and collars may lose more.

2. **Damaged nitride etches faster.** Plasma-damaged column walls and hole-etch-damaged collars loosen the clamp.

3. **Ligament peaks reach about six times the film stress.** At +250 MPa, about 1.5 GPa, leaving a safety factor that defects consume.

4. **Support stress is carried in-plane.** Pillars cannot resist it in bending; it is transferred to the periphery at the array edge.

5. **The array edge is the weak point.** A 400 nm undercut ledge must be supported by dummy pillars or stopped by a guard ring.

---

## Study Questions

1. Extend the reference dip-out to 150 s. Compute the new support thickness, opening CD growth, and the narrowest ligament.

2. If the collar nitride etches at 3 nm/min for its first 2 nm and 1 nm/min after, what collar recess results from a 105 s dip? Is the pillar still clamped?

3. Estimate the local peak stress in the top support for 56 nm openings, using the net-section approach.

4. Explain why a compressive top support causes the array edge to curl downward after the dip-out. Which direction of curl is more dangerous to the dummy pillars?

5. Calculate the undercut into a periphery lower oxide of undoped PE-TEOS instead of BPSG. How many dummy rows would be needed to support it?

---

**Next Chapter:** [Chapter 12: Residual Oxide, Incomplete Dip-Out & Bottom-Stop Breakthrough](./12-residual-oxide-bottom-stop.md)

---

**Chapter 11 Development Status:** Complete  
**Version:** 1.0
