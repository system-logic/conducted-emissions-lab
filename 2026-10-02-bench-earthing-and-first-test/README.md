# Bench earthing and first test

Stage opened 2026-10-02. This file states the tasks of the stage and the results expected from each of them.
Nothing here is measured yet: results will be added to this folder as separate documents, and each task below
will get a link to its result.

The stage continues [lab bench preparation](../2026-09-26-lab-bench-preparation/). It has three parts:
first the items left open in stage 1 are closed, then the first test circuit is measured, then the oscilloscope
is used to separate the two kinds of interference.

## Part A. Closing the open items of stage 1

Stage 1 was measured with the reference plate not connected to protective earth. That was deliberate, to close the
first series. This stage starts with a more thorough preparation of the bench itself: the background is checked again
without a prototype, this time with full earthing.

| No. | Task | Method | Expected result | Status |
|---|---|---|---|---|
| A1 | Earth the reference plate and bond the enclosures | Plate connected to protective earth with a 2.5 mm² cable; LISN and load enclosures bonded to the plate with short wide straps or pressed against it | Bonding in place and described; DC resistance between the LISN enclosure and the plate recorded (the standard requires no more than 2.5 mΩ) | Open |
| A2 | Fix the geometry of the leads and of the prototype | By the standard: leads and prototype are not pressed against the plate (see "Geometry" below) | Geometry built, measured with a ruler, photographed and kept the same for all later measurements | Open |
| A3 | Repeat the background protocol with earthing | Steps 4–13 of the [stage 1 protocol](../2026-09-26-lab-bench-preparation/06-background-protocol.md), same analyser settings, max hold over 3–4 sweeps, marker on the trace maximum | Steps 4 and 13 differ by less than 5 dB at 150 kHz. Step 4 is not worse than in stage 1 (≈25 dBµV at 150 kHz and 0–5 dBµV above 1 MHz on the screen); if it is worse, a mains filter at the bench inlet is needed | Open |
| A4 | Find out what earthing does to the hump at 8–17 MHz | Compare steps 9–12 with stage 1 | Recorded whether the hump is still there and whether its frequency still depends on what is connected. In stage 1 it moved between 8 and 17 MHz, which was attributed to the leads and enclosures acting as an antenna | Open |
| A5 | Refine the LISN correction in the lower decade | Direct method: generator on the output terminal, oscilloscope on the terminal and on the BNC, ratio of voltages at 150 kHz, 300 kHz, 500 kHz and 1 MHz | Measured correction within −9.7 dB ±0.5, the value accepted in stage 1 (calculation from the circuit: −9.9 dB at 135 kHz). If it is outside, the [corrections file](../2026-09-26-lab-bench-preparation/07-corrections.md) gets values by frequency | Open |
| A6 | Measure the leakage between the LISN channels | NanoVNA: PORT 1 on the output terminal of one channel, PORT 2 on the BNC of the other channel, the free BNC terminated with 50 Ω | A number by frequency. No criterion was set in stage 1; low priority | Open |
| A7 | Record the spacing of the comb from the PC | With the PC on, read the frequency spacing between neighbouring lines of the comb at 10–30 MHz | Spacing recorded; it would identify the converter in the PC. Not recorded in stage 1 | Open |

### Geometry

Stage 1 planned leads of 20–30 cm pressed against the plate. That plan is dropped: the leads and the prototype are placed
as the standard describes (GOST CISPR 25—2023, identical to CISPR 25:2021, clauses 6.2 and 6.3):

| Item | In the standard | On this bench |
|---|---|---|
| Reference plate | At least 1000 × 400 mm for the voltage method, bonded to the shielded enclosure | Aluminium sheet covering almost the whole table; size to be recorded; no shielded enclosure |
| LISN | Placed directly on the plate, enclosure bonded to it, DC resistance no more than 2.5 mΩ | Task A1 |
| Power leads between the LISN and the device | 200 mm, tolerance +200 mm, straight, 50 ±5 mm above the plate on a non-conductive support | As in the standard (task A2) |
| Device under measurement | 50 ±5 mm above the plate on a non-conductive support, enclosure not bonded unless that is how it is installed | As in the standard (task A2) |
| Load | On the plate, metal enclosure bonded to the plate | Task A1 |
| Room | Shielded enclosure | Ordinary room; a known and stated limit of the bench |

Every deviation from the standard is to be written down in the result document.

## Part B. First test circuit

The test circuits are built on a small set of boards with a fixed layout, so that a change of topology does not
change the tracks. This addresses the weakness stated in the root README for claim C5, where the layout was not
controlled between prototypes.

| Board | Topologies | How the topology is changed |
|---|---|---|
| Cell board | Buck and boost | The board is the same for both: only the connection of the source and of the load and the control change |
| Two cell boards | Push-pull and bridge | Two identical cell boards are used together |
| Flyback board | Flyback | A separate board |

Every board has places for current shunts. For emission measurements the shunts are removed and replaced with a wire
soldered flush to the board, as a continuation of the track.

What this structure does not remove is stated here in advance: the flyback is on a different layout from the others,
so its comparison with them is less strict; and two boards used together add the connections between them.

