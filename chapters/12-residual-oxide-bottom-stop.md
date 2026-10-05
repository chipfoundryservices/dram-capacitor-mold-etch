# Chapter 12: Residual Oxide, Incomplete Dip-Out & Bottom-Stop Breakthrough

## Overview

The dip-out has two failure modes that pull in opposite directions. Too little removal leaves oxide on the pillars, which costs capacitance (Chapter 1) and, where the oxide forms a bridge, holds pillars together or apart in ways the dielectric cannot repair. Too much exposure, or a weak bottom stop, lets HF reach the oxide beneath the bottom stop and undercut the landing pads. Between them lies the overetch budget. This chapter locates the last oxide, explains why some of it resists removal, treats the bottom stop as a barrier, and sets the overetch.

**Learning Objectives:**
- Identify where residual oxide forms and rank the causes
- Explain the effect of dopant segregation, densification, and interfacial layers on removal
- Compute the capacitance loss from residual oxide of a given distribution
- Describe bottom-stop breakthrough mechanisms and their consequences
- Set the overetch from the distribution of path times and the bottom-stop margin

---

## 12.1 Where the Last Oxide Hides

### 12.1.1 Geometric Hiding Places

The path analysis of Chapter 4 identified the farthest oxide: the bottom corners of the lower oxide, about 660 nm below the support-open column bottom and 27–47 nm laterally away. Those corners are removed last in a uniform etch. Real dip-outs have other late regions:

```
Late-removal regions (ranked by observed frequency, illustrative):
  1. Cells under a blocked column (particle, polymer, trapped gas)
  2. Gap bottoms at the bottom stop, especially in the bottom 20–50 nm
  3. The underside of the middle support (oxide shadowed by the support)
  4. Interfaces: PE-TEOS on middle SiN; BPSG on bottom stop
  5. Bow regions where pillars nearly touch (gap < 10 nm)
```

### 12.1.2 Blocked Columns

A column that does not fill with liquid (Chapter 4), or that is plugged by a particle, leaves the oxide in its opening-cell to be removed laterally from the neighbouring columns. The upper oxide is reachable from neighbours at 90 nm pitch: the extra distance is about 45 nm, which adds about 40 s at 70 nm/min. The lower oxide is reachable laterally through the gaps under the middle support. The extra path is short compared with the vertical path, so in a well-wetted dip a single blocked column costs little.

The dangerous case is a cluster: several adjacent columns blocked by a large particle, a patch of polymer, or a pocket of trapped gas that spans them. The lateral distance from the nearest working column then reaches hundreds of nanometres and the oxide survives the dip.

```
Residual-oxide cluster from n blocked adjacent columns (upper oxide):
  Extra lateral distance ≈ (√n / 2) × 90 nm
  n = 1  → 45 nm  → +40 s   (covered by overetch)
  n = 7  → 120 nm → +100 s  (exceeds overetch: oxide remains)
```

### 12.1.3 Gap Bottoms

At the bottom of the lower oxide, the last oxide sits in the corners between the pillar foot, the bottom stop, and the neighbouring pillar. The BPSG in contact with the bottom stop may be different from bulk BPSG: dopant can segregate to or away from the interface, and the first nanometres of BPSG deposited on nitride may be denser. A thin layer of slow oxide at the interface survives the bulk removal.

---

## 12.2 Slow Oxide

### 12.2.1 Densification and Dopant Loss

BPSG near any free surface during high-temperature steps loses boron and phosphorus by outdiffusion. The TiN fill at 550–600 °C occurs with the BPSG enclosed by the bottom stop and the middle support, but the hole walls were open during the fill. A skin of dopant-depleted BPSG a few nanometres thick may form at the hole wall, adjacent to the pillar. That skin etches several times slower than the bulk:

```
Illustrative depleted skin:
  thickness 2 nm, rate 80 nm/min (instead of 600)
  time to remove: 2 / 80 × 60 = 1.5 s  (negligible)
```

