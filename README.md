# ARM Timer Interrupt and UART Communication

## Overview
In this lab, the ARM Generic Interrupt Controller (GIC) and UART JTAG were configured to demonstrate the use of interrupts. The project specifically involved setting up ARM’s interval timer to trigger an interrupt every two seconds, displaying the message "Timeout" via UART.

---

## Lab Objectives
- Gain practical experience with ARM interval timers and interrupts.
- Learn to configure and handle interrupts using the ARM Generic Interrupt Controller (GIC).
- Practice UART communication through the JTAG interface on ARM-based hardware.

---

## Technical Details

### ARM Interval Timer

**Configuration:**
- Two 32-bit registers (split into lower and upper 16 bits).
- Timer1 used (base address: `0xFF202000`).

**Register Map:**

| Address Offset | Access | Description                                       |
|----------------|--------|---------------------------------------------------|
| base           | R/W    | Status Register                                   |
| base+4         | R/W    | Control Register                                  |
| base+8         | R/W    | Timeout period (lower 16 bits)                    |
| base+12        | R/W    | Timeout period (upper 16 bits)                    |
| base+16        | R/W    | Counter Snapshot (lower 16 bits)                  |
| base+20        | R/W    | Counter Snapshot (upper 16 bits)                  |

**Interrupt:** Triggered on timeout.

---

### UART JTAG Peripheral

**Base Address:** `0xFF201000`

**Register Map:**

| Address Offset | Access | Description                                       |
|----------------|--------|---------------------------------------------------|
| base           | R/W    | Data Register (send/receive)                      |
| base+4         | R/W    | Control Register                                  |

**Interrupt:** Triggered on data-received or transmission-ready states.

---

## Project Tasks Completed

1. **Interval Timer Setup**
   - Determined initial counter values to achieve a precise 2-second interval.
   - Configured and initialized ARM Timer1, enabling interrupts.

2. **Interrupt Service Routine (ISR)**
   - Implemented ISR to handle timer interrupts.
   - ISR functionality included sending the string "Timeout" followed by a newline character (`0x0A`) to the UART JTAG interface.

3. **Testing & Verification**
   - Verified timer functionality and interrupt handling by observing periodic output in the UART JTAG interface.

---

## Technologies and Tools
- **ARM Assembly**
- **Interrupt-driven programming**
- **UART communication via JTAG**
- **ARM GIC** (Generic Interrupt Controller)

---

## Lab Environment
- Used CPULator ARM simulator environment for ARM assembly and peripheral simulation.

---
