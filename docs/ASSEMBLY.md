# Assembly and Test Guide

> [!CAUTION]
> Use this guide with the v0.9 corrected prototype. Revision v0.8 is invalidated. See [Known Issues](KNOWN_ISSUES.md).

## Assembly order

1. Identify the v0.9 silkscreen. Inspect the bare PCB for damaged pads, blocked holes, or solder-mask defects.
2. Orient the PCB with the **front/component side facing you** and the **U1 notch at the top**. The square H1 and U1 pad 1 markers must both be on the left of their respective DIP rows at the notch end. Match H1 pad 1 to the host socket's pin 1. Check that the 2.54 mm lateral offset between H1 and U1 clears nearby components.
3. Solder R1-R3 and C1 on the bottom side. Close one jumper in each of P1, P26, and P27 using the [Jumper Guide](JUMPER_GUIDE.md).
4. Solder the H1 machine-pin strips on the bottom using an alignment socket or jig. The mating pins point toward the host socket.
5. Solder the U1 precision socket on the top. Align its notch with the front silkscreen notch and the square U1 pad.
6. Solder J_EXT if external address control is required. Clean flux and inspect every joint under magnification.

## Unpowered checks before installation

- With U1 empty, identify both DIP pin positions by the notch-up top view. Use the [DIP position table](../validation/V0.9_VERIFICATION.md#dip-28-position-check) to check pins 1, 14, 15, 28, 26, and 27 against that orientation.
- Check common-pin continuity between H1 and U1, including 14 (GND), 15 (D3), and 28 (VCC). Check for a short between VCC and GND.
- Confirm that U1 pins 1, 26, and 27 have continuity only through the selected jumper options. H1 pin 1 has no connection to the circuit.
- Confirm that A13, A14, and A15 each measure approximately 10 kOhm to GND with the host and external controls disconnected and U1 empty. Confirm J_EXT pin 1 (square pad) is A13.
- Fit the unpowered adapter into the host socket, check pin 1 alignment again, and inspect the assembled clearance before applying power.

## First power-up

1. Fit a memory device with a known-good image duplicated into every selectable bank. Align memory pin 1 with the U1 square pad.
2. Leave the external address inputs disconnected for the first power-up. Check that the host runs normally with the external inputs held low by the board's pull-downs.
3. Power off before attaching or moving test connections. Test one external input at a time and record the host socket family, memory type, jumper settings, and results.