The skin itself is not a problem, because it is thin. But it is in contact with the pillar, so if a dip is cut short at exactly the point the bulk clears, the skin is what remains on the TiN.

### 12.2.2 Interfacial Layers on the Pillar

The TiN was deposited on the oxide hole wall. The first TiN layer forms a Ti–O–Si interface with the oxide, and a thin mixed layer of TiOₓ and SiOₓ can form. HF removes SiO₂ readily but TiO₂ only very slowly. The interface after the dip-out is therefore a TiN surface with a thin Ti-rich oxide, plus possibly a fraction of a monolayer of silicate. This is not "residual oxide" in the defect sense, but it is part of the dielectric stack.

### 12.2.3 Fluorocarbon Residue

Fluorocarbon polymer from the support-open etch, left on the column walls, protects the oxide beneath it from HF. The oxide is undercut laterally from the sides, and the polymer film collapses into the gaps as a flake. Flakes of polymer with oxide attached are a known source of residual-oxide defects and of bridges between pillars.

---

## 12.3 What Residual Oxide Costs

### 12.3.1 Capacitance

From Chapter 1, residual oxide of thickness t_ox on a fraction f of the pillar area reduces C_s by a fraction f × t_ox/(EOT + t_ox):

```
Residual oxide signatures and capacitance loss (EOT = 0.50 nm):
  Signature                                   f        t_ox    ΔC/C
  ────────────────────────────────────────────────────────────────────
  Bottom 30 nm of every pillar (gap bottoms)  0.021    3 nm    −1.8%
  Uniform 0.3 nm skin on all pillars          1.0      0.3 nm  −37%(*)
  Cluster of 7 blocked columns (28 cells)     1.0      thick   those cells
                                                               ≈ −60–90%
  (*) An oxide skin on every pillar acts as an added dielectric layer;
      0.3 nm of SiO₂ adds 0.3 nm to EOT. This is why "no detectable
      residual oxide" is the specification.
```

The uniform skin case shows why residual oxide is measured in fractions of a nanometre. A uniform 0.3 nm skin is not a localized defect at all; it is a shift in the whole capacitor dielectric. It comes from the interfacial chemistry of Section 12.2.2 and is controlled by the TiN surface preparation rather than by the dip time.

### 12.3.2 Bridges

Residual oxide between two pillars that holds them at a fixed gap is benign if the gap is larger than twice the dielectric and plate thickness. If the oxide bridge holds two pillars at a gap of 5–8 nm, the dielectric (about 5 nm on each pillar) fills the gap and the plate cannot enter; the cells survive but with lower capacitance and higher leakage at that point. If the bridge pulls the pillars into contact as it dries, the result is a short.

---

## 12.4 The Bottom Stop

### 12.4.1 Role

The bottom stop separates the mold from the landing-pad level. Beneath it is oxide between the landing pads, and beneath that the bit lines and storage-node contacts. If HF penetrates the bottom stop, it etches that oxide:

```
Consequences of bottom-stop breakthrough:
  HF reaches inter-pad oxide → undercuts the pads; pads can lift or tilt
  HF reaches the bit-line spacer oxide → bit-line to storage-node shorts
  Later depositions fill the cavity → voids, leakage paths
```

### 12.4.2 Uniform Loss

Chapter 4 estimated uniform bottom-stop loss as 0.45 nm average, 0.8 nm at the first-exposed sites. On a 20 nm film this is harmless.

### 12.4.3 Local Weak Points

The bottom stop does not fail uniformly; it fails where it was already damaged:

```
Bottom-stop weak points (ranked, illustrative):
  1. The collar around each pillar foot: the capacitor hole etch
     punched through the stop and the TiN was deposited against its
     cut edge. The interface is a vertical seam through the barrier.
  2. Side punch from the hole etch: holes that landed off-pad
     punched the stop beside the pad (Book #29). The TiN filled the
     punch; the stop around it is thinned.
  3. Thin spots from incoming deposition variation (≥ 3σ low).
  4. Pinholes from particles during the stop deposition.
```

