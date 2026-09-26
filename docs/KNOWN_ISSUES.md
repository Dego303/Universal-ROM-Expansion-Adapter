# Known Issues

## v0.8: mirrored DIP-28 physical pin orientation

**Status:** confirmed in real hardware on 2026-09-26; revision v0.8 is invalidated.

**Severity:** critical. Do not fabricate, assemble, install, or power v0.8.

The U1 memory footprint and H1 host footprint use a left/right mirrored physical pad-numbering orientation relative to the standard top-view DIP-28 convention. The silkscreen `PIN1` indication consequently appears on the opposite side of the package notch from physical device pin 1.

Rotating a memory device by 180 degrees does not correct a left/right mirror. There is no valid top-side insertion orientation for a standard DIP-28 memory device on the assembled v0.8 adapter.

### Discovery

The defect was exposed during the first test in a Roland SBX-80 27C64 host socket using an AT28C256 and the documented jumper configuration. The host displayed corrupted LCD characters. It booted normally again after the adapter was removed and the original ROMs were restored. A second test after rotating the memory 180 degrees also failed, which is consistent with the mirrored physical mapping.

### Why previous checks did not catch it

- KiCad DRC checks connectivity and manufacturing constraints, not whether a custom footprint follows the physical DIP top-view numbering convention.
- The published/ordered electrical fingerprint comparison established that both v0.8 data sets were identical; it did not establish that either one was physically correct.
- Continuity checks performed by printed pad numbers can reproduce the same numbering error unless physical package pin positions are independently checked against a datasheet.

### Required corrective action

1. Do not perform further powered tests with v0.8.
2. Verify any memory device exposed to the faulty adapter in a programmer before reuse.
3. Correct and independently review both H1 and U1 physical pad numbering against the standard DIP-28 top view.
4. Add a physical-position validation table covering pins 1, 14, 15, and 28, plus configurable pins 26 and 27.
5. Fabricate a new revision and pass unpowered continuity checks before any host power-up.
6. Release corrected fabrication files only after a known-good image boots successfully in real hardware.

No corrected hardware revision is available in this repository yet.
