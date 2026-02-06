# Single-Stage Pipeline Register (Valid / Ready Handshake)

This repository implements a fully synthesizable **single-stage pipeline register** in **SystemVerilog** using a standard **valid/ready handshake protocol**.  
The design correctly handles backpressure, prevents data loss or duplication, and resets to a clean empty state.

🔗 **EDA Playground Simulation Link**  
https://www.edaplayground.com/x/dz2J

---

## Project Objective

Design and verify a one-deep pipeline buffer that:
- Accepts input data only when `in_valid` and `in_ready` are asserted
- Stores data internally until consumed
- Drives `out_valid` correctly
- Supports downstream backpressure via `out_ready`
- Resets to a clean empty state

---

## Design Overview

The module sits between an input and output interface and implements a **single-entry pipeline register** using a valid/ready handshake.

### Handshake Conditions
- **Input Transfer:** `in_valid && in_ready`
- **Output Transfer:** `out_valid && out_ready`
- **Ready Logic:**  
  `in_ready = !buffer_full || (out_ready && out_valid)`

---

## Features

- Fully synthesizable SystemVerilog RTL
- Parameterized data width
- Standard valid/ready handshake
- Correct backpressure handling
- Active-low asynchronous reset
- Testbench with waveform dumping
- Compatible with industry simulators

---

## Project Structure
