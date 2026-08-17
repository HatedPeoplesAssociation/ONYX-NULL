# ONYX-NULL Release Tools

This directory contains tooling used to prepare official ONYX-NULL software, firmware, documentation, or hardware releases.

---

# Purpose

Release tooling may eventually handle:

- version validation
- changelog generation
- artifact collection
- checksum generation
- manifest generation
- signing
- release notes
- reproducibility metadata

---

# Separation of Duties

Building and signing should remain separate operations.

A normal developer should be able to build ONYX-NULL without access to official release-signing keys.

---

# Conceptual Release Flow

```text
SOURCE TAG
    │
    ▼
BUILD
    │
    ▼
VERIFY
    │
    ▼
GENERATE MANIFEST
    │
    ▼
SIGN
    │
    ▼
PUBLISH
```

---

# Release Manifest

A release should eventually record:

```text
Project Version:

Source Commit:

Hardware Revision:

Firmware Version:

NULL/OS Version:

Build Toolchain:

Artifacts:

SHA-256:

Signing Key ID:

Known Issues:
```

---

# Signing

Private release-signing keys must never be stored in this repository.

---

# Release Validation

Before publication verify:

- clean Git state
- correct tag
- correct version
- successful tests
- expected artifacts
- matching hashes
- valid signatures
- documentation updated

---

# Current Status

No official ONYX-NULL release tooling currently exists.
