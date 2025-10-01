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

- Core: **NEC µPD8039H MCU** (MCS-48 family, Harvard architecture, external program memory)
- Program/storage: **2732 EPROM (4KB)** labeled "8DE-1" - contains firmware, command parser, character generator
- RAM: **6116 SRAM (2KB)** for line buffer, graphics mode bitmap storage
- Glue logic: **74LS series TTL** for bus latches, timing, state control
- Drivers: **Transistor arrays** for printhead solenoids (ULN-class), **stepper motor drivers**
- Custom modules: **GP-DR-2** hybrid printhead driver module
- Clocking: **11 MHz crystal** for µPD8039H operation

### Connectors (top-level)

- **DB-25**: RS-232C serial interface (male connector)
- **Power**: Internal PSU (+5V logic, +24V motors/solenoids) with protection
- **DIP Switches**: 4-position rear panel configuration (character sets, CR/LF mode)
- **Internal**: Stepper motor, DC carriage motor, printhead solenoid array connections

### Configuration / Service

- **DIP switches**: 4-position bank (character sets, CR/LF mode)
- **Self-test**: Power-on test sequence (prints ROM font table)
- **Test points**: Available on logic PCB for voltage/signal testing
- **Diagnostics**: Service mode accessible via switch sequence
- **Common Failures**: Ribbon wear, driver transistor failure, stepper motor issues

### ICs  

| RefDes | Exact top marking | Manufacturer | Part / Type | Function | Package | Notes |  
|---|---|---|---|---|---|---|  
| P1 | M74LS04P | Mitsubishi | 74LS04 Hex Inverter | TTL logic, signal inversion | DIP-14 | Used in control logic and oscillator circuits |  
| P2 | SN74LS373N | Texas Instruments | 74LS373 Octal Transparent Latch | Bus latch | DIP-20 | Buffers data/address lines |  
| P3 | LB1233 4J5(2003) | Sanyo | LB1233 | Stepper motor driver | DIP-16 | Drives carriage/paper feed stepper motors |  
| P4 | MBL8049H | Fujitsu (MBL) | Intel 8049 MCU (MCS-48 family) | Main controller | DIP-40 | Executes firmware from external EPROM |  
| P5 | HN482732AG-20 (label “BASE -2”) | Hitachi | 27256 EPROM (32K × 8) | Firmware storage | DIP-28 | Contains firmware code and printer command set |  
| P6 | SN7404N | Texas Instruments | 74LS04 Hex Inverter | TTL logic | DIP-14 | Additional inversion/buffering |  
| P7 | M5L842308P-11 | Mitsubishi | MB842308 | 8K × 8 Dual-Port SRAM | Parallel/serial buffer | DIP-28 | Shared buffer between host interface & MCU |  
| P8 | HM3-6116-5 | Harris | 6116 2K × 8 SRAM | Working RAM | DIP-24 | General scratchpad / line buffer |  
| P9 | SN7404H | TI / NEC | 74LS04 Hex Inverter | TTL logic | DIP-14 | Used in timing and strobe circuits |  
| P10 | SRM2016C20 | Mitsubishi | 6116-class SRAM (2K × 8) | Working RAM | DIP-24 | Buffer memory |  
| P11 | HM3-6116-5 | Harris | 6116 2K × 8 SRAM | Working RAM | DIP-24 | Same as P8 |  
| P12 | MB74LS00 | Fujitsu | 74LS00 Quad 2-input NAND | TTL logic | DIP-14 | General control gating |  
| GP-DR-2 | GP-DR-2 | Seikosha | Custom hybrid driver | Printhead solenoid driver | Custom | Drives high-current printhead pins with protection diodes |


### Connectors

| RefDes | Connector type / style | Pins / rows  | Notes |
|---|---|---|---|
| CN1 | DB-25 female |  | parallel |
| CN2 | Control panel| 6-pin |  |
| CN3 | Internal stepper motor | 8-pin | Paper feed mechanism |
| CN4 | Internal carriage motor | 8-pin | DC motor with position feedback |
| CN5 | Printhead solenoid array | 3-pin | Dot impact mechanism |
| CN6 | Mains power inlet | 6-pin | Region-specific AC input |
| DIPSW | DIP switch bank | 8-position | Character set and CR/LF configuration |

---

## Firmware and ROM Information

### EPROM Details
- **Type**: 2732 EPROM (4KB capacity)
- **Label**: "8DE-1" (primary firmware), "8DE-2" (alternate/extended)
- **Address Space**: 0x0000 to 0x0FFF
- **Content Organization**:
  - Boot/initialization code and vector table
  - Command parser for escape sequences
  - Character generator tables (5×7 dot patterns)
  - DIP switch configuration tables
  - Self-test/diagnostic routines

### Character Set and Graphics
- **Font**: 5×7 dot matrix within 9×9 cell
- **Limitation**: No descenders - letters g, j, p, q, y appear truncated
- **Character Sets**: Multiple national variants (US, UK, German, etc.)
- **Graphics Mode**: ~60 DPI horizontal, 9 LPI vertical
- **Graphics Protocol**: Host sends packed bit data, left-to-right

### Control Sequences
- **ESC/P-like subset** with printer-specific extensions:
  - `0x1B 0x30` - Set line spacing
  - `0x0D` - Carriage Return (CR or CR+LF via DIP switch)
  - `0x1B 0x58` - Enter graphics mode
  - `0x1B 0x57` - Expanded width mode
  - Various positioning and formatting commands

