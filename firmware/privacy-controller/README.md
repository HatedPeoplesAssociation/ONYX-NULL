# ONYX-NULL Privacy Controller

This directory is reserved for firmware and documentation related to a possible dedicated ONYX-NULL privacy controller.

---

# Purpose

A privacy controller may provide an independent hardware path between physical user controls and privacy-sensitive peripherals.

Potentially controlled hardware includes:

- Wi-Fi
- Bluetooth
- microphone
- cameras
- optional cellular modem

---

# Conceptual Model

```text
PHYSICAL SWITCH
      │
      ▼
PRIVACY CONTROLLER
      │
      ├────────► POWER SWITCH
      │              │
      │              ▼
      │          PERIPHERAL
      │
      └────────► HARDWARE LED
```

---

# Primary Requirement

The main operating system should not be able to override a physical privacy switch.

If the physical switch requests OFF, the controlled hardware should be electrically disabled where the design supports that property.

---

# Trusted Indicators

A future design may use indicators directly controlled from the privacy power domain.

For example:

```text
RADIO POWER
    │
    ├──► RADIO
    │
    └──► INDICATOR
```

This can make the indicator reflect actual electrical power rather than only software state.

---

# Firmware Responsibilities

Possible responsibilities include:

- read switch states
- control power gates
- debounce switches
- report hardware state
- control trusted LEDs
- detect hardware faults

---

# Firmware Non-Responsibilities

The privacy controller should ideally not handle:

- user messages
- calls
- contacts
- encryption keys
- application data
- general networking

---

# Fail-Safe Design

The project must define what happens if the controller fails.

Possible policy:

```text
CONTROLLER FAILURE
       │
       ▼
PRIVACY-SENSITIVE HARDWARE
       │
       ▼
OFF
```

Whether this is practical depends on final hardware architecture.

---

# Testing

Future tests should include:

- switch transitions
- rapid switch toggling
- controller reset
- corrupted state
- host compromise simulation
- power loss
- boot sequencing
- indicator accuracy

---

# Current Status

This is a conceptual subsystem.

No privacy-controller architecture has been finalized.
