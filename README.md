# ONYX-NULL

> **Open Mobile Communications Platform**

### Trust less. Verify more.

ONYX-NULL is an open-source hardware and software research project focused on developing an **owner-controlled, privacy-focused, secure mobile communications platform**.

The project is built around a simple question:

> **How much trust can we remove from a modern mobile device?**

Rather than assuming every component of a phone is trustworthy, ONYX-NULL aims to explicitly identify trust boundaries, minimize proprietary dependencies, physically isolate sensitive hardware where practical, and document exactly what the device can — and cannot — protect.

---

## ⚠️ Project Status

**Current Stage:** `Research / Pre-P0`

ONYX-NULL is currently in the **research and early prototyping stage**.

There is currently **no finished ONYX-NULL phone**.

Hardware specifications, software architecture, security mechanisms, and other design decisions documented in this repository may change significantly as research and testing progress.

Security features described in planning documents should be considered **design objectives until implemented, tested, and independently reviewed**.

### Current Objective

Develop the knowledge, threat model, architecture, and laboratory environment required to build the first ONYX-NULL prototype.

### First Major Milestone

> **ONYX-NULL P0 successfully places its first telephone call.**

---

# Why ONYX-NULL?

Modern smartphones require users to trust an enormous technology stack.

This can include:

- application processors
- cellular basebands
- Wi-Fi/Bluetooth firmware
- proprietary firmware
- operating systems
- application frameworks
- cloud infrastructure
- telecommunications providers
- hardware vendors
- application developers
- update infrastructure

ONYX-NULL explores what happens when the design philosophy changes from:

> **Trust the platform.**

to:

> **Assume components can fail or become compromised, then design boundaries around them.**

The objective is not to eliminate trust.

The objective is to make trust **explicit, minimized, documented, and verifiable wherever possible.**

---

# Core Principles

## Owner Control

The owner of the device should have meaningful control over the hardware and software operating within it.

Whenever possible, the device should not depend on infrastructure or services that the owner cannot replace.

---

## Open Development

ONYX-NULL is intended to be developed publicly.

The long-term goal is to publish:

- hardware schematics
- PCB source files
- bills of materials
- mechanical CAD
- firmware source
- software source
- OS build configuration
- build tools
- testing procedures
- security documentation
- privacy documentation
- assembly instructions

Someone should eventually be able to study the repository and understand **how the device works without having to trust the project maintainers' word for it.**

---

## Explicit Trust

Every component that must be trusted should be documented.

This includes proprietary components.

ONYX-NULL will not pretend closed-source firmware does not exist simply because it is inconvenient.

Instead:

**Identify it.  
Document it.  
Isolate it.  
Minimize it.  
Replace it when practical.**

---

## Isolation Over Assumption

Potentially untrusted components should be isolated where practical rather than simply assumed to behave correctly.

This is particularly important for components such as:

- cellular modems
- Wi-Fi radios
- Bluetooth controllers
- USB peripherals
- cameras
- microphones
- proprietary firmware

A compromised component should not automatically mean a compromised device.

---

## Physical Verification

Critical privacy controls should eventually provide **hardware-enforced guarantees wherever practical**.

For example:

```text
Software Wi-Fi Disable

OS
 │
 └── "Please turn Wi-Fi off."
             │
             ▼
          Firmware
```

versus:

```text
Hardware Wi-Fi Disable

POWER
  │
  X  ← physical disconnect
  │
Wi-Fi Radio
```

If a radio has no power, malicious radio firmware cannot simply ignore a software request to disable itself.

The same philosophy may be applied to:

- microphones
- cameras
- Wi-Fi
- Bluetooth
- optional cellular hardware

---

## Transparency

Security limitations are part of the documentation.

Failures are part of the documentation.

Proprietary dependencies are part of the documentation.

Design mistakes are part of the documentation.

ONYX-NULL should earn trust through **evidence and transparency**, not marketing claims.

---

## Reproducibility

The long-term objective is for another person to reproduce ONYX-NULL using only publicly available project documentation.

That means publishing editable source files rather than only finished manufacturing artifacts.

The project should eventually provide:

