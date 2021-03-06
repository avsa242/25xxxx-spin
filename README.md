# 25xxxx-spin
-------------

This is a P2X8C4M64P/Propeller 2 driver object for 25xxxx-series flash memories

**IMPORTANT**: This software is meant to be used with the ~~[spin-standard-library](https://github.com/avsa242/spin-standard-library) (P8X32A) or~~ [p2-spin-standard-library](https://github.com/avsa242/p2-spin-standard-library) (P2X8C4M64P). Please install the applicable library first before attempting to use this code, otherwise you will be missing several files required to build the project.

## Salient Features

* SPI connection at up to 20MHz (tested at 200MHz fSYS - may work at higher SPI clocks - YMMV)
* Read device ID, Mfr. ID, JEDEC ID
* Read, write a byte
* Read, write a block (write limited to a page per transaction - 256 bytes)
* Erase a sector (4kB), 32kB block, 64kB block, entire chip
* Read busy flag

## Requirements

P2/SPIN2:
* p2-spin-standard-library

## Compiler Compatibility

* P2/SPIN2: FlexSpin (tested with 5.5.0)
* ~~PNut~~ (incompatible - no preprocessor)

## Limitations

* Very early in development - may malfunction, or outright fail to build
* Single-lane SPI only (no Dual-SPI or Quad-SPI - unplanned, for now)
* SPI driver is relatively slow, compared to memory's capability; not suitable for high-performance applications
* Developed using 128Mbit part found on Parallax P2 Evaluation board - some methods may currently have hardcoded settings with this specific density chip in mind
* Tested only with Winbond W25Q128

## TODO

- [x] Add methods for basic I/O (read, write bytes)
- [x] Add methods for larger transactions
- [x] Add a simple hex dump demo
- [ ] Add a simple backup to SD app
- [ ] Add support for other density parts (may be untested)
- [ ] Port to SPIN1/P1
