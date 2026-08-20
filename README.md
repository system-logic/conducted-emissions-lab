# Conducted Emissions Lab

Conducted emissions from switching voltage converters, 150 kHz – 30 MHz.

Between 2015 and 2019 I worked in a university EMC lab and published a series of papers and patents on this subject. The ideas hold up; the discipline does not. The results rested on one-off prototypes, with no reproducibility protocol, and were measured with a detector for which no limits are defined in this band.

The goal here is to re-test those results on a bench I build myself, and to publish everything — raw captures, processing code, conclusions — so the work can be contested rather than believed.

## What I claimed, and what is wrong with it

**C1 — Three-zone spectral model.** The spectrum divides into 0.15–3, 3–16 and 16–30 MHz, each zone traceable to a distinct physical source. *The boundaries are not universal — they follow from the switching frequency, diode recovery times and layout of my particular prototypes.*

**C2 — Quantitative map of element contributions.** Each element of the power stage contributes a quantifiable amount to the total. *Adding an element does not add only its own parasitics; it changes the whole network. The difference between spectra before and after adding a diode is not the diode's emission. Measured with an RMS detector, while limits in this band are defined for quasi-peak and average.*

**C3 — Source localisation and inverse identification.** Topology and parameters — switching frequency, duty cycle, transition times, parasitic capacitances — can be read off the shape of the spectrum. *Validated against the same prototypes it was derived from. That is fitting, not prediction.*

**C4 — Snubbers on MOSFETs are an EMC measure, not an efficiency measure.** Up to roughly 1.5 kW a snubber does not improve efficiency but substantially improves the electromagnetic picture. *The 1.5 kW figure stands for the argument rather than a measured threshold, and devices have moved on in ten years.*

**C5 — Topological hierarchy by conducted emission.** PWM inverter, LLC converter and phase-shifted inverter can be ranked, phase-shifted best. *Declared on a single criterion, with layout uncontrolled between prototypes and the conditions of comparison unstated.*

All five share one root weakness: few prototypes, no reproducibility protocol, a detector without defined limits here. One remedy covers them — a new dataset with fixed geometry, standards-referenced measurement, and deliberate parameter variation.

## What this bench is not

No shielded enclosure, no calibrated measuring receiver. Relative comparisons under a fixed, documented geometry are sound and reproducible. Absolute levels against regulatory limits are not — nothing here is a compliance result.

## Original body of work

Published in Russian, 2015–2019; two papers also in Springer translation. Cited throughout by ID.

| ID | Title | Venue | Year |
|---|---|---|---|
| Z2015-01 | Analysis of PWM-converter interference emitted to the mains in the 0.15–3 MHz band | *Tekhnologii EMS*, no. 1(52), pp. 21–27 | 2015 |
| Z2015-02 | Evaluation of matching networks for measuring asymmetric industrial radio noise | *Metrologiya*, no. 2, pp. 64–71 | 2015 |
| Z2015-03 | Analysis of conducted emission from a high-frequency converter | *Prospects of Fundamental Sciences Development*, XII Int. Conf., TPU, pp. 1485–1487 | 2015 |
| Z2016-01 | On sources of conducted emission in the design of a bridge voltage inverter | *Tekhnologii EMS*, no. 1(56), pp. 41–48 | 2016 |
| Z2016-02 | Conducted emission of a bridge voltage inverter in current-stabilisation mode and ways to reduce it | *Proceedings of TUSUR*, vol. 19, no. 1, pp. 14–17 | 2016 |
| Z2016-03 | Parameter selection for a non-isolated voltage converter with EMC in mind | *Silovaya Elektronika*, no. 3, pp. 72–77 | 2016 |
| Z2016-04 | Soft-switching methods for the transistor switches of a boost converter in a spacecraft power system | *Proceedings of TUSUR*, vol. 19, no. 2, pp. 90–93 | 2016 |
| Z2016-05 | Parameter selection for a converter installation under electromagnetic compatibility constraints | *Elektrotekhnika*, no. 1, pp. 16a–18 | 2016 |
| Z2017-01 | Battery charge module for space applications | *Proceedings of TUSUR*, vol. 20, no. 1, pp. 121–125 | 2017 |
| Z2017-02 | Dynamic processes in non-isolated single-ended converters under soft switching | *Silovaya Elektronika*, no. 3, pp. 52–55 | 2017 |
| Z2019-01 | Conducted emission in push-pull converters with hard and soft switching | *Silovaya Elektronika*, no. 2, pp. 62–65 | 2019 |

DOIs: Z2016-02 — `10.21293/1818-0442-2016-19-1-14-17`; Z2016-04 — `10.21293/1818-0442-2016-19-2-90-93`; Z2017-01 — `10.21293/1818-0442-2017-20-1-121-125`.

Translations: Z2015-02 as *An appraisal of matching devices for measurements of asymmetrical industrial radio interference*, Measurement Techniques, 2015, 58(6), p. 702. Z2016-05 as *Working conditions of a converter installation with electromagnetic compatibility*, Russian Electrical Engineering, 2016, 87, pp. 14–16.

Publisher typeset versions are not redistributed here. Z2015-02, Z2015-03 and Z2016-05 I have not been able to retrieve in the original.

| ID | Patent | Number | Year | |
|---|---|---|---|---|
| P2015-01 | Lithotripter transmission cable with improved shielding | RU 159 076 U1 | 2015 | [`RU159076.pdf`](patents/RU159076.pdf) |
| P2017-01 | Buck converter with a non-dissipative snubber | RU 174 772 U1 | 2017 | [`RU174772.pdf`](patents/RU174772.pdf) |
| P2020-01 | Asymmetric-current power supply for electrochemical processes | RU 203 341 U1 | 2020 | [`RU203341.pdf`](patents/RU203341.pdf) |

Also: *Electromagnetic Compatibility of Electronic Devices*, teaching guide, TUSUR, 2016 (co-author).

## How the work is published

This file is the starting position and stays as written.

Each stage of the work gets its own folder, named by the date it was done, with its own README describing that stage — whatever it happened to consist of. Raw captures and notes live in the same folder.

## Licence

Text, data and figures: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Code: [MIT](LICENSE).
