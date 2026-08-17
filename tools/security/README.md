# ONYX-NULL Security Development Tools

This directory contains developer-facing tooling for validating ONYX-NULL security properties.

These tools are intended for testing systems owned or explicitly authorized by the tester.

---

# Purpose

Potential tooling may validate:

- boot integrity
- firmware versions
- signatures
- firewall state
- network exposure
- hardware isolation
- system configuration
- update packages
- file integrity

---

# Security Testing Philosophy

Security tests should attempt to verify concrete claims.

Example:

```text
Claim:
Wi-Fi is physically disconnected.

Test:
Measure radio power rail and verify no device enumeration.

Result:
PASS / FAIL
```

---

# Potential Tools

Examples:

```bash
onx-verify-boot
```

```bash
onx-check-firmware
```

```bash
onx-network-audit
```

```bash
onx-verify-update
```

---

# Scope

Security tools should clearly identify their scope.

A passing test does not prove the entire system secure.

---

# Non-Destructive Default

Security validation tools should prefer read-only behavior unless modification is explicitly necessary.

---

# Authorized Testing

Tools intended for active testing should only be used against systems and networks the operator owns or is authorized to test.

---

# Results

Results should record:

```text
Test:

Target:

Hardware Revision:

Software Version:

Expected:

Observed:

Result:

Notes:
```

---

# Current Status

No custom ONYX-NULL security-validation tool currently exists.
