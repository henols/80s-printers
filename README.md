# Nakajima NP-2200 9 pin matrix printer

# NP-2200-2 Board — Summary (raw markdown)

## Identification / markings
- Board ID: **NP-2200-2**
- PCB code: **220-31012**
- Text: **NEC-14T**, **MADE IN JAPAN**
- Manufacturer on silkscreen: **NAKAJIMA PRECISION CO., LTD**
- EPROM label: **NP-2200 D0000403**

## Architecture overview
- Core: **NEC D8049** MCU with companion **D8155** (RAM + I/O + timer) and **D8255** (PPI).
- Program/storage: **MBM27128K** (27128 EPROM, 16 KB) + **NEC D4016CX-20** SRAM (2 KB × 8).
- Glue logic: Hitachi **74LS** family (LS04, LS05, LS02, LS373, LS00) and open-collector **7406/7407**.
- Drivers: Two **Sanyo LB1234** driver/pre-driver ICs.
- Custom module: **IC116 NH-2200B** potted hybrid (board-specific interface/driver).
- Clocking: X101 crystal/resonator present (freq not printed in photos).

## Connectors (top-level)
- Two 36-pin micro-ribbon (Centronics-style) external connectors (left and right edges).
- Internal headers: **CN101** 26-pin 2×13, **CN103** shrouded IDC (dual row, pin count not fully visible).
- Small harness headers: **CN104** 1×7, **CN105** 1×10, **CN106** 1×3 (white), **CN107** 1×2 (red).

## Configuration / service
- DIP switches: **DS101**, **DS102** (8-position each).
- Jumpers: **J101–J105** (solder-select pads).
- Test points: **TP1–TP6**.
- Trimmer: **VR/TVR** single-turn potentiometer.
- LEDs and typical R/C networks (many **RA10x** resistor arrays; numerous **R1xx/C1xx** discretes).

## Likely purpose / era
- Mid-1980s printer/typewriter engine controller (matches parts/connector set and “Nakajima Precision” silkscreen).


## ICs (markdown table)

| RefDes | Exact top marking | Manufacturer | Part / Type | Function | Package | Notes |
|---|---|---|---|---|---|---|
| IC101 | D8049HC 055 | NEC | 8049 MCU (MCS-48) | Main controller | DIP-40 | — |
| IC102 | D8155C-2 | NEC | 8155 | RAM + I/O + timer | DIP-40 | — |
| IC103 | D8255AC-2 | NEC | 8255 PPI | Programmable peripheral interface | DIP-40 | — |
| IC104 | MBM27128K (sticker: "NP-2200 D0000403") | Fujitsu | 27128 EPROM | Program ROM (16 KB) | DIP-28 (socket) | — |
| IC105 | D4016CX-20 | NEC | 4016 SRAM | 2 KB × 8 static RAM | DIP-24 | — |
| IC106 | HD74LS373P | Hitachi | 74LS373 | Octal transparent latch | DIP-20 | — |
| IC107 | HD74LS02P | Hitachi | 74LS02 | Quad 2-input NOR | DIP-14 | — |
| IC108 | HD74LS04P | Hitachi | 74LS04 | Hex inverter | DIP-14 | — |
| IC109 | HD74LS04P | Hitachi | 74LS04 | Hex inverter | DIP-14 | — |
| IC111 | HD7406P (4J3T) | Hitachi | 7406 | Hex inverter, open-collector | DIP-14 | — |
| IC112 | HD7407P (4J4T) | Hitachi | 7407 | Hex buffer, open-collector | DIP-14 | — |
| IC113 | HD74LS05P | Hitachi | 74LS05 | Hex inverter, open-collector | DIP-14 | — |
| IC114 | LB1234 (4D3) | Sanyo | LB1234 | Driver / power pre-driver | DIP-16 | — |
| IC115 | LB1234 (4D3) | Sanyo | LB1234 | Driver / power pre-driver | DIP-16 | — |
| IC116 | NH-2200B (LGIH) | (Nakajima hybrid) | Potted hybrid module | Board-specific interface/driver | SIP/DIP-style module | Exact function unknown from markings |
| IC126 | HD74LS04P | Hitachi | 74LS04 | Hex inverter | DIP-14 | — |
| IC129 | HD74LS04P | Hitachi | 74LS04 | Hex inverter | DIP-14 | — |
| IC131 | HD74LS00P | Hitachi | 74LS00 | Quad 2-input NAND | DIP-14 | — |


