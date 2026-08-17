# ONYX-NULL // Master R&D Roadmap

**Mission:** Develop an open-source, owner-controlled mobile communications platform emphasizing verifiable security, hardware isolation, minimal trust, repairability, and reproducibility.

**Principle:** _Trust less. Verify more._

---

## STAGE 0 — Establish the Project

-  Create a dedicated ONYX-NULL project directory.
    
-  Create the Git repository.
    
-  Create the initial README.
    
-  Write a one-paragraph project mission.
    
-  Define what ONYX-NULL **is**.
    
-  Define what ONYX-NULL **is not**.
    
-  Explicitly avoid claims such as "untraceable," "unhackable," or "anonymous."
    
-  Define the intended audience.
    
-  Define your initial budget.
    
-  Start a development journal.
    
-  Record every major design decision and why it was made.
    
-  Create an issue tracker.
    
-  Create project milestones.
    
-  Create a version-numbering convention.
    

### Initial repository

```text
onyx-null/
├── README.md
├── LICENSES/
├── docs/
├── hardware/
├── mechanical/
├── firmware/
├── software/
├── os/
├── tools/
├── tests/
└── prototypes/
```

---

# STAGE 1 — Threat Modeling

**Do this before designing hardware.**

-  Research basic threat modeling.
    
-  Identify the information ONYX-NULL needs to protect.
    
-  Identify likely adversaries.
    
-  Separate ordinary privacy threats from sophisticated attacks.
    
-  Document assumptions.
    
-  Document trust boundaries.
    
-  Document unavoidable metadata.
    
-  Document what upstream network providers can observe.
    
-  Document what radio operators can observe.
    
-  Document physical-access threats.
    
-  Document malicious-app threats.
    
-  Document malicious-peripheral threats.
    
-  Document supply-chain threats.
    
-  Document stolen-device scenarios.
    
-  Document firmware-compromise scenarios.
    
-  Document account-compromise scenarios.
    
-  Document malicious Wi-Fi scenarios.
    
-  Document USB attack scenarios.
    
-  Document microphone/camera abuse.
    
-  Document location-leakage mechanisms.
    
-  Decide which threats ONYX-NULL will actually address.
    
-  Explicitly list threats it **doesn't** claim to solve.
    

### Produce

```text
docs/THREAT_MODEL.md
docs/TRUST_MODEL.md
docs/SECURITY_GOALS.md
docs/NON_GOALS.md
```

---

# STAGE 2 — Define V0 Requirements

Don't design the ultimate phone yet.

Define **ONYX-NULL P0**.

-  Must boot an open-source operating system.
    
-  Must connect to Wi-Fi.
    
-  Must output audio.
    
-  Must accept microphone input.
    
-  Must have a usable display.
    
-  Must support SIP/VoIP.
    
-  Must make an outgoing telephone call.
    
-  Must receive encrypted Internet calls.
    
-  Must support a VPN.
    
-  Must function without cellular service.
    
-  Cellular modem is **not required for P0**.
    
-  Cameras are **not required for P0**.
    
-  Pocket-sized packaging is **not required for P0**.
    
-  Battery power is **not required for the first bench prototype**.
    

### Produce

```text
docs/REQUIREMENTS-P0.md
```

---

# STAGE 3 — Learn Basic Electronics

Do not skip this.

### Theory

-  Voltage
    
-  Current
    
-  Resistance
    
-  Ohm's law
    
-  Electrical power
    
-  Series circuits
    
-  Parallel circuits
    
-  Ground
    
-  Short circuits
    
-  Pull-up resistors
    
-  Pull-down resistors
    
-  Capacitors
    
-  Diodes
    
-  LEDs
    
-  Transistors
    
-  MOSFETs
    
-  Voltage regulators
    
-  Logic levels
    
-  ADC
    
-  PWM
    

### Interfaces

-  GPIO
    
-  UART
    
-  I²C
    
-  SPI
    
-  USB basics
    

### Buy

-  Multimeter
    
-  Breadboards
    
-  Jumper wires
    
-  Resistor assortment
    
-  Capacitor assortment
    
-  LEDs
    
-  Buttons
    
-  MOSFETs
    
-  RP2040 development board
    
-  Basic soldering iron
    
-  Solder
    
-  Flux
    
-  Wire cutters
    
-  Wire strippers
    

### Build

-  Light an LED.
    
-  Control an LED with a button.
    
-  Control an LED from a microcontroller.
    
-  Read a button from GPIO.
    
-  Communicate over UART.
    
-  Connect an I²C sensor.
    
-  Switch a load with a MOSFET.
    
