# ONYX-NULL Network Threat Model

## Purpose

This document tracks information exposed during network communications.

## Network Participants

Potential participants include:

```text
ONYX-NULL
   │
Wi-Fi AP
   │
Local router
   │
ISP
   │
VPN provider
   │
Internet
   │
Service provider
   │
Remote endpoint
```

## Observable Metadata

Depending on configuration, participants may observe:

* IP addresses
* timing
* connection duration
* traffic volume
* destination addresses
* DNS queries
* protocol information
* account identifiers

## VPN

A VPN changes which infrastructure can directly observe destination information.

It does not make the device anonymous.

The VPN provider becomes an additional trust relationship.

## DNS

DNS configuration should be documented and tested for leaks.

## VoIP

VoIP providers may observe:

* account identity
* originating IP
* destination number
* call timing
* call duration
* billing information

Encrypted signaling and media do not necessarily eliminate provider metadata.

## Research Goals

Testing should eventually determine:

* observable traffic without VPN
* observable traffic with VPN
* DNS behavior
* SIP metadata
* media encryption behavior
* fail-open/fail-closed behavior
