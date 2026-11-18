# Known Issues

## v0.9 corrected prototype

U1 and H1 follow the DIP-28 top-view numbering. The PCB and project-local footprints were verified against the package orientation, and KiCad 10.0.8 reported zero violations, zero unconnected items, and zero footprint errors. See the [v0.9 verification report](../validation/V0.9_VERIFICATION.md).

Physical assembly, unpowered continuity, mechanical fit, and powered read tests are pending. Follow the [assembly and test guide](ASSEMBLY.md) for prototype validation.

## v0.8 invalidated

**Do not fabricate, assemble, install, or power v0.8.** Hardware testing on 2026-09-26 confirmed that U1 and H1 had left/right mirrored pad numbering relative to the standard DIP-28 top view. A 180-degree rotation could not correct the handedness. The host ran normally again after the original ROMs were reinstalled.

The v0.8 KiCad DRC and electrical equivalence check did not detect the physical pad-numbering error. Verify any memory exposed to v0.8 in a programmer before reuse. The v0.8 files are a historical record of the invalidated revision.
