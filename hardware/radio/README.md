# ONYX-NULL Radio Hardware

This directory contains research, designs, testing, component evaluations, and documentation related to wireless hardware used by ONYX-NULL.

---

# Philosophy

Radio hardware is treated as a potentially untrusted subsystem.

The ONYX-NULL architecture should minimize the privileges and physical access available to radio components.

A radio being necessary for communication does not mean it should automatically be trusted with unrestricted access to the rest of the device.

---

# Potential Radios

ONYX-NULL may eventually interact with:

- Wi-Fi
- Bluetooth
- GNSS
- optional cellular modem
- external radio modules
- experimental mesh-radio hardware

Not every ONYX-NULL configuration needs every radio.

---

# Default Direction

The initial ONYX-NULL architecture does not require cellular connectivity.

A baseline configuration may operate using:

```text
ONYX-NULL
     │
     ▼
   Wi-Fi
     │
     ▼
 Internet
     │
     ├── SIP / VoIP
     ├── VPN
     └── Encrypted Messaging
```

---

# Optional Cellular Architecture

Cellular capability should remain optional.

Potential arrangements include:

```text
ONYX-NULL
     │
     ├── Wi-Fi Only
     │
     ├── External Cellular Hotspot
     │
     └── Physically Isolated Optional Modem
```

An external hotspot can separate the main handset's trusted computing environment from the cellular baseband.

It does not eliminate location or metadata produced by the cellular hotspot itself.

---

# Hardware Isolation

Preferred radio architecture:

```text
POWER RAIL
    │
    ▼
PHYSICAL SWITCH
    │
    ▼
LOAD SWITCH
    │
    ▼
RADIO MODULE
```

The privacy switch should affect actual electrical power rather than merely requesting that firmware disable the radio.

---

# Hardware Enable Lines

Many radio modules provide signals such as:

```text
ENABLE
RESET
WAKE
POWER_ENABLE
```

These may be useful for normal power management.

They should not automatically be considered equivalent to a true physical power disconnect.

The design should determine what electrical state actually prevents operation.

---

# Software Control

Software may additionally control radio operation.

Software control must not be described as equivalent to physical power isolation.

---

# Radio Trust Boundary

Conceptually:

```text
┌──────────────────────┐
│ Trusted Compute      │
│                      │
│ CPU                  │
│ RAM                  │
│ Storage              │
└──────────┬───────────┘
           │
     Restricted Bus
           │
┌──────────▼───────────┐
│ Radio Module         │
│                      │
│ Firmware may be      │
│ proprietary          │
└──────────┬───────────┘
           │
        Antenna
```

The radio should receive only the access necessary to perform its function.

---

# Research Requirements

For every radio module, document:

```text
Manufacturer:
Part Number:

Technology:

Wi-Fi Standards:
Bluetooth Version:
GNSS:
Cellular:
Other:

Firmware Required:
Firmware Open:
Driver Open:

Host Interface:
USB:
PCIe:
SDIO:
UART:
Other:

DMA Capability:
Memory Access:

Frequency Bands:
Transmit Power:

Power Rails:
Idle Current:
Transmit Current:
Peak Current:

Hardware Reset:
Hardware Enable:
Physical Power Isolation Possible:

Antenna Requirements:

Linux Support:

AOSP Support:

Datasheet Available:

Firmware Update Method:

Known Vulnerabilities:

Lifecycle Status:

Possible Alternatives:

Notes:
```

---

# Antenna Design

Future RF design must consider:

- antenna type
- antenna placement
- antenna clearance
- impedance
- feed-line routing
- grounding
- shielding
- enclosure materials
- nearby high-speed signals
- display interference
- battery placement
- human-body effects

---

# Verification

Hardware radio isolation should eventually be tested by:

- measuring module power rails
- measuring current draw
- confirming device enumeration disappears
- confirming transmissions cease
- checking enable/reset pins
- testing whether software can override the physical switch
- documenting the test equipment used

---

# Radio State Indicators

The device may eventually provide hardware-visible state indicators.

The design should avoid a situation where software reports:

```text
RADIO OFF
```

while hardware remains powered.

Where practical, indicators should derive from the actual switched power state.

---

# RF Testing

Future testing may include:

- spectrum observation
- transmit-power verification
- antenna performance
- coexistence testing
- interference testing
- power consumption
- Wi-Fi throughput
- Bluetooth operation
- physical kill-switch effectiveness

---

# Regulatory Considerations

Radio hardware must be designed and operated within applicable spectrum and equipment regulations.

Prototype development does not eliminate regulatory requirements for intentional radio transmitters.

---

# Privacy Limitation

A powered and transmitting radio may potentially be detected or localized.

ONYX-NULL hardware controls can determine whether a radio is operational.

They cannot make an active RF transmission physically invisible.
