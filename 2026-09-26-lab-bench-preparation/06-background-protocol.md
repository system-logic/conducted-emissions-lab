# Bench background measurement protocol (25 September)

## 6.1. Conditions

| Parameter | Value |
|---|---|
| Analyser | TinySA Ultra, RF input, attenuation 0 dB, dBµV, 10 dB/div (−10…+90) |
| Band | 150 kHz – 30 MHz, 2 MHz/div |
| RBW (resolution bandwidth) | 10 kHz (CISPR norm — 9 kHz); at step 0 it was 300 kHz |
| Sweep | ≈8 s; max hold was not turned on, single trace |
| Path | output terminal → LISN (positive channel) → BNC → limiter → TinySA |
| Correction | steps 0–3: +9.7 dB (no limiter); steps 4–13: +15.8 dB |
| Load | electronic load, leads to the terminal ≈1 m; control and fans powered from a mains transformer with a linear regulator |
| Source | laboratory power supply, up to 6.5 A |
| Instruments | oscilloscope, TinySA, NanoVNA — all on their own batteries |
| Surroundings | PC a few metres away; load transformer, power supply and PC on the same socket group |
| Reference plane | the plate on the bench was used as a common conductor, **not connected to protective earth** |

The plate not being earthed is a deliberate state of the bench for the first video.
This was done deliberately, in order to close the first series. The second series will begin with a more
thorough preparation of the bench itself: the background check without a prototype will be repeated,
this time with full earthing (see [6.6](#66-rework-plan), item 2).

Levels at 150 kHz were read from the screenshots by the grid, accuracy ≈5 dB. The marker on the screenshots was
on the hump in the middle of the band, not on the trace maximum.

## 6.2. Summary table

Levels in dBµV on the screen (without correction).

| Step | State | Screen, 150 kHz | Hump / comb | Floor above 10 MHz |
|---|---|---|---|---|
| 0 | Load 7 A, RBW 300 kHz, no limiter | ≈35 | comb merged, 30–50 | 20–30 |
| 1 | Load connected, its power off, power supply terminals disconnected | ≈40 | comb 20–40 | 5–15 |
| 2 | Power supply terminals connected | ≈40 | comb 20–45 | 5–15 |
| 3 | Power supply on, 6 A | ≈40 | comb 25–40 | 5–10 |
| 4 | Empty LISN: neither power supply nor load | ≈25 | none | 0–5 |
| 5 | Load leads connected, load power off | sharp lines up to 40 | comb 10–30 | 0–5 |
| 6 | Load control and fans on | ≈40 | comb 20–40 | 5–15 |
| 7 | Power supply connected, off | ≈45 | comb 20–45 | 5–15 |
| 8 | Power supply on, 6.5 A | ≈45 | comb 20–45 | 10–15 |
| 9 | PC switched off (the rest as in 8) | ≈40 | hump 37 at 8 MHz | 5–10 |
| 10 | Load current 0 (by the regulator) | ≈35 | hump 27 at 8 MHz | 5–10 |
| 11 | Power supply off, terminals connected | ≈35 | hump 23 at 15 MHz | 0–5 |
| 12 | Power supply terminals disconnected | ≈40 | hump 17 at 17 MHz | 0–5 |
| 13 | Load power off, leads connected | ≈40 | none | 0–5 |

Screenshots: 14 files, one per step (step numbering matches the table), see [tinysa-screenshots/](tinysa-screenshots/).

## 6.3. Interference sources

| Source | Evidence | Contribution |
|---|---|---|
| Load leads (≈1 m) and its enclosure acting as an antenna | step 13 against step 4: everything off, the only difference is the leads; the resonance wanders over 8–17 MHz | +10–15 dB at 150 kHz; determines the spectrum shape 150 kHz – 5 MHz |
| Load fans and control | step 12 against 13; noise 150 kHz – 2 MHz | a few dB at the bottom |
| Personal computer | step 8 against 9: the comb of equally spaced lines at 10–30 MHz disappears | the whole comb, 20–45 on the screen (36–61 at the port) |
| Current and power supply | steps 9–12 | within the reading accuracy |

## 6.4. What is justified

- LISN, limiter, cable and analyser: bench floor ≈25 dBµV at 150 kHz
  and 0–5 dBµV above 1 MHz on the screen (step 4) → 41 and 16–21 dBµV at the standard port.
- Laboratory power supply: switching on, switching off and current up to 6.5 A add nothing noticeable.

## 6.5. What this means for measurements

CISPR 25 limits, voltage method, peak detector, dBµV at the port of the standard LISN
(GOST CISPR 25—2023 (identical to CISPR 25:2021), Table 6, RBW 9 kHz). The standard gives these values as examples:
the class is agreed between the customer and the supplier.

| Band | Class 1 | Class 2 | Class 3 | Class 4 | Class 5 |
|---|---|---|---|---|---|
| 150–300 kHz | 110 | 100 | 90 | 80 | 70 |
| 0.53–1.8 MHz | 86 | 78 | 70 | 62 | 54 |
| 5.9–6.2 MHz | 77 | 71 | 65 | 59 | 53 |
| 26–28 MHz | 68 | 62 | 56 | 50 | 44 |

In these bands quasi-peak limits are 13 dB lower, average limits 20 dB lower.

Corrected on 2026-10-01. The first version of this table was quoted from memory with a 10 dB step
between classes in every band; in the standard the step is 10 dB only at 150–300 kHz
(see [error log](08-errors.md)). The margin above 10 MHz below was recalculated accordingly.

In the working state (step 9, PC off) the background is ≈40 dBµV on the screen at 150 kHz,
that is **≈56 dBµV at the standard port against a class 5 limit of 70 — a margin of 14 dB**.
Above 10 MHz the floor is 5–10 on the screen (21–26 at the port) against a class 5 limit of 44 at 26–28 MHz:
a margin of 18–23 dB for class 5, and more for the other classes.

The comb from the PC (up to 45 on the screen, 61 at the port) exceeds the limits of classes 3–5
at 26–28 MHz (56, 50 and 44).
This is the only source without whose removal measurement is impossible.

## 6.6. Rework plan

1. **Switch the PC off during measurements — mandatory.**
2. Geometry according to the method (desirable, for repeatability):
   the plate connected to protective earth with a 2.5 mm² cable; the LISN and load enclosures
   bonded to the plate with short wide straps (or pressed against it); leads from the terminal to the prototype
   20–30 cm, pressed against the plate. Check: steps 4 and 13, difference at 150 kHz less than 5 dB;
   step 4 must not get worse after earthing, otherwise a mains filter at the bench inlet is needed.
   **Postponed to the second series: the first video shows results without the plate earthed.**
3. A filter between the prototype and the load (based on the first prototype measurements): an inductor
   of several tens of microhenries and capacitors to ground on both sides. It is outside the measured
   port, there are no requirements for it.
4. For each prototype measurement, take three spectra: empty LISN, bench without the prototype
   in working mode, bench with the prototype.
5. Turn on max hold for 3–4 sweeps: a single trace at RBW 10 kHz
   jumps by 5–10 dB from sweep to sweep. Put the marker on the trace maximum.
