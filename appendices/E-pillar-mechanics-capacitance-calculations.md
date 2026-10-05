# Appendix E: Pillar Mechanics & Capacitance Calculations

Closed-form models used in the book, with derivations, reference values, and worked examples. Each model is deliberately simple so that it can be checked by hand and recalibrated with measured data.

---

## E.1 Capacitance of a Pillar

```
C_s = ε₀ · 3.9 · π · d_avg · H_eff / EOT
H_eff = H_mold − t_top − t_mid − t_bottom

Reference: d_avg = 28 nm, H_eff = 1410 nm, EOT = 0.50 nm
  A = π × 28 × 1410 = 1.240 × 10⁵ nm²
  C_s = 3.453 × 10⁻¹¹ F/m × 1.240 × 10⁻¹³ m² / 0.50 × 10⁻⁹ m = 8.57 fF

Sensitivities:
  ∂C_s/∂H_eff = 0.61 fF per 100 nm
  ∂C_s/∂d_avg = 0.31 fF per nm
  ∂C_s/∂EOT   = −1.7 fF per 0.1 nm
```

## E.2 Residual Films

A film of thickness t and relative permittivity k_f on area fraction f adds t × 3.9/k_f to the EOT there:

```
ΔC_s/C_s = −f × t_eq / (EOT + t_eq),   t_eq = t × 3.9/k_f

SiO₂ (k = 3.9): t = 2 nm, f = 0.05 → −0.05 × 2/2.5 = −4.0%
SiO₂ skin everywhere: t = 0.3 nm, f = 1 → −0.3/0.8 = −37.5%
TiO₂ (k = 40), insulating: t = 1 nm, f = 1 → t_eq = 0.0975 → −16%
```

## E.3 Sense Signal

```
ΔV_BL = (V_core/2) · C_s/(C_s + C_BL)
V_core = 1.10 V, C_BL = 40 fF, C_s = 8.6 fF → 97 mV
```

---

## E.4 Beam Deflection of a Span

```
Uniform load q (N/m) on span L:
  clamped–clamped   δ_max = q L⁴ / (384 EI)   (at mid-span)
  pinned–pinned     δ_max = 5 q L⁴ / (384 EI)
  cantilever        δ_tip = q L⁴ / (8 EI)

Point load F at mid-span, clamped–clamped:
  δ = F L³ / (192 EI);  k = 192 EI / L³
```

## E.5 Capillary Load

```
ΔP = 2γ cos θ / g          (slit)
q  = α · ΔP · d

Water, g = 17 nm, d = 28 nm, α = 1:  q = 0.237 N/m
IPA (21.7 mN/m):                      q = 0.0715 N/m
```

## E.6 Reference Deflections (EI = 1.21 × 10⁻²⁰ N·m²)

```
Span        Fluid     α = 1       α = 0.15
────────────────────────────────────────────
760 nm      Water     17.1 nm     2.56 nm
760 nm      IPA       5.15 nm     0.77 nm
650 nm      Water     9.14 nm     1.37 nm
650 nm      IPA       2.75 nm     0.41 nm
1580 nm     Water     319 nm      48 nm      (no middle support)
1580 nm     IPA       96 nm       14 nm
1580 nm cantilever, water, α = 1: 15.3 µm
```

---

## E.7 Elastocapillary Collapse Thresholds

Force on the pillar scales as 1/(gap). Let δ₀ be the linear deflection at the initial gap g.

**Single pillar, rigid neighbour:**
```
δ = δ₀ g / (g − δ)  →  δ² − gδ + δ₀g = 0
Stable solution exists iff δ₀ ≤ g/4; at threshold δ = g/2
```

**Symmetric pair:**
```
δ = δ₀ g / (g − 2δ)  →  2δ² − gδ + δ₀g = 0
Stable solution exists iff δ₀ ≤ g/8; at threshold δ = g/4 (gap halved)
```

**Pair margin:**
```
M = (g/8) / δ₀(α_ref)
α_crit = α_ref · M
Reference: g = 17 nm → g/8 = 2.125 nm; IPA δ₀(0.15) = 0.77 nm → M = 2.76
```

