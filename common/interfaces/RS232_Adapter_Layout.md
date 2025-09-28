# Generic RS-232 adapter, Wiring Card

## Pin Mapping

```
DB9 → DB25
  2  TXD (Yellow) →  3  RXD
  3  RXD (Blue)   →  2  TXD
  5  GND (Black)  →  7  GND
  7  RTS (Brown)  →  4  RTS
  8  CTS (White)  →  5  CTS
  4  DTR (Grey)   → 20  DTR
  6  DSR (Purple) →  6  DSR
  1  DCD (Pink)   →  8  DCD
```

---
### DB9-Female (PC / DTE)
```
  5 4 3 2 1
   9 8 7 6
```
| Pin | Signal | Color |
|-----|--------|-------|
| 1   | DCD    | Pink  |
| 2   | TXD    | Yellow|
| 3   | RXD    | Blue  |
| 4   | DTR    | Grey  |
| 5   | GND    | Black |
| 6   | DSR    | Purple|
| 7   | RTS    | Brown |
| 8   | CTS    | White |
| 9   | RI (unused) | —  |

---

### DB25-Male (Printer / DCE)
```
  13··········1
   25········14
```
| Pin | Signal | Color |
|-----|--------|-------|
| 2   | TXD    | Yellow|
| 3   | RXD    | Blue  |
| 4   | RTS    | Brown |
| 5   | CTS    | White |
| 6   | DSR    | Purple|
| 7   | GND    | Black |
| 8   | DCD    | Pink  |
| 20  | DTR    | Grey  |
| ... | (others unused) | —  |

---


## Jumper Blocks (2×2)

### Block A — TXD / RXD
```
+---------+---------+
| PC TXD  | PR TXD  |   PC/PR TXD = Yellow
| (Yellow)| (Blue)  |   PC/PR RXD = Blue
+---------+---------+   
| PR RXD  | PC TXD  |
| (Blue)  | (Yellow)|
+---------+---------+
```
- **Vertical shunts:** PC TXD → PR RXD, PC RXD → PR TXD (straight)
- **Horizontal shunts:** PC TXD → PR TXD, PC RXD → PR RXD (null)

### Block B — RTS / CTS
```
+---------+---------+
| PC RTS  | PR CTS  |   PC/PR RTS = Brown
| (Brown) | (White) |   PC/PR CTS = White
+---------+---------+   
| PR RTS  | PC CTS  |
| (White) | (Brown) |
+---------+---------+
```
- **Vertical shunts:** PC RTS → PR CTS, PC CTS → PR RTS (straight)
- **Horizontal shunts:** PC RTS → PR RTS, PC CTS → PR CTS (null)

### Block C — DTR / DSR
```
+---------+---------+
| PC DTR  | PR DSR  |   PC/PR DTR = Grey
| (Grey)  | (Purple)|   PC/pr DSR = Purple
+---------+---------+   
| PR DDR  | PC DSR  |
| (Purple)| (Grey)  |
+---------+---------+
```
- **Vertical shunts:** PC DTR → PR DSR, PC DSR → PR DTR (straight)
- **Horizontal shunts:** PC DTR → PR DTR, PC DSR → PR DSR (null)

---

## Tie Rows (1×3 headers)

### D‑PC (from DB9)
```
[DTR Grey] [DSR Purple] [DCD Pink]
```
Shunt locally as needed (e.g. DTR↔DSR, DSR↔DCD).

### D‑PR (from DB25)
```
[DTR Grey] [DSR Purple] [DCD Pink]
```
Shunt if printer requires (e.g. DSR↔DCD).

---

## Notes

- **GND (Black)** always tied: DB9‑5 ↔ DB25‑7  
- Use heat‑shrink or tags to mark ends.  
- Verify with multimeter before powering:  
  - With Block A vertical → DB9‑2 ↔ DB25‑3, DB9‑3 ↔ DB25‑2  
  - With Block B horizontal → DB9‑7 ↔ DB25‑5, DB9‑8 ↔ DB25‑4  
  - With Block C horizontal → DB9‑4 ↔ DB25‑20, DB9‑6 ↔ DB25‑6  
