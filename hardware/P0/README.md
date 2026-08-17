# ONYX-NULL P0

**Prototype:** ONX-P0  
**Status:** Planned  
**Development Stage:** Bench Prototype

P0 is the first functional ONYX-NULL communications prototype.

P0 is intentionally simple.

It does not need to look like a smartphone.

It does not need to fit in a pocket.

It does not need to contain custom hardware.

Its purpose is to prove that the core communications architecture works.

---

# Objective

The primary objective is:

> **ONYX-NULL P0 successfully places its first telephone call.**

Everything else is secondary.

---

# Required Capabilities

P0 must eventually:

- boot an open-source operating system
- provide a usable display
- connect through Wi-Fi
- capture microphone audio
- output audio
- support encrypted Internet connectivity
- support a VPN
- support SIP/VoIP
- place an outgoing telephone call

---

# Optional Capabilities

P0 may include:

- touchscreen input
- hardware privacy-switch experiments
- external keyboard
- external mouse
- external headset
- USB audio interface
- external debug console

---

# Not Required

P0 does not require:

- cellular service
- cellular modem
- custom PCB
- battery operation
- cameras
- custom enclosure
- custom operating system
- production-grade power management
- production-grade security
- pocket-sized construction

---

# Expected Architecture

```text
              ONYX-NULL P0

                 DISPLAY
                    │
                    ▼
            ┌──────────────┐
            │   COMPUTE    │
            │   PLATFORM   │
            │              │
            │ Linux        │
            │ VPN          │
            │ SIP Client   │
            └────┬────┬────┘
                 │    │
              Wi-Fi  Audio
                 │    │
                 │    ├── Microphone
                 │    └── Speaker
                 │
                 ▼
              INTERNET
                 │
                 ▼
             SIP / VoIP
                 │
                 ▼
                PSTN
```

---

# Initial Hardware Categories

P0 will require:

- compute platform
- storage
- display
- touch interface if applicable
- Wi-Fi interface
- microphone
- speaker or headset
- audio interface
- USB-C or equivalent power input
- development/debug interfaces

---

# P0 Development Stages

## P0-A — Boot

Goal:

- compute platform powers on
- Linux boots successfully
- serial/debug access works

## P0-B — Display

Goal:

- display initializes
- graphical environment works
- touchscreen works if applicable

## P0-C — Networking

Goal:

- Wi-Fi operates
- Internet connectivity works
- VPN connectivity works

## P0-D — Audio

Goal:

- microphone capture works
- speaker output works
- full-duplex audio works

## P0-E — SIP

Goal:

- SIP client connects
- test call between two SIP endpoints succeeds

## P0-F — Encrypted VoIP

Goal:

- encrypted signaling works
- encrypted media works
- stable two-way voice call succeeds

## P0-G — PSTN

Goal:

- ONYX-NULL successfully places a call to an ordinary telephone number

At P0-G, the primary P0 milestone has been reached.

---

# Documentation Requirements

Record:

- exact hardware
- exact part numbers
- firmware versions
- operating system
- kernel version
- drivers
- configuration
- power requirements
- network configuration
- VPN configuration
- VoIP configuration
- problems encountered
- failed experiments
- solutions
- photographs
- test results

---

# P0 Completion Record

When P0 successfully makes its first PSTN call, complete:

```text
Date:

Prototype Revision:

Compute Platform:

RAM:

Storage:

Operating System:

Kernel:

Display:

Wi-Fi Hardware:

Audio Hardware:

Microphone:

Speaker:

VPN:

SIP Software:

VoIP Provider:

Call Destination Type:

Call Duration:

Audio Quality:

Result:

Problems:

Notes:
```



Document the successful call.

Create a repository tag for the milestone.
