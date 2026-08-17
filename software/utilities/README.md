# ONYX-NULL Utilities

This directory contains supporting utilities for ONYX-NULL development, diagnostics, maintenance, testing, and device management.

---

# Purpose

Utilities are tools that support ONYX-NULL without being fundamental operating-system components.

Possible examples include:

- hardware diagnostics
- network diagnostics
- audio tests
- battery diagnostics
- firmware information tools
- system-information tools
- provisioning tools
- log collection
- recovery helpers
- configuration utilities

---

# Utility Philosophy

Utilities should:

- perform one clear function
- remain simple
- expose useful technical information
- avoid unnecessary privileges
- avoid unnecessary network access
- be scriptable where practical
- provide human-readable output

---

# Potential Structure

```text
utilities/
├── README.md
├── hardware-info/
├── network-test/
├── audio-test/
├── battery-test/
├── privacy-test/
├── firmware-info/
└── provisioning/
```

---

# Hardware Information

A hardware-info utility may eventually display:

```text
ONYX-NULL Hardware

Platform:
ONX-M1 REV-B

Compute:
<model>

RAM:
<capacity>

Storage:
<model>

Wi-Fi:
<model>

Audio Codec:
<model>

Battery:
<model>

Privacy Controller:
<version>
```

---

# Firmware Information

A firmware utility may display:

```text
Component:

Firmware:

Version:

Hash:

Source Status:

Latest Known Version:
```

This information may help verify reproducibility and update state.

---

# Network Test Utility

Potential checks include:

- interface state
- IP configuration
- DNS
- VPN
- routing
- connectivity
- unexpected listeners

Example:

```text
Wi-Fi:
CONNECTED

VPN:
ACTIVE

DNS:
THROUGH VPN

Default Route:
VPN

Unexpected Listening Ports:
NONE
```

---

# Privacy Test Utility

A privacy-test utility may help verify:

- microphone isolation
- camera isolation
- Wi-Fi kill switch
- Bluetooth kill switch
- network leakage
- DNS leakage

It should measure observable behavior rather than merely checking configuration values.

---

# Audio Test Utility

Potential functions:

- microphone level
- speaker playback
- earpiece playback
- loopback
- latency testing
- full-duplex testing

---

# Battery Test Utility

Potential measurements:

```text
Voltage

Current

Temperature

Charge State

Estimated Capacity

Power Draw

Battery Health
```

---

# Diagnostics

Diagnostic utilities should produce enough information to troubleshoot issues without automatically collecting excessive personal information.

---

# Diagnostic Bundles

If a support bundle is implemented, it should clearly show what will be included before export.

Avoid automatically including:

- contacts
- call history
- message contents
- credentials
- precise location
- private keys

---

# Provisioning

Provisioning tools may eventually configure:

- device identity
- Wi-Fi
- VPN
- SIP
- security keys
- update channels

Provisioning secrets should not be written to insecure logs.

---

# CLI Preference

Many low-level utilities should provide a CLI interface even if a graphical interface exists.

Example:

```bash
onx-hwinfo
```

```bash
onx-netcheck
```

```bash
onx-privacy-test
```

```bash
onx-audio-test
```

This improves:

- debugging
- automation
- testing
- documentation

---

# Exit Codes

CLI utilities should use meaningful exit codes.

Example:

```text
0 = Success

1 = Test Failure

2 = Invalid Configuration

3 = Hardware Unavailable
```

---

# Machine-Readable Output

Where useful, utilities may support:

```bash
--json
```

for automated testing.

Example:

```json
{
  "wifi_power": false,
  "microphone_power": false,
  "vpn_active": true
}
```

---

# Safety

Utilities interacting with hardware must avoid destructive actions unless clearly requested.

Dangerous operations should require explicit confirmation or separate commands.

---

# Root Privileges

Utilities should avoid requiring root unless necessary.

If elevated privileges are required, document exactly why.

---

# Logging

Utilities should not write persistent logs unless needed.

Temporary diagnostics should be clearly identified.

---

# Testing

Utilities should eventually include:

- unit tests
- invalid input tests
- permission tests
- hardware-absence tests
- failure-path tests
- machine-readable output tests

---

# Current Status

No production ONYX-NULL utilities currently exist.

Early development will likely begin with small command-line diagnostic tools used during P0 testing.
