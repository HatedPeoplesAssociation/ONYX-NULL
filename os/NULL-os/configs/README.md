# NULL/OS Configuration

This directory contains version-controlled configuration used to build and operate NULL/OS.

---

# Potential Contents

Examples include:

- kernel configuration
- firewall rules
- system-service configuration
- sandbox policy
- SELinux policy
- sysctl configuration
- networking defaults
- logging defaults

---

# Rule

Security-relevant configuration should live in version control rather than being applied manually after installation.

---

# Documentation

Important settings should explain:

```text
SETTING

DEFAULT

PURPOSE

SECURITY IMPACT

PRIVACY IMPACT
```

---

# Secrets

Never commit:

- passwords
- private keys
- API credentials
- SIP passwords
- VPN private keys
- signing keys

Configuration requiring secrets should use placeholders or documented provisioning procedures.
