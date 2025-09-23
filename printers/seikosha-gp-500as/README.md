# Seikosha GP-500AS Dot Matrix Printer

The Seikosha GP-500AS is a 9-pin dot matrix printer from the 1980s, manufactured by Seikosha (Seiko Instruments). Known for reliable performance and quality construction, Seikosha printers were popular choices for home and business computing applications during the 8-bit and early 16-bit computer era.

---
![Printer Unit](pictures/seikosha_gp_500as.png)
For detailed photographs of the PCB and components, see **[PICTURES.md](PICTURES.md)**.

## GP-500AS Board — Summary

### Identification / markings

- Board ID: **[To be documented]**
- PCB code: **[To be documented]**
- Text: **[To be documented]**
- Manufacturer: **Seikosha (Seiko Instruments)**
- EPROM label: **[To be documented]**

### Architecture overview

- Core: **[MCU to be identified]**
- Program/storage: **[EPROM details to be documented]**
- Glue logic: **[Logic family to be documented]**
- Drivers: **[Driver ICs to be documented]**
- Custom modules: **[Custom components to be documented]**
- Clocking: **[Crystal/oscillator details to be documented]**

### Connectors (top-level)

- **[Connector details to be documented]**

### Configuration / service

- DIP switches: **[To be documented]**
- Jumpers: **[To be documented]**
- Test points: **[To be documented]**
- Trimmers: **[To be documented]**

### ICs

| RefDes | Exact top marking | Manufacturer | Part / Type | Function | Package | Notes |
|---|---|---|---|---|---|---|
| *[To be populated during analysis]* | | | | | | |

### Connectors

| RefDes | Connector type / style | Pins / rows  | Notes |
|---|---|---|---|
| *[To be populated during analysis]* | | | |

---

## Board Specifications

### Physical Characteristics
- **PCB Dimensions**: *[To be measured]*
- **Component Height**: *[To be measured]*
- **Mounting**: *[To be documented]*

### Power Requirements
- **Supply Voltage**: *[To be documented]*
- **Current Draw**: *[To be measured]*
- **Power Connectors**: *[To be documented]*

---

## References

### Datasheets and Technical Documentation
- **[Component datasheets to be added as identified]**

### Service Information
- **Service Manual**: *[Not currently available]*
- **Parts Lists**: *[Not currently available]*
- **Schematic Diagrams**: *[Not currently available - reverse engineering needed]*

### Related Documentation
- **Seikosha Printer Family**: *[Related models and compatibility information]*
- **Interface Standards**: *[Era-specific interface standards]*

---

## RS-232 Serial Interface Configuration

The Seikosha GP-500AS uses a serial interface. For connection to modern PCs, use the [generic RS-232 adapter](../../common/interfaces/RS232_Adapter_Layout.md) with these specific jumper settings:

### Adapter Configuration for GP-500AS

- **Block A (TX/RX):** Vertical (straight, Yellow↔Blue)
- **Block B (RTS/CTS):** Horizontal (crossed, Brown↔White)
- **Block C (DTR/DSR):** Horizontal (straight per-signal, Grey↔Purple)
- **Tie rows:** None (add Purple↔Pink on PR side if printer needs carrier)

### Connection Notes
- Verify printer's serial interface requirements before connecting
- Test with multimeter to confirm proper signal routing
- May require additional handshaking signals depending on printer firmware