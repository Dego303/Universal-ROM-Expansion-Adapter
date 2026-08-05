# Jumper Guide

## Naming

- `H26` and `H27` mean pins 26 and 27 from the host ROM socket.
- `A13`, `A14`, and `A15` mean the external address inputs on `J_EXT`.
- `VCC` means a fixed logic-high connection.
- `P1`, `P26`, and `P27` configure memory pins 1, 26, and 27.

Close exactly one option in each group.

## Configuration matrix

| Host socket | Replacement memory | P1 | P26 | P27 | External inputs |
|---|---|---|---|---|---|
| 27C64 | 27C256 | VCC | A13 | A14 | A13, A14 |
| 27C64 | AT28C256 / 28C256 | A14 | A13 | VCC | A13, A14 |
| 27C64 | 27C512 / SST27SF512 | A15 | A13 | A14 | A13, A14, A15 |
| 27C128 | 27C256 | VCC | H26 | A14 | A14 |
| 27C128 | AT28C256 / 28C256 | A14 | H26 | VCC | A14 |
| 27C128 | 27C512 / SST27SF512 | A15 | H26 | A14 | A14, A15 |
| 27C256 | 27C256 | VCC | H26 | H27 | None |
| 27C256 | AT28C256 / 28C256 | H27 | H26 | VCC | None |
| 27C256 | 27C512 / SST27SF512 | A15 | H26 | H27 | A15 |

## Why the settings differ

A standard 27C256 uses pin 1 as VPP in read mode and pin 27 as A14. AT28C256-compatible EEPROMs use pin 1 as A14 and pin 27 as active-low write enable. The adapter routes these pins through selectable jumpers so the same PCB can support both families.

For AT28C256 read-only use in the host, `P27` must select `VCC`, holding write enable inactive.

## External header

`J_EXT` pin order:

1. A13
2. A14
3. A15
4. GND

Unused external address inputs are held low by 10 kOhm pull-down resistors.

## Safe initial test

Program every selectable bank with the same known-good image before changing an external address input. This makes every bank behave identically and isolates hardware problems from firmware problems.
