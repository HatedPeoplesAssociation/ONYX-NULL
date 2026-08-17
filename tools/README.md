# ONYX-NULL Tools

This directory contains developer-facing tools, helper scripts, build utilities, flashing helpers, diagnostics, repository automation, and other tooling used during ONYX-NULL research and development.

Tools in this directory are not necessarily intended for end users.

---

# Purpose

The tools directory may eventually include utilities for:

- setting up development environments
- building firmware
- building NULL/OS
- generating manifests
- generating checksums
- flashing prototypes
- collecting hardware information
- validating repository structure
- running tests
- generating documentation
- checking dependencies
- verifying releases
- inspecting firmware
- manufacturing preparation

---

# Directory Structure

A future structure may look like:

```text
tools/
├── README.md
├── TOOL_POLICY.md
├── ENVIRONMENT.md
├── build/
├── flash/
├── hardware/
├── security/
├── manufacturing/
├── release/
└── repo/
```

---

# Tooling Philosophy

ONYX-NULL tooling should be:

```text
DOCUMENTED
   +
REPRODUCIBLE
   +
SAFE
   +
SCRIPTABLE
   +
TRANSPARENT
```

A tool should make development easier without hiding important behavior.

---

# Safety

Some development tools may perform destructive actions.

Examples include:

- erasing storage
- flashing firmware
- writing bootloaders
- modifying partitions
- resetting cryptographic state
- generating manufacturing files
- deleting build artifacts

Destructive tools must clearly indicate what they will modify.

---

# Dangerous Operations

A destructive command should not silently execute based on ambiguous arguments.

Preferred behavior:

```text
Target:
ONX-P0

Operation:
ERASE AND FLASH

Device:
/dev/...

This operation will destroy existing data.
```

Tools should require explicit arguments for destructive actions.

---

# Privileges

Avoid requiring root unless necessary.

If root privileges are required, document:

```text
Why:

What is accessed:

What is modified:

Security impact:
```

---

# Secrets

Never store secrets directly in tooling source.

Do not commit:

- private signing keys
- API tokens
- passwords
- SIP credentials
- VPN private keys
- production certificates

Use environment variables, protected files, hardware tokens, or other appropriate secret-management mechanisms.

---

# Dependencies

Each tool should document its dependencies.

Example:

```text
Python:
3.x

Required Packages:

External Tools:

Supported Operating Systems:
```

---

# Version Pinning

Tool versions should be pinned where reproducibility depends on exact behavior.

Examples include:

- compiler toolchains
- firmware SDKs
- PCB-generation tools
- image-building tools

---

# CLI Design

Command-line tools should:

- provide `--help`
- fail clearly
- use meaningful exit codes
- support automation
- avoid unnecessary interactive prompts
- produce machine-readable output where useful

---

# Example

```bash
onx-tool --help
```

Potential conventions:

```text
0 = Success

1 = General Failure

2 = Invalid Arguments

3 = Hardware Not Found

4 = Verification Failed
```

---

# Machine-Readable Output

Where useful, tools may support:

```bash
--json
```

Example:

```json
{
  "hardware": "ONX-P0",
  "result": "pass",
  "firmware_version": "0.1.0"
}
```

---

# Logging

Tool output should avoid exposing:

- credentials
- cryptographic keys
- personal data
- unnecessary device identifiers

Debug output should still follow this rule.

---

# Dry-Run Support

Tools that modify hardware or files should support dry-run behavior where practical.

Example:

```bash
onx-flash --target ONX-P0 --dry-run
```

This allows users to inspect intended operations before execution.

---

# Testing

Developer tools should eventually include:

- unit tests
- invalid input tests
- failure-path tests
- permission tests
- compatibility tests

---

# Licensing

All ONYX-NULL-developed tools should use clearly documented open-source licenses.

Source files should use appropriate SPDX identifiers where practical.

---

# Current Status

**Stage:** Research / Pre-P0

Most early ONYX-NULL tooling will begin as small development scripts and grow only when repeated workflows justify automation.
