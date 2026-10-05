# Appendix D: Process Windows

Reference windows for the mold etch module. "Target" is the reference process; "window" is the range within which the specification of Chapter 1 is met with the other parameters at target. All values are illustrative starting points for a design of experiments.

---

## D.1 Support-Open Etch

```
Parameter                 Target           Window            Limited by
─────────────────────────────────────────────────────────────────────────────────
SN1 time                  EP + 25%         EP + 15–40%       sliver (low) / TiN, ACL (high)
OX bias power             2500 W           2200–2900 W       bottom CD (low) / TiN loss (high)
OX C₄F₆ / O₂ ratio        1.14             1.0–1.3           etch stop (high) / TiN, ACL (low)
SN2 time                  20 s             17–26 s           middle sliver (low) / mask (high)
LAND time                 25 s             15–40 s           landing ≥ 50 nm / ≤ 150 nm
Bias pulse duty (SN)      50%              40–70%            TiN loss (high duty) / time
Wafer temperature         40 °C            30–50 °C          polymer balance
Pressure (OX)             25 mT            20–32 mT          profile, ARDE
ACL thickness             300 nm           ≥ 280 nm          mask remaining ≥ 30 nm
```

---

## D.2 Dip-Out

```
Parameter                 Target           Window            Limited by
─────────────────────────────────────────────────────────────────────────────────
HF concentration          5.00 wt%         4.8–5.2           support loss / time
HF temperature            25.0 °C          24.5–25.5 °C      rate uniformity
HF time                   105 s            85–130 s          residual oxide (low) /
                                                             bottom stop, collars (high)
Pre-wet time              8 s              5–15 s            trapped gas (low)
Dispense flow             1.5 L/min        1.0–2.0           film continuity (low)
Spin speed (HF)           300 rpm          200–500           edge film (high) / boundary
                                                             layer (low)
Transition overlap        1.0 s            0.5–1.5 s         dry edge (low) / mixing
```

---

## D.3 Rinse and Dry

```
Parameter                 Target           Window            Limited by
─────────────────────────────────────────────────────────────────────────────────
Rinse time                45 s             35–60 s           residual F (low) / TiN
                                                             oxidation (high)
Rinse DIW O₂              ≤ 5 ppb          ≤ 20 ppb          TiN oxidation
IPA time                  30 s             20–45 s           residual water (low)
IPA temperature           25–50 °C         20–60 °C          γ (low T) / early front (high)
IPA water content         ≤ 100 ppm        ≤ 300 ppm         last-meniscus γ
Dry spin ramp             300→1500 rpm     ramp 2–6 s        single front
N₂ nozzle scan            2–5 mm/s         matched to front  droplets / secondary fronts
Chamber RH at dry         ≤ 30%            ≤ 40%             watermarks
```

---

## D.4 Structure (Design Windows)

```
Parameter                 Reference        Window            Limited by
─────────────────────────────────────────────────────────────────────────────────
Pillar diameter (avg)     28 nm            26–30 nm          C_s (low) / gap (high);
                                                             margin flat near 27 nm
Lower span                760 nm           ≤ 780 nm          collapse margin
Top support               120 nm           100–140 nm        clamp / capacitance
Middle support            50 nm            40–60 nm          clamp, HF loss / C_s
Bottom stop               20 nm            ≥ 15 nm after dip HF barrier
Support stress            +250 MPa         +150 to +400 MPa  buckling / fracture
Support-open CD           50 nm            45–56 nm          dip-out access / solid
                                                             fraction, TiN exposure
Support-open overlay      ± 5 nm (3σ)      ± 6 nm            crescent depth
```

---

## D.5 Sensitivities (Reference Point)

```
Output                    Input                    Sensitivity
──────────────────────────────────────────────────────────────────────
TiN crescent loss         SN1 time                 +0.04 nm/s
                          OX bias power            +0.5 nm per 300 W
Landing depth             LAND time                +4.8 nm/s
Lower-oxide path time     BPSG B content           −28% per wt% B
Support loss (each face)  HF time                  +0.017 nm/s
                          HF temperature           +7%/K
Collapse margin           Lower span               ∝ L⁻⁴ (−0.5%/nm at 760)
                          Fluid γ                  ∝ γ⁻¹
Leaning rate              Margin                   ≈ ×6 per −5% margin near M = 2.8
C_s                       Exposed height           +0.61 fF per 100 nm
                          Residual skin            −(t/(EOT + t)) × area fraction
```

---

**Appendix D Version:** 1.0
