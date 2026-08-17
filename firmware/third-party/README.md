# ONYX-NULL Third-Party Firmware

This directory documents third-party firmware dependencies used by ONYX-NULL hardware.

Do not commit proprietary firmware binaries unless redistribution is explicitly permitted.

---

# Purpose

For each dependency, document enough information for another builder to identify exactly what firmware was used.

---

# Entry Template

```text
Component:

Manufacturer:

Part Number:

Firmware Name:

Firmware Version:

Firmware License:

Redistribution Permitted:

Official Download Source:

SHA-256:

Signature Available:

Signature Verified:

Update Method:

Required For:

Open Alternative:

Notes:
```

---

# Redistribution

If redistribution is prohibited or unclear:

- do not copy the firmware into this repository
- provide instructions for obtaining it legally from the vendor
- provide the expected cryptographic hash
- document the version used

---

# Integrity Verification

Whenever firmware is downloaded from an external source, verify it where possible using:

- vendor signatures
- published hashes
- TLS source
- independent release metadata

---

# Proprietary Firmware Register

All proprietary firmware should also appear in:

`../../docs/PROPRIETARY_COMPONENTS.md`

---

# Security Advisories

Track vendor security advisories when available.

Important firmware vulnerabilities should be reflected in:

- component documentation
- changelog
- security testing
- update recommendations

---

# Current Status

No third-party firmware dependency has been approved for final ONYX-NULL hardware.
