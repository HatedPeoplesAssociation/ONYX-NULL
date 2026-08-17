# ONYX-NULL Hardware Development Tools

This directory contains developer utilities used to inspect, test, configure, and validate ONYX-NULL hardware during development.

---

# Possible Tools

Examples include:

- GPIO test tools
- power-rail validation
- switch-state tests
- serial-console helpers
- I²C scanning
- SPI testing
- USB enumeration
- sensor diagnostics
- battery telemetry
- thermal monitoring

---

# Philosophy

Hardware tools should expose measurable state.

Prefer:

```text
3V3_WIFI = 0.01 V
```

over:

```text
Wi-Fi appears off
```

where physical measurement is available.

---

# Potential Commands

Examples:

```bash
onx-hwinfo
```

```bash
onx-gpio-test
```

```bash
onx-power-test
```

```bash
onx-switch-test
```

---

# Test Equipment

Some tests may require external equipment such as:

- multimeter
- oscilloscope
- logic analyzer
- bench power supply
- USB analyzer
- spectrum analyzer

The tool documentation should distinguish software measurements from external physical measurements.

---

# Hardware Revision

Tools should identify the hardware revision before performing revision-specific operations.

Example:

```text
Detected:
ONX-M1 REV-A
```

---

# Safe Operation

Tools controlling power rails must avoid:

- invalid voltage combinations
- unsafe power sequencing
- exceeding component limits

---

# Register Access

Low-level register tools may be useful during development.

They should not be exposed casually in production configurations if they weaken security.

---

# Current Status

No ONYX-NULL-specific hardware development tool currently exists.
