# ONYX-NULL Build Tools

This directory contains helper tools used to build ONYX-NULL software, firmware, operating-system images, and related artifacts.

---

# Purpose

Build tooling may eventually handle:

- firmware compilation
- NULL/OS builds
- package builds
- dependency setup
- artifact collection
- manifest generation
- checksum generation

---

# Conceptual Workflow

```text
SOURCE
  │
  ▼
SET UP ENVIRONMENT
  │
  ▼
BUILD
  │
  ▼
VERIFY
  │
  ▼
PACKAGE
  │
  ▼
ARTIFACTS
```

---

# Build Commands

The long-term goal is to provide simple documented commands.

Examples:

```bash
./tools/build/firmware
```

```bash
./tools/build/null-os
```

```bash
./tools/build/all
```

These commands are placeholders until implemented.

---

# Build Output

Generated output should be placed in a predictable directory.

Example:

```text
out/
├── firmware/
├── os/
├── packages/
└── manifests/
```

---

# Clean Builds

Build tooling should support removing generated artifacts.

Example:

```bash
./tools/build/clean
```

A clean operation should not delete source files.

---

# Dependency Verification

Build tools should eventually verify:

- dependency versions
- compiler versions
- expected hashes
- required toolchain

---

# Reproducibility

Build scripts should avoid embedding:

- usernames
- hostnames
- current working-directory paths
- uncontrolled timestamps

where these would break reproducibility.

---

# Failure Behavior

Build failures should identify:

- failed stage
- command
- dependency
- artifact affected

rather than silently continuing.

---

# Current Status

No unified ONYX-NULL build tool currently exists.
