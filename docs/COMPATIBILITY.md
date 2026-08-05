# Compatibility

## Supported host socket families

- 27C64-style 28-pin socket
- 27C128-style 28-pin socket
- 27C256-style 28-pin socket

## Supported replacement memory families

- 27C256
- SST27SF256 and other devices using the standard 27C256 read pinout
- AT28C256 and pin-compatible 28C256 devices
- 27C512
- SST27SF512 and other devices using the standard 27C512 read pinout

SST27SF256 uses the same adapter jumper settings as 27C256. SST27SF512 uses the same adapter jumper settings as 27C512.

## Not supported by this PCB

- 32-pin 28C512 devices
- memories requiring 3.3 V-only operation
- memories with non-standard control-pin assignments unless separately verified
- in-system programming through this adapter

## Verification rule

Always compare the exact manufacturer datasheet for the device you intend to install. Similar part numbers do not guarantee identical pin assignments, voltage requirements, programming methods, or timing.
