# Error and correction log

This section is a substantive part of the material, not an appendix.

| Error | How it was found | Correction |
|---|---|---|
| The "input" and "output" labels on the limiter were swapped | S11 at 10 kHz differed by exactly 12 dB (double pass through the 6 dB attenuator) | Labels corrected, tables rearranged |
| The thyristor driver had a KT3107 (PNP) instead of an NPN | The circuit "inverted": with the base near ground the thyristor turned on | Replaced with KP501B (field-effect transistor), 330 Ω from its source to the thyristor gate, 1 kΩ from the gate to ground |
| First LISN measurement with one-metre banana-to-crocodile leads | Impedance kept rising without stopping (310 Ω at 30 MHz), the residual matched 2 Ω + 1.4 µH | Re-measured with short 2.5–3 cm conductors |
| TinySA grid reading error of 35 dB | The marker showed 36.6 dBµV, while the estimate from the grid gave 75 | All levels re-read from the screenshots, conclusions rewritten |
| Core dimensions in early notes (Ø100 mm, magnetic path 25 cm) | Marking 0077109A7 and physical measurement: 58 × 36 × 14 mm, path 14.3 cm | Inductance drop under current recalculated |
| First channel isolation reading −90…−100 dB | The instrument sweep had stopped, the picture was frozen | Re-measured: no worse than −85 dB |
| CISPR 25 limits quoted from memory with a 10 dB step between classes in every band | Check against GOST CISPR 25—2023, Table 6: the step is 10 dB only at 150–300 kHz, 8 dB at 0.53–1.8 MHz, 6 dB at 5.9–6.2 and 26–28 MHz | Limits table replaced, margin above 10 MHz recalculated: 18–23 dB for class 5 instead of "no margin" |

Details: limiter labelling — [03-limiter.md, 3.4](03-limiter.md#34-labelling-error);
banana-to-crocodile leads — [05-lisn.md](05-lisn.md) (discarded attempt);
core dimensions — [04-lisn-inductor.md](04-lisn-inductor.md);
channel isolation — [03-limiter.md, 3.3](03-limiter.md#33-conclusions);
CISPR 25 limits — [06-background-protocol.md, 6.5](06-background-protocol.md#65-what-this-means-for-measurements).
