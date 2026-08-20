# Conducted Emissions Lab

Conducted emissions from switching voltage converters, 150 kHz – 30 MHz: a home-built pre-compliance bench, open data, and a re-test of claims I published between 2015 and 2021.

Between 2015 and 2021 I worked in a university EMC lab and published nine papers and three patents on this subject. The ideas hold up; the discipline does not. The results rested on one-off prototypes, with no reproducibility protocol, and were measured with a detector for which no limits are defined in this band. This repository restates those results as falsifiable claims and tests them on a bench built from scratch, with everything published — raw captures, metadata, processing code — so the work can be contested rather than believed.

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

Nine papers and three patents, published in Russian, 2015–2021. Two papers also appeared in translated English editions indexed in Scopus. Everything in this project cites these by ID.

Publisher typeset versions are not redistributed here — those rights sit with the journals, and with Springer for the translations. Links point to legally available copies. Patent texts are public documents and are included in full.

### Papers

| ID | Title | Venue | Year | DOI / link |
|---|---|---|---|---|
| Z2015-01 | <title> | <journal> | 2015 | <link> |
| Z2015-02 | <title> | <journal> | 2015 | <link> |
| Z2016-01 | <title> | <journal> | 2016 | <link> |
| Z2016-02 | <title> | <journal> | 2016 | <link> |
| Z2016-03 | <title> | <journal> | 2016 | <link> |
| Z2017-01 | <title> | <journal> | 2017 | <link> |
| Z2017-02 | <title> | <journal> | 2017 | not retrieved |
| Z2019-01 | <title> | <journal> | 2019 | <link> |
| Z2019-02 | <title> | <journal> | 2019 | not retrieved |

Two papers could not be retrieved. The gap is recorded rather than hidden.

**Translated editions.** <Z…> appeared in *Measurement Techniques* as <title>, <link>. <Z…> appeared in *Russian Electrical Engineering* as <title>, <link>.

### Patents

| ID | Subject | Number | Year | File |
|---|---|---|---|---|
| P2015-01 | High-voltage medical cable with improved shielding | <no.> | 2015 | [`patents/`](patents/) |
| P2017-01 | Buck converter with non-dissipative snubber | <no.> | 2017 | [`patents/`](patents/) |
| P2020-01 | Asymmetric-current supply for electrochemical processes | <no.> | 2020 | [`patents/`](patents/) |

## How this repository is organised

Each stage of the work is a folder, written once and left alone. Documents are dated snapshots, not living pages: when a later result changes the picture, it arrives as a new file that references the old one by ID. Nothing is silently revised.

`claims.md` is the single exception. Its status column is meant to move — that is the whole point of keeping a claims register — and each change carries a link to the data behind it.

Planned: `bench/` (LISN, electronic load, transient limiter), `calibration/`, `data/`, `tools/`.

## Licence

Text, data and figures: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Code: [MIT](LICENSE). Use either freely, with attribution.
