# Open questions

- Earthing the reference plate — the second series, which begins with a repeat of the background check without a prototype, with full earthing.
- Leakage between the LISN channels (not measured; low priority).
- Refinement of the correction in the lower decade by a direct method (generator + oscilloscope) — postponed to the second video.
- Whether a 1 kΩ resistor is fitted on the measurement boards of the LISN (the standard circuit has it; the build sketch does not) — to be confirmed by inspection.
- Two doubtful rows in the limiter tables (channel A, 30 MHz; channel B, 10 kHz).

## Closed

- Check of the target curve and the limits against the text of CISPR 25 — done on 2026-10-01 against GOST CISPR 25—2023 (identical to CISPR 25:2021): the LISN curve is confirmed ([05-lisn.md, 5.3](05-lisn.md#53-comparison-with-the-cispr-25-curve)), the limits were corrected ([06-background-protocol.md, 6.5](06-background-protocol.md#65-what-this-means-for-measurements)).
- Check of the Kool Mu drop against the 0077109A7 datasheet — done on 2026-10-01: ≈95 % retained at 60 ampere-turns, the calculation is confirmed ([04-lisn-inductor.md](04-lisn-inductor.md#conclusions)).
- Check of the LISN under a current of 5 and 10 A — closed on 2026-10-01 by the core datasheet; a direct check is not planned.
- Diode type in the limiter — identified on 2026-10-01 as BAS316 from the package, the marking A6 and the NXP datasheet ([03-limiter.md](03-limiter.md#34-labelling-error)); the manufacturer is not established.
- Inductance of the inductors after fixing with cable ties — covered by the LISN channel check, which was made with the ties in place and the enclosure closed ([05-lisn.md](05-lisn.md)).
