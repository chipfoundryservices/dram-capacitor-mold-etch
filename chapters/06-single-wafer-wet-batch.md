# Chapter 6: Single-Wafer Wet Processors & Batch Benches

## Overview

The dip-out is called a dip because it began as one: a cassette of wafers lowered into a tank of HF. Modern DRAM fabs run most mold dip-outs in single-wafer spin processors, with the HF, rinse, solvent displacement, and drying performed in one chamber without the wafer ever leaving the liquid until the final dry. Batch benches remain in use where cost per wafer dominates and the forest is strong enough. This chapter describes both, with attention to the features that matter for a pillar forest: keeping the wafer wet between steps, controlling temperature and concentration, delivering fresh acid uniformly, and rinsing without damage.

**Learning Objectives:**
- Describe a single-wafer dip-out sequence and explain why every transition is wet-to-wet
- Estimate the diffusion boundary layer on a spinning wafer and its effect on uniformity
- Set dispense flow from the HF consumption of the array
- Compare single-wafer and batch processing for leaning, uniformity, and cost
- Design the rinse to remove HF from the gaps before solvent displacement

---

## 6.1 The Single-Wafer Spin Processor

### 6.1.1 Architecture

```
Single-wafer wet chamber (schematic):
                 dispense arm(s): HF, DIW, IPA, N₂
                        │
         ┌──────────────▼──────────────┐
         │  ═══════ wafer ═══════      │  ← spin chuck (pins or Bernoulli)
         │          │ spindle          │     50–2000 rpm
         │   ╲______│______╱           │  ← multi-level cups: separate
         │    cup 1 (acid) / cup 2      │     drains for HF, DIW, IPA
         │    (rinse) / cup 3 (solvent) │
         └─────────────────────────────┘
          back-side rinse nozzle; exhaust; N₂ blanket
```

A platform carries 8–16 such chambers around a central robot, with front-end load ports. Each chamber has separate drains for acid, rinse, and solvent so that reclaimable chemicals are not mixed.

### 6.1.2 The Reference Sequence

```
Step         Fluid              Flow (L/min)  Speed (rpm)  Time (s)
──────────────────────────────────────────────────────────────────────
Pre-wet      DIW                1.5           300          8
HF dip       5 wt% HF, 25 °C    1.5           300          105
Rinse 1      DIW (overlap)      2.0           500          15
Rinse 2      DIW                2.0           800          30
IPA          IPA, 25–50 °C      0.8           300          30
Dry          N₂ + IPA vapor     —             300 → 1500   20
──────────────────────────────────────────────────────────────────────
Process time                                               ≈ 210 s
Chamber time with load/unload                              ≈ 270 s
```

### 6.1.3 Wet-to-Wet Transitions

At no point between the pre-wet and the final dry may the wafer surface be uncovered. Each new fluid is started before the previous one stops, so that the film on the wafer is displaced rather than broken. A gap of even 0.3 s between HF and rinse lets the film thin at the edge, where centrifugal flow and evaporation are strongest, and dries the outer forest under a mixture of HF and water. The result is an edge ring of leaning pillars. Overlap times of 0.5–1.5 s are typical.

---

## 6.2 Flow, Boundary Layer, and Uniformity

### 6.2.1 The Rotating-Disk Boundary Layer

On a spinning wafer under a continuous jet, the liquid film flows outward and the diffusion boundary layer above the surface has a thickness nearly independent of radius:

```
δ_D ≈ 1.61 · (D/ν)^(1/3) · (ν/ω)^(1/2)

D = 1.5 × 10⁻⁹ m²/s, ν = 1.0 × 10⁻⁶ m²/s, ω = 300 rpm = 31.4 rad/s
(D/ν)^(1/3) = 0.114;   (ν/ω)^(1/2) = 178 µm
δ_D ≈ 1.61 × 0.114 × 178 µm ≈ 33 µm
```

The ideal rotating disk gives uniform mass transfer across the wafer. Real wafers depart from it near the dispense point (impingement), at the edge (film breakup and acceleration), and where the jet scans.

