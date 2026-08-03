# u-blox NEO-M8N

## Purpose

Provides GNSS positioning, speed, altitude, heading, and UTC time for the cycling computer.

---

## Why Selected?

Selected because it provides:

- Mature and reliable GNSS solution
- Low power consumption
- UART interface
- Stable NMEA output
- Widely adopted in embedded applications

---

## Interfaces

UART

Output Protocol

- NMEA

Common Sentences

- GGA
- GLL
- GSA
- GSV
- RMC
- VTG

---

## Responsibilities

- Position
- Speed
- Altitude
- UTC Time
- Navigation source

---

## Current Development

- [v] Module selected
- [ ] UART driver
- [ ] NMEA parser
- [ ] Navigation module

---

## Future Work

- UBX protocol optimization
- Faster update rate
- GNSS filtering

---

## References

- NEO-M8N Datasheet
- Receiver Description