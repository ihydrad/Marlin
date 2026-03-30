# EEPROM Backup — Anet A8 / AM8

Snapshot taken from Repetier-Server. Restore with commands below after flashing.

## Parameters

| Parameter | Value |
|---|---|
| Steps/mm X | 100 |
| Steps/mm Y | 100 |
| Steps/mm Z | 400 |
| Steps/mm E | 95 |
| Hotend PID Kp | 21.00 |
| Hotend PID Ki | 1.25 |
| Hotend PID Kd | 86.00 |
| Bed PID Kp | 181.00 |
| Bed PID Ki | 30.69 |
| Bed PID Kd | 711.74 |
| Home Offset X | -7 |
| Home Offset Y | -43 |
| Home Offset Z | 0 |

## Restore G-code

```gcode
; Steps/mm
M92 X100 Y100 Z400 E95

; Max acceleration (mm/s^2)
M201 X3000 Y3000 Z100 E10000

; Max feedrate (mm/s)
M203 X200 Y200 Z8 E150

; Default acceleration
M204 P1500 R1500 T1500

; Advanced settings (jerk, min segment time)
M205 B20000 S0 T0 X10 Y10 Z0.40 E5.00

; Home offset
M206 X-7 Y-43 Z0

; Hotend PID
M301 P21.00 I1.25 D86.00

; Bed PID
M304 P181.00 I30.69 D711.74

; Save to EEPROM
M500
```
