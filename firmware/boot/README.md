# ONYX-NULL Boot Firmware

This directory is reserved for boot firmware, bootloader configuration, boot-chain documentation, and related security work.

---

# Purpose

The boot process establishes the initial trusted state of the device.

Potential components include:

- SoC ROM
- first-stage bootloader
- second-stage bootloader
- firmware initialization
- verified boot
- kernel loading
- recovery environment

---

# Conceptual Boot Chain

```text
POWER ON
   │
   ▼
ROM
   │
   ▼
FIRST-STAGE BOOTLOADER
   │
   ▼
SECOND-STAGE BOOTLOADER
   │
   ▼
VERIFY OS
   │
   ▼
KERNEL
   │
   ▼
NULL/OS
```

---

# Security Goals

The boot architecture should eventually aim for:

- authenticated boot
- integrity verification
- rollback protection
- recovery
- owner-controlled keys where practical
- visible development/release state
- documented trust anchors

---

# Trust Anchor

The architecture should document the root of trust.

Possible trust roots include:

- SoC ROM key
- secure element
- TPM
- owner-enrolled key
- manufacturer key

---

# Owner Control

ONYX-NULL should research whether the owner can:

- enroll custom boot keys
- replace boot keys
- recover from key loss
- verify installed keys
- unlock development mode
- relock after modification

---

# Verified Boot

Verified boot should answer:

> Is the software being loaded authorized by the configured trust policy?

It does not prove that authorized software contains no vulnerabilities.

---

# Development Mode

Development mode may allow:

- unsigned boot images
- alternative kernels
- recovery tools
- debug access

Release mode should clearly indicate when these protections are relaxed.

---

# Rollback

Where possible, the boot process should prevent installation of known-vulnerable older firmware or operating-system components.

Recovery requirements must be considered.

---

# Current Status

No final ONYX-NULL boot architecture has been selected.
