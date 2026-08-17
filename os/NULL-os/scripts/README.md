# NULL/OS Scripts

This directory contains build, development, testing, and maintenance scripts used by NULL/OS.

---

# Possible Scripts

Future examples:

```text
setup-build-env

build

build-kernel

build-image

verify

flash

run-tests

generate-manifest
```

---

# Requirements

Scripts should:

- fail clearly
- avoid silent destructive actions
- document required dependencies
- use reproducible inputs where practical
- avoid embedding secrets
- provide useful error messages

---

# Destructive Actions

Scripts that:

- erase devices
- flash firmware
- overwrite storage
- delete build data

must clearly indicate what they will modify.

---

# Privileges

Avoid requiring root unless necessary.

If root is required, document why.

---

# Automation

Manual build commands should eventually be converted into scripts so another developer can reproduce the workflow.
