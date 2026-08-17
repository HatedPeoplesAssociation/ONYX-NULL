# NULL/OS Boot Model

## Purpose

This document defines the intended relationship between NULL/OS and the ONYX-NULL boot chain.

---

# Security Objective

The boot process should attempt to ensure that the software executing on the device matches an authorized system state.

---

# Conceptual Chain

```text
HARDWARE ROOT OF TRUST
        │
        ▼
BOOT ROM
        │
        ▼
BOOTLOADER
        │
        ▼
VERIFY KERNEL / SYSTEM
        │
        ▼
KERNEL
        │
        ▼
NULL/OS
```

---

# Verified Boot

Verified boot should verify cryptographic authenticity and integrity before executing protected software.

---

# Owner Control

ONYX-NULL should investigate an owner-controlled boot model.

Important questions include:

- Can the owner install a new trusted key?
- Can the bootloader be unlocked?
- Can it be relocked?
- Is unlock state visible?
- Does unlocking destroy secrets?
- Can rollback protection remain functional?
- Can custom operating systems remain verified?

---

# Development State

A development system may allow:

- unsigned images
- debug kernels
- alternative boot environments
- root shell

This state must be clearly distinguishable from a locked release configuration.

---

# Release State

A future release configuration may aim for:

```text
VERIFIED IMAGES ONLY

DEBUG RESTRICTED

ROLLBACK PROTECTED

TRUST STATE VISIBLE
```

---

# Recovery

A secure boot chain must still provide a recovery mechanism.

Recovery should not silently bypass all security properties.

See:

`RECOVERY.md`

---

# Boot Measurements

If measured boot is supported, research may evaluate recording cryptographic measurements of:

- bootloader
- kernel
- system image
- firmware configuration

---

# Limitation

Verified boot answers:

> Is this software authorized?

It does not answer:

> Is this software free from vulnerabilities?
