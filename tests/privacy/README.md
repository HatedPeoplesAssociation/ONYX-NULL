# ONYX-NULL Privacy Tests

This directory contains tests used to measure ONYX-NULL privacy behavior.

Privacy testing focuses on what information the device exposes, stores, transmits, or makes available.

---

# Privacy Test Areas

Testing may include:

- telemetry
- default network connections
- location services
- microphone isolation
- camera isolation
- radio isolation
- identifiers
- crash reporting
- account requirements
- metadata
- DNS leakage
- VPN failure behavior

---

# Suggested Structure

```text
privacy/
├── README.md
├── PRIV-001-default-network/
├── PRIV-002-microphone-kill/
├── PRIV-003-camera-kill/
├── PRIV-004-radio-kill/
├── PRIV-005-telemetry/
└── PRIV-006-location-services/
```

---

# PRIV-001 — Default Network Activity

Goal:

Determine what external endpoints a default ONYX-NULL installation contacts.

Test conditions:

```text
Fresh Install

No User Applications

Network Connected

No User Interaction
```

Record:

- DNS queries
- destination IPs
- protocols
- timing
- reason for connection

---

# PRIV-002 — Microphone Kill Switch

Goal:

Verify that microphone input becomes unavailable when the physical microphone isolation control is disabled.

Potential evidence:

- recording attempt
- electrical measurement
- hardware-state signal
- audio waveform

---

# PRIV-003 — Camera Kill Switch

Goal:

Verify that camera hardware cannot capture data while physically disconnected.

---

# PRIV-004 — Radio Kill Switch

Goal:

Verify that the selected radio stops operating when physically disconnected.

Check:

- power rail
- device enumeration
- network connectivity
- RF transmission where practical

---

# PRIV-005 — Telemetry

Goal:

Identify whether NULL/OS or ONYX-NULL applications send telemetry by default.

Document every discovered endpoint.

---

# PRIV-006 — Location Services

Goal:

Determine which components can access or infer location information.

Investigate:

- GNSS
- Wi-Fi
- Bluetooth
- application permissions
- external services

---

# PRIV-007 — Persistent Identifiers

Goal:

Identify persistent identifiers generated or exposed by the system.

Examples:

- device ID
- installation ID
- network identifiers
- advertising IDs

---

# PRIV-008 — Crash Reporting

Goal:

Determine whether crash reports are generated or transmitted automatically and what they contain.

---

# PRIV-009 — Account Requirement

Goal:

Verify whether the device can perform core functionality without creating an ONYX-NULL-controlled online account.

---

# PRIV-010 — Diagnostic Bundle

Goal:

Verify that diagnostic exports do not silently include unnecessary sensitive information.

Potential checks:

- contacts
- call history
- credentials
- private keys
- location
- message content

---

# Privacy Test Philosophy

A privacy claim should identify:

```text
WHAT IS PREVENTED

WHAT IS REDUCED

WHAT REMAINS POSSIBLE
```

Avoid absolute language unless the property is physically or mathematically enforceable.

---

# Current Status

No production privacy tests have been completed yet.
