# ONYX-NULL Firmware

This directory contains firmware source, firmware-related research, configuration, build instructions, update procedures, and documentation for embedded controllers and hardware components used by ONYX-NULL.

Firmware is treated as part of the ONYX-NULL trust model.

A component running firmware should not be considered trustworthy solely because the hardware itself is physically present in the device.

---

# Directory Purpose

This directory may eventually contain:

```text
firmware/
├── README.md
├── CONTROLLERS.md
├── UPDATE_MODEL.md
├── BUILDING.md
├── boot/
├── ec/
├── privacy-controller/
├── power-controller/
├── radio/
└── third-party/
```

Not every subsystem will necessarily require custom firmware.

---

# Firmware Philosophy

ONYX-NULL should prefer firmware that is:

- open source
- reproducibly buildable
- signed where appropriate
- minimal
- auditable
- replaceable
- isolated from unrelated system resources
- documented
- updateable without weakening security

Where proprietary firmware is unavoidable, ONYX-NULL should document:

```text
WHAT IT DOES
     +
WHAT IT CAN ACCESS
     +
HOW IT IS UPDATED
     +
HOW IT IS VERIFIED
     +
HOW IT IS ISOLATED
```

---

# Trust Model

Firmware may execute below or beside the operating system.

Examples include:

- boot firmware
- embedded-controller firmware
- USB controller firmware
- radio firmware
- power-management firmware
- secure-element firmware
- touchscreen firmware
- storage-controller firmware

Because firmware can operate outside normal application sandboxing, its privileges must be explicitly documented.

---

# Firmware Classification

Firmware should use one of the following classifications:

```text
OPEN

SOURCE-AVAILABLE

PROPRIETARY

ROM

UNKNOWN
```

These classifications describe source availability, not security quality.

---

# Firmware Status

Firmware entries may use:

```text
RESEARCHING
CANDIDATE
IN-USE
DEPRECATED
REPLACED
UNSUPPORTED
```

---

# Firmware Inventory

Every firmware-bearing component should eventually document:

```text
Component:

Manufacturer:

Part Number:

Firmware Name:

Firmware Version:

Firmware Classification:

Source Available:

License:

Build System:

Firmware Storage Location:

Firmware Update Method:

Firmware Signature Verification:

Rollback Protection:

Host Privileges:

DMA Access:

Network Access:

Storage Access:

Secret Access:

Physical Isolation:

Hardware Reset Available:

Physical Power Control:

Known Vulnerabilities:

Replacement Options:

Notes:
```

---

# Open Firmware

Where ONYX-NULL develops firmware directly, source code should be published in this repository.

Source should include:

- build instructions
- toolchain requirements
- dependency versions
- flashing instructions
- recovery instructions
- test procedures
- release hashes
- licensing information

Where practical, source files should include SPDX license identifiers so licensing information stays associated with the file itself.

---

# Proprietary Firmware

Some third-party components may require proprietary firmware.

These components are not automatically rejected.

Instead, ONYX-NULL should ask:

1. Is this firmware necessary?
2. What privileges does it have?
3. What hardware can it access?
4. Can it access system memory?
5. Can it access cryptographic keys?
6. Can it communicate externally?
7. Can it be physically disabled?
8. Is it signed?
9. Can older firmware be installed?
10. Is an open alternative available?

The answers should be documented.

See:

`../docs/PROPRIETARY_COMPONENTS.md`

---

# Firmware Boundaries

A desirable architecture looks like:

```text
┌───────────────────────────────┐
│        TRUSTED SYSTEM         │
│                               │
│ CPU                           │
│ RAM                           │
│ Storage                       │
│ NULL/OS                       │
└──────────────┬────────────────┘
               │
        Restricted Interface
               │
        ┌──────▼───────┐
        │ Peripheral   │
        │ Firmware     │
        │              │
        │ Potentially  │
        │ Untrusted    │
        └──────────────┘
```

Firmware compromise should not automatically imply complete system compromise.

---

# Firmware Updates

Firmware updates should eventually provide:

- authenticity verification
- integrity verification
- version tracking
- rollback protection where practical
- recovery procedures
- documented release notes

A firmware update system should not accept arbitrary unsigned firmware unless a deliberate development mode is enabled.

---

# Development Mode

Development hardware may require relaxed firmware restrictions.

If so, development mode should be clearly distinguishable from a production-security configuration.

Possible differences include:

```text
DEVELOPMENT

Unsigned Firmware Allowed
Debug Interface Enabled
Rollback Allowed
Verbose Logging Enabled
```

versus:

```text
RELEASE

Signed Firmware Required
Debug Restricted
Rollback Protected
Minimal Logging
```

---

# Firmware Release Naming

Example:

```text
ONX-FW-P0-v0.1.0

ONX-EC-v0.1.0

ONX-PRIVACY-v0.1.0

ONX-BOOT-v0.1.0
```

Firmware releases should correspond to specific source commits.

---

# Firmware Testing

Testing may include:

- successful boot
- failed-signature rejection
- corrupted-image rejection
- downgrade rejection
- recovery
- power-loss during update
- invalid input handling
- interface fuzzing
- hardware-switch interaction
- watchdog behavior
- long-duration stability

---

# Documentation Requirement

Firmware security claims must identify whether they are:

```text
DESIGN GOAL
IMPLEMENTED
TESTED
INDEPENDENTLY REVIEWED
```

Do not describe a planned protection as though it already exists.

---

# Current Status

**Stage:** Research / Pre-P0

No production ONYX-NULL firmware currently exists.

Early P0 development will primarily use firmware supplied by selected development hardware while the project documents those dependencies and defines the future firmware trust model.
