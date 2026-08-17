# ONYX-NULL Component Register

This document tracks hardware components researched, considered, accepted, rejected, or currently used by ONYX-NULL.

The component register is broader than a BOM.

A BOM records what a specific hardware revision uses.

The component register records the project's ongoing component research.

---

# Status Values

Components should use one of the following statuses:

```text
RESEARCHING
CANDIDATE
APPROVED
PROTOTYPE
REJECTED
REPLACED
OBSOLETE
```

---

# Security Classification

Components may also be assigned a trust classification:

```text
TRUSTED

RESTRICTED

UNTRUSTED

UNKNOWN
```

These classifications describe the intended architecture rather than making a claim that a component is free from vulnerabilities.

---

# Component Entry Template

Copy the following template for each component:

```text
## Component Name

Status:

Category:

Manufacturer:

Part Number:

Purpose:

Approximate Cost:

Lifecycle Status:

---

### Documentation

Datasheet Available:

Reference Manual Available:

Schematics Available:

Manufacturer Documentation:

---

### Software

Linux Support:

Kernel Driver:

Driver Open Source:

Firmware Required:

Firmware Open Source:

Firmware Update Method:

---

### Security

Trust Classification:

Host Interface:

DMA Access:

Memory Access:

Storage Access:

Network Access:

Secrets Accessible:

Secure Boot Interaction:

Firmware Signature Verification:

Known Vulnerabilities:

---

### Isolation

Can Be Physically Powered Off:

Independent Power Rail:

Hardware Reset:

Hardware Enable Pin:

IOMMU Isolation Possible:

Other Isolation:

---

### Electrical

Input Voltage:

Typical Current:

Peak Current:

Package:

Operating Temperature:

---

### Availability

Primary Supplier:

Secondary Supplier:

Minimum Order Quantity:

Alternative Components:

---

### Decision

Advantages:

Disadvantages:

Reason Accepted or Rejected:

Notes:
```

---

# Compute Platforms

## Example Placeholder

```text
Component:

Status: RESEARCHING

Category: Compute Platform

Manufacturer:

Part Number:

Purpose: Primary ONYX-NULL compute platform
```

---

# Wi-Fi / Bluetooth

Add researched wireless modules here.

Important factors include:

- firmware openness
- Linux support
- host interface
- DMA
- power control
- independent power domain
- antenna requirements

---

# Audio

Track:

- codecs
- amplifiers
- microphones
- speakers
- earpieces

---

# Power

Track:

- PMICs
- charger ICs
- load switches
- regulators
- fuel gauges
- USB-C controllers

---

# Security Hardware

Track:

- secure elements
- TPMs
- hardware key-storage devices
- security microcontrollers

---

# Displays

Track:

- LCD panels
- OLED panels
- touch controllers
- display adapters

---

# Cameras

Track:

- image sensors
- camera modules
- hardware power-control options

---

# Sensors

Track:

- accelerometers
- gyroscopes
- magnetometers
- proximity sensors
- ambient-light sensors

---

# Connectors

Track:

- USB-C
- board-to-board connectors
- FPC connectors
- battery connectors
- debug connectors

---

# Decision Philosophy

A component should not be selected only because it is technically capable.

Selection should also consider:

```text
DOCUMENTATION
      +
AVAILABILITY
      +
SECURITY
      +
PRIVACY
      +
LINUX SUPPORT
      +
POWER
      +
REPAIRABILITY
      +
COST
      +
LONGEVITY
```

---

# Proprietary Components

A proprietary component is not automatically rejected.

Instead, ONYX-NULL should ask:

1. Is it necessary?
2. What does it have access to?
3. Can it be isolated?
4. Can it be physically disabled?
5. Is the interface documented?
6. Is the driver open?
7. Is an open alternative available?
8. What would happen if its firmware were malicious?

The answer should be documented before accepting the component.
