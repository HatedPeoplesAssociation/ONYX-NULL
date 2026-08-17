# ONYX-NULL Firmware Update Model

## Purpose

This document defines the intended security model for updating firmware used by ONYX-NULL.

Firmware updates are security-sensitive because they may replace code executing below the main operating system.

---

# Goals

The update system should aim to provide:

- authenticity
- integrity
- version tracking
- rollback protection where practical
- reliable recovery
- reproducibility
- transparent release history

---

# Basic Model

A future firmware update process may look like:

```text
SOURCE
  │
  ▼
BUILD
  │
  ▼
FIRMWARE IMAGE
  │
  ▼
HASH
  │
  ▼
SIGN
  │
  ▼
DISTRIBUTE
  │
  ▼
DEVICE VERIFIES SIGNATURE
  │
  ▼
INSTALL
```

---

# Authenticity

The device should verify that an update was authorized by an accepted signing key.

The presence of a valid signature proves authorization by the holder of the signing key.

It does not prove that the firmware itself is free of vulnerabilities.

---

# Integrity

Firmware packages should use cryptographic hashes to detect corruption or modification.

Release documentation should publish hashes for distributed artifacts.

---

# Rollback Protection

Where supported, the device should prevent replacing current firmware with an older vulnerable release.

Possible mechanisms include:

- monotonic version counters
- hardware rollback indexes
- secure-element counters
- signed minimum-version metadata

Rollback protection should account for legitimate recovery requirements.

---

# Recovery

Firmware updates must consider failure scenarios such as:

- power loss
- corrupted update
- interrupted flashing
- invalid signature
- incompatible firmware
- failed boot

Potential recovery designs include:

```text
A/B Firmware

Primary + Recovery Image

ROM Bootloader

External Programmer
```

---

# A/B Firmware

A/B updates may allow:

```text
CURRENT SLOT A
     │
     ├── write update to SLOT B
     │
     ▼
verify SLOT B
     │
     ▼
boot SLOT B
     │
success?
  │      │
 YES     NO
  │      │
keep   return
B      to A
```

This can reduce the risk of bricking hardware during updates.

---

# Signing Keys

Signing-key management should be documented separately.

Key considerations include:

- offline root key
- release-signing key
- key rotation
- revocation
- backups
- contributor access
- compromise response

Private signing keys must never be committed to the repository.

---

# Development Firmware

Development devices may permit unsigned firmware.

Release devices should not automatically inherit that policy.

Development and release security states should be clearly distinguishable.

---

# Firmware Metadata

Each firmware release should include:

```text
Firmware Name:

Version:

Compatible Hardware:

Commit:

Build Toolchain:

Build Date:

SHA-256:

Signing Key ID:

Minimum Previous Version:

Release Notes:

Known Issues:
```

---

# Third-Party Firmware

If firmware is supplied by a hardware vendor, document:

- vendor
- version
- download source
- hash
- signature verification
- update mechanism
- changelog
- security bulletins
- whether downgrade is possible

---

# Update Testing

Before release, test:

- valid update
- invalid signature
- corrupted update
- wrong hardware revision
- interrupted update
- power failure
- rollback attempt
- recovery procedure

---

# Current Status

The final ONYX-NULL firmware-update architecture has not yet been selected.
