# NMEA Protocol

## Purpose

NMEA is the primary communication protocol between the GNSS receiver and the cycling computer.

It provides navigation data through UART.

---

## Why NMEA?

Selected because:

- Default output of NEO-M8N
- Human-readable
- Easy debugging
- Well documented

---

## Required Sentences

| Sentence | Purpose |
|----------|---------|
| GGA | Position & Altitude |
| RMC | Speed & Time |
| VTG | Ground Speed |
| GSA | Satellite Status |
| GSV | Satellite Information |

---

## Responsibilities

- Position
- Speed
- Altitude
- UTC Time

---

## Current Development

- [x] Protocol selected
- [ ] UART reception
- [ ] Parser
- [ ] Error handling

---

## Future Work

- UBX migration
- Faster update rate

---

## References

- NMEA 0183
- u-blox Receiver Manual

## Note

- Ceramic Patch Antenna is essential