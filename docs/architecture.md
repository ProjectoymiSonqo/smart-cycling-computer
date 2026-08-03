# System Architecture

## Design Goals

The Smart Cycling Computer is designed with the following goals:

- Modular architecture
- Reliable data acquisition
- Low power consumption
- Extensible hardware interface
- Maintainable firmware

## Overview

The Smart Cycling Computer is built around the nRF52840 and integrates navigation, wireless connectivity, rider sensors, air-data sensing, display, and power management.

The system is designed to remain modular so that sensing, display, and expansion modules can evolve independently.

## High-Level Architecture


```text

                         +----------------------+
                         |      Mobile App      |
                         |   Configuration /    |
                         |    Data Transfer     |
                         +----------+-----------+
                                    |
                                   BLE
                                    |
+-------------+      UART      +----+-----+       SPI / I2C      +-------------+
|  NEO-M8N    +--------------->|          +--------------------->|   Display   |
|    GNSS     |                | nRF52840 |                      +-------------+
+-------------+                |          |
                               |          |<------------------------+
+-------------+    BLE / ANT+  |          |                         |
| Heart Rate  +--------------->|          |                         |
| Power Meter |                +----+-----+                         |
+-------------+                   ^   |                             |
                                  |   |                             |
                         +--------+   | I2C / SPI                   |
                         |            v                             |
                         |    +---------------+                     |
                         |    | Differential  |<---- Pitot Tube ----+
                         |    | Pressure      |
                    I2C  |    | Sensor        |
                         |    +-------+-------+
			 |    
                         +----------+ 
                                    |         
                                    |
                         +----------------------+
                         |  Power Management    |
                         | Battery / Fuel Gauge |
                         +----------------------+

                         Expansion Interface
                                  |
                         Front Light Module
```

## Software Architecture

Application

────────────────────

Ride Manager

Navigation

Display UI

Settings

────────────────────

Services

Location Manager

Sensor Manager

BLE Manager

Power Manager

────────────────────

Drivers

GNSS Driver

Display Driver

Pressure Driver

────────────────────

HAL 