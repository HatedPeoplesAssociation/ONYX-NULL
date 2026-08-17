# ONYX-NULL Test Policy

## Purpose

This document defines how ONYX-NULL tests should be written, performed, documented, and reviewed.

---

# Core Rule

Every significant technical claim should eventually have a corresponding test or clearly documented reason why direct testing is not practical.

---

# Test Requirements

A test should answer:

```text
What property is being tested?

Why does it matter?

What equipment is required?

What is the exact procedure?

What result is expected?

What was actually observed?

Can another person reproduce it?
```

---

# Test Independence

Where practical, critical tests should be repeated by:

- another developer
- another machine
- another hardware sample
- another laboratory

Independent reproduction is especially valuable for:

- security claims
- privacy claims
- reproducible builds
- hardware isolation
- battery safety
- RF behavior

---

# Test Types

Tests may be:

```text
AUTOMATED

MANUAL

ELECTRICAL

NETWORK

SOFTWARE

SECURITY

PRIVACY

MECHANICAL

RF
```

---

# Pass Criteria

Pass criteria must be defined before running the test where practical.

Avoid changing the success condition after observing the result.

---

# Failure Criteria

A test should clearly define what constitutes failure.

---

# Inconclusive Results

Use:

```text
INCONCLUSIVE
```

when evidence is insufficient to confidently classify a test as pass or fail.

---

# Test Equipment

Equipment should be documented.

Example:

```text
Multimeter:

Oscilloscope:

Logic Analyzer:

Power Supply:

Network Capture Device:

RF Equipment:
```

Model numbers should be recorded where relevant.

---

# Calibration

Tests requiring accurate measurement should document whether test equipment calibration is relevant.

---

# Environmental Conditions

Where relevant, record:

```text
Ambient Temperature:

Humidity:

Power Source:

Network Conditions:

Device Temperature:
```

---

# Software Versions

Record:

- kernel version
- NULL/OS version
- firmware versions
- application versions
- tool versions

---

# Hardware Versions

Record:

- prototype
- mainboard revision
- radio revision
- battery
- enclosure revision

---

# Security Testing

Security tests must be performed only on hardware, software, systems, and networks owned by the tester or where explicit authorization exists.

---

# Destructive Tests

Tests that may damage hardware should be clearly marked:

```text
DESTRUCTIVE TEST
```

and should not be run on the only available prototype.

---

# Safety-Critical Testing

Battery and thermal testing require additional caution.

Unsafe tests should be redesigned or performed in an appropriate laboratory environment.

---

# Evidence Retention

Evidence should be stored with the test where practical.

Examples:

```text
tests/security/SEC-001/
├── README.md
├── results/
├── logs/
└── evidence/
```

---

# Retesting

Tests should be rerun when:

- hardware revision changes
- firmware changes
- relevant software changes
- architecture changes
- previous failure is fixed

---

# Current Status

This policy applies to all future ONYX-NULL validation work.
