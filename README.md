# Audible Turn Signal Indicator

A single-layer **60 × 35 mm** through-hole PCB designed in Altium Designer as an academic
hardware project. The circuit uses a discrete-transistor oscillator and output stage to
produce an audible indication through an external speaker when supplied with **9–16 V DC**.

The repository contains editable Altium sources, PCB views, manufacturing outputs, and the
original Russian engineering drawings prepared in the ESKD format. Assembly and electrical
validation are not documented here.

## Block diagram

![Functional block diagram](hardware/images/block-diagram.svg)

- **Power input.** XS1 supplies the circuit from a 9–16 V DC source; VD1 is in series with the
  positive input.
- **Oscillator.** An asymmetric astable multivibrator generates the drive signal.
- **Output stage.** A push-pull transistor stage drives the output network.
- **Output network.** The structural diagram specifies a high-frequency filter before the
  external speaker, connected via XP1.

The original [structural diagram (E1)](docs/original-ru/turn-signal-indicator_E1_block-diagram.PDF)
is available in Russian.

## Schematic

The circuit uses four bipolar transistors (VT1–VT4), two diodes (VD1–VD2), seven resistors,
and three capacitors. It is implemented entirely with discrete components, without a
microcontroller.

- [Circuit schematic (E3, PDF)](docs/original-ru/turn-signal-indicator_E3_schematic.PDF)
- [Editable schematic (Altium SchDoc)](hardware/altium/turn-signal-indicator_E3_schematic.SchDoc)

The PDF is the original Russian-language ESKD drawing; the editable Altium file is the
source for further changes.

## PCB

<p align="center"><img src="hardware/images/pcb-3d.png" alt="3D view of the single-layer PCB" width="560"></p>

![PCB layout](hardware/images/pcb-layout.png)

Single-layer, **60 × 35 mm** PCB with through-hole components and four mounting holes.
The board layout and mechanical details are available in the
[PCB fabrication drawing](docs/original-ru/turn-signal-indicator_PP_board-drawing.PDF).

## Connectors

| Connector | Pin 1 | Pin 2 |
| --- | --- | --- |
| XS1 — DC input | +9–16 V | GND |
| XP1 — speaker output | Output 1 | Output 2 |

The speaker is external to the PCB and connects across XP1 pins 1 and 2.

## Known issues / documentation notes

- **Connector designation.** The original parts list (PE3) identifies the two connectors as
  XS1 and **XS2**, while the updated Altium design uses **XS1** and **XP1**. The original PE3
  should be revised to match the current schematic before issuing a new documentation set.
- **Validation status.** The PCB design and manufacturing exports are provided, but no
  assembly photographs, bench measurements, or functional test report are included. These
  files should not be taken as evidence of a tested production design.

## Bill of materials

| Ref | Qty | Part | Description |
| --- | ---: | --- | --- |
| C1 | 1 | К10-17Б | 150 nF, 40 V, ±20% |
| C2 | 1 | КМ5Б | 1 nF, 160 V, ±10% |
| C3 | 1 | JRB1H3R3M02000500110000B (JB Capacitors) | Polarized capacitor; 3.3 µF in the exported BOM |
| R1 | 1 | CF-25 (Yageo) | 15 kΩ, 0.25 W, ±5% |
| R2, R6 | 2 | CF-25 (Yageo) | 2.7 kΩ, 0.25 W, ±5% |
| R3 | 1 | CF-25 (Yageo) | 470 kΩ, 0.25 W, ±5% |
| R4 | 1 | CF-25 (Yageo) | 22 kΩ, 0.25 W, ±5% |
| R5 | 1 | CF-25 (Yageo) | 8.2 kΩ, 0.25 W, ±5% |
| R7 | 1 | CF-25 (Yageo) | 3 kΩ, 0.25 W, ±5% |
| VD1 | 1 | КД102А | Diode |
| VD2 | 1 | КД103А | Diode |
| VT1, VT4 | 2 | КТ361Б | PNP bipolar transistor |
| VT2, VT3 | 2 | КТ315Б | NPN bipolar transistor |
| XS1 | 1 | KLS2-300-5.00-02P-2S (KLS Electronic) | 2-pin connector, 5.00 mm pitch |
| XP1 | 1 | KLS2-300-5.00-02P-2S (KLS Electronic) | 2-pin connector, 5.00 mm pitch |

**Total:** 18 components across 15 BOM lines. See the
[full BOM (CSV)](docs/turn-signal-indicator.csv) and the
[original parts list (PE3, PDF)](docs/original-ru/turn-signal-indicator_PE3_parts-list.pdf).

## Engineering documentation

The following original drawings are in Russian and follow the ESKD documentation format:

| Document | Description |
| --- | --- |
| [E1](docs/original-ru/turn-signal-indicator_E1_block-diagram.PDF) | Structural diagram |
| [E3](docs/original-ru/turn-signal-indicator_E3_schematic.PDF) | Circuit schematic |
| [PP](docs/original-ru/turn-signal-indicator_PP_board-drawing.PDF) | PCB fabrication drawing |
| [SB](docs/original-ru/turn-signal-indicator_SB_assembly-drawing.pdf) | Assembly drawing |
| [PE3](docs/original-ru/turn-signal-indicator_PE3_parts-list.pdf) | Parts list |
| [Specification](docs/original-ru/turn-signal-indicator_SP_specifictaion.pdf) | Assembly specification |

## Project files

- [Altium project](hardware/altium/turn-signal-indicator.PrjPcb) and associated schematic,
  PCB, library, BOM, and output-job files in [`hardware/altium/`](hardware/altium/).
- [Gerber archive](fabrication/turn-signal-indicator_gerber.zip) and
  [STEP model](fabrication/turn-signal-indicator.step).

The Gerber files are design outputs; their presence does not imply manufacturing or
functional validation.
