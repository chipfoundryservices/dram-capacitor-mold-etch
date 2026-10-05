# Index: Book #30 Navigation Guide

## Quick Navigation

**Total Content:** 16 chapters + 7 appendices + glossary  
**Estimated Read Time:** 20–28 hours for the complete book; 5–9 hours for a focused reading path

| Part | Chapters | Theme |
|------|----------|-------|
| I | 1–4 | Fundamentals: the pillar capacitor, the post-electrode structure and support lattice, support-open etch physics, HF chemistry |
| II | 5–9 | Hardware: support-open plasma chamber, single-wafer and batch wet, vapor HF, rinse and drying, chemical delivery and defects |
| III | 10–14 | Phenomena: leaning and collapse, support integrity, residual oxide and the bottom stop, electrode integrity, advanced schemes |
| IV | 15–16 | Production: metrology, inspection, APC, integration, yield, cost |

---

## Part I: Fundamentals (Chapters 1–4)

### Chapter 1: [The Pillar Capacitor & Why the Mold Must Go](./chapters/01-pillar-capacitor-mold-role.md)
**Estimated Time:** 55 min | **Difficulty:** Foundation | **Reading Level:** All roles  
**Focus:** Why must the mold be removed, and what must the module deliver?

**Key Topics:**
- Sense signal (97 mV) and the 8–10 fF target
- Cylinder versus pillar; the outer surface as the capacitor (8.6 fF)
- The forest: 577 pillars/µm², 17 nm gaps, slenderness 57
- Module flow and the specification sheet (leaning ≤ 1 per 10⁹)

**Critical Equations:** C_s = ε₀·3.9·π·d·H_eff/EOT; ΔC/C = −f·t/(EOT + t)  
**Study Questions:** 6

---

### Chapter 2: [The Post-Electrode Structure, Support Lattice & Support-Open Pattern](./chapters/02-post-electrode-structure-support-lattice.md)
**Estimated Time:** 60 min | **Difficulty:** Intermediate | **Reading Level:** Process/Integration  
**Focus:** What does the mold etch inherit?

**Key Topics:**
- TiN fill, seam, top isolation
- PE-TEOS vs BPSG in HF (70 vs 600 nm/min); thermal history
- Support films; solid fraction 39% / 46% after the open
- Support-open pattern: 50 nm on 90 nm hex, 28% open; overlay and crescents

**Critical Equations:** Open fraction = πr²/((√3/2)b²); r_far = b/√3 − d_SO/2  
**Study Questions:** 6

---

### Chapter 3: [Support-Open Etch Physics](./chapters/03-support-open-etch-physics.md)
**Estimated Time:** 65 min | **Difficulty:** Advanced | **Reading Level:** Process/Equipment  
**Focus:** How do you cut nitride and oxide among metal pillars?

**Key Topics:**
- Column geometry with TiN crescents
- TiF₄ passivation; chemistries and selectivities
- TiN top loss ≈ 5 nm; mask budget ≈ 250 of 300 nm
- Landing 50–150 nm into BPSG; charging on floating pillars

**Critical Equations:** ER = ER₀/(1 + kA); loss = Γ·Y/n  
**Study Questions:** 6

---

### Chapter 4: [HF Chemistry of Mold Removal](./chapters/04-hf-mold-removal-chemistry.md)
**Estimated Time:** 65 min | **Difficulty:** Intermediate | **Reading Level:** Process/Research  
**Focus:** What sets the dip time, and what limits removal?

**Key Topics:**
- HF, HF₂⁻, (HF)₂; rates and activation energies
- Longest path: 66 s; reference 105 s; losses ≈ 1.75 nm/face
- Da ≈ 10⁻⁵: reaction-limited
- Wetting and trapped gas; vapor HF and residues

**Critical Equations:** R = k₁[HF] + k₂[HF₂⁻]; Da = vL/D; d ln R/dT = E_a/kT²  
**Study Questions:** 6

---

## Part II: Hardware Design (Chapters 5–9)

