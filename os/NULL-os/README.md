# NULL/OS

**ONYX-NULL Operating System**

**Status:** Research / Architecture Development

NULL/OS is the working name for the operating-system platform intended for ONYX-NULL.

NULL/OS is not currently a finished operating system.

---

# Mission

NULL/OS aims to provide an owner-controlled software environment designed around:

- minimal trust
- strong isolation
- transparent configuration
- encrypted storage
- secure updates
- reproducible builds
- hardware privacy integration
- minimal telemetry
- secure communications

---

# Core Principle

> Trust less. Verify more.

NULL/OS should not simply declare itself private or secure.

Security and privacy properties should be documented, tested, and measurable.

---

# Architecture Goals

NULL/OS should eventually provide:

```text
                   NULL/OS

┌──────────────────────────────────┐
│             USER                 │
├──────────────────────────────────┤
│          APPLICATIONS            │
│                                  │
│ Communications                   │
│ Browser                          │
│ Utilities                        │
├──────────────────────────────────┤
│      APPLICATION ISOLATION       │
├──────────────────────────────────┤
│         SYSTEM SERVICES          │
│                                  │
│ Audio                            │
│ Networking                       │
│ Update Service                   │
│ Hardware State                   │
├──────────────────────────────────┤
│       SECURITY FRAMEWORK         │
│                                  │
│ Permissions                      │
│ MAC / SELinux                    │
│ Sandboxing                       │
│ Encryption                       │
├──────────────────────────────────┤
│            KERNEL                │
├──────────────────────────────────┤
│             HARDWARE             │
└──────────────────────────────────┘
```

---

# Design Goals

NULL/OS should aim for:

- secure default configuration
- minimal privileged software
- strong application boundaries
- full-storage encryption
- verified boot where supported
- secure updates
- rollback protection where supported
- hardware-backed cryptographic keys where available
- firewall controls
- VPN support
- minimal default network activity
- transparent hardware state
- reproducible builds where practical

---

# Non-Goals

NULL/OS does not claim to provide:

- perfect anonymity
- perfect security
- immunity to all zero-day exploits
- radio invisibility
- protection from every malicious upstream provider
- security guarantees unsupported by underlying hardware

---

# P0 Relationship

ONYX-NULL P0 does not require NULL/OS.

P0 may initially run an existing Linux distribution.

This allows hardware and communication development to proceed before committing to a long-term operating-system architecture.

---

# Candidate Foundations

NULL/OS research may evaluate:

```text
Hardened Linux
Mobile Linux
AOSP
AOSP-derived architecture
```

The final foundation should be selected only after requirements and security tradeoffs are documented.

---

# Documentation

Important NULL/OS documents include:

```text
ARCHITECTURE.md

SECURITY_MODEL.md

PACKAGE_POLICY.md

NETWORK_POLICY.md

PRIVACY_POLICY.md

UPDATE_MODEL.md

BOOT_MODEL.md

STORAGE_MODEL.md

RECOVERY.md

BUILDING.md

REPRODUCIBILITY.md

HARDWARE_INTEGRATION.md
```

---

# Current Status

NULL/OS currently exists as a design and research effort.

Do not treat documented future features as implemented security properties.
