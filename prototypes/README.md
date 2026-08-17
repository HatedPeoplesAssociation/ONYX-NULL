# ONYX-NULL Prototypes

This directory contains records, build notes, photographs, test results, configuration details, and lessons learned from ONYX-NULL prototype devices.

Prototype documentation exists to preserve the real development history of the project.

ONYX-NULL prototypes are expected to fail, change, and reveal design mistakes.

Those failures should be documented rather than hidden.

---

# Directory Structure

```text
prototypes/
├── README.md
├── PROTOTYPE_POLICY.md
├── BUILD_RECORD_TEMPLATE.md
└── P0/
```

Future revisions may expand to:

```text
prototypes/
├── P0/
├── P1/
├── P2/
├── EVT/
└── DVT/
```

---

# Prototype Philosophy

The purpose of a prototype is not to look finished.

The purpose is to answer specific engineering questions.

The expected progression is:

```text
QUESTION
   ↓
PROTOTYPE
   ↓
TEST
   ↓
FAILURE / SUCCESS
   ↓
DOCUMENT
   ↓
REDESIGN
```

---

# Prototype Naming

Suggested naming convention:

```text
ONX-P0
ONX-P0.1
ONX-P0.2

ONX-P1
ONX-P1.1

ONX-P2
```

Later development stages may use:

```text
EVT
DVT
R1
```

---

# Prototype Stages

## P0 — Bench Prototype

Primary goal:

> Successfully place the first ONYX-NULL telephone call.

P0 may be:

- oversized
- powered from the wall
- built from development boards
- connected with jumper wires
- mounted on a workbench
- mechanically unfinished

---

## P1 — Portable Prototype

Primary goals may include:

- battery operation
- handheld form
- basic enclosure
- portable audio
- stable Wi-Fi
- reliable VoIP

---

## P2 — Isolation Prototype

Primary goals may include:

- physical radio isolation
- microphone isolation
- camera isolation
- improved power architecture
- hardware privacy-state reporting

---

## EVT — Engineering Validation

The purpose of EVT is to determine whether the electrical design works as intended.

Potential goals:

- custom PCB validation
- power validation
- interface validation
- thermal validation
- hardware bring-up
- major subsystem testing

---

## DVT — Design Validation

The purpose of DVT is to determine whether the integrated product design meets its requirements.

Potential goals:

- enclosure
- reliability
- ergonomics
- production-like hardware
- repairability
- security testing
- privacy testing

---

# Required Prototype Documentation

Every significant prototype should record:

```text
Prototype ID:

Build Date:

Builder:

Objective:

Hardware:

Software:

Firmware:

Power:

Network:

Enclosure:

Cost:

Known Problems:

Tests Performed:

Result:

Lessons Learned:
```

---

# Photographs

Every significant prototype should be photographed.

Useful photographs include:

- full bench setup
- front
- back
- internal wiring
- PCB
- connectors
- switches
- power system
- test equipment
- enclosure

Photographs should clearly identify the prototype revision.

---

# Prototype Configuration

A prototype should document exact components rather than only broad descriptions.

Preferred:

```text
Compute:
Manufacturer + exact model

Display:
Manufacturer + exact part number

Wi-Fi:
Exact chipset/module

Audio:
Exact codec/interface
```

Avoid:

```text
some Raspberry Pi

USB audio thing

Wi-Fi adapter
```

---

# Software Configuration

Record:

- operating system
- kernel
- packages
- application versions
- configuration
- patches
- build commit

---

# Firmware Configuration

Record:

- firmware component
- firmware version
- source status
- hashes where relevant

---

# Cost Tracking

Every prototype should track approximate cost.

Example:

```text
Compute:
$00.00

Display:
$00.00

Audio:
$00.00

Power:
$00.00

Mechanical:
$00.00

Misc:
$00.00

TOTAL:
$00.00
```

---

# Failures

Prototype documentation should include failures.

Examples:

- wrong connector
- unstable power
- broken driver
- audio feedback
- poor thermals
- failed suspend
- bad PCB footprint
- insufficient current
- enclosure collision

Do not rewrite project history to make development appear cleaner than it was.

---

# Lessons Learned

Each prototype should conclude with:

```text
KEEP

CHANGE

REMOVE

RESEARCH

NEXT
```

This turns prototype results into actionable development decisions.

---

# Release Warning

Prototype hardware is experimental.

Do not describe prototype revisions as production-ready or security-certified.

---

# Current Status

The first active prototype is:

**ONYX-NULL P0**
