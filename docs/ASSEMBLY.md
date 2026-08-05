# Assembly and Test Guide

## Assembly order

1. Inspect the bare PCB for damaged pads, blocked holes, or solder-mask defects.
2. Solder R1-R3 and C1 on the bottom side.
3. Configure one jumper in each of P1, P26, and P27.
4. Solder the lower H1 machine-pin strips using an alignment socket or jig.
5. Solder the upper U1 precision socket.
6. Solder J_EXT if external address control is required.
7. Clean flux and inspect every joint under magnification.

## Bench checks before installation

- Verify no short between VCC and GND.
- Check 1:1 continuity for the common pass-through pins.
- Confirm pins 1, 26, and 27 follow only the selected jumper routes.
- Confirm unused A13, A14, and A15 inputs measure approximately 10 kOhm to GND.
- Verify the square J_EXT pad is pin 1 / A13.

## First power-up

1. Use a replacement memory containing a known-good image duplicated into every bank.
2. Leave external address inputs disconnected for the first boot.
3. Confirm the host starts normally with all external address inputs low.
4. Power off before attaching or moving temporary clips.
5. Test one external address input at a time.
6. Permanently solder control wires only after the temporary setup has been verified.

## Prototype warning

The first hardware batch is intended to validate pin fit, socket clearance, solderability, and real-hardware operation. Do not force machine pins into a vintage socket. Stop if insertion requires excessive pressure.
