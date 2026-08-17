# ONYX-NULL Security Tests

This directory contains tests used to validate ONYX-NULL security boundaries and protections.

---

# Security Test Areas

Testing may include:

- boot integrity
- verified boot
- rollback protection
- firmware verification
- application isolation
- privilege boundaries
- USB security
- update security
- storage protection
- debug-interface exposure
- hardware isolation
- authentication
- recovery security

---

# Suggested Test Structure

```text
security/
├── README.md
├── SEC-001-boot-integrity/
├── SEC-002-rollback-protection/
├── SEC-003-update-signature/
├── SEC-004-usb-locked-state/
├── SEC-005-app-isolation/
└── SEC-006-debug-interface/
```

---

# SEC-001 — Boot Integrity

Goal:

Verify that unauthorized modifications to protected boot components are detected or rejected.

Potential targets:

- bootloader
- kernel
- system image

---

# SEC-002 — Rollback Protection

Goal:

Verify that an older prohibited software or firmware version cannot be installed when rollback protection is enabled.

---

# SEC-003 — Update Signature

Goal:

Verify that an update with an invalid signature is rejected.

Test variants:

```text
Valid Signature

Modified Package

Wrong Signing Key

Missing Signature
```

---

# SEC-004 — USB Locked State

Goal:

Verify that a locked device does not expose unnecessary USB functionality.

Potential checks:

- file access
- debugging
- shell access
- unauthorized USB modes

---

# SEC-005 — Application Isolation

Goal:

Verify that one application cannot read another application's private data through normal interfaces.

---

# SEC-006 — Debug Interface

Goal:

Verify the expected state of:

- JTAG
- SWD
- UART
- SSH
- development interfaces

in development and release configurations.

---

# SEC-007 — Storage Encryption

Goal:

Verify that protected user data is not trivially readable from raw storage without required authentication material.

---

# SEC-008 — Recovery Security

Goal:

Verify that recovery mode does not automatically expose encrypted user data.

---

# SEC-009 — Firmware Integrity

Goal:

Verify firmware version and integrity where verification mechanisms exist.

---

# SEC-010 — Hardware Kill-Switch Override

Goal:

Verify that software cannot override a physical privacy switch.

Example:

```text
Wi-Fi switch OFF
      │
      ▼
Software attempts enable
      │
      ▼
Radio remains OFF
```

---

# Security Test Rules

Security tests should:

- define exact scope
- avoid unsupported conclusions
- document assumptions
- retain evidence
- identify hardware/software versions

---

# Authorized Testing

Only perform active security testing on systems you own or are explicitly authorized to test.

---

# Current Status

No production security tests have been completed yet.
