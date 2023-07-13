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
* memory.common.spin2h (provided by p2-spin-standard-library)

## Compiler Compatibility

| Processor | Language | Compiler               | Backend      | Status                |
|-----------|----------|------------------------|--------------|-----------------------|
| P1        | SPIN1    | FlexSpin (6.1.1)       | Bytecode     | Not yet implemented   |
| P1        | SPIN1    | FlexSpin (6.1.1)       | Native/PASM  | Not yet implemented   |
| P2        | SPIN2    | FlexSpin (6.1.1)       | NuCode       | FTBFS                 |
| P2        | SPIN2    | FlexSpin (6.1.1)       | Native/PASM2 | OK                    |

(other versions or toolchains not listed are __not supported__, and _may or may not_ work)

## Limitations

* Single-lane SPI only (no Dual-SPI or Quad-SPI - unplanned, for now)
* SPI driver is relatively slow, compared to memory's capability; not suitable for high-performance applications
* Tested only with Winbond W25Q128

