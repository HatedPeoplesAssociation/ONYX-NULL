# ONYX-NULL Threat Model

## Status

Draft.

This threat model will evolve as the architecture changes.

## Purpose

The purpose of this document is to define what ONYX-NULL attempts to protect, what threats it considers relevant, and what assumptions are made.

## Assets

ONYX-NULL may store or process:

* cryptographic keys
* account credentials
* contacts
* call history
* messages
* network configuration
* local files
* device configuration
* microphone input
* camera input
* authentication secrets
* personal metadata

## Potential Adversaries

The project considers threats including:

* malicious applications
* commercial data collection
* compromised websites
* malicious Wi-Fi networks
* opportunistic attackers
* thieves
* stalkers
* compromised peripherals
* compromised radio firmware
* supply-chain tampering
* malicious USB devices

## Attack Surfaces

Potential attack surfaces include:

* operating system
* bootloader
* kernel
* applications
* browser
* USB
* Wi-Fi
* Bluetooth
* cellular modem
* GNSS
* firmware
* update infrastructure
* audio subsystem
* cameras
* physical ports
* supply chain

## Threat Scenarios

ONYX-NULL should consider:

* stolen device
* malicious application
* compromised Wi-Fi access point
* malicious USB accessory
* compromised radio firmware
* compromised update server
* unauthorized microphone access
* unauthorized camera access
* account compromise
* malicious browser content
* physical tampering
* metadata correlation

## Design Direction

Where practical, ONYX-NULL should:

* reduce attack surface
* isolate radios
* minimize privileged software
* restrict DMA
* use hardware-backed key protection
* implement secure or verified boot
* encrypt persistent storage
* minimize telemetry
* use hardware privacy switches
* support secure updates

## Out of Scope

ONYX-NULL does not guarantee protection against:

* radio direction finding
* physical observation
* compromised upstream telecommunications networks
* unknown vulnerabilities
* advanced silicon-level implants
* every possible supply-chain attack
* perfect anonymity

See `NON_GOALS.md`.
