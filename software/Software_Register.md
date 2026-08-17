# ONYX-NULL Software Register

This document tracks software components researched, developed, adopted, rejected, or used by ONYX-NULL.

---

# Purpose

The software register records:

- applications
- libraries
- services
- tools
- daemons
- third-party dependencies

that may become part of ONYX-NULL.

---

# Status Values

```text
RESEARCHING

CANDIDATE

APPROVED

IN-USE

REJECTED

REPLACED

DEPRECATED
```

---

# Trust Classification

Software may use:

```text
CORE TRUST

PRIVILEGED

SANDBOXED

UNTRUSTED

UNKNOWN
```

---

# Entry Template

```text
## Software Name

Status:

Category:

Upstream Project:

Version:

Purpose:

License:

Source Available:

---

### Security

Trust Classification:

Runs As:

Privileges:

Filesystem Access:

Network Access:

Microphone Access:

Camera Access:

Location Access:

Hardware Access:

Secrets Accessible:

Sandbox:

---

### Dependencies

Direct Dependencies:

Important Transitive Dependencies:

Binary Dependencies:

Proprietary Dependencies:

---

### Maintenance

Upstream Active:

Security Advisories:

Update Method:

Maintainer:

---

### Decision

Advantages:

Disadvantages:

Alternatives:

Reason Accepted or Rejected:

Notes:
```

---

# Categories

Suggested categories:

```text
COMMUNICATIONS

SECURITY

UTILITY

SYSTEM SERVICE

LIBRARY

DEVELOPMENT TOOL
```

---

# Decision Principle

Software should not be selected simply because it works.

Selection should consider:

```text
SECURITY
   +
MAINTENANCE
   +
LICENSE
   +
DEPENDENCIES
   +
PRIVILEGES
   +
PRIVACY
   +
AUDITABILITY
```

---

# Current Status

No final ONYX-NULL software stack has been selected.
