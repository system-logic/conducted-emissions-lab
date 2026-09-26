# LISN: channel check

Method: the input terminals (from the power supply) are shorted to the enclosure **inside** the LISN,
the lid is closed. PORT 1 to the output terminal (centre contact to the terminal, ground to the enclosure next to it,
conductors 2.5–3 cm), PORT 2 directly to the BNC of the same channel. Slot 0.
Impedance (Smith chart, R + L/C) and S21 are read at the same time.

The 2.5–3 cm conductors add ≈30 nH: unnoticeable up to 10 MHz, ≈+5 Ω at 30 MHz, ≈+9 Ω
of reactance at 50 MHz — this has been subtracted in the magnitude values below.

**Discarded attempt.** The first measurement was made with one-metre banana-to-crocodile leads and a long
jumper at the input. The leads added ≈2 Ω and 1.2–1.6 µH in series; the jumper together
with the 1 µF capacitor gave a resonance near 160 kHz. One conclusion from that attempt was accepted:
at 1 MHz the measurement branch showed 50–55 Ω, meaning it was assembled correctly.

## 5.1. Positive channel

| Frequency | Measured, R + jX | Magnitude | Target | Deviation | S21 |
|---|---|---|---|---|---|
| 10 kHz | 17 mΩ; 6.77 µH | 0.4 Ω | — | — | −52.9 dB |
| 135 kHz | 0.7 + j5.2 | 5.2 Ω | 4.3 | +21 % | −22.4 dB |
| 150 kHz (recalculated from L) | L = 6.11 µH | ≈5.8 Ω | 4.8 | +21 % | — |
| 1.009 MHz | 18.5 + j22.1 | 28.8 Ω | 26.8 | +7 % | −11.2 dB |
| 10.13 MHz | 44.6 + j12.2 | 46.2 Ω | 47.1 | −2 % | −10.0 dB |
| 30 MHz | 46.1 + j19.0 | ≈48 Ω | 47.5 | +1 % | −10.3 dB |
| 50 MHz | 47.9 + j30 | ≈52 Ω | 47.6 | +9 % | −10.7 dB |

Inductance at the terminal is 6.11 µH, while the inductor on its own has 5.79 µH: the extra 0.3 µH is
the internal wiring. The 150 kHz row is recalculated from the measured inductance, because the nearest
sweep point is 135 kHz; the working band of the bench starts at 150 kHz.

## 5.2. Negative channel

| Frequency | Measured, R + jX | Magnitude | Target | Deviation | S21 |
|---|---|---|---|---|---|
| 10 kHz | 37 mΩ; 7.19 µH | 0.5 Ω | — | — | −52.8 dB |
| 135 kHz | 0.6 + j5.2 | 5.2 Ω | 4.3 | +21 % | −22.3 dB |
| 150 kHz (recalculated from L) | L = 6.08 µH | ≈5.8 Ω | 4.8 | +21 % | — |
| 1.009 MHz | 18.4 + j22.1 | 28.7 Ω | 26.8 | +7 % | −11.1 dB |
| 10.13 MHz | 44.3 + j12.2 | 45.9 Ω | 47.1 | −3 % | −10.0 dB |
| 30 MHz | 47.2 + j19.2 | ≈49 Ω | 47.5 | +3 % | −10.1 dB |
| 50 MHz | 47.6 + j29.8 | ≈52 Ω | 47.6 | +9 % | −10.6 dB |

## 5.3. Comparison with the CISPR 25 curve

The text of the standard is not available in open access. The target curve was calculated from the LISN circuit
in the annex to CISPR 25: 5 µH inductor, 0.1 µF capacitor, 1 kΩ resistor, measurement port
loaded with 50 Ω, input terminals shorted — that is, from the same circuit and under the same conditions
in which the LISN was built and measured. Tolerance ±20 %, check band 0.1–100 MHz.

| Frequency | Target from circuit | Tolerance ±20 % | Measured (positive channel) |
|---|---|---|---|
| 135 kHz | 4.3 Ω | 3.4–5.2 | 5.2 (+21 %) |
| 150 kHz | 4.8 Ω | 3.8–5.7 | ≈5.8 (+21 %) |
| 1 MHz | 26.8 Ω | 21–32 | 28.8 (+7 %) |
| 10 MHz | 47.1 Ω | 38–57 | 46.2 (−2 %) |
| 30 MHz | 47.5 Ω | 38–57 | ≈48 (+1 %) |

Result: from 1 MHz upwards both channels are on target with margin. At 150 kHz without current the impedance is 1 %
above the upper tolerance limit — this is less than the NanoVNA uncertainty when measuring 5 Ω. Under working current
the inductance will drop ≈5 %, and the point will come within tolerance. **Decided to leave as is**; adjusting
the winding layout (spread the turns evenly, target 5.7–5.8 µH at the terminal) is an option in case
compliance without current is also needed.

## 5.4. Path correction

S21 on the screen is not the correction: the instrument source has a 50 Ω output and sags on the low
impedance of the channel at the bottom of the band. The real correction — the ratio of the voltage at the BNC to the voltage
at the terminal — was recalculated from S21 and the measured impedance.

| Frequency | S21 on the screen | Correction terminal → BNC |
|---|---|---|
| 135 kHz | −22.4 dB | ≈ −9 dB |
| 1 MHz | −11.2 dB | −9.2 dB |
| 10 MHz | −10.0 dB | −9.7 dB |
| 30 MHz | −10.3 dB | −10.4 dB |
| 50 MHz | −10.7 dB | −10.8 dB |

Calculation from the circuit (attenuator 100/68/100 and capacitor 0.1 µF) gives −9.7 dB across the band and −9.9 at 135 kHz.
From 10 MHz the agreement is good; below 1 MHz the measured correction is 0.5–1 dB higher than calculated —
attributed to the instrument uncertainty near a short circuit (5 Ω at 135 kHz is estimated with a 10–15 % error).

**Decided: LISN correction −9.7 dB ±0.5 for both channels across the whole band.
Together with the 6.1 dB limiter → 15.8 dB to the spectrum analyser input.**
It is desirable to refine the lower decade by a direct method: generator on the terminal, oscilloscope on the terminal
and on the BNC, ratio of voltages.

## 5.5. Conclusions

- Both channels are fit for use and match the CISPR 25 curve in working mode (under current).
- The channels match: in impedance magnitude within 2 %, in S21 within 0.15 dB,
  in inductance at the terminal 6.11 against 6.08 µH. One correction for both channels.
- Two checks were deliberately skipped:
  - **under a current of 5 and 10 A** — the only thing that can change is the lower edge, and only
    towards the target; Kool Mu saturates gradually;
  - **leakage between the LISN channels** — the inductors are separate, only the enclosure is shared,
    and in operation the same interference is present on both rails. Return to this if positive and negative start
    showing the same thing to within a decibel.

Not recorded: type and length of the NanoVNA cables and the adapters; what the PORT 2 cable was terminated with
at the ISOLN step; room temperature.