### 6.2.2 Does Mass Transfer Matter?

Chapter 4 showed that the gaps themselves are reaction-limited. The question here is whether the boundary layer above the wafer supplies HF fast enough:

```
HF demand at peak (BPSG etching across the array):
  oxide removal ≈ 0.91 µm³/µm² over ≈ 66 s
  ≈ 0.91 × 10⁻⁶ m × 3.7 × 10⁴ mol/m³ × 6 / 66 s
  ≈ 3.1 × 10⁻³ mol/(m²·s) (array area)

Supply through the boundary layer:
  D·c₀/δ = 1.5 × 10⁻⁹ × 2600 / 33 × 10⁻⁶ ≈ 0.12 mol/(m²·s)

Ratio supply/demand ≈ 40
```

The boundary layer is not limiting at 300 rpm. At 50 rpm it thickens to about 80 µm and the margin falls to about 16. In a puddle (no flow), the film becomes depleted within the dip (Chapter 4), so puddle processes are not used for the dip-out.

### 6.2.3 Dispense Flow

The dispense must also replace the acid fast enough to keep its concentration constant. At 1.5 L/min and a film about 50 µm thick on a 707 cm² wafer (3.5 mL), the film is replaced every 0.14 s. Concentration in the film stays within 0.1% of the supply. The dispense flow is set by film continuity at the edge, not by chemistry: below about 0.8 L/min at 300 rpm, the film thins at the edge and risks breaking.

### 6.2.4 Temperature in the Film

The acid leaves the point-of-use heat exchanger at 25.0 ± 0.2 °C but cools by evaporation and gains heat from the chuck and chamber as it flows outward. A radial temperature drop of 0.5 K from centre to edge gives a 2.3% radial rate difference (Chapter 4). Chamber humidity, exhaust flow, and chuck temperature are therefore controlled, and some processors dispense through a scanning arm to even out the residence time.

---

## 6.3 Batch Immersion

### 6.3.1 The Batch Bench

```
Batch dip-out (schematic):
  HF tank (recirculated, filtered, 25 °C) → overflow DIW rinse
  → quick-dump rinse → IPA-vapor (Marangoni) dryer
  50 wafers per lot, 2 lots in process
```

### 6.3.2 Advantages

- Lowest chemical use per wafer (the HF bath is shared and recirculated for hours)
- High throughput per footprint: 200–400 wafers/h per bench
- Long, uniform immersion with excellent temperature control in a large tank

### 6.3.3 Risks for a Pillar Forest

1. **Transfers through the liquid surface.** Moving a lot from the HF tank to the rinse tank lifts every wafer through an air–liquid interface. The film drains for 2–5 s in air. Small regions can dry under a mixture of HF and water before re-immersion.
2. **Wafer-to-wafer flow.** Flow between closely spaced wafers is lower near the cassette supports, giving local rate differences.
3. **Particles and bath age.** A shared bath accumulates silicate, boron, and phosphorus from every lot, and particles from every wafer.
4. **Final drying.** A batch Marangoni dryer is gentle, but the drying front on a vertically withdrawn wafer moves slowly across a large area, and any disturbance (vibration, IPA vapor fluctuation) leaves a line of leaning pillars.

```
Leaning density, illustrative comparison (same structure):
  Single-wafer, IPA dry       0.4 per 10⁹ pillars
  Batch, Marangoni dry        1.5 per 10⁹ pillars, with transfer lines
```

Batch processing is still used for earlier, sturdier generations, or with a final single-wafer IPA or supercritical dry after a batch HF and rinse that never lets the wafers emerge.

---

## 6.4 Rinsing the Forest

### 6.4.1 Removing HF from the Gaps

At the end of the HF step, every gap between pillars is full of 5% HF. The rinse must replace it with water before the solvent step. Diffusion out of a 1.6 µm deep gap takes milliseconds (Chapter 4), so the gaps follow the film above them. The rinse time is set by how fast the film above the wafer reaches low HF concentration:

