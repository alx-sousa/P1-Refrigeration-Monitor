# Rev B design decisions

## 1. Retrofit rather than refrigerator control

The prototype monitors refrigerator condition externally. It does not switch the compressor and does not replace the refrigerator's existing control electronics.

This keeps the first product scope focused on observation, local alerting and future event interpretation.

## 2. Four-layer PCB

Rev B uses a four-layer stack:

- L1 Top — components/signals/local power loops;
- L2 GND_PLANE — continuous ground reference;
- L3 PWR_SIG — logic/secondary power distribution;
- L4 Bottom — secondary signals/crossovers.

The main reasons are return-path continuity, reduced routing congestion and a more controlled environment for USB, SPI, RF-adjacent routing and switching power stages.

## 3. Main components on one side

Keeping the principal components on one side supports future PCBA, inspection and rework. It also helps reserve the opposite mechanical volume for battery/enclosure integration.

## 4. One external USB-C port

One connector is used for:

- external power;
- battery charging;
- native ESP32-C6 USB Serial/JTAG programming and console/service.

Internal UART access remains recovery-only.

## 5. Battery-backed local operation

The hardware includes a 1S LiPo power architecture because loss of external power should not immediately remove monitoring capability.

No public battery-runtime claim will be made until measured on the fabricated system.

## 6. Switched low-duty-cycle loads

TPS22917 load switches are used where useful to avoid permanent consumption from blocks that do not need to remain active continuously, including battery measurement, probe power and TFT logic power.

## 7. Local alarm independent of remote connectivity

The buzzer is controlled locally by the MCU. Future cloud/app availability is not intended to be a prerequisite for basic local alerting.

## 8. RTC with independent backup

The RTC is retained to support time-stamped events across main-rail sleep/off periods.

## 9. External temperature probe

The temperature sensing element is separated from the exterior electronics. This simplifies retrofit installation and keeps the main PCB outside the refrigerated volume while allowing a dedicated probe to be placed where temperature is relevant.

## 10. Product-oriented display integration

The 1.69-inch IPS panel is integrated through a specific FPC connector and dedicated backlight supply rather than through a hobby display module. This reduces module dependence and supports a cleaner enclosure architecture.

## 11. RF-aware placement

The ESP32-C6 antenna region is kept close to the PCB boundary and away from avoidable routing/metal. Final validation must still be performed with the real display, battery and enclosure.

## 12. Fail-safe reset behavior

Charging, backlight, switched sensors and externally visible outputs should start in defined states during reset. Hardware defaults and firmware initialization must work together rather than assuming GPIOs are immediately controlled.

## 13. DRC is not validation

A DRC-clean PCB verifies layout rules, not real electrical function. Rev B will only gain functional claims after fabrication, measurement and documented bring-up.
