# 1S Li-Ion Powerbank with TP4056 Charger and BMS

## Overview

This project is a single-cell (1S) lithium-ion powerbank designed for 3.7V Li-Ion batteries (4.2V fully charged).

The board integrates:

* Li-Ion linear charging circuit (TP4056)
* Battery Management System (BMS) for protection
* PCB designed in KiCad
* Local symbol and footprint libraries included in repository

The design is intended for educational use, prototyping, and small-scale DIY applications.

---

## System Architecture

The powerbank consists of:

1. Li-Ion Cell (1S, 3.7V nominal)
2. TP4056 charging IC (CC/CV charger)
3. Protection circuit (BMS)
4. Output stage (battery output terminals / USB if implemented)

---

## Battery Specification

* Battery type: Lithium-Ion (Li-Ion)
* Configuration: 1S (single cell)
* Nominal voltage: 3.7V
* Fully charged voltage: 4.2V
* Recommended cell type: 18650
* Recommended capacity: 2000–3500mAh

⚠ Only use high-quality and undamaged cells.

---

## Charging Circuit – TP4056

The design uses the TP4056 linear Li-Ion charger IC.

Charging method:

* CC/CV (Constant Current / Constant Voltage)
* Charge termination voltage: 4.2V ±1%
* Programmable charge current via RPROG resistor
* Typical charge current: up to 1A (depends on RPROG value)
* Input voltage: 5V (USB supply)

Important notes:

* The TP4056 is a linear charger and dissipates power as heat.
* Provide sufficient copper area under the IC for thermal dissipation.
* High charge current increases temperature significantly.

Charge status pins:

* CHRG – charging indicator
* STDBY – charge complete indicator

---

## BMS Protection Features

The Battery Management System provides:

* Overcharge protection
* Overdischarge protection
* Overcurrent protection
* Short-circuit protection

Typical protection thresholds (may vary depending on protection IC used):

* Overcharge cutoff: ~4.25V
* Overdischarge cutoff: ~2.5–2.7V
* Overcurrent threshold: depends on MOSFET and design

---

## Electrical Parameters

* Battery configuration: 1S
* Maximum charge current: up to 1A (configurable)
* Maximum discharge current: depends on MOSFET and PCB trace width
* Input voltage: 5V
* Output voltage: 3.0–4.2V (battery dependent)

---

## PCB Information

* 2-layer PCB
* Designed in KiCad
* Custom symbol and footprint libraries included in repository
* Gerber files available for manufacturing

PCB files:

* powerbank.kicad_sch – schematic
* powerbank.kicad_pcb – PCB layout
* Gerbers located in `/hardware/gerbers`

---

## Repository Structure

```
/hardware
 ├── pcb
 ├── libraries
 │    ├── symbols
 │    └── footprints
 ├── gerbers
 └── bom
```

Local libraries are included to ensure portability of the project.

---

## Manufacturing

To manufacture the board:

1. Use Gerber files from `/hardware/gerbers`
2. Upload them to your PCB manufacturer
3. Verify drill and copper layers before ordering

Recommended:

* 1oz copper
* FR4 substrate
* 2-layer board

---

## Safety Notice

Lithium-ion batteries can be dangerous if misused.

* Do not short-circuit the battery
* Do not overcharge or overdischarge
* Do not use damaged or swollen cells
* Do not leave charging unattended
* Do not exceed recommended charge current

Use this project at your own risk.

---

## Disclaimer

This project is provided for educational purposes only.
The author assumes no responsibility for damage, injury, or loss resulting from improper use.

---

## License

Open-source hardware project.
You may modify and use it for personal, educational, and non-commercial purposes.
