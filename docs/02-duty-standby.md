# 02 Duty/standby sequence (#7)

[← Back to README](../README.md)

| Function | Rule |
|---|---|
| Lead selection | Lowest run hours becomes lead at each rotation; rotation weekly **or** every N run hours ⟨choose⟩ |
| Start | On demand, start the lead; prove flow within 10 s |
| Failover | Lead fails to prove → lead to FAULT (alarm P2) → start the lag automatically |
| Both failed | Alarm P1 (no pump available) |
| Exercise | Each idle pump runs for 30 s weekly (anti-seize), as real plant does |
| Manual | Hand/off/auto per pump; hand mode bypasses rotation but **not** safety permissives |
| Records | Run hours, starts and faults per pump; rotation log |
