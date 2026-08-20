# Claims register

Five results from the 2015–2021 cycle, restated as claims that can be tested and, if wrong, refuted. Each carries the weakness I now see in the original evidence and the experiment that will settle it.

This is the one document in the repository that changes. The status column moves as measurements come in; everything above it stays as written. Status values: `to be verified` · `confirmed` · `refined` · `refuted`.

| ID | Claim | Status |
|---|---|---|
| C1 | Three-zone spectral model | `to be verified` |
| C2 | Quantitative map of element contributions | `to be verified` |
| C3 | Source localisation and inverse identification | `to be verified` |
| C4 | Snubbers on MOSFETs are an EMC measure, not an efficiency measure | `to be verified` |
| C5 | Topological hierarchy by conducted emission | `to be verified` |

---

## C1 — Three-zone spectral model

**Claim.** The conducted emission spectrum divides into three zones — 0.15–3 MHz, 3–16 MHz, 16–30 MHz — each traceable to a distinct physical source.

**Basis.** Z2016-03, where the three regions are named and attributed; supported by Z2015-01 and Z2019-01.

**Weakness.** The boundaries are not universal. They follow from the switching frequency, diode recovery times, magnetics construction and layout of my particular prototypes. Stated as fixed numbers, they overreach.

**Test.** Re-derive the boundaries as functions of circuit parameters rather than fixed frequencies, and check whether the zone structure survives when switching frequency and edge rate are varied deliberately.

**Status.** `to be verified`

---

## C2 — Quantitative map of element contributions

**Claim.** Each element of the power stage contributes a quantifiable amount to the total emission level.

**Basis.** Z2016-01, Z2016-02, Z2019-01 — all built on incremental assembly.

**Weakness.** Two, and the first is serious. Adding an element does not add only its own parasitics — it changes the whole network: impedances, loops, resonances. The difference between spectra before and after adding a diode is not the diode's emission; it is the change of the system when a diode is added to that specific circuit. Second, the measurements used an RMS detector, while limits in this band are defined for quasi-peak and average detectors, so the map is quantitatively conditional.

**Test.** Repeat on a fixed geometry with standards-referenced detectors, and state the result as a system delta under a defined configuration rather than as an element's emission.

**Status.** `to be verified`

---

## C3 — Source localisation and inverse identification

**Claim.** The source of an emission, and converter parameters — switching frequency, duty cycle, transition times, parasitic capacitances — can be identified from the shape of the spectrum.

**Basis.** Z2015-01, where measured spectra are matched against a Fourier model of the switching waveform.

**Weakness.** Different parameter combinations may in principle produce indistinguishable spectra. Identification was validated mostly against the same prototypes it was derived from, which is fitting rather than prediction.

**Test.** Blind run: take a circuit, capture its spectrum, and identify topology and the parameters shaping that spectrum without prior knowledge. The prediction is recorded before the box is opened.

**Status.** `to be verified`

---

## C4 — Snubbers on MOSFETs are an EMC measure, not an efficiency measure

**Claim.** With MOSFET switches at powers up to roughly 1.5 kW, snubber networks do not improve efficiency, but do substantially improve the electromagnetic picture.

**Basis.** Z2017-02 (loss budgets for each snubber family), Z2017-01 (efficiency and emission measured on the same module), Z2016-04.

**Reasoning.** At higher power the switches themselves are slower, so a snubber genuinely reduces switching loss and pays for itself. At lower power the switch and the snubber are comparable in speed, there is little switching loss left to recover, and the snubber's own dissipation — which scales with switching frequency — lowers total efficiency.

**Weakness.** The 1.5 kW boundary is conditional: it stands for the argument rather than marking a measured threshold. Device performance has moved considerably in ten years, so the balance has probably shifted.

**Test.** Efficiency and emission measured together, on the same platform, with and without snubbers, swept across power and switching frequency, and repeated with modern devices.

**Status.** `to be verified`

---

## C5 — Topological hierarchy by conducted emission

**Claim.** PWM inverter, LLC converter and phase-shifted inverter can be ranked by conducted emission, with the phase-shifted topology best.

**Basis.** Z2019-01, with the hard-switched baseline from Z2016-01.

**Weakness.** Optimality was declared on a single criterion. Control complexity and cost were not weighed, the conditions of comparison were not stated, and layout was not controlled between prototypes although it must affect the upper zone of the spectrum.

**Test.** Same base board, same component set, same layout across all three topologies, with the comparison stated together with its criterion and its conditions.

**Status.** `to be verified`

---

## Root weakness common to all five

A small number of one-off prototypes, no reproducibility protocol, a detector without defined limits in this band. One remedy covers all five: a new dataset with fixed geometry, standards-referenced measurement including a software quasi-peak detector, and deliberate parameter variation.
