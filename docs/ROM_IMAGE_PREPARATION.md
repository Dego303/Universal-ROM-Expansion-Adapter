# ROM Image Preparation

A larger memory does not automatically create a larger continuous address space. The host still sees its original ROM window; the added address inputs select which bank occupies that window.

## Duplicate-image test files

For the safest first test, repeat the original image until the replacement memory is full:

| Host window | Replacement size | Repeat count |
|---:|---:|---:|
| 8 KiB | 32 KiB | 4 |
| 8 KiB | 64 KiB | 8 |
| 16 KiB | 32 KiB | 2 |
| 16 KiB | 64 KiB | 4 |
| 32 KiB | 64 KiB | 2 |

Example on a Unix-like system:

```sh
cat original.bin original.bin original.bin original.bin > repeated-32k.bin
```

Always verify the final file size and checksum before programming.

## Firmware development

To use different code or data in the added banks, the host firmware must safely control the required address input or inputs. Whole-ROM bank switching may also require duplicated vectors, duplicated bank-switch routines, or a bank-switch routine executed from RAM. Those decisions are host-specific and are outside the scope of this hardware repository.

## Copyright

Do not upload or distribute proprietary firmware images unless you have permission or the image is legally redistributable.
