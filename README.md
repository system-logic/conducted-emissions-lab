# Conducted Emissions Lab

Conducted emissions from switching voltage converters, 150 kHz – 30 MHz.

**Evgenii Zagorodskikh** — power electronics and EMC by specialisation. Currently deputy head of a telecommunications and data networks section in a communications department; 6.5 years with the company. Open to research and engineering work in power electronics and EMC; relocation and remote work are possible. Contact: [LinkedIn](https://www.linkedin.com/in/evgenii-zagorodskikh-58671042a/).

**What is here.** A home bench for measuring conducted emission, built and checked by me, with every measurement, correction and mistake written down. Current state: the bench is ready; measurements of converter prototypes come next.

**Where to start:**

- [Bench background protocol](2026-09-26-lab-bench-preparation/06-background-protocol.md) — what the bench itself picks up, step by step, and which source makes measurement impossible until it is removed.
- [Error and correction log](2026-09-26-lab-bench-preparation/08-errors.md) — what went wrong and how it was found.
- [LISN channel check](2026-09-26-lab-bench-preparation/05-lisn.md) — impedance against the CISPR 25 curve and the path correction.
- [Limiter](2026-09-26-lab-bench-preparation/03-limiter.md) — attenuation, channel isolation and a labelling error found from the measurement.

The rest of this file is the starting position of the project: what I claimed in 2015–2019 and why it needs re-testing.

From 2012 to 2018 I worked at a university, in its EMC lab and then at its space technology research institute, and between 2015 and 2019 published a series of papers and patents on this subject; the last of them came from analysing material collected earlier. The work was also written up as a PhD thesis: it was accepted and passed the pre-defence, after which I withdrew it myself, judging it not developed enough, and did not complete the degree. I think the ideas hold up; the discipline does not. The results rested on one-off prototypes, with no reproducibility protocol, and the detector was not the same throughout. The spectra in the papers come partly from an SMV11 selective microvoltmeter, which measures quasi-peak, and partly from an Agilent spectrum analyser photographed from its screen, which measures RMS; the papers do not state in every case which instrument was used. Measurements for the lab's customers were always quasi-peak; in my own research the two were mixed. CISPR 25 gives its limits for peak, quasi-peak and average detectors, so the RMS spectra cannot be compared with the limits, and the two kinds of spectra cannot be compared with each other.

The goal here is to re-test those results on a bench I build myself, and to publish everything — raw captures, processing code, conclusions — so the work can be contested rather than believed.

## What I claimed, and what is wrong with it

**C1 — Three-zone spectral model.** The spectrum divides into 0.15–3, 3–16 and 16–30 MHz, each zone traceable to a distinct physical source. *The boundaries are not universal — they follow from the switching frequency, diode recovery times and layout of my particular prototypes.*

**C2 — Quantitative map of element contributions.** Each element of the power stage contributes a quantifiable amount to the total. *Adding an element does not add only its own parasitics; it changes the whole network. The difference between spectra before and after adding a diode is not the diode's emission. The detector is not stated consistently: RMS from the spectrum analyser or quasi-peak from the SMV11, while the limits of CISPR 25 are given for peak, quasi-peak and average detectors.*

**C3 — Source localisation and inverse identification.** Topology and parameters — switching frequency, duty cycle, transition times, parasitic capacitances — can be read off the shape of the spectrum. *Validated against the same prototypes it was derived from. That is fitting, not prediction.*

**C4 — Soft switching, snubbers on MOSFETs included, is an EMC measure first and an efficiency measure second.** In low-power MOSFET circuits a snubber does not improve efficiency, and may cost some, yet substantially improves the electromagnetic picture. *Where "low power" ends was never measured: the figure of roughly 1.5 kW that went with this claim is nominal, not a threshold, and devices have moved on in ten years.*

**C5 — Topological hierarchy by conducted emission.** PWM inverter, LLC converter and phase-shifted inverter can be ranked, phase-shifted best. *Declared on a single criterion, with layout uncontrolled between prototypes and the conditions of comparison unstated.*

All five share one root weakness: few prototypes, no reproducibility protocol, and a mix of detectors not recorded capture by capture. One remedy covers them — a new dataset with fixed geometry, standards-referenced measurement, and deliberate parameter variation.

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

## Stages

| Folder | Stage |
|---|---|
| [`2026-09-26-lab-bench-preparation`](2026-09-26-lab-bench-preparation/) | Lab bench preparation: LISN, limiter, instrument calibration, bench background |
| [`2026-10-02-bench-earthing-and-first-test`](2026-10-02-bench-earthing-and-first-test/) | Bench earthing and first test: open items of stage 1, test boards with a fixed layout, separation of common-mode and differential-mode interference (tasks and expected results; in progress) |

## Licence

Text, data and figures: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (full text: [`LICENSE-CC-BY-4.0.txt`](LICENSE-CC-BY-4.0.txt)). Code: [MIT](LICENSE).