```
Dilution of the film by continuous flow (well-mixed film approximation):
  film volume ≈ 3.5 mL; flow 2.0 L/min = 33 mL/s → exchange time ≈ 0.1 s
  to reduce 5% HF to 1 ppm (≈ 5 × 10⁴ dilution) ≈ 11 exchange times ≈ 1.2 s

Real rinses take 30–45 s because of:
  - recirculating eddies near the dispense point and edge
  - HF adsorbed on the chamber walls, cup, and chuck
  - the back-side and bevel
```

Residual HF in the IPA step etches oxide very slowly but, more importantly, fluorinates the TiN surface and forms fluoride residues when the solvent dries. Chapter 13 relates fluorine on the TiN to dielectric leakage.

### 6.4.2 Rinse Water

```
Rinse DIW (reference):
  Resistivity       ≥ 18 MΩ·cm
  Dissolved O₂      ≤ 5 ppb (degassed)
  Temperature       23–25 °C
  Optional          CO₂-doped (0.1–1 µS/cm) to prevent charging
```

Degassed water matters for the TiN. Dissolved oxygen in water oxidizes TiN at the surface; 8 ppm O₂ (air-saturated) grows several ångströms of TiOₓ during a 45 s rinse, while degassed water grows much less. CO₂ doping lowers the resistivity of the water so that it does not build up static charge as it flows over the insulating supports, which can attract particles and, in extreme cases, discharge through pillars.

---

## 6.5 Materials and Safety

Every wetted part is fluoropolymer (PFA, PTFE, PVDF) or sapphire. HF at 5% is acutely toxic by skin absorption, and the platform has leak detection in every cup and drain, interlocks on the dispense valves, and separate exhaust for acid. The IPA step adds flammability: chambers with IPA have explosion-proof electrical design, inert purge, and IPA vapor monitoring. Combining acid and solvent in one chamber is routine but requires drain segregation and checks that no HF reaches the IPA reclaim.

---

## 6.6 Throughput and Fleet

```
Single-wafer platform (reference):
  12 chambers, chamber time ≈ 270 s
  Raw throughput 12 × 3600/270 = 160 wafers/h
  With robot and availability limits ≈ 120 wafers/h
For 100,000 wafer starts per month:
  100,000 / (720 h × 120 × 0.9) ≈ 1.3 → 2 platforms (with redundancy)
```

Chamber-to-chamber matching for the dip-out is judged by residual-oxide inspection, support loss (±0.3 nm), and leaning density. A chamber whose leaning density drifts upward is usually a drying problem (Chapter 8) rather than an HF problem.

---

## Summary and Key Takeaways

1. **Never let the wafer dry between steps.** Overlap every transition by about one second.

2. **Spin boundary layers are not limiting.** About 33 µm at 300 rpm, with 40× margin over the peak HF demand.

3. **Flow is set by film continuity, not chemistry.** The film must not break at the edge.

4. **Batch is cheaper but riskier.** Transfers through the liquid surface and slow drying fronts raise leaning.

5. **Rinse with degassed water.** Oxygen in the rinse oxidizes the TiN; residual HF fluorinates it.

---

## Study Questions

1. Compute δ_D at 100 rpm and at 1000 rpm. At which speed does the supply/demand ratio fall below 20?

2. A chamber shows a 0.8 K centre-to-edge temperature drop in the HF film. What radial difference in BPSG removal time results? Does the 60% overetch cover it?

3. Estimate the HF consumption per wafer for single-pass dispense at 1.5 L/min for 105 s. If the acid costs $3 per litre at 5%, what is the HF cost per wafer?

4. Why is a puddle HF process, attractive for chemical savings, unsuitable for the dip-out? Use the depletion estimate from Chapter 4.

5. List three failure mechanisms that could produce an edge ring of leaning pillars in a single-wafer processor, and the test that would distinguish them.

---

**Next Chapter:** [Chapter 7: Vapor-HF Mold Removal Reactors](./07-vapor-hf-reactors.md)

---

**Chapter 6 Development Status:** Complete  
**Version:** 1.0
