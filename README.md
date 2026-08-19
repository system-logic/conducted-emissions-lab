# Conducted Emissions Lab

Re-examining my own EMC research from 2015–2021 — this time with a reproducible method, a home-built measurement path, and open data.

Between 2015 and 2021 I worked in a university EMC lab and published a series of papers on conducted emissions from switching converters in the 150 kHz – 30 MHz band. Rereading them today, I think the ideas were sound and the discipline was not: too much rested on single prototypes, with no reproducibility protocol and a non-standard detector. This repository is the attempt to fix that — to state what I claimed then as falsifiable claims, and to test each one with measurements I can hand to anyone else to repeat.

## What's here

| Folder / file | Contents |
|---|---|
| [`problem-statement.md`](problem-statement.md) | Subject, method, and the thesis that runs through the whole cycle |
| [`claims.md`](claims.md) | The five claims from 2015–2021, their known weaknesses, and verification status |
| [`references.md`](references.md) | Bibliography of the original papers and patents |
| `patents/` | Patent documents (full text) |
| `legacy/` | Digitised results from the original publications |

Planned, not yet here: `bench/` (LISN, electronic load, transient limiter), `calibration/`, `data/`, `tools/`.

## Bench status

| Item | Status |
|---|---|
| Ground plane, 1 × 1 m aluminium | <status> |
| LISN (CISPR 25, DC) | partially built |
| Linear electronic load, 300 W / 60 V / 10 A | nearly complete |
| Transient limiter | <status> |
| Spectrum analyser | acquired |
| VNA (NanoVNA-H4) | acquired |
| Oscilloscope (Micsig TO1104) | in service |

No shielded room, no calibrated receiver. Every deviation from the standard method is documented rather than hidden — see `calibration/` once it exists.

## Why this is not a compliance lab

<One short paragraph: what this bench can legitimately claim (relative comparisons under a fixed geometry, reproducible by others) and what it cannot (absolute levels certified against limits). Write this before anyone asks.>

## Video

The work is documented in long-form video: <link once published>. The repository is the primary record; the video is the commentary.

## Language

Source papers are in Russian; bibliography gives DOIs and links. Everything written for this project is in English.

## Licence

<CC-BY-4.0 for data and text, MIT for code — decide and state it.>
