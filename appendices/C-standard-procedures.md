# Appendix C: Standard Procedures

Step-by-step procedures for qualifying and monitoring the mold etch module. Each procedure lists purpose, materials, steps, and acceptance criteria. Values are illustrative.

---

## C.1 Support-Open Chamber Qualification

**Purpose:** Qualify a support-open chamber after installation or major PM.

**Materials:** Blanket SiN, PE-TEOS, BPSG, and ACL monitor wafers; 3 full-structure wafers (post-CMP pillar arrays with support-open mask).

**Steps:**
1. Run 5 seasoning wafers (bare Si with ACL) through the full recipe.
2. Measure blanket rates for each step film (SN1 on SiN, OX on PE-TEOS, SN2 on SiN, LAND on BPSG) at 49 sites.
3. Measure ACL loss at each step chemistry.
4. Run 3 structure wafers. Record SN1 endpoint time.
5. On structure wafers: CD-SEM opening top CD (13 sites); HV-SEM middle-support opening (9 sites); TEM cross-section at centre and edge (landing depth, TiN crescent loss, column profile).
6. Compare with fleet reference.

**Acceptance:**
```
Blanket rates within ± 3% of fleet mean; uniformity ≤ 3% (1σ)
SN1 endpoint time within ± 5% of fleet mean
Opening top CD 50 ± 2 nm (mean)
Middle-support opening ≥ 40 nm at all sites; no slivers in 10⁴ HV-SEM openings
Landing depth 50–150 nm at all sites
TiN crescent loss ≤ 5 nm (TEM)
```

---

## C.2 Dip-Out Chamber Qualification

**Purpose:** Qualify a single-wafer wet chamber for the dip-out.

**Materials:** Blanket BPSG, PE-TEOS, and support-SiN monitors; particle monitor wafers; 3 full-structure wafers after support open.

**Steps:**
1. Verify HF concentration at the nozzle by titration (5.00 ± 0.05 wt%) and temperature by in-line thermocouple (25.0 ± 0.2 °C).
2. Run blanket monitors with the HF step only (timed 30 s): measure BPSG, PE-TEOS, SiN rates at 49 sites.
3. Run 3 particle monitors through the full sequence (pre-wet → dry): count adders ≥ 30 nm.
4. Run 3 structure wafers through the full sequence.
5. Inspect structure wafers: HV e-beam leaning inspection (≥ 0.5% of array); FTIR residual oxide on monitor blocks; XPS on test array (F, O, Si on TiN); support thickness by OCD.
6. One structure wafer to TEM: gap bottoms, bottom-stop thickness, collars.

**Acceptance:**
```
BPSG rate 600 ± 18 nm/min; SiN rate ≤ 1.2 nm/min
Particle adders ≤ 10 per wafer (≥ 30 nm)
Leaning events ≤ 1.5× fleet median; no cluster ≥ 10 pillars
FTIR residual below detection on all monitor blocks
F ≤ 3 at%, Si ≤ 0.5 at% (XPS)
Bottom stop ≥ 15 nm at all TEM sites; no cavities under collars
```

---

## C.3 Leaning Inspection Recipe Setup

1. Select inspection blocks: centre, mid-radius, edge, and array-edge blocks in at least 5 dies.
2. Set HV e-beam landing energy to see pillar segments through the top-support openings (typically 15–25 kV); confirm on a known collapse wafer.
3. Set cell-to-cell comparison on the hexagonal lattice; define defect classes: pair, triple, cluster (≥ 4), support crack, top distortion.
4. Calibrate with FIB cross-sections at ≥ 20 flagged sites and ≥ 20 unflagged sites.
5. Report events per 10⁹ pillars inspected, pillars per event, and spatial signature.

---

## C.4 Drying Front Verification

1. Run a structure wafer with a reduced-margin test array (longer lower span or thinner pillar) to amplify leaning.
2. Map leaning density radially. A uniform map indicates a well-behaved front; rings indicate secondary fronts or edge breakup; spokes or arcs indicate nozzle path problems.
3. Adjust N₂ nozzle start position, scan speed, and spin ramp. Repeat until the radial map is flat within 2×.

---

## C.5 HF Bath Life Monitoring (Recirculated Systems)

1. Log wafers processed since bath change.
2. Daily: blanket BPSG and SiN monitors; NIR/conductivity concentration; silicate estimate.
3. Change bath at 400 wafers, or when BPSG rate falls by more than 4% after spiking, or when SiN rate rises by more than 15%.

---

## C.6 Queue-Time Control

1. Record dry-end time for each wafer (tool log).
2. Transfer to N₂ stocker within 30 min if the dielectric ALD is not available.
3. Hold lots exceeding 4 h in air or 12 h in N₂; disposition by XPS on a monitor wafer from the same lot (TiOₓ ≤ 1.0 nm equivalent).

---

## C.7 TEM Cross-Section Protocol for the Forest

1. Protect the top with a carbon cap; deposit e-beam Pt before ion-beam Pt.
2. Lamella orientation: along a row of the hexagonal lattice (pillars aligned) and at 30° (gaps aligned), one of each.
3. Thickness ≤ 40 nm so that a single row of pillars is resolved.
4. Measure: pillar diameter at five heights, gaps, support thickness, collar recess, bottom-stop thickness, residual films (EDS for Si, O, F, P).

---

**Appendix C Version:** 1.0
