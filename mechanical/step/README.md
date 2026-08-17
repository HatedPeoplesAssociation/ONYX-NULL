# ONYX-NULL STEP Exports

This directory contains STEP exports of ONYX-NULL mechanical designs and hardware reference models.

STEP files are intended for interoperability between CAD packages and for integration with PCB and mechanical workflows.

---

# Purpose

STEP models may be used for:

- enclosure design
- PCB mechanical verification
- interference checking
- assembly visualization
- manufacturing communication
- component placement
- documentation

---

# Source of Truth

STEP files are exported artifacts.

The editable CAD files under:

`../cad/`

remain the authoritative mechanical source where applicable.

---

# Naming Convention

Example:

```text
ONX-ENC-P0.step

ONX-ENC-R1-REV-A.step

ONX-M1-REV-A-PCB.step

battery-reference.step

display-reference.step
```

---

# Component STEP Models

Reference component models may include:

- PCB
- display
- battery
- USB-C connector
- speakers
- cameras
- switches
- buttons
- connectors
- antennas

---

# Source Documentation

Each externally obtained STEP model should record:

```text
Component:
Manufacturer:
Part Number:
Source:
Date Retrieved:
License / Redistribution Status:
Accuracy:
Notes:
```

Do not redistribute third-party CAD files unless redistribution is permitted.

---

# Accuracy Classification

Reference models may use:

```text
MANUFACTURER

MEASURED

SIMPLIFIED

ESTIMATED
```

Meaning:

### MANUFACTURER

Provided directly by the component manufacturer.

### MEASURED

Created using physical measurements.

### SIMPLIFIED

Geometry intentionally reduced for mechanical reference.

### ESTIMATED

Some dimensions are approximate.

---

# Coordinate Alignment

Where practical, exported assemblies should use a consistent origin and orientation.

Recommended device orientation:

```text
+X = Right
+Y = Top
+Z = Front
```

If another coordinate system is used, document it.

---

# PCB Integration

STEP exports of PCB assemblies should include:

- PCB outline
- major connectors
- tall components
- hardware switches
- camera modules
- USB-C connector
- mounting holes
- antenna keep-out zones

---

# Interference Checking

STEP assemblies should eventually be used to verify:

- PCB fits enclosure
- battery does not collide
- buttons align
- switches align
- display fits
- ports remain accessible
- cables have clearance
- speakers have acoustic space

---

# Versioning

STEP exports should correspond to a specific design revision.

Do not silently overwrite old production-relevant exports.

Example:

```text
ONX-ENC-R1-REV-A.step
ONX-ENC-R1-REV-B.step
```

---

# Current Status

No final ONYX-NULL STEP assemblies currently exist.

Initial STEP files will be created once P0 hardware dimensions are established.