### Chapter 5: [Plasma Chambers for the Support Open](./chapters/05-support-open-plasma-chamber.md)
**Estimated Time:** 50 min | **Difficulty:** Intermediate | **Reading Level:** Equipment/Process  
**Key Topics:** Dual-frequency CCP; ion energy vs TiN; bias pulsing; four-step recipe; drift; throughput  
**Study Questions:** 5

### Chapter 6: [Single-Wafer Wet Processors & Batch Benches](./chapters/06-single-wafer-wet-batch.md)
**Estimated Time:** 50 min | **Difficulty:** Intermediate | **Reading Level:** Equipment/Process  
**Key Topics:** Wet-to-wet sequence; boundary layer (33 µm); flow; batch risks; rinse with degassed DIW  
**Critical Equations:** δ_D = 1.61(D/ν)^(1/3)(ν/ω)^(1/2)  
**Study Questions:** 5

### Chapter 7: [Vapor-HF Mold Removal Reactors](./chapters/07-vapor-hf-reactors.md)
**Estimated Time:** 45 min | **Difficulty:** Advanced | **Reading Level:** Equipment/Research  
**Key Topics:** Adsorbed-layer regime; Kelvin condensation in gaps; reactor design; P and (NH₄)₂SiF₆ residues; hybrids  
**Critical Equations:** ln(p/p_sat) = −γV_m cos θ/(RT·w/2)  
**Study Questions:** 5

### Chapter 8: [Rinse & Drying Systems](./chapters/08-rinse-drying-systems.md)
**Estimated Time:** 55 min | **Difficulty:** Intermediate | **Reading Level:** All process/equipment  
**Key Topics:** Laplace pressure; asymmetry α; IPA displacement; spin and Marangoni drying; surface modification; supercritical CO₂  
**Critical Equations:** ΔP = 2γ cos θ/g; q = α·ΔP·d  
**Study Questions:** 5

### Chapter 9: [Chemical Delivery, Filtration, Particles & Defects](./chapters/09-chemical-delivery-defects.md)
**Estimated Time:** 45 min | **Difficulty:** Intermediate | **Reading Level:** Equipment/Facilities  
**Key Topics:** Blending; reclaim and bath life; filtration; flower defects; watermarks; metals and chloride; matching  
**Study Questions:** 5

---

## Part III: Process Phenomena (Chapters 10–14)

### Chapter 10: [Pillar Leaning, Bending & Collapse](./chapters/10-pillar-leaning-collapse.md)
**Estimated Time:** 75 min | **Difficulty:** Advanced | **Reading Level:** Process/Integration/Research  
**Focus:** Why do pillars fall, and how often?

**Key Topics:**
- EI = 1.21 × 10⁻²⁰ N·m²; 17 nm deflection under water
- Thresholds g/4 (single) and g/8 (pair)
- Lognormal α model: IPA margin 2.76 → 1.2 × 10⁻⁹
- Optimum d = 0.6a; adhesion after contact; stress-driven leaning

**Critical Equations:** δ = qL⁴/384EI; δ₀ ≤ g/8; P = ½erfc(ln M/σ√2); M ∝ Ed³(a−d)²/(γL⁴)  
**Study Questions:** 6

### Chapter 11: [Support Lattice Integrity](./chapters/11-support-lattice-integrity.md)
**Estimated Time:** 50 min | **Difficulty:** Advanced | **Reading Level:** Integration/Process  
**Key Topics:** HF thinning and collar loss; ligament stress ≈ 6σ₀; in-plane stress transfer; array-edge undercut; design rules  
**Study Questions:** 5

### Chapter 12: [Residual Oxide, Incomplete Dip-Out & Bottom-Stop Breakthrough](./chapters/12-residual-oxide-bottom-stop.md)
**Estimated Time:** 50 min | **Difficulty:** Intermediate | **Reading Level:** Process/Device  
**Key Topics:** Late regions; blocked-column clusters; slow oxide; capacitance cost; collar leaks; overetch setting  
**Study Questions:** 5

### Chapter 13: [Electrode Integrity](./chapters/13-electrode-integrity.md)
**Estimated Time:** 45 min | **Difficulty:** Intermediate | **Reading Level:** Device/Process  
**Key Topics:** TiN in HF, water, air; TiOₓ and F; leakage tails; crescent loss and field; seams; pre-ALD treatments  
**Study Questions:** 5

