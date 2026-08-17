# ONYX-NULL Embedded Controller Firmware

This directory is reserved for firmware used by a future ONYX-NULL embedded controller.

---

# Possible Responsibilities

The embedded controller may eventually manage:

- power button
- hardware buttons
- battery state
- charging state
- hardware privacy switches
- indicator LEDs
- thermal events
- wake events
- low-level power sequencing

---

# Security Principle

The embedded controller should receive only the authority required for its responsibilities.

It should not unnecessarily access:

- user storage
- application memory
- cryptographic keys
- microphone content
- camera content
- network traffic

---

# Potential Architecture

```text
PHYSICAL CONTROLS
       │
       ▼
┌────────────────┐
│ Embedded       │
│ Controller     │
└───────┬────────┘
        │
        ├── Power Management
        ├── LEDs
        ├── Buttons
        └── Privacy State
```

---

# Firmware Goals

Future EC firmware should aim for:

- minimal code
- open-source implementation
- simple interfaces
- documented protocol
- secure update process
- watchdog
- fault handling
- testability

---

# Host Interface

Potential interfaces include:

- I²C
- SPI
- UART
- GPIO

The final interface should minimize unnecessary attack surface.

---

# Fail-Safe Behavior

Privacy controls should fail in a predictable manner.

For example, the design should explicitly define what happens if:

- EC crashes
- EC firmware is corrupted
- host OS stops responding
- battery is critically low
- hardware switch changes during boot

---

# Current Status

No embedded-controller hardware has been selected.
