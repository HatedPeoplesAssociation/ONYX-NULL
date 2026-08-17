# NULL/OS Architecture

## Status

Conceptual.

This document defines the intended high-level architecture of NULL/OS.

---

# Layers

NULL/OS should separate responsibilities into distinct layers.

```text
┌───────────────────────────────┐
│ USER                          │
├───────────────────────────────┤
│ APPLICATIONS                  │
├───────────────────────────────┤
│ APPLICATION SANDBOX           │
├───────────────────────────────┤
│ SYSTEM SERVICES               │
├───────────────────────────────┤
│ SECURITY POLICY               │
├───────────────────────────────┤
│ KERNEL                        │
├───────────────────────────────┤
│ DRIVERS                       │
├───────────────────────────────┤
│ FIRMWARE                      │
├───────────────────────────────┤
│ HARDWARE                      │
└───────────────────────────────┘
```

---

# Applications

Applications should receive only the permissions necessary for their function.

Potential application categories include:

- communications
- browser
- password manager
- file manager
- settings
- diagnostics
- utilities

---

# Application Isolation

Application compromise should not automatically provide access to:

- other application data
- cryptographic keys
- microphone
- camera
- location
- network interfaces
- system configuration

Isolation mechanisms will depend on the selected OS foundation.

Potential technologies include:

- namespaces
- seccomp
- Linux capabilities
- mandatory access control
- SELinux
- containers
- Android-style application UIDs

---

# System Services

System services should remain minimal.

Potential services include:

```text
network manager
audio service
update service
hardware-state service
power manager
logging service
time synchronization
```

Every privileged service increases attack surface and should therefore have a documented purpose.

---

# Hardware Layer

NULL/OS should integrate with ONYX-NULL hardware without assuming hardware peripherals are trustworthy.

Potential untrusted or restricted-trust hardware includes:

- Wi-Fi
- Bluetooth
- optional modem
- GPU
- USB peripherals
- third-party controllers

---

# Physical Privacy Controls

Physical privacy controls exist below software policy.

Conceptual example:

```text
USER
 │
 ▼
PHYSICAL MIC SWITCH
 │
 ▼
ELECTRICAL DISCONNECT
 │
 ▼
MICROPHONE
```

NULL/OS may observe the switch state.

It should not be able to override the disconnected state.

---

# Network Architecture

```text
APPLICATION
     │
     ▼
NETWORK POLICY
     │
     ▼
FIREWALL
     │
     ▼
VPN
     │
     ▼
NETWORK INTERFACE
```

The final implementation may differ depending on OS foundation.

---

# Boot Architecture

Conceptually:

```text
ROM
 │
 ▼
BOOTLOADER
 │
 ▼
VERIFY SYSTEM
 │
 ▼
KERNEL
 │
 ▼
SYSTEM IMAGE
 │
 ▼
NULL/OS
```

See:

`BOOT_MODEL.md`

---

# Storage Architecture

Conceptually:

```text
PHYSICAL STORAGE
       │
       ▼
ENCRYPTION
       │
       ▼
SYSTEM DATA
       │
       ├── Applications
       ├── User Data
       └── Configuration
```

See:

`STORAGE_MODEL.md`

---

# Update Architecture

Updates should eventually support:

- authenticated metadata
- signed artifacts
- atomic installation
- rollback or recovery
- version tracking

See:

`UPDATE_MODEL.md`

---

# Architecture Rule

Every major subsystem should answer:

> What happens if this subsystem is completely compromised?

The architecture should attempt to prevent one compromised component from becoming complete device compromise.
