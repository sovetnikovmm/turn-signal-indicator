# Audible Turn Signal Indicator

This discrete transistor circuit produces a tone while the turn signal supplies power. The vehicle flasher sets the repetition rate of the audible bursts, while an oscillator on the board generates the sound within each burst.

| Parameter | Specification |
|---|---|
| Supply shown on the schematic | 9 V DC |
| Output | External loudspeaker |
| PCB | 60 × 35 mm, single-sided |
| Assembled board dimensions | 60 × 35 × 16 mm |

## Block Diagram

![Functional block diagram of the audible indicator](docs/images/block-diagram.svg)

Power enters through a reverse-polarity protection diode. An asymmetric multivibrator generates pulses, and a push-pull output stage drives the speaker. A series capacitor couples the changing output voltage to the speaker and blocks DC.

## Schematic

![Transistor oscillator and push-pull speaker driver](docs/images/schematic.svg)

XS1 accepts the supply on pin 1 and ground on pin 2. VD1 protects the circuit against reversed input polarity. VT1 and VT2 form the oscillator. The R3–C1 and R4–C2 networks influence its timing. The collector of VT2 drives the bases of the complementary output transistors VT3 and VT4. Their common emitter output feeds the loudspeaker through C3 and connector XP1.

## PCB Design

![3D view from the component side](docs/images/pcb-3d.png)

All components mount on the top of the single-sided board. The two screw terminals sit at opposite ends, with four mounting holes near the corners. The design report specifies copper-clad glass laminate (СФ-1Н-35Г), a minimum track width and clearance of 0.45 mm each, and a minimum nominal hole diameter of 1.2 mm.

![Bottom copper routing in blue, overlaid with top-side component outlines and designators](docs/images/pcb-layout.png)

## Built Device

![Assembled through-hole prototype connected to an external speaker](docs/images/pcb-real.png)

The prototype uses the left terminal for power and the opposite terminal for the external speaker. Applying 9 V to XS1 starts the oscillator. Removing power stops the tone. The project report describes bench measurements at the oscillator output and across the speaker, allowing the two waveforms to be compared.

## Bill of Materials

| Designator | Description | Value | Quantity | Manufacturer | Part Number | Package |
|---|---|---|---:|---|---|---|
| C1 | Non-polarized capacitor 40V 20% | 0.15 µF | 1 | | | Through-hole |
| C2 | Non-polarized capacitor 160V 10% | 1000 pF | 1 | | | Through-hole |
| C3 | Polarized capacitor 50V 20% | 3.3 µF | 1 | | | Through-hole |
| R1 | Carbon film resistor ±5%, 0.25 W | 15 kΩ | 1 | | | Through-hole |
| R2, R6 | Carbon film resistor ±5%, 0.25 W | 2.7 kΩ | 2 | | | Through-hole |
| R3 | Carbon film resistor ±5%, 0.25 W | 470 kΩ | 1 | | | Through-hole |
| R4 | Carbon film resistor ±5%, 0.25 W | 22 kΩ | 1 | | | Through-hole |
| R5 | Carbon film resistor ±5%, 0.25 W | 8.2 kΩ | 1 | | | Through-hole |
| R7 | Carbon film resistor ±5%, 0.25 W | 3 kΩ | 1 | | | Through-hole |
| VD1 | Silicon Diode | KD102A | 1 | | | Through-hole |
| VD2 | Silicon Diode | KD103A | 1 | | | Through-hole |
| VT1, VT4 | PNP bipolar junction transistor | KT361B | 2 | | | KT-13 |
| VT2, VT3 | NPN bipolar junction transistor | KT315B | 2 | | | KT-13 |
| XP1 | 2-pin connector (plug) | KLS 2Pin 5.0mm | 1 | | | Through-hole |
| XS1 | 2-pin connector (socket) | KLS 2Pin 5.0mm | 1 | | | Through-hole |

The table covers the 18 board-mounted components. The speaker connects externally.

## Documentation in Russian

- [Engineering report (РПЗ, DOCX)](docs/original-ru/design-report.docx) — circuit operation, PCB design, prototype assembly and bench measurements.
- [Block diagram (Э1)](docs/images/block-diagram.svg)
- [Circuit schematic (Э3)](docs/images/schematic.svg)