**Scaling at fixed pitch a (gap g = a − d):**
```
δ₀ ∝ γ d L⁴ / (g E d⁴) = γ L⁴ / (E d³ g)
M ∝ g / δ₀ ∝ E d³ g² / (γ L⁴) = E d³ (a − d)² / (γ L⁴)
dM/dd = 0 → d = 0.6a  (27 nm at a = 45 nm)
```

## E.8 Statistical Leaning Model

```
ln α ~ N(ln α_med, σ²),  α_med = 0.15, σ = 0.17
P(collapse per pair site) = ½ erfc[ ln(α_crit/α_med) / (σ√2) ] = ½ erfc[ ln M / (σ√2) ]

M       z = ln M/σ     P
──────────────────────────────
1.0     0              0.5
1.5     2.39           8 × 10⁻³
2.0     4.08           2 × 10⁻⁵
2.25    4.77           9 × 10⁻⁷
2.5     5.39           3.5 × 10⁻⁸
2.76    5.97           1.2 × 10⁻⁹
3.0     6.46           5 × 10⁻¹¹
3.5     7.37           9 × 10⁻¹⁴
```

## E.9 Adhesion After Contact

```
Van der Waals force per length, two parallel cylinders of radius R at separation D:
  F/ℓ = A √(R/2) / (8√2 D^(5/2))
  A = 3 × 10⁻¹⁹ J, R = 14 nm, D = 0.3 nm → 0.45 N/m
Elastic restoring force at contact (each pillar bent g/2, L = 760 nm):
  F_el = (192 EI/L³)(g/2) = 5.3 N/m × 8.5 nm = 45 nN
Contact length for balance: 45 nN / 0.45 N/m = 100 nm
```

---

## E.10 HF Path and Losses

```
t_path = (path length) / (etch rate)
Upper oxide: 47 nm / 70 nm/min = 40 s
Lower oxide: √(660² + 47²) / 600 nm/min = 66 s
HF time = t_path,max × (1 + 3σ_rate) + t_wet = 66 × 1.14 + 8 ≈ 83 s (3σ); reference 105 s
Support loss per face = R_SiN × t_exposed = 1.0 × 105/60 = 1.75 nm
Bottom-stop loss = R_stop × (t_HF − t_path) = 0.7 × 39/60 = 0.45 nm
```

## E.11 Transport

```
Damköhler number: Da = v_front L / D_eff
  v = 10 nm/s, L = 660 nm, D_eff = 1.0 × 10⁻⁹ m²/s → Da ≈ 7 × 10⁻⁶

HF consumption: 6 × n_SiO₂ / c_HF = 6 × 3.7 × 10⁴ / 2.6 × 10³ ≈ 85 volumes per oxide volume

Rotating-disk boundary layer: δ_D = 1.61 (D/ν)^(1/3) (ν/ω)^(1/2)
  300 rpm → 33 µm

Kelvin condensation (slit, width w): ln(p/p_sat) = −γ V_m cos θ / (R T w/2)
  Water, 45 °C: w = 17 nm → 0.95; w = 5 nm → 0.83
```

## E.12 Support-Open Geometry

```
Opening cell (hex pitch b): area = (√3/2) b²;  b = 90 nm → 7015 nm²
Pillars per opening: 7015 / 1734 = 4.05
Open fraction: π (d_SO/2)² / 7015 = 1963 / 7015 = 28%
Farthest lateral distance: b/√3 − d_SO/2 = 52 − 25 = 27 nm
Crescent (circle–circle overlap, r₁ = 25, r₂ = 16, spacing 26): 317 nm²
Top-support solid fraction: [7015 − (3256 + 1963 − 951)] / 7015 = 39%
```

## E.13 Worked Example: Effect of a 30 nm Lower Middle Support

The middle support is deposited 30 nm lower (lower span 730 nm, upper 680 nm):

```
Lower-span margin: 2.76 × (760/730)⁴ = 3.24 → P ≈ 2 × 10⁻¹²
Upper-span margin: (650 nm reference upper margin = 2.76 × (760/650)⁴ = 5.16)
                   5.16 × (650/680)⁴ = 4.31 → P ≈ 0
C_s unchanged (same support thickness)
Hole etch: SN2 step at a different depth (Book #29) — check twist and bow
Conclusion: a ~500× improvement in lower-span collapse for a 30 nm move.
```

---

**Appendix E Version:** 1.0