-  Completely remove power from a peripheral using a physical switch.
    
-  Verify the disconnected power rail with your multimeter.
    

That final experiment becomes the foundation of ONYX-NULL's hardware kill switches.

---

# STAGE 4 — Strengthen Linux Knowledge

-  Understand the Linux boot sequence.
    
-  Learn what the bootloader does.
    
-  Understand the kernel.
    
-  Understand initramfs.
    
-  Understand systemd.
    
-  Understand `/dev`.
    
-  Understand `/sys`.
    
-  Understand `/proc`.
    
-  Learn Linux permissions.
    
-  Learn users/groups.
    
-  Learn Linux capabilities.
    
-  Learn process isolation.
    
-  Learn namespaces.
    
-  Learn cgroups.
    
-  Learn filesystems.
    
-  Learn disk encryption.
    
-  Compile a C program manually.
    
-  Compile software from source.
    
-  Compile a Linux kernel.
    
-  Boot a custom kernel.
    
-  Break a test Linux installation.
    
-  Recover it without reinstalling.
    

---

# STAGE 5 — Networking Fundamentals

Learn what actually happens when ONYX-NULL communicates.

-  Ethernet
    
-  MAC addresses
    
-  ARP
    
-  IPv4
    
-  IPv6
    
-  DHCP
    
-  DNS
    
-  TCP
    
-  UDP
    
-  NAT
    
-  Routing
    
-  TLS
    
-  Certificates
    
-  Public-key cryptography basics
    
-  VPN concepts
    
-  WireGuard
    
-  Wi-Fi fundamentals
    

### Laboratory

-  Capture your own traffic with Wireshark.
    
-  Identify DNS requests.
    
-  Identify TCP handshakes.
    
-  Observe TLS connections.
    
-  Configure WireGuard.
    
-  Capture traffic again.
    
-  Compare what is observable before and after the VPN.
    
-  Document exactly what each network participant can see.
    

### Produce

```text
docs/NETWORK_THREAT_MODEL.md
```

---

# STAGE 6 — Learn VoIP

Research:

-  PSTN
    
-  SIP
    
-  RTP
    
-  SRTP
    
-  SIP over TLS
    
-  Codecs
    
-  PBXs
    
-  DID numbers
    
-  Caller ID
    
-  NAT traversal
    
-  STUN
    
-  TURN
    
-  ICE
    
-  E911 implications
    
-  VoIP metadata
    

### Laboratory

-  Install a SIP client on Linux.
    
-  Establish SIP between two computers.
    
-  Make an audio call.
    
-  Configure encrypted signaling.
    
-  Configure encrypted media.
    
-  Experiment with Asterisk or another PBX.
    
-  Place an outbound PSTN call.
    
-  Receive an inbound PSTN call.
    

### Implement ONYX-NULL incoming behavior

```text
CALL
 │
 ▼
VoIP server
 │
 ▼
answer
 │
 ▼
play prerecorded greeting
 │
 ▼
disconnect
 X

NO RECORDING
NO VOICEMAIL
NO BEEP
```

-  Verify that no caller audio is stored.
    
-  Document exactly what the VoIP provider can still observe.
    

---

# STAGE 7 — Study Existing Secure/Open Phones

Research existing projects rather than reinventing every solution.

Study:

-  GrapheneOS architecture.
    
-  Android security architecture.
    
-  AOSP.
    
-  CalyxOS.
    
-  PinePhone.
    
-  PinePhone Pro.
    
-  Librem 5.
    
-  Existing Linux mobile environments.
    
-  Existing open hardware projects.
    

For each, investigate:

-  Boot architecture
    
-  Secure/Verified Boot
    
-  Application sandbox
    
-  Modem isolation
    
-  Wi-Fi architecture
    
-  Hardware switches
    
-  Audio subsystem
    
-  Power management
    
-  Battery management
    
-  Display interface
    
-  Cameras
    
-  Sensors
    
-  Firmware dependencies
    
-  Proprietary components
    
-  Update model
    
-  Known security limitations
    

### Produce

```text
docs/REFERENCE-DESIGNS.md
```

---

# STAGE 8 — Select P0 Hardware

Only now choose the actual components.

Research:

-  ARM vs RISC-V.
    
-  SBC vs SoM.
    
-  Compute Module options.
    
-  Mainline Linux support.
    
-  Open driver availability.
    
-  Firmware requirements.
    
-  IOMMU availability.
    
-  Secure Boot capability.
    
-  Hardware crypto support.
    
-  Long-term component availability.
    

Select:

-  Compute platform
    
