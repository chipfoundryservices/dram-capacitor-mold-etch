# Appendix G: Troubleshooting Guide

Symptom-driven guide for DRAM capacitor mold etch excursions. For each symptom: likely causes ranked from most to least common, checks to separate them, and corrective actions. Chapter references point to the underlying physics.

---

## G.1 Leaning Rate Up (Whole Wafer, Radially Uniform)

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Water in IPA or incomplete              IPA water content; IPA time log;    Replace IPA; restore
   displacement (Ch. 8.2)                  watermark count                     IPA time/flow
2. Pillar thinner / span longer than       Hole-etch CD trend; mold thickness  Feed back to hole
   nominal (Ch. 10.4)                      records; TEM                        etch / mold dep
3. TiN fill modulus or seam change         Fill tool log; TEM seam; XRD        Restore fill recipe
   (Ch. 2.1, 10.4)
4. Collar loosened (support or hole-etch   TEM collar recess                   Hole-etch strip; dip
   strip change) (Ch. 11.1)                                                    time
```

## G.2 Leaning in Rings, Arcs, or at the Wafer Edge

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Secondary drying front / edge breakup   Radial leaning map; spin-ramp log;  Retune N₂ nozzle start
   (Ch. 8.3)                               N₂ nozzle position                  and scan; IPA vapor
2. Dry gap at a transition (Ch. 6.1.3)     Valve timing log                    Restore overlap
3. Film thinning at the edge (low flow,    Flow log; spin speed                Increase flow / reduce
   high spin) (Ch. 6.2.3)                                                      speed in HF and IPA
4. Focus-ring wear tilting columns (edge   SO-etch edge landing; ring hours    Ring change; edge
   pillar crescents larger) (Ch. 5.5)                                          offsets
```

## G.3 Leaning "Flowers" (Rings Around a Point)

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Particles pinning the meniscus          SEM at flower centre; particle      Filter change; nozzle
   (Ch. 9.3)                               monitor adders                      and arm clean
2. Splash-back droplets during dry         Cup condition; exhaust              Cup clean; exhaust
                                                                               balance
3. Bubbles at dispense                     Line degas; filter venting          Vent filters; check
                                                                               fittings
```

## G.4 Leaning at Array Edges or in Rows

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Support crack along a row (Ch. 11.2)    SEM/TEM of top support              Lower support stress;
                                                                               check SO-etch damage
2. Array-edge undercut / peeling           TEM at array edge; undercut         Dummy rows; guard ring;
   (Ch. 11.4)                              length                              shorten dip
3. Support stress gradient (Ch. 10.6)      Film stress maps                    Deposition uniformity
4. Plate-fill stress (late leaning)        Inspect before and after plate      Fill stress (Ch. 16.2)
   (Ch. 16.2)
```

## G.5 Residual Oxide (FTIR or Capacitance Low, Whole Wafer)

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. BPSG slower (dopant low, extra          Deposition metrology; thermal       Feed-forward HF time
   thermal budget) (Ch. 2.2)               history                             or fix upstream
2. HF weak or cold (Ch. 4.2)               Titration; thermocouple             Recalibrate blend/HX
3. Landing too shallow (longer path)       SO landing depth                    LAND time (Ch. 3.5)
   (Ch. 4.3)
4. Bath aged (recirculated) (Ch. 9.2)      Bath counter; silicate              Change bath
```

## G.6 Residual Oxide in Clusters

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Polymer residue on column walls →       Post-strip XPS (C, F); contact      Improve post-SO strip
   trapped gas (Ch. 4.5, 12.1)             angle on monitor                    and clean
2. Pre-wet missing or short                Recipe log                          Restore pre-wet
3. Particles plugging columns              Pre-dip inspection                  SO-etch chamber clean
4. Middle-support slivers (lower oxide     HV-SEM openings                     SN2 time; SO feedback
   unreachable) (Ch. 3.4)
```

## G.7 Support Thinner Than Target

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. HF time or temperature high             Recipe/HX logs                      Restore
2. Support film H content up (dep drift)   Blanket SiN HF rate; FTIR N–H       Fix deposition
3. Top support thin after CMP              Post-CMP thickness                  CMP control
4. SO etch ran past the ACL                ACL remaining; SO step times        ACL thickness; times
```

## G.8 Bottom-Stop Breakthrough / Cavities Under Pads

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Leaky pillar collar (Ch. 12.4)          TEM at feet; HF exposure time       Collar seal; shorten
                                                                               overetch
2. Hole-etch side punch / gouge            Book #29 metrology                  Hole-etch BO step
3. Bottom stop thin (deposition)           Film metrology                      Fix deposition
4. Dip far too long                        Recipe log                          Restore
```

## G.9 TiN Crescent Loss High

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Electrode late in life (less polymer)   Electrode RF hours                  Apply age offset; change
   (Ch. 5.5)
2. Pulsing fault (continuous bias)         Generator logs                      Repair
3. SN1 overetch too long                   SN1 endpoint and OE                 Restore OE %
4. SO overlay error (larger crescents)     Overlay metrology                   Litho correction
```

## G.10 Leakage Tail Up, Capacitance Normal

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. Queue time exceeded (TiOₓ)              Queue log; XPS                      Enforce queue limits
2. Rinse O₂ high                           DIW degasser                        Repair degasser
3. F on TiN high (short rinse)             XPS F                               Restore rinse
4. Sharp crescent edges / seam opening     TEM pillar tops                     SO chemistry; fill
   (Ch. 13.3–13.4)
5. Vapor-HF residue (P) if used            XPS P                               Bake / rinse
```

## G.11 Middle-Support Slivers

```
Likely causes                              Checks                              Actions
─────────────────────────────────────────────────────────────────────────────────────────────
1. SN2 time short vs thicker middle SiN    Mold records; SN1 endpoint ratio    Feed-forward SN2
2. OX → SN2 transition leaves polymer      Transition purge time               Lengthen purge
3. Column narrow at the middle support     HV-SEM CD; OX taper                 OX chemistry (less
                                                                               polymer at depth)
```

---

**Appendix G Version:** 1.0
