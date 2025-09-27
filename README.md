# 80s Printers Documentation Collection

This repository documents vintage dot matrix printers from the 1980s era, preserving hardware specifications, firmware, and technical details for historical and educational purposes.

## Printer Collection

### Nakajima NP-2200
**9-pin dot matrix printer with NEC 8049 MCU**
- [Documentation](printers/nakajima-np-2200/)
- Architecture: NEC D8049HC + D8155 + D8255
- Interface: Centronics parallel

### Diconix Model-150
**Portable inkjet printer**
- [Documentation](printers/diconix-model-150/)
- Architecture: *To be documented*
- Interface: Centronics parallel

### Seikosha GP-500AS
**9-pin dot matrix printer with Intel 8039 MCU**
- [Documentation](printers/seikosha-gp-500as/)
- Architecture: Intel 8039 + 27256 EPROM + dual-port RAM
- Interface: RS-232C serial

## Common Resources

### Interfaces
- **Centronics Parallel**: Standard 36-pin connector used by most printers
- **Serial RS-232**: Alternative interface for some models
  - [Generic RS-232 Adapter Design](common/interfaces/RS232_Adapter_Layout.md) - Jumperable DB9↔DB25 adapter

### Components
- **NEC 8049 Family**: Popular MCU choice for printer controllers
- **Intel 8255 PPI**: Programmable Peripheral Interface
- **Intel 8155**: RAM + I/O + Timer combo chip

### Tools
- [FX-80 Glyph Viewer](tools/fx80-viewer.html) - Browser-based ROM glyph visualization tool

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
