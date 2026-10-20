# Rev B validation plan

This document defines the next validation milestones. No item below should be reported as passed until measured on fabricated hardware.

## Pre-fabrication gates

| Gate | Acceptance objective |
|---|---|
| USB differential impedance | Close 90 Ω differential geometry using the actual PCB manufacturer's stackup |
| Global DRC | Fatal = 0, Error = 0; every remaining warning reviewed and justified |
| Unrouted nets | 0 |
| Gerber viewer | Independently inspect copper, solder mask, paste, silkscreen, board outline, PTH and NPTH |
| BOM / PnP | Verify MPN → footprint → orientation for ICs/connectors |
| TPS63802 feedback | Close resistor values/tolerance against target VDD_LOGIC |
| Battery pack NTC | Confirm R25/Beta and charger compatibility |
| Battery connector pinout | Physically confirm BAT+/NTC/GND |
| Display FPC | Confirm insertion/orientation with the real panel |
| Physical ON/OFF strategy | Finalize product-level power-off behavior |

## Electrical bring-up sequence

1. Visual inspection under magnification.
2. Check critical rails for shorts to GND.
3. Power from a current-limited USB supply with the battery disconnected.
4. Verify protected VBUS/system path.
5. Verify charger/power-path idle state and fail-safe CE# behavior.
6. Verify VDD_LOGIC from the TPS63802.
7. Check MCU boot/reset/USB enumeration.
8. Verify I²C devices individually.
9. Verify switched load rails individually.
10. Validate battery-measurement divider against a DMM.
11. Connect the selected battery pack only after NTC/pinout validation.
12. Characterize charging current and component temperatures conservatively.
13. Integrate the display at minimum backlight duty.
14. Integrate the DS18B20 field probe.
15. Verify Hall switching with the intended magnet/enclosure geometry.
16. Verify buzzer output and interactions with Hall/RF/display.

## Measurement records

Each bench test should capture:

- test ID and date;
- PCB revision / assembly identifier;
- firmware commit;
- instrument model;
- supply voltage/current limit;
- ambient condition;
- procedure;
- acceptance criterion;
- measured result;
- evidence link/photo/plot;
- pass/fail;
- resulting design action.

## Performance validation after bring-up

### Power / battery

- idle/sleep current;
- active display current;
- Wi-Fi TX peaks;
- probe-measurement current;
- buzzer/backlight simultaneous load;
- battery runtime under a defined usage profile;
- charge current and thermal rise.

### Thermal

- buck-boost temperature;
- charger temperature during charge;
- backlight boost temperature;
- enclosure internal temperature under representative ambient conditions.

### RF

- RSSI/throughput with battery and display installed;
- influence of enclosure material;
- influence of refrigerator placement and nearby metal;
- reconnect behavior.

### Temperature probe

- comparison against a reference thermometer/instrument;
- cable/connector robustness;
- response time in the intended placement;
- effect of repeated probe power cycling.

### Door sensing

- switching distance/repeatability;
- tolerance to mechanical misalignment;
- immunity to buzzer/backlight activity;
- behavior near enclosure screws/metal.

### Field pilot

Field validation should record events rather than jump directly to a certification claim. Examples:

- normal door opening;
- prolonged door-open event;
- temperature recovery after opening;
- external power interruption;
- battery-backed operation;
- connectivity outage;
- abnormal temperature excursion.
