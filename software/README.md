# ONYX-NULL Software

This directory contains user-space software developed specifically for ONYX-NULL.

Software in this directory is separate from the operating system itself.

NULL/OS provides the platform.

The `software/` directory contains applications, services, libraries, and utilities that run on top of that platform.

---

# Directory Structure

```text
software/
├── README.md
├── communications/
├── security/
└── utilities/
```

---

# Purpose

ONYX-NULL software may eventually provide:

- VoIP calling
- SIP integration
- secure messaging integration
- contact management
- hardware privacy-state reporting
- diagnostics
- network inspection
- device configuration
- update management
- security tools
- recovery utilities
- hardware testing tools

---

# Software Philosophy

ONYX-NULL software should follow:

```text
MINIMAL
   +
AUDITABLE
   +
LEAST PRIVILEGE
   +
DOCUMENTED
   +
REPRODUCIBLE
```

Software should not receive more authority than it requires.

---

# Separation From NULL/OS

The distinction is:

```text
NULL/OS
   │
   ├── Kernel
   ├── Drivers
   ├── Core Services
   ├── Security Policy
   └── Update Infrastructure

software/
   │
   ├── Communications Apps
   ├── Security Tools
   └── User Utilities
```

This separation allows applications to evolve independently from the base operating system.

---

# Application Trust

Applications should generally be treated as less trusted than the operating system.

Conceptually:

```text
APPLICATION
     │
     ▼
SANDBOX
     │
     ▼
SYSTEM API
     │
     ▼
NULL/OS
```

Application compromise should not automatically grant complete device compromise.

---

# Permissions

Applications should receive only required permissions.

Examples include:

```text
Microphone

Camera

Contacts

Files

Network

Location

Bluetooth

Hardware State
```

Access should follow least privilege.

---

# Network Access

Network access should not automatically be granted to every application.

Where supported, applications should have explicit network policy.

Possible states:

```text
NO NETWORK

LOCAL NETWORK

INTERNET

VPN ONLY
```

---

# Privileged Software

Software requiring elevated privileges must document:

```text
Why privilege is required

What interfaces are exposed

What data is accessible

What happens if the software is compromised
```

Privileged code should remain as small as practical.

---

# Programming Languages

Language selection should consider:

- memory safety
- maintainability
- performance
- dependency ecosystem
- platform support
- auditability

Memory-safe languages should be preferred for new security-sensitive code where practical.

Potential candidates include:

- Rust
- Go
- memory-safe managed languages
- carefully constrained C where hardware interaction requires it

---

# Dependencies

Dependencies should remain minimal.

Each significant dependency should be evaluated for:

- maintenance status
- license
- security history
- network behavior
- update frequency
- transitive dependencies

---

# Proprietary Software

Core ONYX-NULL functionality should not depend on proprietary user-space applications.

If proprietary applications are supported, they should remain outside the trusted base system.

---

# Logging

Software should avoid logging:

- passwords
- cryptographic keys
- message contents
- microphone data
- unnecessary account identifiers
- unnecessary location information

Debug builds may contain additional logging.

Release builds should minimize sensitive logs.

---

# Configuration

Configuration should be:

- documented
- versioned where appropriate
- easy to reset
- safe by default

Secrets must not be committed to the repository.

---

# Testing

Software testing may include:

- unit tests
- integration tests
- fuzzing
- static analysis
- dependency scanning
- permission testing
- network behavior testing
- failure testing

---

# Security Review

Security-sensitive software should answer:

> What happens if this process is completely compromised?

The system architecture should attempt to contain that failure.

---

# Licensing

Software source should include clear licensing information once the ONYX-NULL licensing model is finalized.

Source files may use SPDX identifiers where appropriate.

---

# Current Status

**Stage:** Research / Pre-P0

No production ONYX-NULL user-space software currently exists.

Early P0 development may rely on existing open-source applications while ONYX-NULL-specific software requirements are defined.
