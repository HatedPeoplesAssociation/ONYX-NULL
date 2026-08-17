# Building NULL/OS

## Purpose

This document will describe how to build NULL/OS entirely from documented source and dependencies.

The final commands do not yet exist.

---

# Goal

A future contributor should be able to perform:

```text
CLONE SOURCE
     │
     ▼
SET UP TOOLCHAIN
     │
     ▼
BUILD
     │
     ▼
VERIFY ARTIFACT
     │
     ▼
FLASH DEVICE
```

without undocumented private infrastructure.

---

# Build Environment

Each supported release should document:

```text
Host Operating System:

Architecture:

Compiler:

Compiler Version:

Build System:

Container Image:

Dependencies:

Required Storage:

Required RAM:
```

---

# Automated Builds

Build automation should eventually live under:

```text
os/NULL-OS/scripts/
```

or project-level build tooling.

---

# Example Future Workflow

Conceptually:

```bash
git clone <repository>
cd ONYX-NULL

./os/NULL-OS/scripts/setup-build-env

./os/NULL-OS/scripts/build

./os/NULL-OS/scripts/verify
```

These commands are placeholders until the build system exists.

---

# Dependency Pinning

Build dependencies should be version-pinned where practical.

Mutable external dependencies make reproduction more difficult.

---

# Build Outputs

Possible outputs include:

```text
boot.img

system.img

recovery.img

update-package

manifest

checksums

signatures
```

depending on final architecture.

---

# Signing

Building and signing should remain conceptually separate.

Contributors should be able to build the software without possessing official ONYX-NULL release-signing keys.

---

# Development Images

Development builds may differ from production releases.

Potential development functionality:

- debugging
- SSH
- root access
- additional logs
- unsigned modules

These differences must be documented.

---

# Clean Build

A clean build should not require undocumented files from a developer's personal machine.

---

# Current Status

The NULL/OS build system has not yet been implemented.