### Chapter 14: [Advanced Schemes](./chapters/14-advanced-mold-schemes.md)
**Estimated Time:** 50 min | **Difficulty:** Advanced | **Reading Level:** Integration/Research  
**Key Topics:** 2.0 µm molds and a third support; sequential removal; Si and C molds; 4F²; 3D DRAM lateral release  
**Study Questions:** 5

---

## Part IV: Production Scale (Chapters 15–16)

### Chapter 15: [Metrology, Inspection & Advanced Process Control](./chapters/15-metrology-inspection-apc.md)
**Estimated Time:** 50 min | **Difficulty:** Intermediate | **Reading Level:** Process/Metrology  
**Key Topics:** SN1 endpoint; HV-SEM; sampled leaning inspection; FTIR/XPS; electrical monitors; APC loops  
**Study Questions:** 5

### Chapter 16: [Post-Dip-Out Integration, Yield & Cost of Ownership](./chapters/16-integration-yield-coo.md)
**Estimated Time:** 50 min | **Difficulty:** Intermediate | **Reading Level:** Integration/Management  
**Key Topics:** Queue time; dielectric and plate; late leaning; repairable vs cluster fails; module cost ≈ $12–16/wafer; value of yield  
**Critical Equations:** Y = exp(−D_c A)  
**Study Questions:** 5

---

## Appendices

- [Appendix A: Material Properties](./appendices/A-material-properties.md)
- [Appendix B: Chemistry & Reaction Data](./appendices/B-chemistry-reaction-data.md)
- [Appendix C: Standard Procedures](./appendices/C-standard-procedures.md)
- [Appendix D: Process Windows](./appendices/D-process-windows.md)
- [Appendix E: Pillar Mechanics & Capacitance Calculations](./appendices/E-pillar-mechanics-capacitance-calculations.md)
- [Appendix F: Metrology Reference](./appendices/F-metrology-reference.md)
- [Appendix G: Troubleshooting Guide](./appendices/G-troubleshooting-guide.md)
- [Glossary](./GLOSSARY.md)

---

## Reading Paths by Role

**Process Engineer (8 h):** Ch. 1 → 3 → 4 → 8 → 10 → 12 → 13 → App. D, G  
**Equipment Engineer (7 h):** Ch. 1 → 5 → 6 → 7 → 8 → 9 → 15  
**Integration Engineer (8 h):** Ch. 1 → 2 → 10 → 11 → 12 → 14 → 16  
**Device Engineer (5 h):** Ch. 1 → 12 → 13 → 16  
**Researcher (8 h):** Ch. 3 → 4 → 7 → 10 → 14 → App. E

---

## Study Questions Overview

**Total Study Questions:** 85 (5–6 per chapter × 16 chapters)  
**Nature:** Mostly calculation-based  
**Topics:** Capacitance and residual films, support-open geometry and overlay, TiN loss and mask budget, HF paths and losses, boundary layers, Kelvin condensation, Laplace pressure, beam deflection, collapse thresholds and statistics, support stress, overetch, queue time, metrology statistics, cost

Examples:
- Compute C_s from the exposed height and residual skin
- Compute the support solid fraction for a new opening CD
- Estimate TiN top loss with and without bias pulsing
- Find the dip time and support loss for a new BPSG
- Show why diffusion does not limit removal (Da)
- Compute pillar deflection under water and IPA
- Derive the pair collapse threshold g/8
- Estimate leaning probability from the margin
- Compare two- and three-support 2.0 µm molds
- Find the break-even yield for supercritical drying

---

## How to Use This Index

1. **First time?** Read PREFACE.md, then this INDEX, then Chapter 1.
2. **Focused reading?** Pick your role from the reading paths above.
3. **Reference mode?** Jump to the chapter. Use Appendix G for symptoms and Appendix E for formulas.
4. **Deep dive?** Read Chapters 1–16 in order and work the study questions.

---

**Index Version:** 1.0  
**Last Updated:** 2026-10-05  
**Next:** Begin [Chapter 1: The Pillar Capacitor & Why the Mold Must Go](./chapters/01-pillar-capacitor-mold-role.md)
