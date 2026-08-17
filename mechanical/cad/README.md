# ONYX-NULL CAD Source

This directory contains editable mechanical CAD source files for ONYX-NULL.

These files represent the authoritative mechanical design.

---

# Purpose

CAD source files should allow contributors to:

- inspect the design
- modify the enclosure
- adjust dimensions
- create new revisions
- verify mechanical clearances
- generate manufacturing exports
- reproduce the enclosure

---

# Preferred Characteristics

Mechanical source files should use formats that are:

- editable
- documented
- broadly accessible
- suitable for version control where practical
- exportable to standard formats

---

# Possible CAD Tools

Potential tools include:

- FreeCAD
- OpenSCAD
- Blender for non-critical geometry
- other documented CAD tools

If proprietary CAD software is used, an open or broadly compatible export should also be provided where possible.

---

# Directory Convention

Future structure may look like:

```text
cad/
├── enclosure/
│   ├── front/
│   ├── rear/
│   └── internal-frame/
├── buttons/
├── switches/
├── battery/
├── display/
├── pcb/
└── reference/
```

---

# Revision Naming

Example:

```text
ONX-ENC-P0
ONX-ENC-P1
ONX-ENC-R1-REV-A
```

CAD filenames should include meaningful revision identifiers.

Example:

```text
ONX-ENC-R1-REV-A-front.FCStd
ONX-ENC-R1-REV-A-back.FCStd
ONX-ENC-R1-REV-A-frame.FCStd
```

---

# Dimensional Units

Preferred design unit:

```text
millimeters
```

Dimensions should not depend on ambiguous unit assumptions.

---

# Coordinate System

Mechanical models should use a consistent coordinate system.

Recommended:

```text
X = device width
Y = device height
Z = device thickness
```

The origin should be documented for assembly models.

---

# Reference Geometry

Models should include reference geometry for major components such as:

- PCB
- battery
- display
- USB-C connector
- cameras
- speakers
- hardware switches
- antennas

Reference models should identify whether dimensions come from:

- manufacturer CAD
- datasheet
- direct measurement
- estimated geometry

---

# Tolerances

Critical dimensions should document tolerances.

Examples include:

- PCB mounting holes
- USB-C opening
- display opening
- button travel
- screw bosses
- battery compartment
- FPC clearances
- switch openings

---

# Design for Assembly

CAD should account for:

- assembly order
- screw access
- cable installation
- connector access
- battery insertion
- display installation
- switch installation
- board removal

A component should not become impossible to remove because another permanently blocks it.

---

# Design for Repair

Where practical, designs should support replacing:

- battery
- display
- USB-C assembly
- speakers
- microphones
- buttons
- mainboard

without destroying the enclosure.

---

# Hardware Switches

Physical privacy controls require special attention.

CAD should document:

```text
Switch Position:
Switch Travel:
Actuation Force:
Opening Size:
Internal Clearance:
Mechanical Protection:
State Marking:
```

Switches should resist accidental activation.

---

# Manufacturing

Mechanical source files should eventually support:

- FDM printing
- resin printing
- CNC machining
- injection molding

depending on development stage.

Design rules may differ depending on manufacturing method.

---

# Documentation

Each major CAD revision should include:

```text
Revision:
Date:
Designer:
Compatible Hardware:
Material:
Manufacturing Method:
Known Issues:
Changes:
```

---

# Current Status

No production CAD currently exists.

Early CAD work should focus on:

1. internal component fit
2. mounting
3. switch access
4. connector access
5. thermal clearance
6. basic ergonomics