```text
Source
   │
   ▼
Documented Toolchain
   │
   ▼
Build
   │
   ▼
Verifiable Artifact
```

Independent reproduction is one of the project's major long-term milestones.

---

# What ONYX-NULL Is NOT

ONYX-NULL does **not** claim to be:

- untraceable
- completely anonymous
- unhackable
- surveillance-proof
- immune to radio direction finding
- immune to compromised network infrastructure
- immune to every supply-chain attack
- protection against every possible adversary

Any device actively communicating over a network or transmitting radio signals creates some form of observable information.

Telecommunications providers, Internet providers, VoIP providers, network operators, and other infrastructure may inherently observe certain metadata.

The goal of ONYX-NULL is therefore not:

> **Become invisible.**

The goal is:

> **Minimize unnecessary exposure and unnecessary trust while giving the owner meaningful control over the device.**

---

# P0 — The First Prototype

The first ONYX-NULL prototype will intentionally be simple.

P0 does **not** need:

- custom smartphone PCB
- cellular connectivity
- cameras
- polished enclosure
- custom silicon
- pocket-sized dimensions
- production-ready battery system

P0 needs to prove the communications architecture works.

### P0 Requirements

- [ ] Boot an open-source operating system
- [ ] Provide a usable display
- [ ] Connect through Wi-Fi
- [ ] Provide microphone input
- [ ] Provide audio output
- [ ] Support encrypted networking
- [ ] Support SIP/VoIP
- [ ] Establish an Internet voice call
- [ ] Successfully place an ordinary telephone call

Conceptually:

```text
                ONYX-NULL P0

               ┌───────────┐
               │  Display  │
               └─────┬─────┘
                     │
              ┌──────▼──────┐
              │             │
              │   Compute   │
              │   Platform  │
              │             │
              └──┬───────┬──┘
                 │       │
              Audio    Wi-Fi
                 │       │
                 │       ▼
                 │    Internet
                 │       │
                 │       ▼
                 │      VoIP
                 │       │
                 │       ▼
                 └───── PSTN
```


---

# Architecture Direction

The current architecture being investigated separates trusted computing components from communications hardware wherever practical.

```text
                    ONYX-NULL

              ┌─────────────────┐
              │                 │
              │ Trusted Compute │
              │     Domain      │
              │                 │
              │ CPU             │
              │ Memory          │
              │ Storage         │
              │ Operating System│
              │                 │
              └────────┬────────┘
                       │
                 Restricted I/O
                       │
          ┌────────────┼────────────┐
          │            │            │
          ▼            ▼            ▼
       Wi-Fi         Audio       Optional
       Radio         Hardware      Radio
          │            │            │
      HARDWARE      HARDWARE     HARDWARE
        KILL           KILL         KILL
       SWITCH         SWITCH       SWITCH
```

This architecture is **experimental and subject to change** as research progresses.

No diagram in this repository should be interpreted as a security guarantee until the relevant hardware has been implemented and tested.

---

# Development Path

ONYX-NULL will be developed incrementally.

```text
Research
   ↓
Threat Model
   ↓
Electronics
   ↓
Networking
   ↓
VoIP
   ↓
Bench Prototype
   ↓
First Call
   ↓
Hardware Isolation
   ↓
Battery Operation
   ↓
Custom PCB
   ↓
Custom Enclosure
   ↓
OS Hardening
   ↓
Security Testing
   ↓
Privacy Testing
   ↓
Reproducible Builds
   ↓
Independent Reproduction
   ↓
ONYX-NULL 1.0
```

See [`ROADMAP.md`](ROADMAP.md) for the complete development roadmap.

---

# Planned Documentation

Project documentation will live primarily under `/docs`.

Planned documents include:

