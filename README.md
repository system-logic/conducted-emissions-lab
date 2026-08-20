# Conducted Emissions Lab

Conducted emissions from switching voltage converters, 150 kHz – 30 MHz: a home-built pre-compliance bench, open data, and a re-test of claims I published between 2015 and 2019.

Between 2015 and 2019 I worked in a university EMC lab and published a series of papers and patents on this subject. The ideas hold up; the discipline does not. The results rested on one-off prototypes, with no reproducibility protocol, and were measured with a detector for which no limits are defined in this band. This repository restates those results as falsifiable claims and tests them on a bench built from scratch, with everything published — raw captures, metadata, processing code — so the work can be contested rather than believed.

The five claims and their known weaknesses: [`claims.md`](claims.md).

## Subject

How individual elements of the power stage generate conducted noise, how much each contributes, how operating mode and topology change that, and how EMC measures interact with converter efficiency.

The thesis running through the original cycle, and through this one: emission should be suppressed during design, by choosing operating modes and components that emit least, and only then should a filter be designed — of the minimum necessary complexity. The practice it argues against treats EMC last, curing non-compliance by growing the filter, and pays for it in mass, volume and cost.

## Method

The original work built a prototype one element at a time and captured the spectrum at each step, attributing the change to the element just added. That attribution is the method's weak point and is treated explicitly in `claims.md` (C2).

This project keeps the incremental idea and adds what was missing: a single unified prototype platform so that configurations differ only in the variable under test; 9 kHz resolution bandwidth with quasi-peak and average detectors implemented in software and validated against reference signals; each claim swept across a stated parameter rather than tested at one operating point; and raw data published alongside every conclusion.

## What this bench is not

There is no shielded enclosure and no calibrated measuring receiver. The ambient spectrum in this band carries broadcast signals and emissions from neighbouring equipment, so every measurement is preceded by an ambient baseline.

The consequence is a hard limit on what may be concluded here. Relative comparisons under a fixed, documented geometry — this configuration against that one, measured minutes apart on the same setup — are sound and reproducible by anyone who rebuilds the bench. Absolute levels stated against regulatory limits are not: that requires a calibrated receiver in a controlled environment, and nothing in this repository should be read as a compliance result. Every deviation from the standard method is written down before the results, not after.

## Original body of work

Published in Russian, 2015–2019, two of them also in Springer translation. Everything in this project cites these by ID.

Publisher typeset versions are not redistributed here — those rights sit with the journals. Links point to legally available copies. Patent texts are public documents and are included in full.

### Papers

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

DOIs where assigned: Z2016-02 — `10.21293/1818-0442-2016-19-1-14-17`; Z2016-04 — `10.21293/1818-0442-2016-19-2-90-93`; Z2017-01 — `10.21293/1818-0442-2017-20-1-121-125`.

Z2015-02 is the metrological paper of the cycle — it defines how the measurements in the rest of the work were taken. The Russian original has not been retrieved; the Springer translation below is available. Z2015-03 and Z2016-05 have likewise not been retrieved in the original.

### Translated English editions (Scopus-indexed)

- Zagorodskikh E.V., Skvortsov V.A. An appraisal of matching devices for measurements of asymmetrical industrial radio interference. *Measurement Techniques*, 2015, vol. 58, no. 6, p. 702. — translation of Z2015-02.
- Zagorodskikh E.V., Skvortsov V.A. Working conditions of a converter installation with electromagnetic compatibility. *Russian Electrical Engineering*, 2016, vol. 87, pp. 14–16. — translation of Z2016-05.

### Related

Teaching guide: *Electromagnetic Compatibility of Electronic Devices*, TUSUR, 2016, 45 pp. (co-author) — the lab manual the measurement practice of this cycle was taught from.

Earlier student-level papers (2012–2013) on asymmetric-current supplies are not part of this review; the line of work they belong to ends in patent P2020-01.

### Patents (utility models)

| ID | Subject | Number | Filed | Published | File |
|---|---|---|---|---|---|
| P2015-01 | Lithotripter transmission cable with improved shielding | RU 159 076 U1 | 2015 | 2016 | [`RU159076.pdf`](patents/RU159076.pdf) |
| P2017-01 | Buck converter with a non-dissipative snubber | RU 174 772 U1 | 2017 | 2017 | [`RU174772.pdf`](patents/RU174772.pdf) |
| P2020-01 | Asymmetric-current power supply for electrochemical processes | RU 203 341 U1 | 2020 | 2021 | [`RU203341.pdf`](patents/RU203341.pdf) |

## How this repository is organised

Each stage of the work is a folder, written once and left alone. Documents are dated snapshots, not living pages: when a later result changes the picture, it arrives as a new file that references the old one by ID. Nothing is silently revised.

`claims.md` is the single exception. Its status column is meant to move — that is the whole point of keeping a claims register — and each change carries a link to the data behind it.

Planned: `bench/` (LISN, electronic load, transient limiter), `calibration/`, `data/`, `tools/`.

## Licence

Text, data and figures: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Code: [MIT](LICENSE). Use either freely, with attribution.