-  Display
    
-  Touch controller
    
-  Wi-Fi interface
    
-  Audio interface
    
-  Microphone
    
-  Speaker
    
-  Earpiece/headphones
    
-  USB-C interface
    

### Produce

```text
hardware/P0-BOM.csv
docs/P0-ARCHITECTURE.md
```

---

# STAGE 9 — Build ONYX-NULL P0

Build the ugly version.

```text
Display
   │
Compute board
 ├── Wi-Fi
 ├── microphone
 ├── speaker
 └── USB-C power
```

-  Boot Linux.
    
-  Enable touchscreen.
    
-  Get Wi-Fi working.
    
-  Get microphone working.
    
-  Get speaker working.
    
-  Configure VPN.
    
-  Install SIP client.
    
-  Make encrypted VoIP call.
    
-  Place PSTN call.
    

## MILESTONE

**ONYX-NULL P0 makes its first telephone call.**

Document the date.

Photograph the prototype.

Tag the repository:

`ONYX-NULL-P0`

---

# STAGE 10 — Begin Branding

Now that something actually works:

-  Finalize **ONYX-NULL** project name.
    
-  Research trademark conflicts.
    
-  Secure appropriate domain/social/repository names where desired.
    
-  Design logo.
    
-  Establish typography.
    
-  Establish visual language.
    
-  Establish schematic/documentation style.
    
-  Establish PCB silkscreen conventions.
    
-  Establish product naming conventions.
    

Example:

```text
ONYX-NULL        Project

ONX-P0           Prototype 0
ONX-P1           Prototype 1

ONX-M1           Mainboard
ONX-R1           Radio module

NULL/OS          Operating system
```

-  Create project website.
    
-  Add project philosophy.
    
-  Add documentation portal.
    
-  Add repository link.
    
-  Publish development log.
    

---

# STAGE 11 — Study Security Engineering

Research:

-  Secure Boot
    
-  Verified Boot
    
-  Measured Boot
    
-  TPM
    
-  Secure elements
    
-  Hardware-backed keys
    
-  IOMMU
    
-  DMA attacks
    
-  SELinux
    
-  seccomp
    
-  application sandboxing
    
-  ASLR
    
-  CFI
    
-  memory corruption
    
-  memory-safe languages
    
-  MTE
    
-  rollback protection
    
-  firmware signing
    
-  update security
    
-  supply-chain security
    
-  reproducible builds
    

For **every component**, ask:

> What happens if this component is completely malicious?

Then design around the answer.

---

# STAGE 12 — Hardware Isolation Prototype

Prototype separate power domains.

```text
BATTERY
   │
   ├── trusted system
   │
   ├── SWITCH ──► Wi-Fi
   │
   ├── SWITCH ──► microphone
   │
   ├── SWITCH ──► cameras
   │
   └── SWITCH ──► optional modem
```

-  Build Wi-Fi physical isolation.
    
-  Build microphone physical isolation.
    
-  Build camera physical isolation.
    
-  Determine whether Bluetooth requires independent isolation.
    
-  Determine whether GNSS requires independent isolation.
    
-  Design optional modem isolation.
    
-  Verify every switch electrically.
    
-  Test whether software can override any switch.
    
-  Document results.
    

---

# STAGE 13 — Power System

Only after studying lithium battery safety:

-  Research Li-ion/LiPo chemistry.
    
-  Research battery protection.
    
-  Research charging.
    
-  Research USB-C Power Delivery.
    
-  Research PMICs.
    
-  Research thermal protection.
    
-  Research fuel gauges.
    
-  Research sleep/suspend power.
    

Then:

-  Select protected battery.
    
-  Add charger.
    
-  Add protection circuitry.
    
-  Add fuel gauge.
    
-  Add USB-C charging.
    
-  Measure idle consumption.
    
-  Measure call consumption.
    
-  Measure suspend consumption.
    
-  Test thermal behavior.
    

## MILESTONE

**ONYX-NULL makes a call while completely disconnected from wall power.**

---

# STAGE 14 — Learn KiCad and PCB Design

-  Learn schematic capture.
    
-  Learn symbols.
    
-  Learn footprints.
    
-  Learn PCB layout.
    
-  Learn ground planes.
    
-  Learn trace width.
    
-  Learn impedance basics.
    
-  Learn decoupling.
    
-  Learn EMI/EMC fundamentals.
    
-  Learn differential pairs.
    
-  Learn USB routing.
    
-  Learn manufacturing outputs.
    

Build several practice boards before the phone motherboard.

-  PCB #1 — LED board.
    
-  PCB #2 — microcontroller board.
    
