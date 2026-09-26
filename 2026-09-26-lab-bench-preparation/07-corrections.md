# Corrections file

| Element | Correction | Accuracy |
|---|---|---|
| LISN attenuator (terminal → BNC) | 9.7 dB | ±0.5 (worse at the bottom of the band) |
| Limiter | 6.1 dB | ±0.05 |
| **Total to add to TinySA readings** | **15.8 dB** | ±0.5 |

Reading on the screen + 15.8 dB = voltage at the port of the standard LISN, which
is compared with the limits.

Bench floor (step 4, at the port): 41 dBµV at 150 kHz, 16–21 dBµV above 1 MHz.
Working background (step 9, at the port): ≈56 dBµV at 150 kHz, 21–26 dBµV above 10 MHz.

Sources: LISN correction — [05-lisn.md, 5.4](05-lisn.md#54-path-correction);
limiter — [03-limiter.md, 3.3](03-limiter.md#33-conclusions);
floor and background — [06-background-protocol.md](06-background-protocol.md).
