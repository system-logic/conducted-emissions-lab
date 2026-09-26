# NanoVNA-H4 calibration

Instrument: NanoVNA-H4 rev 4.4 (ZeeTK mixer, hugen firmware based on DiSlord).

## 1.1. Procedure

Full reset (`CONFIG → EXPERT SETTINGS → MORE → CLEAR CONFIG → CLEAR ALL AND RESET`),
restore `MODE = ZEETK` (a setting for the hardware revision, erased by the reset), `SAVE CONFIG`.

| Parameter | Value |
|---|---|
| START / STOP | 10 kHz / 50 MHz |
| Points | 401 (step ≈125 kHz) |
| IF BANDWIDTH | 1000 Hz (during calibration the firmware narrows it to 100 Hz by itself) |
| POWER | AUTO |
| DATA SMOOTH / TRANSFORM | off |
| TRACE 1 / 2 / 3 / 4 | S11 LOGMAG / S21 LOGMAG / S11 SMITH / off |

S11 is the reflection measured at port 1; S21 is the transmission from port 1 to port 2.

Calibration: OPEN, SHORT, LOAD, ISOLN, THRU at the end of the PORT 1 cable → `DONE → SAVE → slot 0`.
Sign of a valid calibration: on the left, a capital `C0` and the letters `D R S T X`. A lowercase `c`
means the range was shifted after calibration — redo it.

## 1.2. Check

| Check | Result | Criterion |
|---|---|---|
| 50 Ω standard, S11 LOGMAG | −50.9…−52 dB across the whole band | below −40 |
| 50 Ω standard, Smith chart | point in the centre | centre |
| OPEN | right edge of the Smith chart, ≈0 dB | right edge |
| SHORT | left edge of the Smith chart, ≈0 dB | left edge |
| Cables through a barrel adapter, S21 | passed (value not recorded) | 0 dB ±0.1 |
| Cables disconnected, S21 | passed (value not recorded) | below −70 dB |

In practice: anything below about −50 dB in S11 is instrument noise, not a property of the object.

## 1.3. When the calibration is no longer valid

START/STOP/points were changed; a cable was replaced, moved or shifted; an adapter was added;
POWER was changed; several hours have passed; the temperature has changed noticeably.
Before each object: `RECALL → slot 0`, check with the 50 Ω standard (worse than −35 dB above 50 kHz — recalibrate).