The collar seam is the main risk. If the TiN–SiN interface at the foot of the pillar is not tight, HF can penetrate along it into the oxide below. The penetration rate along a nanometre seam is diffusion- and wetting-controlled, and the oxide it reaches is etched laterally from a point source.

```
Penetration through a leaky collar (illustrative):
  Time the bottom of the gap is exposed: ≈ 40 s (overetch)
  Etch of inter-pad oxide (undoped HDP or ALD oxide, ≈ 40 nm/min)
    from a point source → cavity radius ≈ 40 × 40/60 ≈ 27 nm
  A 27 nm cavity under a 26 nm pad undercuts most of it.
```

### 12.4.4 Defences

1. **Bottom-stop material.** LPCVD-class nitride with low HF rate; or a bilayer (SiN on a thin SiCN or AlOₓ) that is nearly inert in HF.
2. **Collar sealing.** A short nitride liner or a TiN deposition condition that densifies the TiN–SiN interface at the foot.
3. **Limit the overetch.** Every second after the gap bottoms clear is exposure of the collar.
4. **Inter-pad oxide.** A slower inter-pad dielectric (e.g., SiN or SiCN instead of oxide) limits any cavity.

---

## 12.5 Setting the Overetch

### 12.5.1 The Distribution of Path Times

The overetch must cover the slowest normal path, not the defect paths (blocked clusters), which cannot be fixed by time without unacceptable support and stop loss:

```
Path-time contributors (3σ, illustrative):
  BPSG rate variation (dopant, thermal history)   ± 12%
  Bath temperature (± 0.5 K)                       ± 2.3%
  Column landing depth (60–130 nm)                 ± 35 nm of path ≈ ± 5%
  Wetting delay (pre-wet to full contact)           0–8 s
  Lower-oxide thickness (± 3%)                      ± 3%
  Combined (RSS of rate terms) ≈ ± 14% + 8 s

Required time = 66 s × 1.14 + 8 s ≈ 83 s for the 3σ-slowest site
```

### 12.5.2 The Reference Choice

```
Reference HF time: 105 s
  Margin over 3σ-slowest site: 22 s (≈ 27%)
  Bottom stop exposure at the earliest site: ≈ 105 − 58 = 47 s
  Bottom stop loss at that site: 0.7 × 47/60 ≈ 0.55 nm (uniform)
  Collar exposure: ≈ 47 s
```

The overetch is set long enough to remove all normal oxide with margin, and short enough to limit collar exposure. Residual-oxide defects that remain at 105 s are defect-driven (blocked columns, polymer flakes) and are attacked at their source.

---

## Summary and Key Takeaways

1. **The last oxide is at gap bottoms and under blocked columns.** Single blocked columns are covered; clusters are not.

2. **Slow oxide is thin.** Depleted skins and interfacial layers matter only because they sit on the pillar.

3. **Residual oxide is a dielectric.** A uniform 0.3 nm skin is a 37% capacitance hit; "none detectable" is the right specification.

4. **The bottom stop fails at the pillar collar.** The TiN–SiN seam at the foot is a path through the barrier.

5. **Overetch covers normal variation, not defects.** About 105 s for a 3σ path time of about 83 s.

---

## Study Questions

1. Compute the capacitance loss for residual oxide 2 nm thick in the bottom 50 nm of 10% of the pillars, averaged over the array.

2. A particle 300 nm in diameter blocks the columns beneath it. How many columns and cells does it affect, and is the oxide removed within the reference overetch?

3. If the inter-pad oxide etches at 300 nm/min (doped) instead of 40 nm/min, what cavity forms through a leaky collar in 47 s?

4. Re-derive the overetch for a BPSG with ± 20% (3σ) rate variation. What bottom-stop exposure results?

5. Explain why extending the dip time is the wrong response to clustered residual-oxide defects.

---

**Next Chapter:** [Chapter 13: Electrode Integrity — TiN Oxidation, Fluorine Uptake, Top Recess & Seams](./13-electrode-integrity.md)

---

**Chapter 12 Development Status:** Complete  
**Version:** 1.0
