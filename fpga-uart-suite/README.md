# FPGA UART Transmitter

This project implements an **8-bit UART transmitter** in Verilog, along with a simple top module that continuously sends incrementing data bytes.  
Designed and simulated in **Vivado 2025.1**.

---

## 📂 Files

- `src/uart_byte_tx.v` → Core UART transmitter module
- `src/uart_tx_test.v` → Test top module that drives the transmitter with auto-generated data
- `tb/` (optional) → Place testbench files here
- `doc/` (optional) → Waveform screenshots or block diagrams

---

## 🔧 Features

- Configurable baud rate (9600 / 19200 / 38400 / 57600 / 115200)
- 8-bit parallel data input
- Start bit, data bits, stop bit transmission
- `uart_tx_test` module:
  - Generates a periodic send signal
  - Sends incrementing byte values (`0x00 → 0xFF`)
  - Useful for quick demo on FPGA board (connect `uart_tx` to USB-UART module)

---

## 🧪 Simulation

1. Add RTL files to Vivado project:
   - `src/uart_byte_tx.v`
   - `src/uart_tx_test.v`
2. Create a testbench if needed (e.g. drive `Clk` and `Reset_n`).
3. Run behavioral simulation in Vivado (xsim).
4. Observe `uart_tx` waveform — it should generate a proper UART frame for each byte.

---

## 🚀 Next Steps

- Add **UART Receiver (uart_byte_rx)**
- Build **UART loopback demo** (TX → RX → LED/7-seg)
- Add **FIFO buffer** between TX and system logic
- Connect to PC and verify data with a serial terminal (115200 baud recommended)

---
