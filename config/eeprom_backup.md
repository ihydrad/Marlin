# EEPROM Backup — Anet A8 / AM8

**Дата снятия:** 2026-03-30  
**Источник:** Repetier-Server → EEPROM Settings

## Restore G-code (M503 equivalent)

```gcode
; Steps/mm
M92 X100.00 Y100.00 Z400.00 E95.00

; Max feedrate (mm/s)
M203 X300.00 Y300.00 Z5.00 E25.00

; Max acceleration (mm/s²)
M201 X2000.00 Y2000.00 Z100.00 E10000.00

; Acceleration: print / retract / travel
M204 P400.00 R1000.00 T1000.00

; Advanced: min feedrate, min travel feedrate, min segment time (us)
M205 S0.00 T0.00 B20000.00

; Home offset
M206 X-7.00 Y-43.00 Z0.00

; Hotend PID
M301 P21.00 I1.25 D86.00

; Bed PID
M304 P181.00 I30.69 D711.74

; Preheat PLA
; hotend=190°C  bed=60°C  fan=0

; Preheat ABS
; hotend=240°C  bed=90°C  fan=0

; Save to EEPROM
M500
```
