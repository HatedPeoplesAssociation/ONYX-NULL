# NULL/OS Privacy Policy

## Purpose

This is a technical privacy-design document.

It is not currently a commercial legal privacy policy.

---

# Default Principle

NULL/OS should minimize data generation before attempting to protect data after it has already been collected.

---

# Telemetry

The long-term default should aim for:

```text
NO UNDOCUMENTED TELEMETRY
```

If telemetry is ever introduced, it should be:

- documented
- minimal
- privacy-preserving
- optional where practical
- clearly controlled by the user

---

# Crash Reporting

Crash reports may contain sensitive information.

Any future crash-report system should document:

- contents
- destination
- identifiers
- retention
- user controls

---

# Identifiers

NULL/OS should minimize unnecessary persistent identifiers.

Research areas include:

- advertising identifiers
- network identifiers
- device identifiers
- installation identifiers
- analytics IDs

---

# Location

Location access should follow least privilege.

Applications should not receive location information unless required and authorized.

---

# Microphone

Applications should not receive microphone access by default.

Hardware isolation remains separate from software permissions.

---

# Camera

Applications should not receive camera access by default.

Physical camera isolation should remain independent of software policy where supported.

---

# Contacts

Applications should not automatically receive access to all contacts.

Future architecture should investigate scoped contact access where practical.

---

# Files

Applications should receive only necessary file access.

---

# Network Access

Network access itself may be treated as a permission or policy-controlled capability.

---

# Metadata

Even with encrypted communications, external infrastructure may observe metadata.

NULL/OS documentation should distinguish:

```text
CONTENT CONFIDENTIALITY

from

METADATA PRIVACY
```

---

# Accounts

NULL/OS should minimize mandatory cloud-account dependencies.

Core device operation should not depend on creating an account with ONYX-NULL.

---

# Philosophy

Privacy claims should state what information remains observable.

The objective is not:

> collect everything and promise not to misuse it.

The objective is:

> avoid collecting unnecessary information in the first place.
