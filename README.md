# Book #30: DRAM Capacitor Mold Etch — Support-Lattice Open and Mold-Oxide Removal Around Free-Standing Storage-Node Pillars

## Overview

**Book #30** is a technical reference on **DRAM capacitor mold etch**: the sequence of plasma and wet (or vapor) etches that removes the oxide mold from around the storage-node electrodes after they have been formed, while leaving a thin silicon nitride lattice to hold them upright. Book #29 described how the capacitor holes are cut into the mold. This book picks up the wafer after the holes have been filled with titanium nitride and the tops have been isolated. At that point there are about seventeen billion TiN pillars on a 16 Gb die, each 1.6 µm tall and 28 nm wide on average, standing 17 nm apart on a 45 nm hexagonal lattice, buried in oxide. The oxide must now go. The outer surface of each pillar is the capacitor; while it is buried in oxide it stores nothing.

The module has two halves. First, a **support-open etch** cuts a pattern of openings through the top silicon nitride support, the upper oxide, and the middle silicon nitride support. The openings are about 50 nm wide, placed between pillars so that each one exposes oxide next to four cells. Second, a **mold dip-out** in hydrofluoric acid enters through those openings and dissolves every remaining nanometre of oxide, about 0.9 µm³ of it per square micrometre of array, down to the bottom nitride etch stop. What is left is a forest of free-standing pillars tied together at two heights by a perforated nitride lattice. The wafer must then be rinsed and dried without letting surface tension pull neighbouring pillars together.

Each half is demanding in its own way. The support-open etch is a nitride and oxide etch that must not erode the TiN pillar tops it exposes, must not leave a nitride sliver in any opening, and must land in the lower oxide without reaching the bottom stop. The dip-out must remove oxide from gaps 17 nm wide and 1.6 µm deep, completely, in a few minutes, while the supports and the bottom stop lose no more than a few nanometres. The drying step must hold capillary forces below the point at which a 28 nm pillar bends 17 nm. A single leaning pair is two dead cells; a residual film of 2 nm of oxide on a pillar cuts its capacitance there by four-fifths; a broken support releases hundreds of pillars at once.

**One mold, seventeen billion pillars: remove all of the oxide, none of the nitride, none of the TiN, and let nothing fall over.** This book covers the mechanics, chemistry, equipment, and production engineering that make that possible.

---

## Intended Audience

This book is written for **semiconductor industry professionals** with working knowledge of plasma and wet processing:

- **Process Engineers**: developing support-open plasma recipes and HF dip-out recipes; controlling TiN top loss, nitride loss, residual oxide, pillar leaning, and support integrity
- **Equipment Engineers**: specifying dielectric etch chambers for the support open, single-wafer wet processors, vapor-HF reactors, and low-surface-tension and supercritical drying systems; managing chemical concentration, temperature, filtration, and particles
- **Integration Engineers**: choosing support layer positions and thicknesses, the support-open pattern, the mold doping profile, and the electrode thickness against capacitance, leaning, and cost
- **Device Engineers**: understanding how leaning, residual oxide, electrode damage, and support damage become capacitance loss, shorts, leakage, and retention tails
- **Researchers**: studying elastocapillary collapse of nanopillars, HF transport in nanometre gaps, vapor-phase oxide removal, and mold removal for 4F² and 3D DRAM capacitors

The material assumes Books #1–5 (plasma fundamentals), Books #6–10 (dielectric etch), and Books #11–15 (advanced plasma engineering). Book #29 (*DRAM Capacitor Hole Etch*) is the direct predecessor: it defines the hole, the mold, and the reference process this book inherits. The companion volumes *Silicon Nitride Etch* and *Thermal Oxide Etch* cover the film chemistries in more general settings.

---

## Technical Scope

### Core Concepts Covered

**Architecture & Geometry:**
- Why the pillar capacitor needs its mold removed; capacitance from the outer surface
- The pillar forest: height, diameter, gap, and slenderness
- The support lattice: top, middle, and bottom nitride; open-area fraction; the support-open pattern
- Mechanical stability of supported and unsupported pillars

**Support-Open Etch:**
- Patterning the support-open mask over a planarized pillar array
- Nitride etch selective to TiN and to oxide; oxide etch selective to TiN
- The opening as a 16:1 slot between pillars; landing in the lower oxide
- TiN top loss, pillar-top rounding, and nitride slivers

