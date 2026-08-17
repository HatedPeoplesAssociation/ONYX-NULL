# ONYX-NULL Hardware

This directory contains the electrical hardware designs, component documentation, bills of materials, prototype records, testing information, and manufacturing files for ONYX-NULL.

ONYX-NULL hardware is being developed around four primary principles:

1. Owner control
2. Explicit trust boundaries
3. Physical isolation where practical
4. Reproducibility

The hardware is currently experimental.

---

## Directory Structure

```text
hardware/
├── README.md
├── COMPONENT_REGISTER.md
├── prototypes/
│   └── P0/
├── mainboard/
├── radio/
├── power/
├── audio/
└── bom/
```

---

# Hardware Philosophy

ONYX-NULL should not depend solely on software controls for privacy-sensitive hardware when practical physical controls can provide stronger guarantees.

For example:

```text
SOFTWARE CONTROL

Operating System
      │
      ▼
"Disable Wi-Fi"
      │
      ▼
Wi-Fi Driver
      │
      ▼
Wi-Fi Firmware
```

This requires trusting multiple software and firmware layers.

A future ONYX-NULL design should instead support controls such as:

```text
POWER SOURCE
     │
     ▼
PHYSICAL SWITCH
     │
     X
     │
WI-FI RADIO
```

When the circuit is physically disconnected, software should not be capable of restoring power to the radio.

---

# Hardware Goals

Long-term hardware goals include:

- open schematics
- open PCB layouts
- documented bills of materials
- repairable construction
- replaceable components where practical
- physically controllable radios
- physically controllable microphones
- physically controllable cameras
- isolated untrusted peripherals
- secure key storage
- USB-C charging
- documented debug interfaces
- documented firmware dependencies
- reproducible manufacturing files
- clearly documented hardware revisions
- minimal unnecessary proprietary components

---

# Hardware Trust Model

Each significant component should eventually document:

```text
Component:
Manufacturer:
Part Number:
Function:

Hardware Documentation Available:
Firmware Required:
Firmware Open:
Driver Open:

CPU Access:
DMA Access:
Network Access:
Storage Access:
Secret Access:

Isolation Mechanism:
Physical Power Control:

Known Vulnerabilities:
Replacement Options:
```

Components should not be assumed trustworthy simply because they are required.

---

# Proprietary Components

ONYX-NULL may initially require proprietary components or firmware.

These dependencies must be documented rather than hidden.

See:

`../docs/PROPRIETARY_COMPONENTS.md`

The long-term strategy is:

```text
IDENTIFY
   ↓
DOCUMENT
   ↓
ISOLATE
   ↓
MINIMIZE
   ↓
REPLACE
```

Where replacement is not practical, the remaining trust requirement should be explicitly documented.

---

# Hardware Revisions

Hardware revisions should use explicit revision identifiers.

Example:

```text
ONX-P0

ONX-M1-REV-A
ONX-M1-REV-B
ONX-M1-REV-C

ONX-R1-REV-A
```

Every physical PCB should include its revision in the silkscreen.

Example:

```text
ONYX-NULL
ONX-M1 REV-A
```

---

# Source Files

Native editable design files are the authoritative hardware source.

Preferred tools currently include:

- KiCad for schematics and PCB design
- open or broadly accessible CAD formats for mechanical integration

Generated manufacturing files such as Gerbers do not replace editable design sources.

---

# Manufacturing Files

Each production-capable board should eventually provide:

- schematic source
- schematic PDF
- PCB source
- Gerber files
- drill files
- BOM
- pick-and-place file
- assembly drawing
- board dimensions
- stackup information
- fabrication notes
- assembly notes
- test procedure
- known errata

---

# Hardware Testing

Hardware testing should eventually include:

- voltage verification
- current measurement
- power sequencing
- thermal testing
- hardware-switch verification
- peripheral isolation testing
- USB testing
- audio testing
- suspend/resume behavior
- battery testing
- radio power verification
- fault testing where safe
- long-duration stability testing

Results should be documented and tied to a specific hardware revision.

---

# Safety

Power electronics and lithium batteries require special care.

ONYX-NULL prototypes should use reputable protected cells and established charging and protection designs.

Experimental battery circuits should not be treated as production-safe until properly reviewed and tested.

---

# Current Status

**Stage:** Research / Pre-P0

No production ONYX-NULL hardware currently exists.

The first major hardware milestone is:

> **ONYX-NULL P0 successfully places its first telephone call.**
