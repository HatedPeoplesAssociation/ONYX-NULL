# ONYX-NULL Operating Systems

This directory contains operating-system research, architecture, configuration, build tooling, documentation, and source modifications used by ONYX-NULL.

The working name for the ONYX-NULL operating system is:

# NULL/OS

NULL/OS is currently a design concept.

No final operating-system architecture has been selected.

---

# Directory Structure

```text
os/
├── README.md
└── NULL-OS/
    ├── README.md
    ├── ARCHITECTURE.md
    ├── SECURITY_MODEL.md
    ├── PACKAGE_POLICY.md
    ├── NETWORK_POLICY.md
    ├── PRIVACY_POLICY.md
    ├── UPDATE_MODEL.md
    ├── BOOT_MODEL.md
    ├── STORAGE_MODEL.md
    ├── RECOVERY.md
    ├── BUILDING.md
    ├── REPRODUCIBILITY.md
    ├── HARDWARE_INTEGRATION.md
    ├── profiles/
    ├── configs/
    ├── patches/
    ├── packages/
    ├── scripts/
    └── build/
```

---

# Purpose

The operating system must provide the software environment required to turn ONYX-NULL hardware into a secure and usable communications platform.

Responsibilities may eventually include:

- booting the hardware
- user authentication
- encrypted storage
- application execution
- application isolation
- hardware permissions
- networking
- VPN support
- VoIP
- audio
- display
- hardware privacy-state reporting
- software updates
- firmware coordination
- recovery

---

# Operating-System Philosophy

NULL/OS should follow several principles:

```text
MINIMAL
   +
AUDITABLE
   +
HARDENED
   +
REPRODUCIBLE
   +
OWNER CONTROLLED
```

The system should avoid unnecessary services, dependencies, telemetry, and privileged components.

---

# Security Over Branding

NULL/OS should not become a custom operating system merely for the sake of having a custom operating system.

If an established platform provides stronger security properties than a new implementation, ONYX-NULL should build upon that platform rather than replacing mature security engineering without justification.

---

# Candidate Architectures

Current research may consider:

## Hardened Linux

Potential advantages:

- broad open-source ecosystem
- strong development tooling
- mainline hardware support
- substantial owner control

Research areas:

- application sandboxing
- secure boot
- immutable root filesystem
- update model
- mobile UI
- suspend/resume
- permission architecture

## AOSP-Derived System

Potential advantages:

- mature mobile application sandbox
- mature permission system
- SELinux integration
- mobile power management
- established application ecosystem
- Verified Boot architecture

Research areas:

- hardware compatibility
- custom-device support
- proprietary vendor dependencies
- reproducible builds
- GrapheneOS-inspired hardening concepts

---

# Decision Requirement

The final architecture should be selected based on measurable requirements rather than preference.

Important criteria include:

- exploit resistance
- application isolation
- hardware support
- boot security
- update security
- open-source availability
- reproducibility
- development complexity
- power management
- repairability
- long-term maintenance
- user experience

---

# Hardware Relationship

The operating system should never claim to enforce a hardware privacy property that it cannot actually enforce.

Example:

If a physical microphone switch disconnects the microphone, NULL/OS may report:

```text
MICROPHONE
PHYSICALLY DISCONNECTED
```

But the operating system should not pretend that a software mute is equivalent to physical isolation.

---

# Proprietary Dependencies

Any proprietary operating-system dependencies must be documented.

Examples may include:

- GPU firmware
- Wi-Fi firmware
- storage firmware
- display firmware
- radio firmware

See:

`../docs/PROPRIETARY_COMPONENTS.md`

---

# Current Status

**Stage:** Research / Pre-P0

P0 does not require a custom operating system.

Early prototypes may use an existing Linux distribution while NULL/OS requirements are researched and documented.
