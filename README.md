# Pre-Decoder and Column Decoder Design

## Overview

This project focuses on the design and implementation of a **Pre-Decoder and Column Decoder** for SRAM architecture as part of the **Memory Design and Test (MDT)** course. The design targets optimized decoding for an **8192 × 32-bit memory** while meeting setup, hold, area, and power constraints.

The project includes:

* Decoder architecture selection
* Transistor sizing using Logical Effort
* Schematic design
* Layout implementation
* DRC/LVS verification
* Setup/Hold characterization
* Delay and PPA analysis

---

# Project Details

### Project Title

Pre-Decoder and Column Decoder Design

### Team Members

* Vishal Kumar Singh (MT25157)
* Charu Singh (MT25111)
* Neeti Mishra (MT25130)

### Course

Memory Design and Test (MDT)

### Guided By

Dr. Anuj Grover

---

# Design Specifications

| Parameter         | Requirement                |
| ----------------- | -------------------------- |
| Memory Size       | 8192 × 32                  |
| Address Bits      | 13                         |
| Input Capacitance | < 10 fF                    |
| Output Loading    | 512 Rows                   |
| Setup Time        | < 500 ps                   |
| Hold Time         | Negative at FF/1.32V/-40°C |

---

# Memory Architecture

### Address Distribution

* Higher address bits (A12–A4) used for row decoding
* Lower address bits (A3–A0) used for column decoding

### Selected Configuration

The final architecture uses:

* Three 3:8 pre-decoders

### Reason for Selection

* Best area-power tradeoff
* Reduced tapping complexity
* Lower power consumption

---

# Design Methodology

## Pre-Decoder Design

* Implemented 3:8 decoder architecture
* Logical effort method used for transistor sizing
* Multiple sizing iterations performed for optimization

## Column Decoder Design

* Designed bitline selection logic
* Decoder optimized for delay and load requirements
* Tri-state inverter based improvements implemented

---

# Simulation and Verification

Performed:

* EZwave simulations
* Delay analysis
* Setup and hold characterization

### Setup & Hold Time Results

| Input | Setup Time | Hold Time |
| ----- | ---------- | --------- |
| 000   | 199.6 ps   | -61.7 ps  |
| 111   | 263.15 ps  | -84.44 ps |

### Clock Delay

| Condition      | Delay |
| -------------- | ----- |
| SS/1.08V/125°C | 53 ps |
| FF/1.32V/-40°C | 42 ps |

---

# Layout Design

## 3:8 Pre-Decoder Layout

### Final Area

287.01 µm²

### Improvements

* Area optimization
* Track reduction
* Finger optimization
* Routing correction

## Column Decoder Layout

### Final Area

591.661 µm²

---

# DRC & LVS Verification

Successfully achieved:

* DRC Clean Layout
* LVS Matched Design

Common issues resolved:

* LUP/dup DRC errors
* SCONNECT issues
* Routing alignment problems

---

# Challenges Faced

* Column decoder transistor sizing optimization
* Area reduction with finger-based layouts
* Debugging DRC/LVS violations
* Maintaining setup and hold constraints

---

# Future Work

* Further area optimization
* Delay reduction
* Improved PPA optimization
* Transmission gate implementation
* Parasitic extraction and post-layout analysis

---

# Tools Used

| Stage            | Tool             |
| ---------------- | ---------------- |
| Schematic Design | Cadence Virtuoso |
| Simulation       | EZwave           |
| Layout Design    | Virtuoso Layout  |
| Verification     | DRC/LVS Tools    |

---

# Conclusion

The project successfully implemented a pre-decoder and column decoder architecture for SRAM addressing while meeting timing and loading constraints. The final design achieved optimized area, acceptable setup/hold timing, and clean DRC/LVS verification through multiple design iterations and transistor-level optimizations.
