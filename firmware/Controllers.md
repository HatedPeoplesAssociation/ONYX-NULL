# ONYX-NULL Firmware Controllers

This document tracks controllers that may execute firmware independently of the main ONYX-NULL operating system.

---

# Purpose

Modern embedded devices often contain multiple processors beyond the primary application CPU.

Examples include:

- embedded controllers
- power controllers
- USB controllers
- touchscreen controllers
- battery-management controllers
- radios
- secure elements
- sensor hubs

ONYX-NULL should explicitly document every independent processing environment.

---

# Controller Template

Use the following template for each controller:

```text
Controller Name:

Manufacturer:

Part Number:

Purpose:

CPU Architecture:

Firmware Required:

Firmware Open:

Firmware License:

Firmware Storage:

Firmware Update Mechanism:

Host Interface:

System Privileges:

DMA Access:

Storage Access:

Network Access:

Secret Access:

Can Initiate Host Communication:

Hardware Reset:

Physical Power Control:

Debug Interface:

Secure Boot:

Firmware Signing:

Rollback Protection:

Known Vulnerabilities:

Replacement Options:

Notes:
```

---

# Trust Classification

Controllers should be classified as:

```text
TRUSTED

RESTRICTED

UNTRUSTED

UNKNOWN
```

---

# Embedded Controller

A future ONYX-NULL embedded controller may coordinate functions such as:

- buttons
- privacy switches
- power state
- charging state
- LEDs
- hardware state reporting
- thermal events

The embedded controller should not automatically receive access to:

- user files
- application memory
- cryptographic secrets
- communications content

unless required by architecture.

---

# Privacy Controller

ONYX-NULL may eventually use a dedicated privacy controller.

Possible responsibilities:

- read physical kill-switch state
- control load switches
- report physical hardware state
- drive trusted hardware indicators

Conceptual architecture:

```text
PHYSICAL SWITCH
      │
      ▼
PRIVACY CONTROLLER
      │
      ├──► LOAD SWITCH
      │       │
      │       ▼
      │     RADIO
      │
      └──► HARDWARE INDICATOR
```

The main operating system should not be able to falsely report a powered-off physical state if the hardware remains powered.

---

# Controller Isolation

For each controller determine:

- what buses it can access
- whether it can DMA
- whether it can modify boot state
- whether it can access storage
- whether it can communicate externally
- whether it can access microphones
- whether it can access cameras
- whether it can reset the main processor

---

# Debug Interfaces

Controller debug interfaces may include:

- SWD
- JTAG
- UART
- USB bootloader
- vendor programming interface

Each should document:

```text
Enabled During Development:

Enabled In Release:

Authentication:

Physical Access Required:

Risk:
```

---

# Current Status

No ONYX-NULL custom controller has been selected.

Controller architecture will be defined after the P0 platform and hardware isolation requirements are better understood.
