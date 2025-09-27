# Seikosha GP-500AS Dot Matrix Printer

The Seikosha GP-500AS is a 9-pin dot matrix printer from the 1980s, manufactured by Seikosha (Seiko Instruments). Known for reliable performance and quality construction, Seikosha printers were popular choices for home and business computing applications during the 8-bit and early 16-bit computer era.

---
![Printer Unit](pictures/seikosha_gp_500as.png)
For detailed photographs of the PCB and components, see **[PICTURES.md](PICTURES.md)**.

## GP-500AS Board — Summary

### Identification / markings

- Board ID: **Seikosha GP-LS RN3**
- PCB code: **GP-500AT-2** (shared across GP-500 variants)
- Text: **GP-DR-2 4G SEIKOSHA** (hybrid driver module)
- Manufacturer: **Seikosha (Seiko Instruments)**
- EPROM label: **BASE -2** (HN482732AG-20)

### Architecture overview

- Core: **Intel 8039 MCU** (MCS-48 family)
- Program/storage: **HN482732AG-20** (Hitachi 27256, 32KB EPROM)
- Glue logic: **74LS series TTL** (SN7404N, 74LS00)
- Drivers: **LB1233** (Sanyo motor driver), **GP-DR-2** (hybrid printhead driver)
- Custom modules: **GP-DR-2 4G SEIKOSHA** (dot-matrix printhead driver)
- Clocking: **[Crystal details to be documented]**

### Connectors (top-level)

- **DB-25**: RS-232C serial interface (Centronics-compatible pinout)
- **Power**: On-board power supply section with fuses (T1.6A)
- **Motor/Printhead**: Internal connections to stepper motors and printhead

### Configuration / service

- DIP switches: **[To be documented]**
- Jumpers: **[To be documented]**
- Test points: **[To be documented]**
- Trimmers: **[To be documented]**

### ICs

| RefDes | Exact top marking | Manufacturer | Part / Type | Function | Package | Notes |
|---|---|---|---|---|---|---|
| U1 | HN482732AG-20 | Hitachi | 27256 EPROM | Firmware storage (32KB) | DIP-28 | Label: "BASE -2" |
| U2 | SRM2016C20 | Mitsubishi | 2K × 8 SRAM | Data buffer | DIP-24 | Static RAM |
| U3 | HM3-6116-5 | Harris | 2K × 8 SRAM | Data buffer | DIP-24 | Static RAM |
| U4 | MB842308-11 | Fujitsu | 8K × 8 Dual-port RAM | I/O buffer | DIP-28 | Shared memory |
| U5 | LB1233 | Sanyo | Motor driver IC | Stepper motor control | DIP-16 | Printer mechanics |
| U6 | SN7404N | Texas Instruments | Hex inverter | TTL glue logic | DIP-14 | Standard logic |
| U7 | 74LS00 | Various | Quad NAND gate | TTL glue logic | DIP-14 | Standard logic |
| M1 | GP-DR-2 4G | Seikosha | Hybrid driver module | Printhead driver | Custom | High-current driver |
| Q1-Q3 | 2SB716 | Various | Power transistors | Power regulation | TO-220 | On heatsink |

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
- **Supply Voltage**: 5V logic + motor drive voltages (likely 24V)
- **Current Draw**: *[To be measured]*
- **Power Connectors**: On-board power supply section
- **Protection**: Two T1.6A fuses
- **Regulation**: Large capacitors + power transistors (2SB716) on heatsink

---

## References

### Datasheets and Technical Documentation
- **[Component datasheets to be added as identified]**

### Service Information
- **Service Manual**: Amstrad DMP1 Service Manual (closest match - re-badged GP-500M-2)
  - Contains schematics, board callouts, signal timing
  - Details for 8039/EPROM/6116 configuration
  - Motor and GP-DR-2 printhead drive specifications
- **User Manual**: Amstrad DMP1 Owner's Manual
  - Control/ESC codes, DIP functions, character sets
  - Compatible with GP-500AS operation
- **Alternative Reference**: Commodore MPS-801 Technical Manual (re-badged GP-500VC)
  - Good for mechanics/adjustments and alternative schematics

### Related Documentation
- **Seikosha GP-500 Series**: Family includes GP-500A/AT (parallel), GP-500AS (RS-232), GP-500VC (Commodore serial)
  - Also sold as Amstrad DMP1, Commodore MPS-801, Atari 1029
  - Shared mechanics, firmware, and GP-DR-2 driver module
  - Period: ~1984–1986
- **Performance Specifications**:
  - 10-inch width, 80-column capacity
  - ~50 cps draft speed
  - 9-pin (7 vertical dots per pass) dot matrix
  - Uses Group 628/1231 ribbon (still available)
- **Technical References**:
  - [CPCWiki DMP1 page](https://www.cpcwiki.eu/index.php/Amstrad_DMP1) - Comprehensive documentation
  - [Service manual downloads](https://www.cpcwiki.eu/index.php/Amstrad_DMP1) - DMP1 and MPS-801 manuals
  - [Retro-Bobbel MPS-801 docs](https://retro-bobbel.de/) - Alternative technical reference

---

## RS-232 Serial Interface Configuration

The Seikosha GP-500AS uses a serial interface. For connection to modern PCs, use the [generic RS-232 adapter](../../common/interfaces/RS232_Adapter_Layout.md) with these specific jumper settings:

### Adapter Configuration for GP-500AS

- **Block A (TX/RX):** Vertical (straight, Yellow↔Blue)
- **Block B (RTS/CTS):** Horizontal (crossed, Brown↔White)
- **Block C (DTR/DSR):** Horizontal (straight per-signal, Grey↔Purple)
- **Tie rows:** None (add Purple↔Pink on PR side if printer needs carrier)