-  PCB #3 — USB board.
    
-  PCB #4 — power-control board.
    
-  PCB #5 — ONYX-NULL peripheral board.
    

Only then:

-  Begin ONX-M1.
    

---

# STAGE 15 — ONX-M1 Custom Mainboard

Integrate:

-  Compute module
    
-  Power management
    
-  USB-C
    
-  Display
    
-  Touch
    
-  Audio codec
    
-  Microphones
    
-  Speaker
    
-  Wi-Fi
    
-  Physical radio isolation
    
-  Secure element if appropriate
    
-  Buttons
    
-  Vibration motor
    
-  Sensors
    
-  Debug interfaces
    

Before fabrication:

-  Electrical-rule check.
    
-  Design-rule check.
    
-  Independent schematic review.
    
-  Verify footprints.
    
-  Verify connector orientation.
    
-  Verify voltage rails.
    
-  Verify current requirements.
    
-  Verify component availability.
    

Order:

**ONX-M1 Revision A**

Expect problems.

Document every one.

---

# STAGE 16 — Mechanical Engineering

-  Learn basic CAD.
    
-  Measure PCB.
    
-  Model display.
    
-  Model battery.
    
-  Model buttons.
    
-  Model switches.
    
-  Model speakers.
    
-  Model USB-C.
    
-  Model antennas.
    
-  Design enclosure.
    
-  Design serviceability.
    
-  Make battery replaceable if practical.
    
-  Make screws accessible.
    
-  Avoid unnecessary adhesives.
    
-  3D print prototype.
    
-  Test ergonomics.
    
-  Drop-test sacrificial prototypes.
    
-  Test thermals.
    

---

# STAGE 17 — Develop NULL/OS

Only after hardware is understood.

-  Decide Linux vs AOSP-derived architecture.
    
-  Build automated OS image.
    
-  Minimize default packages.
    
-  Harden kernel configuration.
    
-  Configure sandboxing.
    
-  Configure encrypted storage.
    
-  Implement update system.
    
-  Implement Verified/Secure Boot where hardware permits.
    
-  Implement rollback protection where possible.
    
-  Configure firewall.
    
-  Configure VPN support.
    
-  Integrate SIP client.
    
-  Implement hardware-switch state indicators.
    
-  Ensure software never pretends a physically disabled component is available.
    

---

# STAGE 18 — Proprietary Component Audit

Create a complete inventory.

For every component document:

```text
Component
Manufacturer
Function
Firmware
Firmware open?
Driver open?
Datasheet available?
DMA access?
Network access?
Isolation mechanism?
Can power be physically removed?
Known vulnerabilities?
Replacement available?
```

### Produce

```text
docs/PROPRIETARY_COMPONENTS.md
docs/HARDWARE_TRUST.md
```

Never hide proprietary dependencies.

---

# STAGE 19 — Reproducible Builds

-  Pin toolchain versions.
    
-  Document build environment.
    
-  Automate builds.
    
-  Produce deterministic artifacts where possible.
    
-  Publish hashes.
    
-  Test clean-room rebuild.
    
-  Have another machine reproduce the image.
    
-  Compare artifacts.
    
-  Document remaining sources of nondeterminism.
    

Goal:

```text
PUBLIC SOURCE
      ↓
documented toolchain
      ↓
independent build
      ↓
same artifact/hash
```

---

# STAGE 20 — Security Testing

Create an actual test plan.

Test:

-  Locked-device security.
    
-  USB attack surface.
    
-  Malicious USB peripherals.
    
-  Network exposure.
    
-  Wi-Fi isolation.
    
-  Microphone isolation.
    
-  Camera isolation.
    
-  Boot-chain modification.
    
-  Downgrade attempts.
    
-  Update tampering.
    
-  Application sandbox escape assumptions.
    
-  Lost-device scenario.
    
-  Malicious application scenario.
    
-  Compromised radio scenario.
    
-  Recovery procedures.
    

### Produce

```text
tests/SECURITY-TEST-PLAN.md
docs/SECURITY-RESULTS.md
```

---

# STAGE 21 — Privacy Testing

Measure rather than advertise.

-  Record default outbound connections.
    
-  Document every default network endpoint.
    
-  Measure DNS leakage.
    
-  Test VPN failure behavior.
    
-  Verify radio kill switches.
    
-  Verify microphone kill switch.
    
-  Verify camera kill switch.
    
-  Audit location-related services.
    
-  Audit crash reporting.
    
-  Audit telemetry.
    
-  Document unavoidable metadata.
    

Publish the results.

---

