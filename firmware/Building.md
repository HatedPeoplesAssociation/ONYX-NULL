# Building ONYX-NULL Firmware

## Purpose

This document defines the intended structure for reproducibly building ONYX-NULL-developed firmware.

The exact build commands will evolve once custom firmware exists.

---

# Goals

Firmware builds should eventually be:

- documented
- automated
- reproducible where practical
- dependency-pinned
- source-based
- easy to verify

---

# Build Environment

Every firmware component should document:

```text
Operating System:

Compiler:

Compiler Version:

SDK:

SDK Version:

Build System:

Python Version:

Dependencies:

Environment Variables:
```

---

# Example Structure

```text
firmware/
└── privacy-controller/
    ├── README.md
    ├── src/
    ├── include/
    ├── tests/
    ├── tools/
    ├── build/
    └── Makefile
```

Generated build output should normally not be committed unless required for releases or hardware recovery.

---

# Clean Build

A documented build should support something conceptually equivalent to:

```bash
git clone <repository>
cd ONYX-NULL
./tools/setup-firmware-build
./tools/build-firmware
```

The actual process may differ.

The key requirement is that no undocumented local modifications are required.

---

# Dependencies

Dependencies should be:

- documented
- version-pinned where appropriate
- obtained from known sources
- license-audited

Avoid silently downloading mutable dependencies during builds where practical.

---

# Reproducibility

A reproducible build aims for:

```text
SOURCE A
   │
   ▼
BUILD MACHINE 1
   │
   ▼
HASH X


SAME SOURCE A
   │
   ▼
BUILD MACHINE 2
   │
   ▼
HASH X
```

If builds are not deterministic, the causes should be documented.

---

# Release Artifacts

Firmware releases may include:

```text
.bin
.hex
.uf2
.elf
.map
.sha256
.sig
```

depending on target hardware.

---

# Debug Symbols

Debug artifacts may be useful for development.

Release documentation should distinguish:

- flashable image
- debug ELF
- symbol files
- map files

---

# Compiler Warnings

Firmware should aim to build with warnings enabled.

New warnings should be reviewed rather than automatically ignored.

---

# Static Analysis

Future firmware CI may include:

- compiler warnings
- formatting
- static analysis
- unit tests
- dependency scanning
- size checks

---

# License Headers

Where appropriate, source files should use an SPDX identifier.

Example:

```text
SPDX-License-Identifier: MIT
```

The actual license must match the project component's chosen license.

---

# Build Verification

For every release record:

```text
Commit:

Toolchain:

Build Command:

Artifact:

SHA-256:

Reproduced By:

Result:
```

---

# Current Status

ONYX-NULL does not yet contain custom production firmware.

This document establishes the expected build discipline before firmware development begins.
