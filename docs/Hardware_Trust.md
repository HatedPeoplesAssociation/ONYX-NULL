# ONYX-NULL Hardware Trust

## Purpose

This document records the trust relationships between physical components.

## Core Principle

A component should not automatically gain access to the entire system merely because it exists on the motherboard.

## Areas of Concern

Hardware trust analysis should include:

* CPU
* RAM
* storage
* secure element
* Wi-Fi
* Bluetooth
* cellular modem
* GNSS
* cameras
* microphones
* USB
* display controller
* GPU
* sensors
* power-management controller

## Isolation Techniques

Potential techniques include:

* IOMMU
* separate buses
* power gating
* hardware switches
* restricted USB interfaces
* dedicated microcontrollers
* memory protection
* signed firmware
* least-privileged drivers

## Physical Controls

Preferred privacy-sensitive controls include:

* microphone power disconnect
* camera power disconnect
* Wi-Fi power disconnect
* Bluetooth power disconnect where practical
* modem power disconnect

## Verification

Physical isolation should eventually be verified electrically.

Examples:

* measure power rail voltage
* inspect current draw
* verify radio transmission stops
* verify software cannot restore power