**Mold Removal Chemistry:**
- HF etching of undoped and doped oxide; etch rates and activation energies
- Selectivity to support nitride, the bottom stop, and TiN
- Transport of HF and reaction products in 17 nm gaps
- Vapor-phase HF, catalysts, and residues

**Equipment Design:**
- Dielectric etch chambers for the support open
- Single-wafer spin processors and batch benches for the dip-out
- Vapor-HF reactors
- Rinse and drying: IPA displacement, surface modification, supercritical CO₂
- Chemical delivery, concentration control, filtration, and defects

**Process Phenomena:**
- Pillar leaning, bending, and collapse; elastocapillary instability
- Support lattice integrity: thinning, cracking, sag, and peeling
- Residual oxide, incomplete dip-out, and bottom-stop breakthrough
- Electrode damage: TiN oxidation, fluorine uptake, top recess, and seams
- Advanced schemes: taller molds, multi-tier molds, silicon molds removed dry, and 4F² and 3D DRAM capacitors

**Production Integration:**
- Metrology for leaning, residual oxide, support thickness, and TiN condition
- Electrical monitors: capacitance, pillar-to-pillar shorts, leakage
- Dielectric and plate deposition as customers of the dip-out
- Yield signatures, throughput, and cost of ownership

### Technology Context

- **Device architectures:** 6F² buried-channel DRAM from the 1x to the 1c generation (DDR5, LPDDR5X, HBM core dies); 4F² vertical-channel and 3D DRAM as emerging forms
- **Capacitor structures:** single-sided solid TiN pillar capacitors with a top and middle nitride support (primary focus); double-sided cylinders; three-support and multi-tier molds
- **Process sequence:** The mold etch follows capacitor hole etch, strip and clean, TiN bottom-electrode deposition, and top isolation by CMP or etch-back. It comes before the high-k dielectric ALD, the TiN top electrode, and the plate fill
- **Manufacturing scale:** 300 mm wafers; one support-open plasma etch (about 3 min) and one dip-out-and-dry (about 5 min per wafer in a single-wafer chamber) per wafer

---

## Book Organization

### Part I: Fundamentals (4 Chapters)

**Chapter 1: The Pillar Capacitor & Why the Mold Must Go**
- The 1T1C cell, the sense signal, and the capacitance target
- From hole to pillar: the outer surface as the capacitor
- The pillar forest and its geometry
- Where the mold etch sits in the flow, and its specification sheet

**Chapter 2: The Post-Electrode Structure, Support Lattice & Support-Open Pattern**
- The TiN pillar: deposition, seam, and top isolation
- The mold layers as the dip-out sees them; doped and undoped oxide
- The support lattice: thickness, stress, and open-area fraction
- The support-open mask and its placement against the pillars

**Chapter 3: Support-Open Etch Physics**
- Nitride and oxide etch in a 50 nm opening between metal pillars
- Ion-driven TiN loss and the pillar top
- ARDE in the opening and landing in the lower oxide
- Charging and the conducting pillars

**Chapter 4: HF Chemistry of Mold Removal**
- HF, HF₂⁻, and the dissolution of SiO₂
- Etch rates of the mold oxides, the supports, the stop, and TiN
- Diffusion and depletion in 17 nm gaps
- Vapor-phase HF and its residues

### Part II: Hardware Design (5 Chapters)

**Chapter 5: Plasma Chambers for the Support Open**
- Why a medium-power CCP dielectric chamber
- Frequencies, bias, and ion energy at the pillar top
- Gas delivery and the three-step recipe
- Throughput and chamber matching

**Chapter 6: Single-Wafer Wet Processors & Batch Benches**
- Spin processors: dispense, flow, and boundary layers
- Batch immersion and its withdrawal risk
- Temperature and concentration control
- Rinse design and cross-contamination

**Chapter 7: Vapor-HF Mold Removal Reactors**
- Anhydrous HF with alcohol or water catalysts
- Pressure, temperature, and condensation control
- Byproduct sublimation and residue
- Throughput and integration with drying

**Chapter 8: Rinse & Drying Systems**
- Capillary force and the choice of fluid
- IPA displacement, heated IPA, and Marangoni drying
- Surface modification and contact-angle control
- Supercritical CO₂ drying

**Chapter 9: Chemical Delivery, Filtration, Particles & Defects**
- Blending, titration, and HF concentration control
- Bath and recirculation life
- Filtration, particles, and watermarks
- Preventive maintenance and fleet matching

