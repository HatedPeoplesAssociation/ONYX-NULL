# ONYX-NULL Architecture

## Status

Conceptual.

The architecture will evolve during research and prototyping.

## High-Level Model

```text
                ONYX-NULL

        ┌────────────────────┐
        │ Trusted Compute    │
        │ Domain             │
        │                    │
        │ CPU                │
        │ RAM                │
        │ Storage            │
        │ OS                 │
        └─────────┬──────────┘
                  │
             Restricted I/O
                  │
        ┌─────────┼─────────┐
        │         │         │
        ▼         ▼         ▼
      Wi-Fi     Audio     Optional
      Radio     System     Modem
        │         │         │
     Physical  Physical  Physical
      Power     Control    Power
      Control             Control
```

## Architectural Principles

* radios should be isolated from trusted compute
* proprietary firmware should have minimal privileges
* privacy-sensitive peripherals should support physical control
* unnecessary services should remain disabled
* network identities should be compartmentalized where practical
* security boundaries should be documented

## Hardware Direction

The initial prototype will likely use:

* existing compute module or SBC
* external display
* external audio
* external Wi-Fi
* USB-C power

Later revisions may integrate these components onto a custom mainboard.

## Software Direction

Potential operating-system architectures include:

* hardened embedded Linux
* mobile Linux
* AOSP-derived architecture

The final choice has not yet been made.

## Communication Direction

Primary communication technologies under consideration include:

* SIP
* TLS
* SRTP
* WireGuard
* encrypted messaging systems

Conventional PSTN interoperability may be provided through external VoIP infrastructure.
