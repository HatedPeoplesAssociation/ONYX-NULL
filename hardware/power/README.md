# ONYX-NULL Power System

This directory contains research, designs, test results, and documentation for ONYX-NULL power management.

Power architecture is simultaneously:

- a reliability concern
- a safety concern
- a privacy concern
- a security concern

---

# Responsibilities

The power subsystem may eventually provide:

- battery charging
- battery protection
- voltage regulation
- current monitoring
- fuel gauging
- thermal monitoring
- USB-C input
- USB Power Delivery
- power sequencing
- radio power gating
- peripheral power gating
- suspend power management
- controlled shutdown

---

# Conceptual Architecture

```text
USB-C
  │
  ▼
CHARGER / POWER PATH
  │
  ├──────────────► SYSTEM POWER
  │
  ▼
BATTERY
  │
  ▼
PROTECTION
  │
  ▼
POWER MANAGEMENT
  │
  ├── Compute
  ├── Display
  ├── Audio
  ├── Wi-Fi
  ├── Cameras
  └── Other Peripherals
```

---

# Privacy Power Domains

Privacy-sensitive hardware should use separately controllable power domains where practical.

Example:

```text
MAIN POWER
    │
    ├────────────► COMPUTE
    │
    ├── SWITCH ──► WI-FI
    │
    ├── SWITCH ──► MICROPHONE
    │
    ├── SWITCH ──► CAMERAS
    │
    └── SWITCH ──► OPTIONAL MODEM
```

---

# Hardware Kill-Switch Requirement

A privacy kill switch should ideally control electrical power independently of application software.

Example:

```text
BATTERY
   │
   ▼
REGULATOR
   │
   ▼
PHYSICAL SWITCH
   │
   X
   │
RADIO
```

Software should not be capable of bypassing the disconnected state.

---

# Battery Safety

Lithium-ion and lithium-polymer batteries can cause serious damage or fire if:

- overcharged
- over-discharged
- short-circuited
- punctured
- crushed
- overheated
- charged incorrectly
- used outside specification

Early prototypes should use:

- reputable cells
- proper protection circuitry
- proven charger ICs
- appropriate temperature monitoring
- over-current protection
- over-voltage protection
- under-voltage protection

Do not improvise unsafe battery charging circuits.

---

# Research Areas

Research should cover:

- Li-ion chemistry
- LiPo chemistry
- charging profiles
- battery protection
- USB-C
- USB Power Delivery
- PMICs
- buck converters
- boost converters
- buck-boost converters
- LDO regulators
- fuel gauges
- sleep power
- thermal protection
- current measurement
- power sequencing
- load switches

---

# Power Rails

Every hardware revision should document all significant rails.

Example:

```text
VBAT
5V0_SYS
3V3_SYS
1V8_SYS
3V3_WIFI
1V8_AUDIO
3V3_SENSOR
```

For each rail document:

```text
Nominal Voltage:
Minimum Voltage:
Maximum Voltage:
Maximum Current:
Source:
Loads:
Enable Control:
Physical Switch:
Test Point:
```

---

# Measurements

Every prototype should record:

```text
Input Voltage:

Input Current:

Battery Voltage:

Battery Capacity:

Idle Current:

Suspend Current:

Wi-Fi Idle Current:

Wi-Fi Active Current:

Call Current:

Display-On Current:

Peak Current:

Charging Current:

Charging Temperature:

Runtime:

Shutdown Voltage:
```

---

# Power States

Future versions should document clearly defined states such as:

```text
OFF
BOOT
ACTIVE
CALL
IDLE
SUSPEND
CHARGING
RECOVERY
```

Each state should specify which rails and peripherals remain powered.

---

# USB-C

Research should document:

- connector type
- USB role
- charging behavior
- CC resistors
- current negotiation
- Power Delivery support
- ESD protection
- over-voltage protection
- USB data isolation where relevant

---

# Thermal Testing

Future prototypes should measure temperatures at:

- battery
- charger IC
- PMIC
- application processor
- Wi-Fi module
- regulators
- enclosure surface

Test under:

- idle
- charging
- continuous VoIP call
- heavy CPU load
- heavy Wi-Fi load

---

# Long-Term Goals

The finished power system should aim for:

- safe charging
- replaceable battery where practical
- predictable shutdown
- accurate battery reporting
- low suspend consumption
- physical peripheral isolation
- documented power states
- accessible measurement points
- recoverability from abnormal conditions