### Part III: Process Phenomena (5 Chapters)

**Chapter 10: Pillar Leaning, Bending & Collapse**
- Beam mechanics of a supported TiN pillar
- Capillary loading during drying and the collapse threshold
- Stress-driven leaning and support sag
- Leaning maps, pair statistics, and control

**Chapter 11: Support Lattice Integrity**
- Nitride thinning in HF
- Cracking, bridge failure, and lattice release
- Stress, bow, and support peeling at the array edge
- Support design rules

**Chapter 12: Residual Oxide, Incomplete Dip-Out & Bottom-Stop Breakthrough**
- Where the last oxide hides
- Dopant, density, and seam effects on removal
- Bottom-stop loss and attack beneath it
- Overetch budget and its limits

**Chapter 13: Electrode Integrity — TiN Oxidation, Fluorine Uptake, Top Recess & Seams**
- TiN surface chemistry in HF and water
- Fluorine and oxygen in the electrode and their effect on the dielectric
- Pillar-top loss in the support open
- Seams, voids, and hollow pillars

**Chapter 14: Advanced Schemes — Taller Molds, Three Supports, Silicon Molds, 4F² & 3D DRAM**
- Molds beyond 2 µm and three-support lattices
- Sequential (two-dip) mold removal
- Silicon and carbon molds removed by dry etch
- Capacitor mold removal for 4F² and 3D DRAM

### Part IV: Production Scale (2 Chapters)

**Chapter 15: Metrology, Inspection & Advanced Process Control**
- Endpoint for the support open
- Leaning inspection, residual-oxide detection, and support metrology
- Electrical monitors of capacitance, shorts, and leakage
- Feed-forward and feedback APC

**Chapter 16: Post-Dip-Out Integration, Yield & Cost of Ownership**
- Queue time, TiN surface, and the dielectric ALD
- Plate fill and the supported forest under stress
- Defect modes and yield signatures
- Throughput, chemical consumption, and cost-of-ownership modeling

---

## Key Technical Themes

1. **The outside of the pillar is the capacitor.** About 8.6 fF comes from the outer surface of a 28 nm × 1.6 µm pillar. Every square nanometre still covered by oxide or nitride after the dip-out is lost.
2. **Slender metal, strong liquids.** A pillar with a free span of 760 nm deflects 17 nm under a water meniscus pulling on one side along its whole span. It survives only because the supports cut its span and the drying fluid has low surface tension.
3. **Collapse is an instability.** Capillary force grows as the gap closes. If the linear deflection of two neighbours pulled toward each other exceeds an eighth of the gap, they do not stop; they touch.
4. **The lattice is the skeleton.** About 28% of each support is open. The rest must survive several minutes of HF and hold up to a hundred pillars per micrometre of span.
5. **HF must find every corner.** The farthest oxide is only 27 nm from an opening, but it sits in a gap 17 nm wide and up to 760 nm below the middle support. Removal is fast; proof of complete removal is hard.
6. **Selectivity is measured in nanometres.** At oxide:nitride selectivity near 100:1 for the doped lower mold, the supports still lose 2–4 nm each side; the bottom stop is only 20 nm.

---

## Cross-References to Prior Books

**Related Books in the Series:**

- **Books #1–5** (Plasma Physics & Chemistry Fundamentals): sheaths, ion energy, radical generation
- **Books #6–10** (Dielectric Etch & Fluorocarbon Chemistry): oxide/nitride selectivity, CCP dielectric etch
- **Books #11–15** (Advanced Plasma Engineering): RF delivery, gas delivery, temperature control, endpoint detection
- **Book #26** (DRAM Isolation Trench Etch) and **Book #27** (DRAM Word-Line Conductor Etch): the 6F² array beneath the capacitor
- **Book #29** (DRAM Capacitor Hole Etch): the hole, the mold, the supports, and the reference process inherited here
- **Companion volumes:** *Silicon Nitride Etch*, which covers nitride chemistry and wet nitride behaviour; *Thermal Oxide Etch*, which covers HF oxide etching in general; *Carbon Hard Mask Etch*, which covers the support-open mask open

Book #29 cut seventeen billion holes. This book removes everything between them.

---

## File Organization

