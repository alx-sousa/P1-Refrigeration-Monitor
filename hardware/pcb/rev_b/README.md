# PCB Rev B — 4-layer hardware milestone

**Status: design complete at PCB milestone · pre-fabrication**

Rev B is the current product line. Rev A is historical study material and should not be used to infer current component choices.

## Board intent

Approximate current footprint: **52 × 34 mm**.

The PCB combines:

- ESP32-C6 MCU/RF;
- USB-C power/charging/programming;
- LiPo charger and power path;
- main buck-boost rail;
- RTC backup;
- switched battery measurement;
- external DS18B20 probe interface;
- Hall door sensing;
- 1.69-inch TFT interface and backlight supply;
- local buzzer output.

## Stack

```text
L1  TOP        Components + signals + compact local power loops
L2  GND_PLANE  Continuous ground reference
L3  PWR_SIG    VDD_LOGIC / secondary power distribution
L4  BOTTOM     Secondary signals / crossovers
```

## Current manufacturing status

The PCB layout milestone is complete, but fabrication is intentionally gated by:

- USB 90 Ω differential-impedance closure against the real stackup;
- final DRC after repour;
- Gerber viewer review;
- BOM / PnP verification;
- power-off strategy closure;
- final TPS63802 feedback tolerance review;
- battery NTC / connector validation.

Gerbers and PCBA manufacturing files should be added here only after those gates are closed.
