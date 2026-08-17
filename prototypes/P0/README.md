# ONYX-NULL P0

**Prototype:** ONX-P0  
**Stage:** Bench Prototype  
**Status:** Planned

P0 is the first functional ONYX-NULL prototype.

Its purpose is not to resemble a finished phone.

Its purpose is to prove the core communications path.

---

# Primary Milestone

> **ONYX-NULL P0 successfully places its first telephone call.**

That is the defining success condition for P0.

---

# Core Architecture

```text
DISPLAY
   │
   ▼
COMPUTE PLATFORM
   │
   ├── MICROPHONE
   │
   ├── SPEAKER
   │
   └── WI-FI
          │
          ▼
       INTERNET
          │
          ▼
         VPN
          │
          ▼
      SIP / VoIP
          │
          ▼
         PSTN
```

---

# P0 Requirements

P0 must:

- boot
- display usable output
- connect to Wi-Fi
- capture microphone audio
- output speaker/headset audio
- support VPN connectivity
- run a SIP client
- establish a two-way VoIP call
- place a PSTN call

---

# Not Required

P0 does not require:

- battery operation
- cellular modem
- custom PCB
- custom enclosure
- physical radio switches
- cameras
- polished user interface
- custom NULL/OS build

---

# P0 Build Phases

## P0-A — Compute

Success criteria:

- development board boots
- storage works
- Linux runs
- serial/debug access available

---

## P0-B — Display

Success criteria:

- display operates
- usable UI available
- touch works if applicable

---

## P0-C — Networking

Success criteria:

- Wi-Fi connects
- Internet works
- DNS works
- VPN works

---

## P0-D — Audio

Success criteria:

- microphone works
- speaker/headset works
- simultaneous input/output works

---

## P0-E — SIP

Success criteria:

- SIP account registers
- endpoint-to-endpoint SIP call works

---

## P0-F — Encrypted VoIP

Success criteria:

- signaling encryption verified where configured
- media encryption verified where configured
- stable two-way call achieved

---

## P0-G — PSTN

Success criteria:

- call placed from P0
- ordinary telephone receives call
- two-way audio works
- call terminates normally

At this point:

> **P0 SUCCESS**

---

# Planned P0 Hardware

Not yet selected.

Track candidates here:

```text
Compute:

Display:

Wi-Fi:

Audio:

Microphone:

Speaker:

Power:
```

---

# P0 Software

Initial P0 software may use existing open-source software.

Possible categories:

```text
Linux distribution

SIP client

WireGuard

PipeWire

Network manager
```

No custom NULL/OS build is required for P0.

---

# P0 Security Objective

P0 is a functional prototype.

It does not need to provide the final ONYX-NULL security architecture.

However:

- components should be documented
- proprietary firmware should be identified
- network behavior should be observed
- unnecessary services should be noted

---

# P0 Documentation

P0 should include:

```text
README.md
BUILD.md
BOM.csv
CONFIGURATION.md
ISSUES.md
RESULTS.md
photos/
logs/
```

---

# P0 Completion Evidence

When the first PSTN call succeeds, preserve:

- photograph of prototype
- date
- hardware list
- source commit
- OS version
- SIP configuration description
- network architecture
- call result
- test notes

Do not publish private SIP credentials.

---

# Next Stage

After P0 succeeds, development can move toward:

**P1 — Portable / Battery Prototype**
