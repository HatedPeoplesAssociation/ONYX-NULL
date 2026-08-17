# ONYX-NULL Prototype Policy

## Purpose

This document defines how ONYX-NULL prototypes are named, documented, tested, and preserved.

---

# Core Rule

Every prototype should answer a specific engineering question.

A prototype should not exist merely because it is the next number.

---

# Prototype Questions

Examples:

```text
Can the platform boot?

Can the display work?

Can the system make a VoIP call?

Can the system operate from battery?

Can Wi-Fi be physically isolated?

Can the microphone be physically disconnected?

Can a custom mainboard replace development boards?
```

---

# Naming

Use:

```text
ONX-P0
ONX-P1
ONX-P2
```

Minor iterations may use:

```text
ONX-P0.1
ONX-P0.2
```

---

# Revision Meaning

A new prototype number should reflect a meaningful architectural change.

Small fixes do not necessarily require an entirely new prototype generation.

---

# Prototype Status

Use one of:

```text
PLANNED

BUILDING

ACTIVE

PASS

PARTIAL

FAILED

SUPERSEDED

ARCHIVED
```

---

# Build Freeze

Once a prototype begins formal testing, freeze its configuration where practical.

Do not silently replace parts during testing.

If hardware changes:

- document the change
- update revision
- rerun affected tests

---

# Prototype Evidence

Preserve:

- photographs
- BOM
- source commit
- OS version
- firmware
- configuration
- test results
- known issues

---

# Failed Prototypes

Failed prototypes should remain documented.

A failed prototype may contain important information for future builders.

---

# Physical Labels

Where practical, physical prototypes should be labeled.

Example:

```text
ONYX-NULL
ONX-P1
BUILD 03
```

This prevents confusion between visually similar hardware.

---

# Safety

Unsafe prototypes should be clearly marked.

Examples:

```text
DO NOT CHARGE UNATTENDED

NO BATTERY PROTECTION

EXPOSED MAINS

THERMAL TEST ONLY
```

Unsafe experimental hardware should never be represented as ordinary usable hardware.

---

# Prototype Promotion

A prototype should not be promoted to the next stage until its defined goals have been evaluated.

Example:

```text
P0 Goal:
First PSTN call

Result:
PASS

Proceed:
P1
```

---

# Archiving

Superseded prototypes should retain:

- documentation
- photographs
- configuration
- results

Physical hardware may also be preserved where practical.

---

# Current Status

ONYX-NULL is preparing for P0.
