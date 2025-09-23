# 80s Printers Documentation Collection

This repository documents vintage dot matrix printers from the 1980s era, preserving hardware specifications, firmware, and technical details for historical and educational purposes.

## Printer Collection

### Nakajima NP-2200
**9-pin dot matrix printer with NEC 8049 MCU**
- [Documentation](printers/nakajima-np-2200/)
- Status: ✅ Documented
- Architecture: NEC D8049HC + D8155 + D8255
- Interface: Centronics parallel

### Diconix Model-150
**Portable 9-pin dot matrix printer**
- [Documentation](printers/diconix-model-150/)
- Status: 📝 Template created
- Architecture: *To be documented*
- Interface: *To be documented*

### Seikosha GP-500AS
**9-pin dot matrix printer**
- [Documentation](printers/seikosha-gp-500as/)
- Status: 📝 Template created
- Architecture: *To be documented*
- Interface: *To be documented*

## Repository Structure

```
80s-printers/
├── printers/           # Individual printer documentation
│   ├── nakajima-np-2200/
│   ├── diconix-model-150/
│   └── seikosha-gp-500as/
├── common/            # Shared resources
│   ├── connectors/    # Standard connector pinouts
│   ├── interfaces/    # Centronics, serial, etc.
│   └── components/    # Common ICs and components
└── tools/             # Analysis tools and utilities
```

## Common Resources

### Interfaces
- **Centronics Parallel**: Standard 36-pin connector used by most printers
- **Serial RS-232**: Alternative interface for some models

### Components
- **NEC 8049 Family**: Popular MCU choice for printer controllers
- **Intel 8255 PPI**: Programmable Peripheral Interface
- **Intel 8155**: RAM + I/O + Timer combo chip

## Contributing

When documenting a new printer:
1. Create a folder under `printers/[manufacturer-model]/`
2. Include detailed hardware analysis in README.md
3. Add ROM dumps to `rom/` subdirectory
4. Include PCB photos in `pictures/` subdirectory
5. Update this main README with printer details

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.