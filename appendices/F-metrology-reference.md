# Appendix F: Metrology Reference

Summary of the measurements used for the mold etch module: what each method sees, its resolution or detection limit, its sampling, and its role.

---

## F.1 Method Summary

```
Method              Measures                          Resolution / limit      Role
────────────────────────────────────────────────────────────────────────────────────────────
OES (in situ)       CN, N₂, CO, F emission            ΔI/I ≈ 1% (SN2),        SN1 endpoint;
                                                      5–10% (SN1)             rate feed-forward
CD-SEM (top-down)   Opening top CD, pillar tops       ± 0.5 nm (precision)    Support-open CD
HV-SEM (15–30 kV)   Middle-support opening, pillar    ≈ 3–5 nm                Sliver check; leaning
                    segments below top support                                below top support
HV e-beam inspect.  Leaning pairs, clusters, support  ≈ 5 nm pixel            Leaning rate (sampled)
                    cracks, residual-oxide clusters
OCD / scatterometry Opening depth, support thickness  ± 1 nm (model-based)    Landing, support loss
Ellipsometry        ACL, top-support thickness        ± 0.3 nm                Mask budget, CMP output
FTIR                Si–O band (1070 cm⁻¹) in array    ≈ 0.1% of mold oxide    Bulk residual oxide
XPS                 Ti–N/Ti–O/Ti–F, Si, P, C on TiN   ≈ 0.3 at%; top 5–8 nm   Surface condition
AFM                 Pillar-top height, crescent loss  ± 0.3 nm (z)            TiN top loss
TEM / STEM-EDS      Full forest profile, films, gaps  < 0.5 nm                Reference, failure analysis
FIB-SEM             Cross-sections at flagged sites   ≈ 3 nm                  Leaning diagnosis
Electrical C        Array capacitance                 ≈ 0.5%                  Integrated area, EOT
Comb structures     Node-to-node shorts               single shorts in 10⁶    Leaning, bridges
Leakage I–V         Node-to-plate leakage             fA/cell (array-level)   Surface, top loss, seams
Bit-fail map        Cell-level fails                  single cell             Yield signatures
```

---

## F.2 Sampling Plan (Reference)

```
Step            Measurement                    Frequency
──────────────────────────────────────────────────────────────────
After CMP       Top-support thickness          every lot, 5 sites
After SO mask   ACL CD, thickness              every lot
After SO etch   SN1 endpoint                   every wafer (logged)
                Opening CD (CD-SEM)            1 wafer/lot, 13 sites
                Middle opening (HV-SEM)        1 wafer/lot, 9 sites
                Landing depth (OCD/HV-SEM)     1 wafer/lot
After dip-out   Leaning (HV e-beam, 0.5%)      1 wafer/lot (2 for new chambers)
                FTIR monitor blocks            1 wafer/lot
                Support thickness (OCD)        1 wafer/lot
                XPS test array                 1 wafer/day per chamber
After plate     Leaning (repeat)               1 wafer/week (late leaning)
End of line     C, shorts, leakage, bit-fail   every wafer (test)
Periodic        TEM cross-section              weekly per platform; per PM
```

---

## F.3 Signatures and the Method That Sees Them

```
Defect                          First seen by               Confirmed by
──────────────────────────────────────────────────────────────────────────
Middle-support sliver           HV-SEM                      TEM
Landing too shallow             OCD / HV-SEM                TEM
TiN crescent loss high          AFM / TEM                   Leakage tail
Leaning pairs                   HV e-beam inspection        FIB-SEM; comb shorts
Collapse cluster                HV e-beam inspection        FIB-SEM; bit-fail cluster
Support crack                   HV e-beam / SEM             TEM
Residual oxide (bulk)           FTIR                        TEM-EDS; C monitor
Residual oxide (cluster)        HV e-beam (charging)        TEM; bit-fail cluster
Oxide/F skin on TiN             XPS                         C, leakage
Bottom-stop breakthrough        TEM (cavities)              Shorts to bit line
Seam opening                    TEM                         Leakage; directional leaning
```

---

## F.4 Leaning Statistics

```
Poisson counting: for N events, relative uncertainty ≈ 1/√N
  N = 25 → 20%;  N = 75 → 12%;  N = 300 → 6%
Pillars inspected for N events at rate r: n = N / r
  r = 10⁻⁹, N = 75 → 7.5 × 10¹⁰ pillars (≈ 0.5% of a 300 mm wafer's array)
Report: events/10⁹ pillars; pillars/event; clusters/wafer; radial map
```

---

**Appendix F Version:** 1.0
