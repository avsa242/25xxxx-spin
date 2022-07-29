# 25xxxx-spin
-------------

This is a P2X8C4M64P/Propeller 2 driver object for 25xxxx-series flash memories

**IMPORTANT**: This software is meant to be used with the ~~[spin-standard-library](https://github.com/avsa242/spin-standard-library) (P8X32A) or~~ [p2-spin-standard-library](https://github.com/avsa242/p2-spin-standard-library) (P2X8C4M64P). Please install the applicable library first before attempting to use this code, otherwise you will be missing several files required to build the project.

## Salient Features

* SPI connection at up to 25MHz (tested at up to 300MHz fSYS - may work at higher SPI clocks - YMMV)
* Read device ID, Mfr. ID, JEDEC ID
* Read, write a byte
* Read, write a block (write limited to a page per transaction - 256 bytes)
* Erase a sector (4kB), 32kB block, 64kB block, entire chip
* Read busy flag

## Requirements

P2/SPIN2:
* p2-spin-standard-library

## Compiler Compatibility

| Processor | Language | Compiler               | Backend     | Status                |
|-----------|----------|------------------------|-------------|-----------------------|
| P1        | SPIN1    | FlexSpin (5.9.14-beta) | Bytecode    | Not yet implemented   |
| P1        | SPIN1    | FlexSpin (5.9.14-beta) | Native code | Not yet implemented   |
| P1        | SPIN1    | OpenSpin (1.00.81)     | Bytecode    | Not yet implemented   |
| P2        | SPIN2    | FlexSpin (5.9.14-beta) | NuCode      | Builds, but no start  |
| P2        | SPIN2    | FlexSpin (5.9.14-beta) | Native code | OK                    |
| P1        | SPIN1    | Brad's Spin Tool (any) | Bytecode    | Unsupported           |
| P1, P2    | SPIN1, 2 | Propeller Tool (any)   | Bytecode    | Unsupported           |
| P1, P2    | SPIN1, 2 | PNut (any)             | Bytecode    | Unsupported           |

## Limitations

* Very early in development - may malfunction, or outright fail to build
* Single-lane SPI only (no Dual-SPI or Quad-SPI - unplanned, for now)
* SPI driver is relatively slow, compared to memory's capability; not suitable for high-performance applications
* Developed using 128Mbit part found on Parallax P2 Evaluation board - some methods may currently have hardcoded settings with this specific density chip in mind
* Tested only with Winbond W25Q128

