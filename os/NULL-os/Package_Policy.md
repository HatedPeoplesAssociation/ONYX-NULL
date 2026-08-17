# NULL/OS Package Policy

## Purpose

This document defines how software should be selected for inclusion in NULL/OS.

---

# Principle

Every additional package increases:

- attack surface
- maintenance burden
- dependency complexity
- supply-chain exposure

NULL/OS should therefore install only software with a defined purpose.

---

# Package Categories

Packages may be classified as:

```text
CORE

REQUIRED

OPTIONAL

DEVELOPMENT

REJECTED
```

---

# CORE

Required for fundamental system operation.

Examples may include:

- init system
- kernel userspace
- cryptographic libraries
- package verification
- storage utilities

---

# REQUIRED

Needed for expected ONYX-NULL functionality.

Examples may include:

- networking
- audio
- UI
- VPN
- communication software

---

# OPTIONAL

User-installable functionality not required by the base platform.

---

# DEVELOPMENT

Only included in development images.

Examples:

- compilers
- debuggers
- tracing tools
- SSH server
- hardware diagnostics

These should not automatically ship in release images.

---

# Package Evaluation

Before adding a package, document:

```text
Package:

Purpose:

Source:

License:

Maintainer:

Dependencies:

Network Access:

Privileges:

Security History:

Alternative:

Required By:

Decision:
```

---

# Source

Prefer software from:

- upstream project repositories
- trusted distribution repositories
- reproducible build infrastructure

Avoid unnecessary binary-only packages.

---

# Dependencies

Indirect dependencies matter.

Adding one package may add dozens of libraries.

Dependency impact should be reviewed.

---

# Updates

Packages with known security vulnerabilities should be updated promptly.

The project should maintain a process for monitoring security advisories affecting included software.

---

# Removal

Unused packages and services should be removed rather than simply ignored.

---

# Proprietary Applications

Proprietary applications should not be part of the trusted base system.

If support is provided, they should operate under restrictive application boundaries where practical.

---

# Current Status

No final NULL/OS package set has been selected.
