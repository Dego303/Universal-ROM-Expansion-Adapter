# Universal ROM Expansion Adapter

Open-hardware adapter for using larger 28-pin 8-bit EPROM, EEPROM, and flash-compatible memory devices in vintage equipment.

> [!CAUTION]
> **v0.8 is invalidated. Do not fabricate, assemble, install, or power it.** Real-hardware testing exposed mirrored DIP-28 pad numbering on both interfaces. See [Known Issues](docs/KNOWN_ISSUES.md).

**v0.9 is a corrected prototype.** The U1 memory socket and H1 host interface follow the standard DIP-28 top-view numbering. KiCad 10.0.8 DRC and design-file verification passed. The v0.9 board awaits physical assembly, continuity checks, and first power-up.

The board passes the common address, data, chip-enable, output-enable, power, and ground pins directly between the host socket and the replacement memory. Pins 1, 26, and 27 are configurable. The external header exposes A13, A14, and A15 for bank selection.

## Why this exists

Vintage systems use 27C-series EPROMs for operating systems, program code, configuration data, and lookup tables. This adapter provides a compact development and preservation tool when a larger replacement memory is needed or additional address lines must be controlled externally.

This repository contains **hardware design files only**. Only distribute binary images when you have the legal right to do so.

## Features

- Designed for host sockets wired for 27C64, 27C128, or 27C256.
- Read-mode configurations for 27C256, SST27SF256, AT28C256 and pin-compatible 28C256, 27C512, and SST27SF512.
- A 1x4 header for A13, A14, A15, and GND, with 10 kOhm pull-downs for a low-bank default.
- 100 nF local decoupling, hand-solderable 0805 passives, and solder jumpers.
- 24 x 41 mm, two-layer PCB with KiCad source, BOM, and fabrication files.

## Files and instructions

- [Download the v0.9 prototype test package and fabrication files](https://github.com/Dego303/Universal-ROM-Expansion-Adapter/releases/tag/v0.9)
- [KiCad project](hardware/kicad/Universal-ROM-Expansion-Adapter-v0.9.kicad_pro) and [BOM](hardware/bom/BOM.csv)
- [Jumper Guide](docs/JUMPER_GUIDE.md), [Assembly and Test Guide](docs/ASSEMBLY.md), [Compatibility](docs/COMPATIBILITY.md), and [ROM Image Preparation](docs/ROM_IMAGE_PREPARATION.md)
- [v0.9 change and verification report](validation/V0.9_VERIFICATION.md) and [KiCad DRC report](validation/KiCad_DRC_v0.9.rpt)
- [Gerber and Excellon files](hardware/gerber/README.md)

Close **exactly one** jumper in each group: `P1`, `P26`, and `P27`.

## Prototype fabrication

Use the v0.9 fabrication files for prototype testing. Suggested settings are two-layer FR-4, 1.6 mm thickness, 1 oz copper, and lead-free HASL or ENIG. Follow the unpowered checks in the assembly guide before fitting the prototype into a powered setup.

## Licence

Hardware source and documentation are released under the CERN Open Hardware Licence Version 2 - Permissive (`CERN-OHL-P-2.0`).

## Search terms

27C64, 27C128, 27C256, 27C512, AT28C256, 28C256, SST27SF256, SST27SF512, EPROM adapter, EEPROM adapter, flash ROM adapter, ROM expansion, bank switching, bank selection, vintage hardware, synthesizer repair, arcade repair, retro computing, embedded systems.
