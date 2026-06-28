# Single-Cell Li-Ion 3.3V / 500mA Low-Noise Power Supply

> A compact, robust, low-noise **3.3V linear regulator PCB** designed for **single-cell Li-ion batteries**, featuring comprehensive input protection, thermal optimization, and debugging support. Ideal for embedded systems, RF modules, sensors, and precision analog applications. 

---

## 📌 Overview

This project implements a **2-layer PCB** that converts the output of a **single-cell Li-ion battery (3.8V–4.2V)** into a clean, regulated **3.3V** supply capable of delivering up to **500mA** continuous current.

The design emphasizes:

* Low output noise
* High reliability
* Battery efficiency
* Robust input protection
* Thermal performance
* Easy testing and debugging

---

## ✨ Features

* 🔋 Single-cell Li-ion input (3.8V–4.2V)
* ⚡ Fixed 3.3V regulated output
* 🔌 500mA continuous output current
* 🛡 Reverse polarity protection
* ⚠ Resettable overcurrent protection (PTC Fuse)
* ⚡ TVS surge & ESD protection
* 🔥 Thermal pad with via array
* 💡 Power indication LED
* 📈 Dedicated test points
* 🧩 2-layer PCB with optimized power routing

---

## 📊 Specifications

| Parameter             | Value        |
| --------------------- | ------------ |
| Input Voltage         | 3.8V–4.2V DC |
| Output Voltage        | 3.3V DC      |
| Output Current        | 500mA Max    |
| Typical Load          | 450mA        |
| Operating Temperature | 0°C–70°C     |
| PCB Layers            | 2            |
| Board Size            | <40mm × 20mm |

---

# Architecture

```text
Li-Ion Battery
      │
      ▼
Resettable PTC Fuse
      │
      ▼
TVS Diode Protection
      │
      ▼
P-Channel MOSFET
(Reverse Polarity Protection)
      │
      ▼
LP5912-3.3 LDO
      │
      ▼
Output Capacitors
      │
      ▼
3.3V Output Connector
```

---

# Main Components

| Reference | Part           | Purpose                     |
| --------- | -------------- | --------------------------- |
| U1        | LP5912-3.3DRVR | 500mA Low-Noise LDO         |
| Q1        | DMP2035U-7     | Reverse Polarity Protection |
| F1        | MF-NSMF110-2   | Resettable PTC Fuse         |
| D1        | SMAJ5.0CA      | TVS Surge Protection        |
| D2        | BZT52C6V8      | MOSFET Gate Protection      |
| D3        | Green LED      | Power Indicator             |
| C1        | 22µF           | Input Bulk Capacitor        |
| C2        | 100nF          | Input Decoupling            |
| C3        | 10µF           | Output Stability            |
| C4        | 100nF          | High-Frequency Filtering    |

---

# Protection Features

## Reverse Polarity Protection

A **DMP2035U-7 P-Channel MOSFET** replaces the traditional Schottky diode, providing:

* Lower voltage drop
* Higher efficiency
* Better battery utilization
* Automatic reverse battery protection

---

## Overcurrent Protection

The **MF-NSMF110-2 resettable PTC fuse** protects against:

* Output short circuits
* Component failures
* Excessive current draw

The fuse automatically resets once the fault is removed.

---

## Surge & ESD Protection

A **SMAJ5.0CA TVS diode** protects the input from:

* ESD events
* Hot-plug transients
* Voltage spikes
* Input surges

---

## MOSFET Gate Protection

A **6.8V Zener diode (BZT52C6V8)** limits the gate-to-source voltage to protect the MOSFET during transient events.

---

# Capacitor Configuration

## Input Side

| Component | Function                       |
| --------- | ------------------------------ |
| 22µF      | Bulk energy storage            |
| 100nF     | High-frequency noise filtering |

Placed close to the regulator input to minimize parasitic inductance.

---

## Output Side

| Component | Function                       |
| --------- | ------------------------------ |
| 10µF      | Stability & transient response |
| 100nF     | High-frequency filtering       |

Located directly beside the regulator output pin.

---

# Test Points

For simplified debugging and validation:

| Test Point | Signal |
| ---------- | ------ |
| TP1        | VIN    |
| TP2        | VOUT   |
| TP3        | GND    |

Compatible with multimeters and oscilloscopes.

---

# Thermal Design

Worst-case power dissipation:

```text
P = (VIN − VOUT) × IOUT

= (4.2 − 3.3) × 0.5

≈ 0.45 W
```

Thermal improvements include:

* Exposed thermal pad
* Thermal via array
* Continuous ground plane
* Ground stitching vias

These features improve heat dissipation and ensure reliable operation within the specified temperature range.

---

# PCB Layout Highlights

* 2-layer PCB
* Continuous bottom ground plane
* Wide VIN/VOUT copper pours
* Short power paths
* Thermal vias beneath LDO
* Ground stitching
* 45° trace routing
* Clearly labeled silkscreen
* Dedicated debugging test points

---

# Applications

This board is suitable for:

* 🤖 Embedded Systems
* 📡 RF Modules
* 📟 IoT Devices
* 🌡 Sensor Nodes
* 🎧 Low-Noise Analog Circuits
* 🔬 Laboratory Prototypes
* 📷 Portable Electronics

---

# Repository Structure

```text
├── Hardware/
│   ├── Schematic/
│   ├── PCB/
│   ├── Gerbers/
│   └── BOM/
│
├── Images/
│   ├── PCB_3D.png
│   ├── Top_View.png
│   └── Bottom_View.png
│
├── Datasheets/
│
├── Docs/
│   └── Design_Notes.pdf
│
└── README.md
```

---

# Future Improvements

* Buck-Boost version for full battery discharge operation
* Battery charging circuit integration
* Fuel gauge implementation
* USB Type-C power input
* Power-path management
* Load switch enable/disable control

---

# License

This project is released under the **MIT License**.

---

## 👨‍💻 Author

**Nikhil Abboju**
Power Electronics Engineer | PCB Design | Embedded Hardware | KiCad

