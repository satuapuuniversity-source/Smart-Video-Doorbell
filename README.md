# Kelly Project 3 - Smart Video Doorbell

Unified KiCad 10.0.4 hierarchical PCB combining camera doorbell unit components into a single board, designed via Claude Code in VSCode.

## Hardware
- ESP32-P4NRW32 (main MCU, camera/AI processing)
- ESP32-C6FH4 (wireless coprocessor)
- ESP32-C3-WROOM-02 (secondary MCU)
- W25Q256JVEIQ external flash
- ES8388 audio codec + PAM8302AAD audio power amp
- LI-OV5640-MIPI-AF camera module
- PCA9555PW I/O expander
- SD card slot (Molex 503398-1892)
- PIR motion sensor (AM312)
- Weatherproof doorbell pushbutton
- IR night-vision LEDs (VSMY1850X01 / VSMY2940RG)
- Battery backup: BQ25070 charger, DW01A protection, MAX17048 fuel gauge
- USB-C powered (USB4105-GF-A)

## Design notes
- 7 hierarchical sheets: Power, Main_MCU, Wireless_Coproc, Secondary_MCU_CAN, Aux_MCU, Audio_IO, Camera
- 180 components, 194 nets
- Final ERC: 3 errors / 9 warnings (documented in PROJECT_STATUS.md) - one manual GUI fix remains (U8 CHIP_PU wire redraw)
- Camera unit only - the Chime unit is a separate mains-powered (230V AC) board, not part of this repo

## Repo structure
- `kicad-project/` - full KiCad project (schematics, PCB, BOM, gerbers)

**Scope:** hardware/PCB design only - firmware not included.
