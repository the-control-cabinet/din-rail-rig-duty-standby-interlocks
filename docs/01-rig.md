# 01 The rig

[← Back to README](../README.md)

| Row | Contents |
|---|---|
| Trunking: top | Mains entry (segregated) |
| **Row 1 (fixed)** | 24 V DC PSU (Mean Well HDR-60-24), MCB, **Trend IQ411** (230 V variant, on its own MCB) |
| Trunking: middle | |
| **Row 2 (rotating zone)** | ESP32-S3 on a screw-terminal board, opto-isolated 24 V relay modules, 2N7000 buffer stage, fused terminal blocks, 24 V pilot lights |
| Trunking: bottom | I/O exit to the pump tank |

**Process:** two brushless 24 V submersible pumps in a small tank; DS18B20 probes; ⟨to add⟩ a flow-proving switch (or pump current sensing) and a low-level float switch.

**Safety:** mains segregated top, I/O bottom; the 24 V side is fused per circuit; pumps never run dry (low-level permissive, hardwired where possible).