# STAGE 22 — Documentation for Builders

Assume the reader has never spoken to you.

Write:

-  `README.md`
    
-  `GETTING_STARTED.md`
    
-  `BUILD.md`
    
-  `ASSEMBLY.md`
    
-  `FLASHING.md`
    
-  `RECOVERY.md`
    
-  `SECURITY.md`
    
-  `THREAT_MODEL.md`
    
-  `TRUST_MODEL.md`
    
-  `PRIVACY.md`
    
-  `NETWORKING.md`
    
-  `HARDWARE.md`
    
-  `NULL_OS.md`
    
-  `PROPRIETARY_COMPONENTS.md`
    
-  `KNOWN_LIMITATIONS.md`
    
-  `CONTRIBUTING.md`
    

Also publish:

-  Schematics.
    
-  Native KiCad files.
    
-  PCB files.
    
-  Gerbers.
    
-  BOM.
    
-  Pick-and-place files.
    
-  Enclosure CAD source.
    
-  STEP exports.
    
-  STL exports.
    
-  Firmware source.
    
-  OS source.
    
-  Build scripts.
    
-  Photographs.
    
-  Assembly photographs.
    
-  Troubleshooting guide.
    

---

# STAGE 23 — Licensing

Research licensing carefully before release.

Possible structure:

```text
Hardware       → CERN-OHL
Software       → appropriate OSI license
Documentation  → CC BY-SA / similar
Brand          → ONYX-NULL trademark
```

-  Choose hardware license.
    
-  Choose software license.
    
-  Choose documentation license.
    
-  Add SPDX identifiers where appropriate.
    
-  Audit third-party licenses.
    
-  Document proprietary third-party components.
    
-  Create `LICENSES/`.
    
-  Create attribution documentation.
    
-  Establish trademark policy for ONYX-NULL.
    

The **design can be open while the ONYX-NULL name/logo remains protected branding.**

---

# STAGE 24 — External Review

Before calling it secure:

-  Ask Linux developers to review it.
    
-  Ask embedded developers to review it.
    
-  Ask electrical engineers to review it.
    
-  Ask RF engineers to review it.
    
-  Ask security researchers to review it.
    
-  Ask privacy researchers to review the threat model.
    
-  Publish unresolved criticism.
    
-  Open issues for legitimate findings.
    
-  Fix them.
    
-  Credit researchers.
    

Eventually create:

```text
SECURITY.md
```

with a vulnerability-reporting process.

---

# STAGE 25 — Builder Reproduction Test

This is one of the most important milestones.

Find someone who hasn't worked on ONYX-NULL.

Give them **only the public repository**.

Ask them to build it.

Do not privately walk them through undocumented steps.

Record:

-  Missing instructions.
    
-  Ambiguous instructions.
    
-  Parts they couldn't obtain.
    
-  Software failures.
    
-  Hardware mistakes.
    
-  Toolchain problems.
    

Fix the documentation.

Repeat until someone can independently reproduce the device.

---

# STAGE 26 — Open Hardware Release

OSHWA certification is a natural eventual target.

Before applying:

-  Verify all original design files are public.
    
-  Verify BOM is public.
    
-  Verify editable CAD files are public.
    
-  Clearly identify proprietary components.
    
-  Verify hardware licensing.
    
-  Verify software licensing.
    
-  Verify documentation licensing.
    
-  Label hardware revision.
    
-  Publish complete source.
    
-  Review OSHWA requirements.
    
-  Apply for certification if appropriate.
    

---

# STAGE 27 — ONYX-NULL 1.0

Only call it **1.0** once you have:

-  Working handheld hardware.
    
-  Battery operation.
    
-  Reliable charging.
    
-  Reliable audio.
    
-  Reliable VoIP.
    
-  Physical privacy controls.
    
-  Working OS.
    
-  Secure update process.
    
-  Documented boot security.
    
-  Documented proprietary components.
    
-  Reproducible build process.
    
-  Published schematics.
    
-  Published PCB.
    
-  Published BOM.
    
-  Published enclosure.
    
-  Published source.
    
-  Complete assembly guide.
    
-  Complete threat model.
    
-  Security testing.
    
-  Independent reproduction.
    
-  External review.
    

Then:

```text
╔══════════════════════════════════╗
║                                  ║
║            ONYX-NULL             ║
║                                  ║
║   Open Communications Platform   ║
║                                  ║
║     Trust less. Verify more.      ║
║                                  ║
╚══════════════════════════════════╝
```


Your first objective is:

**ONYX-NULL P0 successfully makes one phone call.**

Everything builds outward from that.
