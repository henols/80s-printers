# Nakajima NP-2200 9 pin matrix printer

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
