# w25qxxx-spin2 
---------------

This is a P2X8C4M64P/Propeller 2 driver object for Winbond 25Qxxx-series Flash memories

## Salient Features

* SPI connection at up to 6.5MHz
* Read device ID, Mfr. ID, JEDEC ID

## Requirements

* N/A

## Compiler Compatibility

* FastSpin (tested with 4.0.3-beta)

## Limitations

* Very early in development - may malfunction, or outright fail to build
* Single-lane SPI only (no Dual-SPI or Quad-SPI - unplanned, for now)
* SPI driver is relatively slow, compared to memory's capability; not suitable for high-performance applications

## TODO

- [ ] Add methods for basic I/O (read, write bytes)
- [ ] Add a simple hex dump demo
- [ ] Add a simple backup to SD app
