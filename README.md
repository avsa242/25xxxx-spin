# w25qxxx-spin2 
---------------

This is a P2X8C4M64P/Propeller 2 driver object for Winbond 25Qxxx-series Flash memories

**IMPORTANT**: This software is meant to be used with the [spin-standard-library](https://github.com/avsa242/spin-standard-library) (P8X32A) or [p2-spin-standard-library](https://github.com/avsa242/p2-spin-standard-library) (P2X8C4M64P). Please install the applicable library first before attempting to use this code, otherwise you will be missing several files required to build the project.

## Salient Features

* SPI connection at up to 6.5MHz
* Read device ID, Mfr. ID, JEDEC ID
* Read, write a byte
* Read, write a block (write limited to a page per transaction - 256 bytes)
* Erase a sector (4kB), 32kB block, 64kB block, entire chip
* Read busy flag

## Requirements

P2/SPIN2:
* p2-spin-standard-library

## Compiler Compatibility

* P2/SPIN2: FastSpin (tested with 4.1.10-beta)
* ~~PNut~~ (incompatible - no preprocessor)

## Limitations

* Very early in development - may malfunction, or outright fail to build
* Single-lane SPI only (no Dual-SPI or Quad-SPI - unplanned, for now)
* SPI driver is relatively slow, compared to memory's capability; not suitable for high-performance applications
* Developed using 128Mbit part found on Parallax P2 Evaluation board - some methods may currently have hardcoded settings with this specific density chip in mind

## TODO

- [x] Add methods for basic I/O (read, write bytes)
- [x] Add methods for larger transactions
- [x] Add a simple hex dump demo
- [ ] Add a simple backup to SD app
- [ ] Add support for other density parts (may be untested)
