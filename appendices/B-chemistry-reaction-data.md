# Appendix B: Chemistry & Reaction Data

Reactions, equilibria, rates, and plasma data used in the book. Values are representative; actual rates depend on film history, concentration, temperature, and tool.

---

## B.1 HF Solution Equilibria (25 °C)

```
HF ⇌ H⁺ + F⁻                K₁ ≈ 6.8 × 10⁻⁴ mol/L
HF + F⁻ ⇌ HF₂⁻              K₂ ≈ 3.9 L/mol
2 HF ⇌ (HF)₂                K₃ ≈ 2.7 L/mol

Concentration conversions:
  49 wt% HF ≈ 28.9 mol/L (ρ 1.18)
  5 wt% HF  ≈ 2.55 mol/L (ρ 1.02)  ≈ 10:1 dilution of 49% by volume
  1 wt% HF  ≈ 0.50 mol/L           ≈ 50:1
```

---

## B.2 Dissolution Reactions

```
Liquid:   SiO₂ + 6 HF → H₂SiF₆ + 2 H₂O
          SiO₂ + 3 HF₂⁻ + H⁺ → SiF₆²⁻ + 2 H₂O  (bifluoride path)
          Si₃N₄ + 18 HF → 2 (NH₄)₂SiF₆ + H₂SiF₆ (net, slow)
          B₂O₃ + 8 HF → 2 HBF₄ + 3 H₂O
          P₂O₅ + HF/H₂O → H₃PO₄, HPO₂F₂ (soluble)
          TiO₂ + 6 HF → H₂TiF₆ + 2 H₂O (slow)

Vapor:    SiO₂ + 4 HF → SiF₄↑ + 2 H₂O   (needs adsorbed H₂O / alcohol)
          Si₃N₄ + 16 HF → 2 (NH₄)₂SiF₆ + SiF₄  (solid residue)
          (NH₄)₂SiF₆ → 2 NH₃ + 2 HF + SiF₄  (sublimes ≈ 100 °C, vacuum)
```

---

## B.3 Wet Etch Rates (nm/min)

```
Material                5% HF 25 °C   1% HF 25 °C   BHF 7:1 25 °C
──────────────────────────────────────────────────────────────────
Thermal SiO₂            23            5             ≈ 80
PE-TEOS (annealed)      70            15            ≈ 200
BPSG (3.5 B, 4 P)       600           120           ≈ 900
Low-H PECVD SiN         1.0           0.2           ≈ 3
LPCVD SiN               0.7           0.15          ≈ 1.5
CVD TiN                 ≈ 0.05        ≈ 0.02        ≈ 0.05
TiO₂ (on TiN)           ≈ 0.3         ≈ 0.1         —

Temperature: oxide E_a ≈ 0.35 eV (≈ 4.6%/K); nitride E_a ≈ 0.55 eV (≈ 7%/K)
Concentration: R ∝ c^1.1–1.3 (unbuffered dilute HF)
```

---

## B.4 Vapor-HF Rates (Reference Conditions)

```
10 kPa, 45 °C, p_HF 2.5 kPa, ethanol 0.6 kPa:
  BPSG       ≈ 150 nm/min
  PE-TEOS    ≈ 25 nm/min
  Thermal    ≈ 8 nm/min
  SiN        ≈ 0.3 nm/min
  TiN        ≈ 0
Incubation:  5–60 s (surface-dependent)
```

---

## B.5 Support-Open Plasma Steps

```
Step   Gas (sccm)                         P (mT)  Source/Bias (W)   Rate (nm/min)
───────────────────────────────────────────────────────────────────────────────────
SN1    CH₂F₂ 40 / CF₄ 60 / O₂ 20 / Ar 300  30      1800 / 1800 pulsed  SiN 240
OX     C₄F₆ 25 / O₂ 22 / Ar 600            25      2200 / 2500 pulsed  Ox 450
SN2    CH₂F₂ 40 / CF₄ 50 / O₂ 15 / Ar 300  30      1800 / 1800 pulsed  SiN 200
LAND   C₄F₆ 25 / O₂ 18 / Ar 600            25      2000 / 2000          BPSG 400

Selectivities: SiN:TiN ≈ 15; Ox:TiN ≈ 40; Ox:ACL ≈ 5; SiN:ACL ≈ 3; Ox:SiN ≈ 6
```

---

## B.6 Volatility of Etch Products

```
Product      b.p. / subl. (°C)    Implication
────────────────────────────────────────────────────────
SiF₄         −86 (subl.)          volatile; Si/SiO₂/SiN etch
BF₃          −100                 volatile
TiF₄         284 (subl.)          involatile at wafer T; TiN passivates in F
TiCl₄        136                  volatile; Cl chemistry etches TiN
WF₆          17                   volatile; W etches in F if exposed
H₃PO₄        dec. > 200           residue in vapor HF
(NH₄)₂SiF₆   ≈ 100 (vac. subl.)   residue from nitride in vapor HF
```

---

## B.7 OES Lines for Support-Open Endpoint

```
Species    λ (nm)     Behaviour at nitride clear
──────────────────────────────────────────────────
CN         387.1      falls
N₂         337.1      falls
CO         483.5      rises (oxide exposed)
F          703.7      rises (less consumption)
Ar         750.4      reference (actinometry)
```

---

**Appendix B Version:** 1.0
