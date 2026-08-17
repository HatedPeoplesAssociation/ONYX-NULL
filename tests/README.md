# ONYX-NULL Tests

This directory contains validation procedures, test plans, test results, fixtures, scripts, and evidence used to verify ONYX-NULL hardware, software, firmware, privacy, networking, and security properties.

Testing is a core part of the ONYX-NULL project.

A design claim is not considered proven simply because it appears in documentation.

---

# Directory Structure

```text
tests/
├── README.md
├── TEST_POLICY.md
├── RESULT_FORMAT.md
├── security/
├── privacy/
├── hardware/
└── network/
```

---

# Testing Philosophy

ONYX-NULL should prefer:

```text
CLAIM
  ↓
TEST
  ↓
MEASUREMENT
  ↓
RESULT
  ↓
DOCUMENTATION
```

over:

```text
CLAIM
  ↓
ASSUMPTION
```

---

# Test Categories

Tests are divided into several major categories.

## Security

Tests security boundaries, boot integrity, permissions, update verification, isolation, and resistance to unauthorized modification.

## Privacy

Tests telemetry, hardware privacy controls, data exposure, metadata, location-related behavior, and unnecessary information leakage.

## Hardware

Tests electrical behavior, power rails, switches, audio, thermals, battery behavior, interfaces, and physical hardware reliability.

## Network

Tests network exposure, firewall behavior, VPN behavior, DNS, SIP/VoIP traffic, unexpected outbound connections, and network failure modes.

---

# Test Status

Tests may use:

```text
PLANNED

READY

RUNNING

PASS

FAIL

BLOCKED

INCONCLUSIVE
```

---

# Test Evidence

Where practical, results should include evidence such as:

- command output
- logs
- screenshots
- packet captures
- photographs
- multimeter measurements
- oscilloscope captures
- spectrum measurements
- hashes
- firmware versions
- hardware revision
- software version

---

# Reproducibility

Another person should eventually be able to reproduce the test using only public documentation.

Each important test should include:

```text
Purpose:

Requirements:

Equipment:

Hardware Revision:

Software Version:

Setup:

Procedure:

Expected Result:

Observed Result:

Evidence:

Result:
```

---

# Failed Tests

Failed tests are valuable.

Do not hide failures.

A failed test should document:

- what failed
- why it matters
- suspected cause
- whether a fix exists
- related issue
- retest requirements

---

# Test Environments

Testing should record the environment.

Examples:

```text
Hardware:
ONX-P0

Mainboard:
ONX-M1 REV-A

NULL/OS:
0.4.0

Firmware:
ONX-EC 0.2.1

Network:
Wi-Fi

Power:
USB-C
```

---

# Test Naming

Suggested format:

```text
SEC-001
SEC-002

PRIV-001
PRIV-002

HW-001
HW-002

NET-001
NET-002
```

---

# Automated Tests

Automated tests should be used where practical.

Examples include:

- software unit tests
- API tests
- dependency checks
- configuration checks
- firewall verification
- reproducible-build checks
- static analysis

---

# Manual Tests

Some properties require manual or physical testing.

Examples include:

- kill-switch electrical verification
- battery thermals
- enclosure fit
- RF behavior
- microphone isolation
- physical repairability

---

# Safety

Tests involving:

- lithium batteries
- high current
- thermal stress
- RF transmission
- deliberate fault injection

must be designed with appropriate safety precautions.

---

# Security Scope

Passing a security test proves only the property that was tested under the documented conditions.

It does not prove that ONYX-NULL is universally secure.

---

# Current Status

**Stage:** Research / Pre-P0

The initial test framework exists to ensure that future ONYX-NULL claims are tied to reproducible evidence.
