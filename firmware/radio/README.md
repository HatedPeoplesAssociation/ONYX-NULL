# ONYX-NULL Radio Firmware

This directory documents firmware associated with ONYX-NULL radio hardware.

Most early radio firmware may be supplied by third-party hardware vendors rather than developed by ONYX-NULL.

---

# Purpose

The project should track:

- firmware versions
- source availability
- update methods
- firmware signatures
- known vulnerabilities
- hardware isolation
- driver requirements

---

# Radio Types

Possible radio firmware includes:

- Wi-Fi
- Bluetooth
- cellular modem
- GNSS
- external radio modules

---

# Trust Position

Radio firmware should generally be treated as:

```text
RESTRICTED TRUST
```

unless a stronger justification exists.

A compromised radio should not automatically compromise the trusted compute system.

---

# Radio Firmware Template

```text
Radio:

Manufacturer:

Part Number:

Firmware:

Firmware Version:

Firmware Open:

Driver Open:

Update Mechanism:

Signature Verification:

Host Interface:

DMA:

Network Capability:

Physical Power Isolation:

Known Vulnerabilities:

Security Advisories:

Notes:
```

---

# Firmware Updates

Vendor radio firmware updates should be tracked carefully.

Document:

- version
- release date
- source URL
- hash
- security fixes
- regressions
- hardware compatibility

---

# Physical Isolation

Firmware cannot override a truly disconnected power rail.

Where practical, hardware isolation should be used to reduce dependence on radio firmware behavior.

---

# Current Status

No final ONYX-NULL radio has been selected.
