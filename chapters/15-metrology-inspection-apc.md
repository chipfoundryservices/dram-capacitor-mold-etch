# Chapter 15: Metrology, Inspection & Advanced Process Control

## Overview

The mold etch is hard to measure. Its product is empty space, its key defect rate is one in a billion, and the surfaces that matter are 1.6 µm down inside gaps 17 nm wide. Most of what can be measured directly is at the top: the support-open CD, the top-support thickness, the pillar tops, and leaning visible from above. What happens below must be inferred from test structures, cross-sections, X-ray and infrared methods, and, finally, electrical tests after the capacitor is complete. This chapter describes the metrology for each step, the inspection for leaning and residual oxide, the electrical monitors, and the control loops that tie them together.

**Learning Objectives:**
- Describe endpoint and in-line metrology for the support-open etch
- Explain how leaning is detected from above and how its statistics are reported
- Compare methods for detecting residual oxide in the forest
- Use electrical monitors to separate capacitance, short, and leakage signatures
- Design feed-forward and feedback control for the support open and the dip-out

---

## 15.1 Support-Open Metrology

### 15.1.1 Endpoint

```
Support-open endpoint (reference):
  SN1 (top SiN):  OES CN 387 nm and N₂ 337 nm fall at clear;
                  open area ≈ 15% of wafer → ΔI/I ≈ 5–10%
                  endpoint + 25% overetch
  OX:             time, fed forward from SN1 endpoint time
  SN2 (middle):   OES weak at A ≈ 17 (ΔI/I ≈ 1–2%); time-based with
                  SN1 endpoint ratio as a rate correction
  LAND:           time
```

The SN1 endpoint time is the best in-situ measure of the chamber's nitride rate on that wafer. Its ratio to the nominal time is used to scale SN2 and, more weakly, OX and LAND.

### 15.1.2 After-Etch Metrology

```
Measurement                  Method                     Sampling
──────────────────────────────────────────────────────────────────────
Opening top CD               CD-SEM (top-down)          13 sites/wafer, 1/lot
Opening bottom (middle SiN)  HV-SEM (back-scattered),   9 sites, 1/lot
  and landing depth          or OCD on a test array
Remaining ACL                Ellipsometry / OCD         5 sites
TiN crescent loss            AFM on a test pad;         weekly; per PM
                             TEM cross-section
Top-support thickness        OCD / ellipsometry         after strip
```

High-voltage SEM (10–30 kV landing energy) sees through the top support and shows whether the middle support has been opened in each column, as a contrast difference in the back-scattered image. It is the primary check for nitride slivers at the middle support.

---

## 15.2 Leaning Inspection

### 15.2.1 Top-Down SEM and E-Beam Inspection

Leaning pillars are visible from above because the pillar tops are clamped by the top support only if the top support is intact; a pillar that leans in the lower span moves its middle and bottom, not its top. Leaning is therefore detected indirectly:

```
What top-down imaging sees after the dip-out:
  - Through the openings: pillar segments below the top support
    (HV-SEM, 15–30 kV); a leaning pair shows as touching segments
  - Top support distortion above a severe collapse cluster
  - Pillar tops displaced where the top support has cracked
```

```
Leaning inspection (reference):
  Tool          HV e-beam inspection, die-to-die and cell-to-cell
  Pixel         ≈ 5 nm
  Coverage      ≈ 0.2–1% of the array area per wafer (sampled blocks)
  Sensitivity   touching or bridged pairs below the top support
  Throughput    ≈ 1–3 wafers/h → sampling, not 100%
```

### 15.2.2 Statistics

At a rate of one per billion and 1.7 × 10¹⁰ pillars per die, a die has about 17 leaning pillars. A 300 mm wafer of 16 Gb dies (about 900 dies) carries about 1.5 × 10¹³ pillars. Inspecting 0.5% of the array area samples about 7.7 × 10¹⁰ pillars and finds about 75 events. That is enough to track the rate lot to lot with a Poisson uncertainty of about 12%. Clustering must be accounted for: leaning events come in pairs and groups, and the defect count should be reported as events and as pillars.

```
Leaning metrics (reference):
  Events per 10⁹ pillars inspected       target ≤ 1
  Pillars per event (mean)               ≈ 2.2 (pairs dominate)
  Clusters ≥ 10 pillars per wafer        0
  Spatial signature                      radial / edge / arc / random
```

### 15.2.3 Cross-Section

Focused ion beam cross-sections and TEM lamellae show the full height of the forest at chosen sites. They are the reference for calibrating top-down inspection and for diagnosing whether leaning is in the lower or upper span.

---

## 15.3 Residual-Oxide Detection