## Connectors (markdown table)

| RefDes | Silkscreen text (nearby) | Connector type / style | Pins / rows | Location on PCB | Notes |
|---|---|---|---|---|---|
| CN101 | "CN101" + "26" | Dual-row pin header (unshrouded) | 26 (2×13) | Lower middle | Internal harness/ribbon |
| CN102 | (left external micro-ribbon) | Micro-ribbon (Centronics-style), female with bail latches | 36 | Left edge | External I/O |
| CN103 | "CN103" | IDC box header (shrouded), dual-row | 2×?? (likely 2×13) | Inboard of left micro-ribbon | Pin count not fully visible |
| (right micro-ribbon) | — | Micro-ribbon (Centronics-style), female with bail latches | 36 | Right edge | External I/O; refdes not visible |
| (right IDC) | — | IDC box header (shrouded), dual-row | 2×?? | Inboard of right micro-ribbon | Refdes/pin count obscured |
| CN104 | "CN104" + "7" | JST-style vertical friction-lock header (white) | 7 (1×7) | Right edge, upper | Small harness |
| CN105 | "CN105" + "10" | JST-style vertical friction-lock header (white) | 10 (1×10) | Right edge, lower | Small harness |
| CN106 | "CN106" | Mini JST-style vertical header (white) | 3 (1×3) | Top edge, near MCU | Small signal/power |
| CN107 | "CN107" | Mini JST-style vertical header (red) | 2 (1×2) | Top edge, near MCU | Likely power/trigger |

| Reference   | Part                          | Type                | Purpose                                 |
|:------------|:------------------------------|:--------------------|:----------------------------------------|
| IC101       | D8049HC 055                   | NEC Microcontroller | 8-bit MCU, board controller             |
| IC102       | D8155C-2                      | NEC Peripheral IC   | Static RAM + I/O ports + timer          |
| IC103       | D8255AC-2                     | NEC Peripheral IC   | Programmable Peripheral Interface (PPI) |
| IC104       | D4016CX-20                    | NEC RAM             | 16K DRAM                                |
| IC105       | Unknown (under EPROM)         | EPROM (socketed)    | Firmware storage                        |
| IC106       | HD74LS373P                    | Latch               | Octal transparent latch                 |
| IC107       | HD74LS02P                     | Logic               | Quad 2-input NOR gate                   |
| IC108       | EPROM NP-2200 D0000403        | EPROM               | Firmware storage                        |
| IC109       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC110       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC111       | HD74LS00P                     | Logic               | Quad 2-input NAND gate                  |
| IC112       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC113       | HD74LS02P                     | Logic               | Quad 2-input NOR gate                   |
| IC114       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC115       | LB1234 4D3                    | Driver IC           | Likely motor/solenoid driver            |
| IC116       | LB1234 4D3                    | Driver IC           | Likely motor/solenoid driver            |
| IC117       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC118       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC119       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC120       | HD74LS02P                     | Logic               | Quad 2-input NOR gate                   |
| IC121       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC122       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC123       | HD74LS04P                     | Logic               | Hex inverter                            |
| IC124       | HD74LS00P                     | Logic               | Quad 2-input NAND gate                  |
| IC125       | HD74LS00P                     | Logic               | Quad 2-input NAND gate                  |
| IC126       | HD74LS00P                     | Logic               | Quad 2-input NAND gate                  |
| IC127       | HD74LS00P                     | Logic               | Quad 2-input NAND gate                  |
| IC128       | HD74LS00P                     | Logic               | Quad 2-input NAND gate                  |
| CN101       | Pin header 26p                | Connector           | Internal connector                      |
| CN102       | Large blue connector (36-pin) | Centronics          | External printer/parallel interface     |
| CN103       | 2-row 18p header              | Connector           | Internal connection                     |
| CN104       | White 6-pin header            | Connector           | Peripheral/power                        |
| CN105       | White 6-pin header            | Connector           | Peripheral/power                        |
| RA101-RA105 | Resistor arrays               | Pull-up networks    | Bus termination / pull-ups              |
| Cxxx        | Various ceramic capacitors    | Decoupling          | Noise suppression and stabilization     |
| Rxxx        | Various resistors             | Resistors           | Biasing, limiting current               |
| VR101       | Variable Resistor             | Trim pot            | Adjustable calibration                  |
