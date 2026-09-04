# Breadboard Power Supply

A dual-rail regulated power supply module for solderless breadboards, designed in KiCad. It takes a 12V barrel-jack input and provides two independently selectable output rails (5V or 3.3V) to power breadboard projects.

## Overview

This board regulates a 12V DC input down to clean 5V and 3.3V rails using an **LM7805** (fixed 5V) and an **LM317** (adjustable, set to 3.3V), then routes the selected voltage to two separate output rails — a "top" rail and a "bottom" rail — matching the standard dual power-rail layout on a breadboard. Each rail's voltage is chosen independently via a jumper selector, and power is switched at the barrel jack with an LED indicator to show when the board is live.

## Features

- 12V DC barrel-jack input with integrated switch
- Two independent output rails (top and bottom), each individually selectable between **5V** and **3.3V**
- Fixed 5V regulation via LM7805
- Adjustable regulation (set to 3.3V) via LM317 with resistor divider
- Power-on LED indicator
- Outputs available both as breadboard-pin headers and screw terminals (for jumper wire connections)

## Specifications

| Parameter          | Value                            |
|---------------------|-----------------------------------|
| Input Voltage       | 12V DC (barrel jack)             |
| Output Voltage(s)   | 5V and 3.3V (independently selectable per rail) |
| Regulators          | LM7805 (TO-220, fixed 5V), LM317 (TO-220, adjustable) |
| Indicator           | Power LED (D1) |
| Output Connectors   | Breadboard pin headers (J2, J4) + screw terminals (J5, J6) |

## Bill of Materials (from schematic)

| Ref | Part | Value / Type |
|-----|------|---------------|
| U1  | LM7805_TO220 | Fixed 5V linear regulator |
| U2  | LM317_TO-220 | Adjustable linear regulator |
| J7  | Barrel_Jack_Switch | 12V power input with integrated switch |
| SW1 | EG1218 | Rail on/off switch |
| D1  | LED | Power indicator |
| C1  | 0.1 µF | Input decoupling capacitor |
| C2  | 10 µF | Output filter capacitor (LM7805 side) |
| C3  | 1 µF | Output filter capacitor (LM317 side) |
| R1  | 330 Ω | LM317 voltage-set divider |
| R2  | 330 Ω | LM317 voltage-set divider |
| R3  | 560 Ω | LM317 voltage-set divider (sets ADJ for 3.3V output) |
| J3  | Conn_01x03 | Output Voltage Selector 1 (top rail: 5V / 3.3V) |
| J8  | Conn_01x03 | Output Voltage Selector 2 (bottom rail: 5V / 3.3V) |
| J2  | Conn_01x02 | Output to breadboard (top rail) |
| J4  | Conn_01x02 | Output to breadboard (bottom rail) |
| J5  | Screw_Terminal_01x02 | Output to jumper wires (top rail) |
| J6  | Screw_Terminal_01x02 | Output to jumper wires (bottom rail) |

## Wiring / Setup

1. Connect a 12V DC power adapter to the barrel jack (J7).
2. Use the voltage selector headers (J3 for the top rail, J8 for the bottom rail) to choose 5V or 3.3V independently for each rail.
3. Flip the switch (SW1) to power on — the LED (D1) will light up to confirm the board is live.
4. Take output either by:
   - Plugging the board's pin headers (J2, J4) directly into the breadboard's power rails, or
   - Wiring from the screw terminals (J5, J6) using jumper wires.

> ⚠️ **Warning:** Double-check the jumper position on J3/J8 before connecting sensitive components — selecting the wrong rail voltage could damage 3.3V-only devices.

## Files in This Repository

| File | Description |
|------|-------------|
| `BreadBoardPowerSchematic.pdf` | Exported circuit schematic |
| `BreadBoardPCB-Design.pdf` | PCB layout |
| `gerbers/` | Gerber manufacturing files for fabrication |
| `BreadBoardPower-3dPic.png` | 3D render of the assembled PCB |
| `BreadBoardPower-3dPic1.png` | 3D render of the assembled PCB (alternate view) |
| `BreadBoardPower-3dPic2.png` | 3D render of the assembled PCB (alternate view) |

## Preview

<p>
  <img src="BreadBoardPower-3dPic.png" width="30%" />
  <img src="BreadBoardPower-3dPic1.png" width="30%" />
  <img src="BreadBoardPower-3dPic2.png" width="30%" />
</p>

## Design Tool

Designed in **KiCad EDA 10.0.1**.

## License

*(Specify your license here, e.g. MIT, CC-BY-SA 4.0, etc.)*

## Author

**anasarif23**
