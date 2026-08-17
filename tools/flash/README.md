# ONYX-NULL Flashing Tools

This directory contains tooling used to write firmware, operating-system images, bootloaders, or other persistent data to ONYX-NULL development hardware.

---

# Warning

Flashing tools may destroy data or render hardware temporarily unbootable.

Use only with a clearly identified target.

---

# Purpose

Potential flashing operations include:

- firmware flashing
- operating-system image flashing
- recovery installation
- bootloader installation
- test-image installation

---

# Safety Requirements

Flashing tools should require an explicit target.

Preferred:

```bash
onx-flash --target /dev/sdX --image image.img
```

Avoid:

```bash
onx-flash image.img
```

when the tool guesses the target automatically.

---

# Target Verification

Before writing, tools should display:

```text
Target:

Device Model:

Capacity:

Serial:

Image:

Image Hash:
```

where available.

---

# Confirmation

Destructive operations should require clear confirmation unless an automation flag is intentionally supplied.

Example:

```text
WARNING

This operation will overwrite:

/dev/...

Type the device name to continue:
```

---

# Dry Run

Where possible:

```bash
onx-flash --dry-run
```

should display the intended operation without modifying hardware.

---

# Image Verification

Before flashing, verify:

- image exists
- size is plausible
- hash matches expected value
- signature where available
- hardware revision compatibility

---

# Post-Flash Verification

After flashing:

- verify written data
- verify expected partitions
- verify boot state if possible

---

# Recovery

Each supported target should document a recovery procedure if flashing fails.

---

# Supported Interfaces

Potential interfaces include:

- USB mass storage
- DFU
- fastboot
- USB boot ROM
- SWD
- JTAG
- vendor bootloader

---

# Logging

Flashing logs should not expose secrets.

Useful fields include:

```text
Hardware Revision

Image Version

Image Hash

Result
```

---

# Current Status

No ONYX-NULL-specific flashing utility currently exists.
