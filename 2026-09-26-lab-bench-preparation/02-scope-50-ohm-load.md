# 50 Ω feed-through load for the oscilloscope

The Micsig TO1104 has no 50 Ω input, so the load is external. Conditions: oscilloscope on battery,
other channels and USB disconnected, DC coupling.

Input model: 50 Ω in parallel with the specified 14.5 pF (1 MΩ is negligible next to 50 Ω).

| Frequency | S11 measured | S11 calculated |
|---|---|---|
| 1 MHz | ≈ −40 dB | −52.8 |
| 10 MHz | −32 dB | −32.8 |
| 30 MHz | −23 dB | −23.3 |
| 50 MHz | −19 dB | −18.9 |

Capacitance from the marker at 10 MHz: **14.5 pF**, matches the specification.
The −40 dB residual at 1 MHz is set by the resistor deviating by about 1 Ω from 50 (a normal tolerance).

Effect on measurements: with a matched source, the capacitance lowers the voltage
by 0.02 dB at 30 MHz and 0.06 dB at 50 MHz → in the uncertainty budget as a line of **less than 0.1 dB**.

Not recorded: values for the load on its own (without the oscilloscope) by frequency;
the oscilloscope channel number. Capacitances of other channels may differ by 1–2 pF.
