# ONYX-NULL Hardware Tests

This directory contains electrical, physical, thermal, power, interface, audio, and reliability testing for ONYX-NULL hardware.

---

# Hardware Test Areas

Testing may include:

- power rails
- current consumption
- charging
- battery
- USB-C
- audio
- display
- touchscreen
- buttons
- privacy switches
- sensors
- thermals
- suspend/resume
- physical assembly

---

# Suggested Structure

```text
hardware/
├── README.md
├── HW-001-power-rails/
├── HW-002-idle-current/
├── HW-003-mic-switch/
├── HW-004-wifi-switch/
├── HW-005-audio/
├── HW-006-thermal/
└── HW-007-battery/
```

---

# HW-001 — Power Rail Verification

Goal:

Verify all major power rails are within expected voltage range.

Record:

```text
Rail:

Expected Voltage:

Measured Voltage:

Tolerance:

Result:
```

---

# HW-002 — Current Consumption

Measure:

```text
Power Off

Boot

Idle

Display On

Wi-Fi Idle

Wi-Fi Active

VoIP Call

Suspend

Charging
```

---

# HW-003 — Microphone Hardware Isolation

Goal:

Verify microphone power or signal path is physically disconnected when switch is OFF.

Measurements may include:

- supply voltage
- signal continuity
- recorded audio

---

# HW-004 — Wi-Fi Hardware Isolation

Goal:

Verify radio loses electrical power when the physical Wi-Fi switch is OFF.

Check:

```text
Power Rail

USB / PCIe / SDIO Enumeration

Network Connectivity

RF Activity
```

---

# HW-005 — Audio

Test:

- microphone
- earpiece
- speaker
- headset
- full-duplex call
- volume
- distortion
- latency
- echo

---

# HW-006 — Thermal

Measure temperatures during:

- idle
- charging
- CPU load
- continuous call
- Wi-Fi load

Important locations may include:

- CPU
- PMIC
- charger
- battery
- radio
- enclosure surface

---

# HW-007 — Battery

Test:

- charging
- discharge
- runtime
- shutdown threshold
- temperature
- fuel-gauge accuracy
- suspend drain

---

# HW-008 — USB-C

Test:

- power input
- data
- orientation
- charging negotiation
- recovery interface
- connector mechanical strength

---

# HW-009 — Buttons

Test:

- power
- volume
- privacy switches
- debounce
- repeated operation

---

# HW-010 — Display

Test:

- initialization
- brightness
- touchscreen
- suspend/resume
- orientation
- connector stability

---

# HW-011 — Suspend / Resume

Goal:

Verify device reliably enters and exits low-power state.

Record:

- suspend current
- wake sources
- resume time
- failed resumes

---

# HW-012 — Power Loss

Goal:

Verify behavior when external power or battery power is unexpectedly removed.

Do not perform unsafe battery fault testing.

---

# Revision Requirement

Hardware tests must identify exact PCB and enclosure revision.

Example:

```text
Mainboard:
ONX-M1 REV-A

Enclosure:
ONX-ENC-P1
```

---

# Current Status

No ONYX-NULL production hardware has completed this test suite yet.