| Document | Purpose |
|---|---|
| `THREAT_MODEL.md` | Defines the threats ONYX-NULL is designed to address |
| `TRUST_MODEL.md` | Documents required trust relationships |
| `SECURITY_GOALS.md` | Defines security objectives |
| `NON_GOALS.md` | Defines what ONYX-NULL explicitly does not attempt to solve |
| `REQUIREMENTS-P0.md` | Requirements for the first prototype |
| `ARCHITECTURE.md` | Overall system architecture |
| `NETWORK_THREAT_MODEL.md` | Documents network-level exposure |
| `REFERENCE_DESIGNS.md` | Research into existing platforms |
| `PROPRIETARY_COMPONENTS.md` | Tracks closed-source dependencies |
| `HARDWARE_TRUST.md` | Hardware trust and isolation analysis |
| `PRIVACY.md` | Privacy architecture and assumptions |

---

# Hardware

Future ONYX-NULL hardware releases are intended to include:

- native KiCad schematics
- native PCB layouts
- BOMs
- Gerber files
- pick-and-place files
- component documentation
- board revision history
- test procedures
- known hardware errata
- mechanical CAD
- enclosure files

Generated manufacturing files will not replace editable source designs.

---

# NULL/OS

`NULL/OS` is the working name for the software platform intended to eventually run on ONYX-NULL hardware.

The final architecture has **not yet been selected**.

Research will evaluate technologies including:

- embedded Linux
- hardened Linux environments
- AOSP-derived architectures
- application sandboxing
- encrypted storage
- Secure Boot
- Verified Boot
- hardware-backed keys
- reproducible builds
- secure update mechanisms
- network isolation

No security properties should be assumed until implemented and tested.

---

# Security

Security claims must be supported by implementation and testing.

ONYX-NULL follows a simple rule:

> **Measure rather than advertise.**

Future testing is intended to cover areas including:

- radio isolation
- microphone isolation
- camera isolation
- boot integrity
- network exposure
- VPN failure behavior
- update integrity
- physical-access scenarios
- malicious peripheral scenarios
- proprietary firmware boundaries
- lost-device scenarios

See [`SECURITY.md`](SECURITY.md) as the project develops.

---

# Open Source / Open Hardware

ONYX-NULL is intended to become an open hardware and open-source software project.

The repository will eventually contain the information necessary to understand, modify, build, and reproduce the platform.

Some third-party components may still require proprietary firmware.

Those dependencies will be **explicitly documented rather than hidden.**

---

# Licensing

ONYX-NULL uses a multi-license structure because hardware, software, documentation, and branding have different requirements.

The intended licensing structure is:

| Component | License |
|---|---|
| Original hardware designs | CERN-OHL-S-2.0 |
| Original ONYX-NULL software | GPL-3.0-or-later |
| Documentation | CC BY-SA 4.0 |
| Third-party components | Their respective licenses |
| ONYX-NULL branding | Reserved separately |

See `LICENSE.md` and `/LICENSES` as licensing documentation is added.

---

# Contributing

ONYX-NULL is currently an experimental research project.

As development progresses, contributions in areas such as the following will be valuable:

- electrical engineering
- embedded systems
- PCB design
- RF engineering
- Linux
- Android/AOSP security
- hardware security
- networking
- VoIP
- cryptography
- power management
- secure boot
- reproducible builds
- threat modeling
- industrial design
- technical documentation

See [`CONTRIBUTING.md`](CONTRIBUTING.md) once contributor guidelines are established.

---

# Project Naming

```text
ONYX-NULL       Overall project

ONX-P0          Prototype 0
ONX-P1          Prototype 1

ONX-M1          Mainboard generation 1
ONX-M2          Mainboard generation 2

ONX-R1          Radio module generation 1

NULL/OS         Operating system
```

---

# Current Development Status

```text
PROJECT:     ONYX-NULL
TYPE:        Open Mobile Communications Platform

STATUS:      Research / Pre-P0

CURRENT:
Threat modeling
Architecture research
Electronics research
Networking research
VoIP research

NEXT:
ONYX-NULL P0

OBJECTIVE:
Successfully place the first telephone call.
```

---

# Disclaimer

ONYX-NULL is experimental.

Current prototypes and designs should not be depended upon for emergency communications, safety-critical applications, or environments requiring certified communications equipment.

Security properties described throughout the project represent objectives until they have been implemented, measured, tested, and independently reviewed.

---

# ONYX-NULL

### Open Mobile Communications Platform

> **Trust less. Verify more.**