| No. | Task | Method | Expected result | Status |
|---|---|---|---|---|
| B1 | Describe the boards | Schematic and layout of the cell board and of the flyback board; for each topology what is fitted and how the source, the load and the control are connected; component values, operating point (input voltage, load current, switching frequency); photographs of the build and of its position on the plate | A description from which the measurement can be repeated | Open |
| B2 | Measure the test circuit | Three spectra for each state, as planned in stage 1: empty LISN, bench without the prototype in working mode, bench with the prototype. Both channels, positive and negative. PC switched off. RBW 10 kHz, max hold over 3–4 sweeps, marker on the trace maximum | Spectra of the prototype that stand clear of the bench background, with the correction of 15.8 dB applied (or the value from A5) | Open |
| B3 | Decide whether a filter between the prototype and the load is needed | From the B2 spectra: compare the bench without the prototype in working mode with the empty LISN | If the load and its leads still add to the spectrum: an inductor of several tens of microhenries and capacitors to ground on both sides, outside the measured port. If not: no filter, and that is recorded | Open |
| B4 | Compare with the limits as a reference | Table 6 of the standard, peak detector, classes 1–5 | A statement of where the prototype stands relative to the classes, with the reminder that this bench gives relative comparisons, not compliance results | Open |
| B5 | Dataset format and first processing code | Data are taken with the oscilloscope, so that both paths are recorded at the same time and under the same conditions. The format of the raw files and of the index of captures is fixed first. A script applies the corrections, computes the spectra and plots them against the limits | Raw data, the index and the code in this folder, so that every figure can be reproduced from them and the data can be used by others | Open |

### Order of the tests

The work goes through the claims C1–C5 of the [root README](../README.md) one after another. The first topology is
the buck converter on the cell board.

| Claim | What is varied | Expected result |
|---|---|---|
| C1, three zones of the spectrum (0.15–3, 3–16, 16–30 MHz) | Switching frequency; gate resistor, that is, the switching edge time | The boundaries of the zones move with these parameters. The author expects this almost with certainty, since the zones follow from the edges of the chosen switches; the measurement is to show by how much, and whether the three-zone description survives in a form tied to the parameters instead of fixed frequencies |
| C4, snubbers | The same operating point with and without a snubber | The difference between the two spectra by band, and the difference in efficiency |

Claims C2, C3 and C5 follow in later tests; C5 needs the bridge topologies on two cell boards. Part C of this stage
works towards C3: it shows which part of the spectrum is common mode and which is differential mode.

### Dataset

Apart from checking the claims, every measurement goes into a dataset that is published in the open: raw captures
together with the conditions under which they were taken. A capture without its conditions is not added.

| For each capture | Recorded |
|---|---|
| What was measured | Board, topology, what is fitted (switches, diode, inductor, snubber, gate resistor) |
| Operating point | Input voltage, load current, switching frequency, duty cycle |
| Bench | Geometry of the leads, earthing state, which LISN channel on which oscilloscope channel, limiter in or out |
| Instrument | Oscilloscope settings: sampling rate, record length, vertical scale, coupling, bandwidth limit |
| Reference captures | The empty LISN and the bench without the prototype taken in the same session |
| Processing | Corrections applied and the version of the code |

The format of the files and of the index is fixed in task B5, before the first capture is taken.

## Part C. Separating the two kinds of interference

The interference on the two lines consists of a part that is the same on both lines (common mode) and a part that is
opposite on them (differential mode). The spectrum analyser on one LISN channel sees their sum. With the oscilloscope
on both LISN channels at once, half the sum of the two voltages gives the common-mode part and half the difference
gives the differential-mode part.

Task numbers in this part start with S, so as not to be confused with the claims C1–C5.

| No. | Task | Method | Expected result | Status |
|---|---|---|---|---|
| S1 | Set up the two-channel path | Both BNC outputs of the LISN through the two limiter channels to two oscilloscope channels, each with a 50 Ω feed-through load; cables of equal length | Path assembled and described. Stage 1 gives the starting point: LISN channels agree within 0.15 dB in S21, limiter channels within 0.03 dB; the input capacitance of the oscilloscope channels may differ by 1–2 pF | Open |
| S2 | Measure how well the path separates the two parts | The same signal applied to both output terminals tied together: whatever appears in the difference is the error of the path. Then a signal applied between the two terminals: whatever appears in the sum is the error | Two numbers by frequency: how far a pure common-mode signal leaks into the difference and a pure differential-mode signal into the sum. They set the limit of what S3 can show | Open |
| S3 | Separate the interference of the test circuit | Both channels recorded at once; sum and difference computed by the code of B5; spectra of both parts | Spectra of the common-mode and differential-mode parts of the same operating point as in B2, and a statement of which part dominates in which band, within the limit found in S2 | Open |
| S4 | Compare with the spectrum analyser | The same operating point measured with the TinySA on each channel | Agreement between the oscilloscope spectra and the analyser spectra stated, with the differences explained or recorded as open | Open |


## Rules carried over from stage 1

- The PC is switched off during measurements. In stage 1 its comb reached 61 dBµV at the LISN port and exceeded
  the class 3–5 limits at 26–28 MHz.
- The marker is put on the trace maximum, and max hold is on for 3–4 sweeps: a single trace at RBW 10 kHz
  jumps by 5–10 dB from sweep to sweep.
- The NanoVNA calibration is recalled and checked with the 50 Ω standard before each object.
- Everything that goes wrong is written into the error log of this stage.

## Still open from stage 1 and not planned here

None. The three items that stage 1 left open (earthing of the plate, leakage between the LISN channels, correction in the
lower decade) are covered by tasks A1–A6. Task A6 also matters for Part C: leakage between the channels limits the separation.
