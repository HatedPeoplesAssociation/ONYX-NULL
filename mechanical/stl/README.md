# ONYX-NULL STL Exports

This directory contains STL files intended primarily for 3D printing ONYX-NULL prototype mechanical components.

---

# Purpose

STL exports may include:

- prototype enclosures
- brackets
- internal frames
- button caps
- switch guards
- display mounts
- battery holders
- test fixtures
- jigs

---

# Source of Truth

STL files are generated manufacturing artifacts.

Editable source files belong in:

`../cad/`

Changes should be made to the CAD source whenever possible and then exported again.

---

# Naming Convention

Example:

```text
ONX-ENC-P0-front.stl

ONX-ENC-P0-back.stl

ONX-ENC-P0-frame.stl

ONX-ENC-R1-REV-A-front.stl
```

---

# Print Information

Each printable design should document recommended settings.

Template:

```text
Model:

Revision:

Material:

Printer Type:

Nozzle:

Layer Height:

Wall Count:

Top Layers:

Bottom Layers:

Infill:

Supports:

Orientation:

Estimated Print Time:

Estimated Material:

Post Processing:

Notes:
```

---

# Materials

Prototype materials may include:

- PLA
- PETG
- ABS
- ASA
- TPU
- nylon

Material selection should account for:

- temperature
- impact resistance
- flexibility
- dimensional stability
- ease of printing
- battery proximity

---

# Heat Considerations

PLA may soften at temperatures encountered in hot environments.

For later functional prototypes, materials with improved temperature resistance may be preferable.

Thermal behavior should be tested rather than assumed.

---

# Print Orientation

Orientation can significantly affect:

- strength
- surface finish
- tolerances
- support requirements
- screw-boss strength

Recommended orientation should be documented for each part.

---

# Tolerances

Consumer 3D printers vary in accuracy.

Prototype designs should allow realistic tolerances for:

- screws
- buttons
- switches
- connectors
- snap features
- PCB mounting
- display openings

Fit tests should be performed before printing full enclosures where practical.

---

# Threaded Fasteners

Potential fastening methods include:

- self-tapping screws
- heat-set threaded inserts
- captive nuts
- machine screws

For reusable prototypes, heat-set inserts may provide better durability than repeatedly threading screws directly into printed plastic.

---

# Prototype Labels

Printed prototypes should ideally include revision information.

Example:

```text
ONYX-NULL
ONX-ENC-P1
REV-A
```

This prevents confusion when multiple physical revisions exist.

---

# Test Fixtures

This directory may also contain fixtures used to test:

- PCB mounting
- switch placement
- USB-C alignment
- display fit
- speaker alignment
- antenna clearance

Small test fixtures should be preferred before printing an entire enclosure when evaluating a single mechanical feature.

---

# Safety

3D printed parts located near:

- batteries
- high-current circuits
- hot regulators
- charging circuitry

must use materials and clearances appropriate for expected temperatures.

A successful print does not automatically mean the enclosure is safe for long-term use.

---

# Current Status

No final ONYX-NULL printable enclosure currently exists.

Initial STL files will focus on fit testing and prototype mounting.
