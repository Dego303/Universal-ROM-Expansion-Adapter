# Universal ROM Expansion Adapter

Open-hardware adapter for using larger 28-pin 8-bit EPROM, EEPROM, and flash-compatible memory devices in vintage equipment.

> [!CAUTION]
> **Do not fabricate, assemble, or power hardware revision v0.8.** Real-hardware testing on 2026-09-26 exposed a left/right mirrored DIP-28 pad-numbering/orientation error affecting both the host and memory interfaces. Rotating the memory by 180 degrees does not correct the mapping. The downloadable v0.8 package is retained only as an invalidated prototype record. See [Known Issues](docs/KNOWN_ISSUES.md).

The board passes the common address, data, chip-enable, output-enable, power, and ground pins directly between the host socket and the replacement memory. Pins 1, 26, and 27 are configurable, while A13, A14, and A15 are available on an external header for manual or firmware-controlled bank selection.

> **Prototype status:** hardware version **v0.8 is invalidated and unsafe to use**. KiCad 10.0.5 DRC passed with 0 violations and 0 unconnected items, but DRC did not detect the mirrored physical DIP orientation. A corrected revision has not yet been released.

## Why this exists

Many synthesizers, samplers, drum machines, digital effects processors, automotive ECUs, industrial controllers, retro computers, and arcade boards use 27C-series EPROMs for operating systems, program code, configuration data, samples, or lookup tables. This adapter provides a compact development and preservation tool when a larger replacement memory is needed or when additional address lines must be controlled externally.

This repository contains **hardware design files only**. It does not contain firmware or ROM images. Only distribute binary images when you have the legal right to do so.

## Features

- Supports host sockets wired for 27C64, 27C128, or 27C256.
- Supports 27C256, SST27SF256, AT28C256/compatible 28C256, 27C512, and SST27SF512-class devices with the documented pinout.
- SST27SF256 uses the standard 27C256 read pinout and therefore uses the same jumper settings as 27C256.
- Handles the important 27C256 versus AT28C256 pinout difference.
- Exposes A13, A14, A15, and GND on a 1x4 header.
- 10 kOhm pull-downs provide a stable low-bank boot state for external address inputs.
- 100 nF local decoupling capacitor.
- Hand-solderable 0805 passives and large solder jumpers.
- 24 x 41 mm, two-layer PCB.
- Open KiCad source, BOM, Gerber package, and jumper documentation.

## Repository layout

- `Universal-ROM-Expansion-Adapter-v0.8-Public-Package.zip` - complete KiCad source, Gerber set, BOM, and validation files.
- `hardware/bom/BOM.csv` - bill of materials.
- `docs/JUMPER_GUIDE.md` - configuration matrix and jumper rules.
- `docs/ASSEMBLY.md` - assembly and first-power-up procedure.
- `docs/ROM_IMAGE_PREPARATION.md` - safe bank-image preparation for testing.
- `docs/COMPATIBILITY.md` - supported host and memory families.
- `docs/KNOWN_ISSUES.md` - confirmed hardware defects and disposition of affected revisions.
- `validation/` - DRC, electrical-equivalence, and privacy audits.

## Important electrical rule

Close **exactly one** jumper in each group: `P1`, `P26`, and `P27`. Never bridge two alternatives in the same group.

See [Jumper Guide](docs/JUMPER_GUIDE.md) before fitting a memory device or connecting external address lines.

## Fabrication

**Do not fabricate the included v0.8 design.** The package is retained for traceability only and contains the confirmed mirrored DIP-28 footprint error described in [Known Issues](docs/KNOWN_ISSUES.md).

The following settings are historical prototype settings, not a fabrication recommendation for v0.8:

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

27C64, 27C128, 27C256, 27C512, AT28C256, 28C256, SST27SF256, SST27SF512, EPROM adapter, EEPROM adapter, flash ROM adapter, ROM expansion, bank switching, bank selection, vintage hardware, synthesizer repair, arcade repair, retro computing, embedded systems.
