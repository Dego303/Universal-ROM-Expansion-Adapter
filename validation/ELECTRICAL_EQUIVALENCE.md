# Electrical equivalence

> [!WARNING]
> This comparison proves only that the published and ordered v0.8 PCB data are electrically identical to each other. It does **not** validate either design against the physical DIP-28 top-view pin convention. Real-hardware testing on 2026-09-26 confirmed that both contain a left/right mirrored DIP-28 pad-numbering/orientation error. Revision v0.8 is invalidated; see [`docs/KNOWN_ISSUES.md`](../docs/KNOWN_ISSUES.md).

The public KiCad file differs from the ordered prototype source only in device-neutral bottom-silkscreen wording.

- Original electrical fingerprint: `f3a376696028e7bfa0e3c38ced7d88d74f4fd079a6db48658fd56b90768274aa`
- Public electrical fingerprint: `f3a376696028e7bfa0e3c38ced7d88d74f4fd079a6db48658fd56b90768274aa`
- Result: **identical**

The fingerprint covers nets, pads, tracks, vias, and the board outline while excluding silkscreen text and graphics. It therefore reproduced the same design error rather than detecting it.
