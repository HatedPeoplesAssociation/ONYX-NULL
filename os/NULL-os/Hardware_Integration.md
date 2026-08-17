# NULL/OS Hardware Integration

## Purpose

This document defines how NULL/OS interacts with ONYX-NULL hardware.

---

# Principle

Hardware state and software state must not be confused.

If hardware is physically disabled, software should recognize the state.

If software disables a device without removing power, it should not describe that as physical isolation.

---

# Hardware Categories

NULL/OS may interact with:

- compute module
- display
- touchscreen
- audio codec
- microphone
- speaker
- Wi-Fi
- Bluetooth
- optional modem
- GNSS
- cameras
- battery controller
- privacy controller
- sensors
- USB-C
- secure element

---

# Privacy Switch Integration

Potential model:

```text
PHYSICAL SWITCH
      │
      ▼
HARDWARE CONTROL
      │
      ├──► PERIPHERAL POWER
      │
      └──► STATE SIGNAL
                │
                ▼
             NULL/OS
```

NULL/OS receives state information.

NULL/OS does not control whether the physical switch is open.

---

# Example UI

```text
Wi-Fi
PHYSICALLY DISCONNECTED
```

versus:

```text
Wi-Fi
SOFTWARE DISABLED
```

These states should remain visibly distinct.

---

# Device Tree

If Linux is selected, hardware configuration may involve:

- Device Tree
- kernel configuration
- drivers
- firmware loading

Device-specific source should remain version-controlled.

---

# Drivers

Drivers should be evaluated for:

- source availability
- maintenance
- privileges
- attack surface
- firmware requirements
- upstream status

Prefer upstream drivers where practical.

---

# Firmware

Firmware dependencies should be documented separately.

See:

`../../firmware/`

and:

`../../docs/PROPRIETARY_COMPONENTS.md`

---

# Debug Interfaces

NULL/OS should expose debug functionality only according to device security state.

Development hardware may enable more debugging than release hardware.

---

# Hardware Detection

The OS should identify supported hardware revisions where possible.

Example:

```text
Hardware:
ONX-M1 REV-B

NULL/OS:
0.8.0
```

---

# Unsupported Hardware

NULL/OS should fail clearly rather than silently assuming incompatible hardware is safe.

---

# Current Status

Hardware integration begins with ONX-P0 once the initial compute platform has been selected.
