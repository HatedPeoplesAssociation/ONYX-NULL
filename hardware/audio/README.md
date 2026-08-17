# ONYX-NULL Audio Hardware

This directory contains ONYX-NULL audio subsystem research, design files, testing, and documentation.

Audio is both a communications subsystem and a privacy-sensitive subsystem.

---

# Required Functions

The audio system may eventually support:

- earpiece
- loudspeaker
- microphone
- secondary microphone
- wired headset
- notification audio
- VoIP audio
- hardware microphone isolation

---

# Conceptual Architecture

```text
MICROPHONE
    │
    ▼
AUDIO CODEC
    │
    ▼
COMPUTE PLATFORM
    │
    ▼
AUDIO CODEC
    │
    ├── Earpiece
    ├── Speaker
    └── Headphones
```

---

# Microphone Privacy

The preferred microphone privacy design should physically prevent microphone audio from reaching the trusted compute system.

Potential approaches include:

## Power Isolation

```text
POWER
  │
  ▼
PHYSICAL SWITCH
  │
  X
  │
MICROPHONE
```

## Signal Isolation

```text
MICROPHONE
    │
    ▼
PHYSICAL SWITCH
    │
    X
    │
AUDIO CODEC
```

The final approach must be electrically verified.

---

# Design Question

The project should determine whether simply removing microphone power is sufficient for the selected microphone technology.

Different microphone types may behave differently.

Testing must verify the actual result rather than assuming isolation.

---

# Requirements

Research should determine:

- microphone type
- microphone sensitivity
- microphone bias requirements
- analog vs digital microphone
- codec compatibility
- codec Linux support
- speaker impedance
- speaker power
- earpiece impedance
- amplifier requirements
- wired headset support
- microphone noise
- echo
- feedback
- acoustic design
- full-duplex behavior
- power consumption

---

# Possible Microphone Types

Research may compare:

```text
Analog Electret
Analog MEMS
Digital PDM MEMS
Digital I²S MEMS
```

Selection should consider:

- privacy isolation
- software support
- audio quality
- physical size
- availability
- power
- circuit complexity

---

# Audio Codec Research Template

```text
Manufacturer:

Part Number:

Input Channels:

Output Channels:

Microphone Inputs:

Speaker Outputs:

Headphone Outputs:

Host Interface:

Digital Audio Interface:

Linux Driver:

Driver Open:

Datasheet Available:

Power Requirements:

Firmware Required:

Hardware Mute:

Hardware Shutdown:

Package:

Lifecycle Status:

Cost:

Notes:
```

---

# Software Interfaces

Potential software interfaces include:

- ALSA
- PipeWire
- PulseAudio compatibility
- Android audio stack if AOSP is eventually selected

---

# Audio Test Plan

Audio testing should eventually include:

- microphone recording
- earpiece playback
- speaker playback
- headset playback
- full-duplex calling
- latency
- echo
- noise floor
- distortion
- feedback
- volume range
- microphone kill-switch verification

---

# Full-Duplex Calling

A communications handset must support simultaneous:

```text
MICROPHONE → REMOTE USER

REMOTE USER → SPEAKER
```

without unacceptable:

- echo
- clipping
- delay
- instability
- feedback

---

# Privacy Verification

When the microphone hardware switch is disabled:

- microphone capture should stop
- the system should not receive meaningful microphone audio
- electrical measurements should confirm isolation
- software should not be capable of overriding the physical state

---

# Hardware State

The user interface should clearly indicate microphone state.

Software should not pretend to control a switch that is physically independent.

Possible future indicator:

```text
MIC
 ● LIVE

MIC
 ○ PHYSICALLY DISCONNECTED
```

---

# Speaker Privacy

Speaker output is not equivalent to microphone input, but the complete audio architecture should still be reviewed for unexpected signal paths.

Any component capable of functioning as an unintended input should be documented.

---

# Current Status

No final audio codec, microphone, speaker, or amplifier has been selected.
