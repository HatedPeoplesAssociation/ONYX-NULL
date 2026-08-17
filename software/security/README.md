# ONYX-NULL Security Software

This directory contains security-focused user-space software developed or configured specifically for ONYX-NULL.

---

# Purpose

Possible security software includes:

- hardware-state monitoring
- integrity verification
- security diagnostics
- firewall management
- credential management
- update verification
- audit tools
- device-lock integration
- security status interface

---

# Philosophy

Security software should not exist merely to display reassuring indicators.

It should represent measurable system state.

For example:

```text
BAD:

"SECURE MODE ENABLED"

GOOD:

Boot Verified: YES
VPN Active: YES
Wi-Fi Power: OFF
Microphone Power: OFF
Update Signature: VALID
```

---

# Hardware State Monitor

A future security service may expose physical hardware states.

Possible states:

```text
Wi-Fi:
POWERED

Bluetooth:
PHYSICALLY DISCONNECTED

Microphone:
PHYSICALLY DISCONNECTED

Camera:
POWERED OFF

Optional Modem:
NOT PRESENT
```

---

# Source of Truth

Software indicators should use the strongest available source of truth.

Preferred:

```text
PHYSICAL STATE
      │
      ▼
HARDWARE SIGNAL
      │
      ▼
SECURITY SERVICE
      │
      ▼
USER INTERFACE
```

Avoid relying solely on an application setting to represent physical hardware state.

---

# Integrity Verification

Potential integrity tools may verify:

- boot state
- system image hashes
- configuration hashes
- package signatures
- firmware versions
- update signatures

---

# Security Dashboard

A future ONYX-NULL security dashboard may summarize:

```text
BOOT

Verified: YES
Locked: YES


NETWORK

VPN: ACTIVE
DNS: VPN
Firewall: ACTIVE


HARDWARE

Wi-Fi: ON
Microphone: OFF
Camera: OFF


SOFTWARE

System Update: CURRENT
Firmware: CURRENT
```

The dashboard should avoid oversimplifying complex security properties into a meaningless single score.

---

# Firewall Management

Security software may expose firewall configuration while preserving secure defaults.

Changes should clearly show consequences.

---

# VPN Monitoring

Potential functionality:

- show active VPN
- verify tunnel status
- detect tunnel loss
- expose kill-switch status
- provide diagnostic information

---

# Credential Management

ONYX-NULL should avoid implementing a new password manager unless there is a strong technical reason.

Established, audited password-management software should be preferred.

---

# Security Keys

Software may support:

- FIDO2
- WebAuthn
- hardware security keys
- passkeys

where supported by the chosen OS foundation.

---

# Root Detection

If NULL/OS has a development mode, security software should clearly report when production security properties are weakened.

Example:

```text
WARNING

DEVELOPMENT MODE ACTIVE

Verified Boot:
DISABLED

Debug Interface:
ENABLED
```

---

# Debug Interfaces

Security tools may report:

- ADB state
- SSH state
- JTAG/SWD state where observable
- USB data mode
- development mode

---

# Update Verification

Security software may provide information about:

```text
Installed Version

Latest Trusted Version

Signature Status

Rollback Status

Firmware Versions
```

---

# Audit Logging

Security events may include:

- failed authentication
- configuration changes
- update installation
- boot-state changes
- privacy-switch transitions

Logs should remain minimal and should not unnecessarily record sensitive user behavior.

---

# Security Alerts

Useful alerts may include:

```text
VPN disconnected

System update failed

Unknown firmware version

Boot verification failed

Debug mode enabled
```

Alerts should describe actual conditions.

---

# No Security Theater

ONYX-NULL security software should avoid:

- fake threat scores
- arbitrary percentage ratings
- unsupported claims
- meaningless "military grade" terminology
- claiming anonymity based on VPN use
- equating software toggles with physical isolation

---

# Privileges

Security services may require elevated privileges.

Each privileged component must document:

```text
Required Privileges:

Reason:

Accessible Data:

Accessible Hardware:

Network Access:

Exposed API:

Compromise Impact:
```

---

# Language Preference

New privileged security services should prefer memory-safe languages where practical.

---

# Testing

Potential testing includes:

- invalid inputs
- privilege boundaries
- unauthorized API calls
- race conditions
- malformed hardware-state messages
- VPN failure
- corrupted update metadata
- compromised client application

---

# Possible Structure

Future organization may include:

```text
security/
├── README.md
├── hardware-state/
├── integrity/
├── firewall/
├── vpn-monitor/
├── update-verifier/
└── security-ui/
```

---

# Current Status

No custom ONYX-NULL security service currently exists.

Security software will be developed only after corresponding hardware and operating-system properties can be measured reliably.