```
dram-capacitor-mold-etch/
├── README.md            ← You are here
├── PREFACE.md
├── INDEX.md
├── GLOSSARY.md
│
├── chapters/
│   ├── 01-pillar-capacitor-mold-role.md
│   ├── 02-post-electrode-structure-support-lattice.md
│   ├── 03-support-open-etch-physics.md
│   ├── 04-hf-mold-removal-chemistry.md
│   ├── 05-support-open-plasma-chamber.md
│   ├── 06-single-wafer-wet-batch.md
│   ├── 07-vapor-hf-reactors.md
│   ├── 08-rinse-drying-systems.md
│   ├── 09-chemical-delivery-defects.md
│   ├── 10-pillar-leaning-collapse.md
│   ├── 11-support-lattice-integrity.md
│   ├── 12-residual-oxide-bottom-stop.md
│   ├── 13-electrode-integrity.md
│   ├── 14-advanced-mold-schemes.md
│   ├── 15-metrology-inspection-apc.md
│   └── 16-integration-yield-coo.md
│
└── appendices/
    ├── A-material-properties.md
    ├── B-chemistry-reaction-data.md
    ├── C-standard-procedures.md
    ├── D-process-windows.md
    ├── E-pillar-mechanics-capacitance-calculations.md
    ├── F-metrology-reference.md
    └── G-troubleshooting-guide.md
```

---

## Constraints & Scope

### What This Book Covers
✅ Support-open plasma etch and mold-oxide dip-out for single-sided TiN pillar capacitors in 6F² DRAM (primary focus)  
✅ The pillar, the supports, and the mold as inputs to the module  
✅ Wet, vapor, and sequential removal; low-surface-tension and supercritical drying  
✅ Pillar mechanics, support integrity, and electrode condition  
✅ The dielectric and plate depositions as customers of the dip-out  
✅ Capacitance, shorts, leakage, yield, and cost of ownership  

### What This Book Does NOT Cover
❌ The capacitor hole etch itself (see Book #29)  
❌ TiN, high-k, and plate deposition chemistry in detail  
❌ The amorphous-carbon mask open for the support-open layer in detail (see *Carbon Hard Mask Etch*)  
❌ MEMS release etches, except as comparison  
❌ Vendor-specific recipes or proprietary tool parameters  

### A Note on Numbers
Numbers in this book come from established mechanics, published etch-rate data and literature trends, and representative production practice. Worked examples use **illustrative values** chosen to show the method, and the arithmetic is written out so readers can substitute their own data. A single **reference process** is used across chapters so that examples connect. It inherits Book #29's array: a 1b-class 6F² cell (F = 17 nm, cell area 1734 nm²), storage nodes on a 45 nm hexagonal pitch, and a 1.60 µm mold (120 nm top SiN support, 650 nm undoped PE-TEOS upper oxide, 50 nm middle SiN support, 760 nm BPSG lower oxide, 20 nm bottom SiN stop). The holes are filled with solid CVD TiN pillars: 32 nm at the top, 28 nm average, 24 nm at the bottom, Young's modulus 400 GPa. The support-open pattern places 50 nm openings on a 90 nm hexagonal lattice (one per four cells, 28% open area). The reference dip-out uses 5 wt% HF at 25 °C, with BPSG at 600 nm/min, PE-TEOS at 70 nm/min, and support SiN at 1.0 nm/min, followed by IPA displacement and spin drying. The dielectric is ZrO₂-based with EOT 0.50 nm. The capacitance, deflection, and transport numbers in Chapters 1, 4, 10, and 12 come from closed-form models written out in Appendix E. Treat recipe values as starting points for a design of experiments, never as qualified process conditions.

---

## Development Status

**Book #30 Foundation:** Complete  
**Part I (Chapters 1–4):** Complete  
**Part II (Chapters 5–9):** Complete  
**Part III (Chapters 10–14):** Complete  
**Part IV (Chapters 15–16):** Complete  
**Back Matter (Appendices A–G, Glossary):** Complete  

---

## Next Steps

1. **Read [PREFACE.md](./PREFACE.md)** for the motivation and reading guidance
2. **Read [INDEX.md](./INDEX.md)** for the detailed chapter outline and reading paths by role
3. **Begin [Chapter 1](./chapters/01-pillar-capacitor-mold-role.md)**: The Pillar Capacitor & Why the Mold Must Go

---

**Book #30 Version:** 1.0  
**Last Updated:** 2026-10-05  
**Series:** ChipFoundryServices Technical Series
