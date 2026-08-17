# NULL/OS Security Model

## Purpose

This document defines the intended software security properties of NULL/OS.

---

# Core Objectives

NULL/OS should aim to provide:

- least privilege
- strong application isolation
- protected cryptographic secrets
- authenticated boot
- encrypted storage
- secure updates
- minimal attack surface
- restricted hardware access
- secure defaults

---

# Threat Assumption

NULL/OS should assume that any exposed component may eventually contain a vulnerability.

The architecture should therefore prioritize containment.

---

# Application Compromise

If an application is compromised, the attacker should not automatically gain access to:

- root privileges
- kernel memory
- other application data
- microphone
- camera
- hardware secrets
- raw storage
- unrestricted networking

---

# Privileged Services

Privileged services should:

- remain minimal
- expose narrow interfaces
- validate all input
- avoid unnecessary network access
- drop privileges where possible

---

# Kernel

The kernel is a critical trust boundary.

Kernel security work may include:

- reducing enabled features
- disabling unused drivers
- compiler hardening
- memory-corruption mitigations
- module-signing policy
- secure boot integration
- attack-surface reduction

---

# Mandatory Access Control

NULL/OS should evaluate mandatory access-control systems.

Possible options include:

- SELinux
- AppArmor
- Landlock

The final technology depends on OS foundation.

---

# Sandboxing

Potential sandbox mechanisms include:

- namespaces
- seccomp
- capabilities
- MAC policies
- filesystem isolation
- per-application identities

---

# Root Access

Production NULL/OS should not require routine root access for normal operation.

Development builds may provide additional debugging functionality.

Development and release states should be clearly distinguishable.

---

# Secrets

Sensitive secrets may include:

- disk-encryption keys
- VPN keys
- authentication credentials
- update keys
- communication credentials

Secrets should receive additional protection where hardware support exists.

---

# Logging

Logs should not collect unnecessary sensitive information.

Avoid recording:

- communication contents
- passwords
- cryptographic keys
- unnecessary location information
- unnecessary persistent identifiers

---

# USB

USB should be treated as a significant attack surface.

Future policy may include:

- data disabled while locked
- restricted device classes
- explicit authorization
- charging-only mode
- debug interface restrictions

---

# Hardware Trust

Software security cannot compensate for every compromised hardware component.

See:

`../../docs/HARDWARE_TRUST.md`

and:

`../../docs/TRUST_MODEL.md`

---

# Security Status Labels

Security features should be labeled as:

```text
PLANNED

IMPLEMENTED

TESTED

REVIEWED
```

A planned feature must not be described as an implemented guarantee.
