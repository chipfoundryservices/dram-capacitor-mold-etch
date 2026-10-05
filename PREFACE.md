# Preface: The Etch That Sets the Capacitor Free

## Why This Book Exists

Most etches in a chip make something: a trench, a line, a hole. The capacitor mold etch makes nothing. Its job is to take away a block of oxide 1.6 µm thick that was put there only to be cut into, filled, and thrown away. When it is done well, nobody sees it. What remains is the most fragile structure ever built at scale on a silicon wafer: about seventeen billion titanium nitride pillars per die, each fifty-seven times taller than it is wide, standing 17 nm from its neighbours, held up by two perforated sheets of silicon nitride.

The pillars are the bottom electrodes of the DRAM storage capacitors. The capacitor dielectric and the top plate will be wrapped around their outer surfaces, so the capacitance of each cell, about 8.6 fF in the reference process of this book, comes from the area that the mold etch exposes. While the pillar is buried, that area is worth nothing. Every square nanometre that stays covered by a film of oxide, or by a fragment of a support that should have been opened, is capacitance the cell will never have.

The method sounds like a single wet dip, and in a sense it is. It asks a great deal of the process:

1. **Open a skeleton, not a field.** Before any HF reaches the mold, a plasma etch must cut openings through the top nitride support, the upper oxide, and the middle nitride support. These openings are placed among the pillars and expose their tops to ion bombardment. The TiN must survive, the nitride must clear in every opening, and the etch must stop well above the bottom stop.

2. **Remove all of the oxide.** HF enters through openings that cover 28% of the lattice and must reach every point of the mold, including the bottom corners 1.6 µm down, through gaps only 17 nm wide. A film of 2 nm left on a pillar costs most of the capacitance there.

3. **Remove none of the nitride.** The supports are 120 nm and 50 nm thick, and the bottom stop is 20 nm. HF etches nitride slowly, but the dip lasts minutes. If the bottom stop is breached, HF reaches the oxide beneath it and undercuts the landing pads.

4. **Leave the TiN alone.** HF and water oxidize and fluorinate the TiN surface. The dielectric is grown on that surface. A few ångströms of TiOₓFᵧ change the leakage and the effective capacitance.

5. **Let nothing fall over.** As the liquid leaves the gaps, menisci pull on the pillars. With water, a pillar with a 760 nm free span would bend 17 nm, enough to touch its neighbour. Once two pillars touch, they stay together. The drying step decides whether the forest stands.

6. **Every pillar standing.** A pair of leaning pillars is two dead cells; a broken support can release hundreds. Repair redundancy covers a few thousand cells per die. The module must deliver leaning defects below about one per billion pillars.

This book treats the mold etch as **a structural process**, governed as much by beam mechanics and capillarity as by chemistry, and not as a cleaning step that happens to use HF.

---

## Unique Aspects of DRAM Capacitor Mold Etch

### 1. The Product Is a Void

Every other etch is judged by the shape it cuts. The mold etch is judged by what it leaves standing and by the cleanliness of the empty space around it. Its defects are invisible from above until something has fallen.

### 2. Plasma and Wet in One Module

The support open is a plasma etch with its own selectivity, profile, and endpoint problems. The dip-out is a wet or vapor etch with transport, concentration, and drying problems. Neither can be optimized alone: a support opening that is 5 nm narrower lengthens the dip-out; a dip-out that is 30 s longer thins every support.

### 3. Mechanics Sets the Window

The process window is not set by an etch rate but by a beam equation. Pillar stiffness scales with the fourth power of diameter and the inverse fourth power of span. A pillar 1 nm thinner is 16% more flexible; a free span 50 nm longer is 29% more flexible.

### 4. Failures Are Collective

A not-open hole in Book #29 is one cell. A collapsed pillar pulls on its neighbours; a cracked support releases a region. Leaning defects come in pairs, triples, and clusters, and their statistics are not Gaussian.

### 5. The Surface Is the Interface

The pillar surface after the dip-out becomes the bottom interface of the capacitor dielectric. Oxygen, fluorine, carbon, and residual silicate on that surface show up months later as leakage and retention tails.

---

## How to Read This Book

### For Process Engineers
Read Chapters 1–4 for the structure and chemistry, then Chapters 10–13 for the failure modes. Use Appendix D for windows and Appendix G for excursions.

### For Equipment Engineers
Read Chapter 1, then Chapters 5–9 for the plasma chamber, wet processor, vapor reactor, drying system, and chemical delivery. Chapter 15 covers the metrology that judges your tools.

### For Integration Engineers
Read Chapters 1–2, then Chapters 10–12 and 14–16. The support design rules in Chapter 11 and the cost model in Chapter 16 are written for you.

### For Device Engineers
Read Chapter 1, Chapter 13 for the electrode surface, and Chapter 16 for yield signatures.

### For Researchers
Read Chapters 3, 4, 10, and 14. The elastocapillary model in Chapter 10 and the gap-transport model in Chapter 4 are deliberately simple and invite refinement.

---

## A Note on the Reference Process

A single reference process runs through every chapter so that numbers connect. It inherits the array of Book #29: a 1b-class 6F² cell on a 45 nm hexagonal storage-node pitch and a 1.60 µm mold of top SiN (120 nm), undoped PE-TEOS (650 nm), middle SiN (50 nm), BPSG (760 nm), and bottom SiN (20 nm). The holes are filled with solid TiN pillars (32/28/24 nm top/average/bottom). The support-open pattern has 50 nm openings on a 90 nm hexagonal lattice. The dip-out is 5 wt% HF at 25 °C followed by IPA displacement and spin drying. All values are illustrative; the arithmetic is shown so that readers can replace them with their own.

---

## Acknowledgments

This book draws on decades of published work in plasma etching, wet chemistry of silicon dioxide and nitride, MEMS release and stiction, and elastocapillarity of nanostructures, and on the shared experience of the engineers who have kept DRAM capacitors standing through every node.

---

**Preface Version:** 1.0  
**Last Updated:** 2026-10-05
