# ONYX-NULL Tool Policy

## Purpose

This document defines how developer tools should be designed, reviewed, and used within ONYX-NULL.

---

# Principle

Development tools are part of the project's security and reproducibility model.

A build or flashing process is not truly documented if it depends on undocumented personal scripts.

---

# Tool Categories

Tools may be classified as:

```text
BUILD

FLASH

TEST

DIAGNOSTIC

MANUFACTURING

RELEASE

REPOSITORY

SECURITY
```

---

# Required Documentation

Every significant tool should document:

```text
Name:

Purpose:

Category:

Language:

Dependencies:

Required Privileges:

Inputs:

Outputs:

Files Modified:

Hardware Modified:

Network Access:

Secrets Required:

Destructive Operations:

Supported Platforms:

Testing:
```

---

# Destructive Tools

Tools capable of destructive behavior must:

- clearly identify the target
- clearly identify the operation
- refuse ambiguous targets
- avoid dangerous defaults
- document recovery where possible

---

# Safe Defaults

Prefer:

```text
READ ONLY
```

over:

```text
WRITE
```

unless the user explicitly requests a modifying operation.

---

# Root

Root privileges should be minimized.

A tool should not run entirely as root when only one small operation requires elevation.

---

# Temporary Files

Temporary files should:

- use secure permissions
- avoid storing secrets unnecessarily
- be cleaned up appropriately

---

# Network Access

Tools should document all network access.

A local build tool should not silently contact unrelated external services.

---

# External Downloads

Tools that download dependencies should document:

- source
- version
- expected hash
- signature verification where available

---

# Reproducibility

Build tools should minimize dependence on:

- host-specific paths
- current timestamps
- mutable dependencies
- undocumented environment variables

---

# Development Versus Release

Release tooling should remain separate from experimental tooling where practical.

A development helper should not automatically gain access to production signing infrastructure.

---

# Shell Scripts

Shell scripts should generally use:

```bash
set -euo pipefail
```

where compatible with intended behavior.

Scripts should quote variables and avoid unsafe expansions.

---

# Python Tools

Python tools should:

- use explicit dependencies
- support virtual environments or isolated packaging
- avoid executing arbitrary shell commands unnecessarily
- validate filesystem paths

---

# Security Review

Tools interacting with:

- firmware
- bootloaders
- signing
- recovery
- production hardware

should receive additional review.

---

# Current Status

This policy will evolve as ONYX-NULL tooling becomes more complex.
