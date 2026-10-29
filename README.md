# DIN-Rail Training Rig: Duty/Standby Pump Rotation and Interlocks (In Progress)

**Two classic BMS plant sequences built on a physical DIN-rail training rig with real 24 V pumps: duty/standby rotation with run-hour balancing and automatic failover, and a state machine with permissives, proving and lockouts. The same sequences are later re-implemented on the rig's Trend IQ411 and in a PLC environment for comparison.**

[![YouTube](https://img.shields.io/badge/YouTube-The%20Control%20Cabinet-red?logo=youtube)](https://www.youtube.com/channel/UC5Cupmz7vlfcodpCX7k8iuQ)
[![Portfolio](https://img.shields.io/badge/Portfolio-the--control--cabinet-24292f?logo=github)](https://github.com/the-control-cabinet/the-control-cabinet)
![Domain](https://img.shields.io/badge/BMS-plant%20sequences-blue)
![Status](https://img.shields.io/badge/Status-In%20progress-yellow)

> **The short version:**
> - **The rig:** a 400 × 300 mm enclosure; row 1 holds a 24 V PSU (HDR-60-24), MCB and a Trend IQ411; row 2 is a rotating zone with an ESP32-S3 and opto-isolated 24 V relays driving **two brushless 24 V submersible pumps**.
> - **Duty/standby (#7):** lead/lag rotation by run hours or weekly, failover on a proving failure, alarms, and a manual override.
> - **Interlocks (#9):** a pump state machine (OFF → START → PROVING → RUN → FAULT/LOCKOUT) with permissives (low-level dry-run protection, hand/off/auto), proving within a time window, and a latched lockout with a reset.
> - **Why it matters:** the same interlock thinking guards the OpenTherm changeover on the real boiler.

**Portfolio position:** Automation level · plant sequences (portfolio #7 and #9). Re-implemented in: [Trend IQ411](https://github.com/the-control-cabinet/trend-iq411-commissioning) · [PLC (IEC 61131-3)](https://github.com/the-control-cabinet/plc-reimplementation-iec61131). Rig companions: [PID rig exercise](https://github.com/the-control-cabinet/pid-anti-hunt-control-rig) (#8) · [Trend IQ411](https://github.com/the-control-cabinet/trend-iq411-commissioning) (#12). Applied later in: [OpenTherm changeover interlock](https://github.com/the-control-cabinet/opentherm-boiler-control-esphome)

---

## Documents

| Doc | Contents |
|---|---|
| [01 The rig](docs/01-rig.md) | Layout, power, I/O, safety |
| [02 Duty/standby sequence (#7)](docs/02-duty-standby.md) | Rotation, failover, run-hour balancing |
| [03 Interlocks and state machine (#9)](docs/03-interlocks-state-machine.md) | States, permissives, proving, lockout |

## Roadmap
- [ ] Complete row 2 wiring (relays, pilot lights, fused terminals)
- [ ] Add flow proving and a low-level float
- [ ] Duty/standby live on the ESP32 with run-hour records
- [ ] State machine and permissive tests recorded
- [ ] Re-implement on the Trend IQ411 and in CODESYS; compare

## Skills demonstrated (as built)
| Skill | Evidence |
|---|---|
| Plant sequences | Duty/standby with failover and run-hour balancing |
| Interlocks | State machine with permissives, proving, lockout |
| Panel building | DIN-rail layout, segregation, fusing |
| Testing | Forced transitions and permissive tests recorded |

📺 [The Control Cabinet on YouTube](https://www.youtube.com/channel/UC5Cupmz7vlfcodpCX7k8iuQ)

*Built and documented by James · part of [The Control Cabinet BMS portfolio](https://github.com/the-control-cabinet/the-control-cabinet). MIT Licence.*
