# NULL/OS Profiles

This directory contains configuration profiles for different NULL/OS use cases and hardware states.

---

# Possible Profiles

Future profiles may include:

```text
development

testing

release

recovery
```

---

# Development

Development profiles may enable:

- debugging
- SSH
- verbose logging
- additional diagnostic tools
- development keys

---

# Testing

Testing profiles may enable:

- instrumentation
- hardware diagnostics
- security tests
- network monitoring

---

# Release

Release profiles should aim for:

- minimal services
- restricted debugging
- production security policy
- signed updates
- minimal logging

---

# Recovery

Recovery profiles should provide only the tools required to diagnose, restore, reinstall, or reset the device.

---

# Rule

A build should clearly identify which profile it uses.

Development builds must not be mistaken for production-secure configurations.