```
Method                        What it sees                  Limit
─────────────────────────────────────────────────────────────────────────
FTIR (Si–O 1070 cm⁻¹) on      Total oxide remaining in the  ≈ 0.1% of mold
an array-like test block      array (area average)          oxide volume
XPS on a test array           Si, O on TiN surface (top     ≈ 0.3 at%
                              few nm, area average)
HV-SEM / e-beam inspection    Clusters of unremoved oxide   clusters ≥ 3–5 cells
                              (charging contrast)
TEM-EDS cross-section         Local residues at gap bottoms sub-nm, few sites
Capacitance (electrical)      Integrated effect on C_s      ≈ 0.5%
```

FTIR is the best fast measure of incomplete dip-out on a whole block: the Si–O stretching band of the mold disappears when the oxide is gone. It does not see a sub-nanometre skin on the TiN. XPS on a large test array sees the skin but not its depth distribution. In practice, a combination of FTIR on monitor blocks, e-beam inspection for clusters, and capacitance after the capacitor module covers the failure modes.

---

## 15.4 Electrical Monitors

After the dielectric and plate, test structures in the scribe and within the array give electrical signatures:

```
Monitor                         Sensitive to
──────────────────────────────────────────────────────────────────────
Array capacitance (large block, Exposed area (residual oxide, support
  e.g. 10⁶ cells in parallel)    thickness), EOT (TiN surface)
Comb of storage nodes          Pillar-to-pillar shorts (leaning,
  (alternating rows connected)   bridges)
Node-to-plate leakage          TiN surface (F, O), top loss (field
                                 hot spots), seams
Bit-fail map (product)          All of the above, cell by cell
```

The bit-fail map separates leaning from other defects by its spatial pattern: leaning pairs are adjacent cells on the hexagonal lattice, which map to specific patterns of word-line and bit-line addresses. A collapse cluster appears as a compact group of fails.

---

## 15.5 Advanced Process Control

### 15.5.1 Support Open

```
Feed-forward:
  Top-support thickness (after CMP)  → SN1 time (or endpoint)
  ACL thickness and CD               → OX and LAND time limits
  Middle-support thickness (from     → SN2 time
    mold deposition records)
Feedback:
  Landing depth (HV-SEM/OCD)         → LAND time
  Opening CD at middle support       → SN2 time, edge gas
  TiN crescent loss trend            → pulsing duty, electrode-age offset
```

### 15.5.2 Dip-Out

```
Feed-forward:
  BPSG dopant (from deposition metrology) and thermal history
                                     → HF time
  Landing depth (from support open)  → HF time (path length)
Feedback:
  FTIR residual on monitor blocks    → HF time
  Support thickness loss             → HF time / bath temperature
  Leaning events (sampled)           → drying recipe (front speed, N₂
                                       nozzle), chamber hold
```

HF time is usually held constant unless a feed-forward input moves outside its normal range; the overetch already covers normal variation (Chapter 12). The drying recipe is not adjusted wafer to wafer; leaning excursions trigger a chamber hold and a hardware check.

### 15.5.3 Consumable and Bath Offsets

```
Support-open chamber: electrode RF hours → O₂/C₄F₆ offset (TiN loss);
                      focus-ring hours → edge gas, edge zone temperature
Dip-out:              bath age (silicate) → HF time offset;
                      filter age → particle trend watch
```

---

## Summary and Key Takeaways

1. **SN1 endpoint is the anchor.** It measures the wafer's nitride rate and scales the later steps.

2. **HV-SEM looks through the top support.** It checks middle-support opening and finds leaning below the top support.

3. **Leaning is sampled, not inspected 100%.** About 0.5% coverage gives about 75 events per wafer at the target rate.

4. **FTIR sees bulk residue; XPS sees the skin.** Electrical capacitance integrates both.

5. **Control the plasma wafer to wafer; hold the dip-out constant.** Leaning excursions are hardware problems.

---

## Study Questions

1. A wafer's SN1 endpoint arrives 12% early. How should SN2, OX, and LAND be adjusted, and why should OX change less than SN2?

2. How much of the array must be inspected to detect a change in leaning rate from 1 to 2 per 10⁹ with 95% confidence in one wafer?

3. FTIR on a monitor block shows 0.3% of the mold oxide remaining. Is this consistent with gap-bottom residue (Chapter 12), with a blocked-column cluster, or with neither? What would you check next?

4. An array capacitance monitor shows −3% C_s but no change in leakage. List the likely causes from Chapters 11–13.

5. Design a feed-forward correction to the HF time based on BPSG boron content, using the sensitivity in Chapter 2.

---

**Next Chapter:** [Chapter 16: Post-Dip-Out Integration, Yield & Cost of Ownership](./16-integration-yield-coo.md)

---

**Chapter 15 Development Status:** Complete  
**Version:** 1.0
