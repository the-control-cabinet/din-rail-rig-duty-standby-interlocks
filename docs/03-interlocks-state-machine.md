# 03 Interlocks and state machine (#9)

[← Back to README](../README.md)

```mermaid
stateDiagram-v2
    [*] --> OFF
    OFF --> START: demand AND permissives OK
    START --> PROVING: pump output on
    PROVING --> RUN: flow proven within 10 s
    PROVING --> FAULT: not proven
    RUN --> OFF: demand removed
    RUN --> FAULT: flow lost > 5 s
    FAULT --> LOCKOUT: 3 faults in 1 h
    FAULT --> OFF: auto-reset after 5 min
    LOCKOUT --> OFF: manual reset
```

| Permissive | Effect if lost |
|---|---|
| Low-level float OK | Immediate stop (dry-run protection), alarm |
| Mode = AUTO | No automatic start |
| No lockout | No start until reset |

**Test plan:** each transition forced and observed; each permissive removed in each state; logged in [data/test-record.csv](../data/test-record.csv).
