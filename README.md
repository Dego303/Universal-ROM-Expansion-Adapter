# Universal ROM Expansion Adapter

Open-hardware adapter for using larger 28-pin 8-bit EPROM, EEPROM, and flash-compatible memory devices in vintage equipment.

The board passes the common address, data, chip-enable, output-enable, power, and ground pins directly between the host socket and the replacement memory. Pins 1, 26, and 27 are configurable, while A13, A14, and A15 are available on an external header for manual or firmware-controlled bank selection.

> **Prototype status:** visible hardware version **v0.8**. The first batch of 10 PCBs has been ordered. KiCad 10.0.5 DRC passes with 0 violations and 0 unconnected items. Physical fit and real-hardware testing are still pending.

## Why this exists

Many synthesizers, samplers, drum machines, digital effects processors, automotive ECUs, industrial controllers, retro computers, and arcade boards use 27C-series EPROMs for operating systems, program code, configuration data, samples, or lookup tables. This adapter provides a compact development and preservation tool when a larger replacement memory is needed or when additional address lines must be controlled externally.

This repository contains **hardware design files only**. It does not contain firmware or ROM images. Only distribute binary images when you have the legal right to do so.

## Features

- Supports host sockets wired for 27C64, 27C128, or 27C256.
- Supports 27C256, AT28C256/compatible 28C256, 27C512, and SST27SF512-class devices with the documented pinout.
- Handles the important 27C256 versus AT28C256 pinout difference.
- Exposes A13, A14, A15, and GND on a 1x4 header.
- 10 kOhm pull-downs provide a stable low-bank boot state for external address inputs.
- 100 nF local decoupling capacitor.
- Hand-solderable 0805 passives and large solder jumpers.
- 24 x 41 mm, two-layer PCB.
- Open KiCad source, BOM, Gerber package, and jumper documentation.

## Repository layout

- `hardware/kicad/` - KiCad project and project-local footprints.
- `hardware/gerber/` - ready-to-upload fabrication ZIP.
- `hardware/bom/` - bill of materials.
- `docs/JUMPER_GUIDE.md` - configuration matrix and jumper rules.
- `docs/ASSEMBLY.md` - assembly and first-power-up procedure.
- `docs/ROM_IMAGE_PREPARATION.md` - safe bank-image preparation for testing.
- `docs/COMPATIBILITY.md` - supported host and memory families.
- `validation/` - DRC, electrical-equivalence, and privacy audits.

## Important electrical rule

Close **exactly one** jumper in each group: `P1`, `P26`, and `P27`. Never bridge two alternatives in the same group.

See [Jumper Guide](docs/JUMPER_GUIDE.md) before fitting a memory device or connecting external address lines.

## Fabrication

Upload `hardware/gerber/Universal-ROM-Expansion-Adapter-v0.8-Gerber.zip` to a PCB manufacturer.

Suggested prototype settings:

- 2 layers
- FR-4
- 1.6 mm thickness
- 1 oz copper
- lead-free HASL or ENIG
- green solder mask
- white top and bottom silkscreen

The public Gerber package uses a neutral bottom silkscreen. Copper, masks, drills, and board outline are unchanged from the DRC-clean electrical baseline.

## Licence

Hardware source and documentation are released under the CERN Open Hardware Licence Version 2 - Permissive (`CERN-OHL-P-2.0`).

## Search terms

27C64, 27C128, 27C256, 27C512, AT28C256, 28C256, SST27SF512, EPROM adapter, EEPROM adapter, ROM expansion, bank switching, bank selection, vintage hardware, synthesizer repair, arcade repair, retro computing, embedded systems.
