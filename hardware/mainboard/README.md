# ONYX-NULL Mainboard

This directory contains research, schematics, PCB layouts, manufacturing files, testing records, and documentation for the ONYX-NULL mainboard.

The planned first custom mainboard is designated:

**ONX-M1**

---

# Purpose

ONX-M1 will eventually replace the collection of development boards used during early ONYX-NULL prototypes.

Early prototype architecture may look like:

```text
Compute Board
    │
    ├── USB Audio Board
    ├── Wi-Fi Adapter
    ├── Power Board
    ├── Display Adapter
    └── Loose Wiring
```

The goal of ONX-M1 is to consolidate required functionality into a reproducible custom carrier/mainboard.

```text
┌───────────────────────────────┐
│            ONX-M1             │
│                               │
│ Compute Module                │
│                               │
│ ├── Power Management          │
│ ├── USB-C                     │
│ ├── Display                   │
│ ├── Touch                     │
│ ├── Audio                     │
│ ├── Wi-Fi Interface           │
│ ├── Privacy Controls          │
│ ├── Sensors                   │
│ └── Debug Interfaces          │
│                               │
└───────────────────────────────┘
```

---

# Design Goals

The mainboard should prioritize:

- electrical reliability
- documented interfaces
- repairability
- modularity
- hardware isolation
- separate power domains
- accessible debug interfaces
- minimal proprietary dependencies
- component availability
- reproducibility
- understandable schematics
- documented test points

---

# Compute Architecture

The initial custom mainboard will likely use a System-on-Module or Compute Module rather than directly routing a modern application processor and RAM.

This allows early revisions to focus on:

- peripheral integration
- power
- security architecture
- radio isolation
- audio
- display
- mechanical design

without requiring ONYX-NULL to immediately design a complete high-speed application processor board.

---

# Planned Interfaces

Possible interfaces include:

- USB-C
- USB 2.0
- USB 3.x
- I²C
- SPI
- UART
- GPIO
- MIPI DSI
- HDMI during early prototypes
- digital audio
- analog audio
- camera interfaces
- debug UART
- hardware kill-switch signals
- battery monitoring
- sensor interfaces

---

# Privacy-Sensitive Components

Special consideration should be given to:

- microphones
- cameras
- Wi-Fi
- Bluetooth
- GNSS
- optional cellular modem

Where practical, these components should have independent hardware power control.

---

# Power Domains

The mainboard should investigate separate power domains such as:

```text
MAIN POWER
    │
    ├── COMPUTE
    │
    ├── DISPLAY
    │
    ├── AUDIO
    │
    ├── SWITCH ──► WI-FI / BT
    │
    ├── SWITCH ──► MICROPHONE
    │
    ├── SWITCH ──► CAMERAS
    │
    └── SWITCH ──► OPTIONAL RADIO
```

The exact design will depend on component requirements.

---

# Debug Interfaces

Debug interfaces should be intentionally designed rather than accidentally exposed.

Potential interfaces include:

- UART
- SWD
- JTAG
- USB recovery
- boot-mode pins

For each interface document:

- purpose
- physical location
- voltage
- authentication
- production behavior
- whether it should remain enabled

---

# Mainboard Revision Convention

```text
ONX-M1-REV-A
ONX-M1-REV-B
ONX-M1-REV-C
```

Every revision must document:

- changes
- known defects
- test results
- compatibility
- manufacturing notes
- rework instructions
- security implications

---

# Required Revision Files

Example:

```text
mainboard/
└── ONX-M1/
    ├── REV-A/
    │   ├── README.md
    │   ├── schematic/
    │   ├── pcb/
    │   ├── manufacturing/
    │   ├── tests/
    │   └── ERRATA.md
```

---

# Before Fabrication

Do not order a mainboard revision until:

- electrical rule checking passes
- design rule checking passes
- footprints are verified
- connector orientation is verified
- voltage rails are verified
- maximum currents are calculated
- component availability is checked
- critical datasheets have been reviewed
- thermal concerns have been considered
- required test points exist
- schematic has received independent review where possible

---

# Revision A Philosophy

Revision A is expected to contain mistakes.

The objective is not perfection.

The objective is to create a testable board from which the next revision can be improved.

All discovered mistakes should be documented publicly.

---

# Current Status

No ONX-M1 schematic currently exists.

Development begins only after ONX-P0 validates the core architecture.
