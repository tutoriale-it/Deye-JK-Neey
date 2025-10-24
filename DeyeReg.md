# Deye Inverter - Modbus Register Map

## PV (Panouri Solare)

| Registru | Nume | Tip Date | Descriere | Unitate | Factor |
|----------|------|----------|-----------|---------|--------|
| 109 | PV1 Voltage | U_WORD | Tensiune PV1 | V | x0.1 |
| 110 | PV1 Current | U_WORD | Curent PV1 | A | x0.1 |
| 111 | PV2 Voltage | U_WORD | Tensiune PV2 | V | x0.1 |
| 112 | PV2 Current | U_WORD | Curent PV2 | A | x0.1 |
| 186 | PV1 Power | U_WORD | Putere PV1 | W | - |
| 187 | PV2 Power | U_WORD | Putere PV2 | W | - |
| 108 | Day PV Energy | U_WORD | Energie PV zilnică | kWh | x0.1 |
| 96 | Total PV Energy | U_WORD | Energie PV totală | kWh | x0.1 |

## BATTERY (Baterie)

| Registru | Nume | Tip Date | Descriere | Unitate | Factor |
|----------|------|----------|-----------|---------|--------|
| 182 | Battery Temperature | U_WORD | Temperatură baterie | °C | -1000, x0.1 |
| 183 | Battery Voltage | U_WORD | Tensiune baterie | V | x0.01 |
| 184 | Battery SOC | U_WORD | State of Charge | % | - |
| 190 | Battery Power | S_WORD | Putere baterie | W | x(-1) |
| 191 | Battery Current | S_WORD | Curent baterie | A | x(-0.01) |
| 70 | Day Battery Charge | U_WORD | Încărcare zilnică | kWh | x0.1 |
| 71 | Day Battery Discharge | U_WORD | Descărcare zilnică | kWh | x0.1 |
| 204 | Battery Capacity (READ) | U_WORD | Capacitate baterie (doar citire) | Ah | - |

## BATTERY SETTINGS (Scriere)

| Registru | Nume | Tip Date | Descriere | Unitate | Factor | Min | Max |
|----------|------|----------|-----------|---------|--------|-----|-----|
| 202 | Absorption Voltage | U_WORD | Tensiune absorbție | V | x100 | 48.0 | 60.0 |
| 203 | Float Voltage | U_WORD | Tensiune float | V | x100 | 48.0 | 58.0 |
| 205 | Empty Voltage | U_WORD | Tensiune goală | V | x100 | 40.0 | 50.0 |
| 210 | Max Charge Current | U_WORD | Curent max încărcare | A | - | 0 | 200 |
| 211 | Max Discharge Current | U_WORD | Curent max descărcare | A | - | 0 | 200 |
| 220 | Shutdown Voltage | U_WORD | Tensiune shutdown | V | x100 | 40.0 | 50.0 |
| 221 | Restart Voltage | U_WORD | Tensiune restart | V | x100 | 40.0 | 52.0 |
| 222 | Low Voltage | U_WORD | Tensiune scăzută | V | x100 | 40.0 | 52.0 |

**⚠️ NOTĂ IMPORTANTĂ:** Pentru scriere în registri, trebuie folosit `use_write_multiple: true` în ESPHome!

## GRID (Rețea)

| Registru | Nume | Tip Date | Descriere | Unitate | Factor |
|----------|------|----------|-----------|---------|--------|
| 150 | Grid Voltage | U_WORD | Tensiune grid | V | x0.1 |
| 160 | Grid Current | S_WORD | Curent grid | A | x0.01 |
| 169 | Grid Power | S_WORD | Putere grid | W | - |
| 79 | Grid Frequency | U_WORD | Frecvență grid | Hz | x0.01 |
| 76 | Day Grid Import | U_WORD | Import zilnic | kWh | x0.1 |
| 81 | Day Grid Export | U_WORD | Export zilnic | kWh | x0.1 |

## LOAD (Sarcină/Casă)

| Registru | Nume | Tip Date | Descriere | Unitate | Factor |
|----------|------|----------|-----------|---------|--------|
| 154 | Load Voltage | U_WORD | Tensiune load | V | x0.1 |
| 178 | Load Power | S_WORD | Putere load | W | - |
| 193 | Load Frequency | U_WORD | Frecvență load | Hz | x0.01 |
| 84 | Day Load Energy | U_WORD | Energie load zilnică | kWh | x0.1 |

## INVERTER

| Registru | Nume | Tip Date | Descriere | Unitate | Factor |
|----------|------|----------|-----------|---------|--------|
| 59 | Inverter Status | - | Status invertor (0=Standby, 1=Self-check, 2=Normal, 3=Alarm, 4=Fault) | - | - |
| 90 | Inverter Temperature | U_WORD | Temperatură invertor | °C | -1000, x0.1 |

---

**Total: 38 registri Modbus**

## Cum se citește factorul:

- `x0.1` = înmulțește cu 0.1 (divide cu 10)
- `x0.01` = înmulțește cu 0.01 (divide cu 100)
- `x100` = înmulțește cu 100 (pentru scriere)
- `x(-1)` = înmulțește cu -1 (inversează semnul)
- `-1000, x0.1` = scade 1000, apoi înmulțește cu 0.1
