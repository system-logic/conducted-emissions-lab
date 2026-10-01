# LISN inductor

Core: **Magnetics 0077109A7**, Kool Mu (Sendust), 58 × 36 × 14 mm,
permeability 125, specified AL = 156 nH/turn² ±8 %, magnetic path length 143 mm.
Marking on the core: "197001 77109A7".
(Early notes mentioned "black toroid Ø100 mm, path length ≈25 cm" — this is wrong.)

Winding: 6 turns, wire 5 × Ø0.6 mm bare copper in a common heat-shrink sleeve, cross-section ≈1.4 mm²,
resistance ≈6 mΩ (at 10 A a drop of 60 mV, heating 0.6 W). The turns are fixed with nylon cable ties.

Marker format: Smith chart, R + L/C (series model), PORT 1 only.

| Frequency | 5 turns: L | 5 turns: R | 6 turns: L | 6 turns: R |
|---|---|---|---|---|
| 10 kHz | 3.7 µH | 57 mΩ | 6.2 µH | 70 mΩ |
| 135 kHz | 4.09 µH | 20 mΩ | 5.79 µH | 48 mΩ |
| 1.009 MHz | 3.95 µH | 2.6 Ω | 5.57 µH | 3.9 Ω |
| 10.13 MHz | 2.5 µH | 104 Ω | 3.52 µH | 150 Ω |
| 30 MHz | 0.99 µH | 307 Ω | 1.19 µH | 460 Ω |

The main value is at 1 MHz (the reactance of the coil there is close to 50 Ω, where the instrument is most accurate).
The 10 kHz point is approximate (reactance 0.2–0.4 Ω).

## Conclusions

- 6 turns give 5.6–5.8 µH — within the chosen target of 5.5–6 µH without current (margin for the drop under current).
  With 5 turns (4.0 µH) the lower edge of the LISN curve would fall outside the tolerance.
- The ratio of inductances 6/5 turns = 1.41 against the theoretical 1.44 (square of the number of turns).
  Measured AL 155–161 against the specified 156 — an independent check of the instrument and the method.
- No self-resonance up to 30 MHz. The drop in L and the growth of losses above 1–2 MHz are a property of Kool Mu 125µ;
  for the LISN this is not harmful (the losses damp parasitic resonances).
- Calculation of the drop under current: field at 6 turns and 10 A ≈5.3 Oe; from the typical material curve
  ≈95 % of the permeability is retained → drop ≈5 % (≈2 % at 5 A). No direct check under current was made.
- Checked on 2026-10-01 against the 0077109A7 datasheet (Magnetics, revision 6/7/2013), the "Typical DC Bias
  Performance" curve: at 60 ampere-turns AL ≈148 nH/turn² (≈95 % of 156), at 30 ampere-turns ≈152.5 (≈98 %) —
  the calculation above is confirmed. The curve is typical, not guaranteed; the guaranteed minimum in the datasheet
  is 80 % at 10.7 ampere-turns/cm and 50 % at 27.8 ampere-turns/cm. The datasheet also confirms AL = 156 ±8 %,
  path length 143 mm and the dimensions (uncoated 57.20 × 35.60 × 14.0 mm; coated limits 58.04 max × 34.74 min × 14.9 max).
- For the future: 50 µH on this core = 18 turns; at 10 A the field is ≈16 Oe and the drop ≈20 %
  (datasheet curve at 180 ampere-turns: ≈82 % retained, drop ≈18 %) —
  a mains version needs a core with permeability 60 or 26, or a lower current.

The inductor on its own was not re-measured after the turns were fixed with cable ties. The channel check
of the LISN ([05-lisn.md](05-lisn.md): 6.11 and 6.08 µH at the terminals) was made with the ties in place
and the enclosure closed, so the inductance after fixing is covered by that measurement.

Not recorded: which inductor is in which channel (the second inductor was not measured separately).