### ROM Dumping Information
- **Availability**: ROM images "8DE-1" and "8DE-2" referenced in CPCWiki
- **Access**: Physical EPROM removal required for dumping
- **Tool Requirements**: EPROM programmer (TL866 or similar)
- **Disassembly**: MCS-48 compatible disassembler needed

---

## Board Specifications

### Physical Characteristics
- **PCB Dimensions**: *[To be measured]*
- **Component Height**: *[To be measured]*
- **Mounting**: *[To be documented]*

### Power Requirements
- **Supply Voltage**: +5V logic, +24V motors/solenoids
- **Current Draw**: *[To be measured - varies with print density]*
- **Power Supply**: Internal switching/linear hybrid
- **Protection**: Fuses and thermal protection
- **Regulation**: Capacitor bank + transistor regulation

### Mechanical Specifications
- **Print Mechanism**: 9-pin serial impact dot matrix
- **Print Head**: Solenoid-driven, 5×7 character matrix in 9×9 cell
- **Paper Feed**: Tractor feed only (continuous form paper)
- **Paper Advance**: Stepper motor, 1/9" steps (9 LPI)
- **Carriage**: DC motor with optical position feedback
- **Ribbon**: Endless fabric loop (~2m length, re-inkable)
- **Print Quality Limitation**: No descenders (g, j, p, q, y truncated)

---

## References

### Datasheets and Technical Documentation
- **[Component datasheets to be added as identified]**

### Service Information
- **Service Manual**: [Amstrad DMP1 Service Manual](https://elektrotanya.com/amstrad_dmp1_printer_sm.pdf/download.html) - 24 pages
  - Complete schematics and circuit diagrams
  - PCB layout and component identification
  - Power supply specifications (+5V logic, +24V motors)
  - Troubleshooting procedures and repair guides
  - Mechanical adjustments and calibration
- **User Manual**: [Amstrad DMP1 Owner's Manual](https://www.manualslib.com/manual/3336071/Amstrad-Dmp1.html) - ~28 pages
  - Complete control code reference
  - DIP switch configuration (character sets, CR/LF modes)
  - Setup and operation procedures
  - Graphics mode programming examples
- **Alternative References**:
  - Commodore MPS-801 Technical Manual (same hardware, different branding)
  - CPC464 Manual sections on printer operation

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
  - [CPCWiki DMP1 page](https://www.cpcwiki.eu/index.php/Amstrad_DMP1_printer) - Comprehensive technical documentation
  - [CPCWiki Printer Resources](https://www.cpcwiki.eu/index.php/Amstrad/Schneider_Printer_Resources) - ROM images and technical data
  - [CPCRulez DMP1 article](https://cpcrulez.fr/hardware-imprimante-amstrad_dmp-1.htm) - Usage examples and code
  - [CPC464 Manual](https://commonplace.doubleloop.net/files/cpc464.en.pdf) - General printer interface reference

---

## Interface Specifications

### RS-232C Serial Interface
The GP-500AS uses a DB-25 male RS-232C serial interface, distinguishing it from the parallel Centronics variants (GP-500A/AT).

**Serial Interface Characteristics:**
- **Connector**: DB-25 male
- **Protocol**: Standard RS-232C
- **Data Format**: Asynchronous serial (start/stop bits)
- **Baud Rates**: Switch-selectable (typical: 300, 600, 1200, 2400 bps)
- **Data Bits**: 7 or 8 bit (DIP switch configurable)
- **Parity**: None, Even, or Odd (DIP switch configurable)
- **Flow Control**: XON/XOFF software handshaking
- **Buffer**: 2KB internal buffer for incoming data

**Electrical Specifications:**
- **Logic Levels**: RS-232C standard (±12V)
- **Input Impedance**: High impedance inputs
- **Output Drive**: Standard RS-232 drive capability

### DIP Switch Configuration
**4-position DIP switch bank on rear panel (GP-500AS serial-specific):**
- **SW1**: Baud rate selection (combined with SW2)
- **SW2**: Baud rate selection (combined with SW1)
  - 00: 300 bps
  - 01: 600 bps
  - 10: 1200 bps
  - 11: 2400 bps
- **SW3**: Character set selection
  - OFF: US ASCII
  - ON: National character set (region-specific)
- **SW4**: Carriage return behavior
  - OFF: CR only (0x0D)
  - ON: CR+LF (0x0D + 0x0A)

### Performance Specifications
- **Print Speed**: 50-80 characters per second
- **Resolution**: ~60 DPI horizontal, 9 lines per inch vertical
- **Buffer Size**: 2KB SRAM (~180 character line buffer)
- **Graphics Transfer**: Bit-packed column data, left-to-right
- **Noise Level**: ~60-65 dB (typical impact printer)

---

## RS-232 Serial Interface Configuration

The Seikosha GP-500AS uses a serial interface. For connection to modern PCs, use the [generic RS-232 adapter](../../common/interfaces/RS232_Adapter_Layout.md) with these specific jumper settings:

### Adapter Configuration for GP-500AS

- **Block A (TX/RX):** Vertical (straight, Yellow↔Blue)
- **Block B (RTS/CTS):** Horizontal (crossed, Brown↔White)
- **Block C (DTR/DSR):** Horizontal (straight per-signal, Grey↔Purple)
- **Tie rows:** None (add Purple↔Pink on PR side if printer needs carrier)
