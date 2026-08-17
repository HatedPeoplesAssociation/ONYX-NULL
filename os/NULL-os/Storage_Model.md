# NULL/OS Storage Model

## Purpose

This document defines the intended handling of persistent user and system data.

---

# Storage Goals

NULL/OS should eventually provide:

- encryption at rest
- secure credential handling
- protected cryptographic keys
- separation between system and user data
- safe deletion where practical
- corruption recovery
- minimal plaintext secrets

---

# Conceptual Layout

```text
PHYSICAL STORAGE
       │
       ├── Boot Metadata
       │
       ├── Verified System
       │
       └── Encrypted User Data
```

---

# Encryption

User data should be encrypted at rest.

Encryption keys should derive from appropriate combinations of:

- user authentication
- hardware-backed secrets
- randomly generated keys

depending on hardware capabilities.

---

# Authentication

Potential authentication mechanisms include:

- strong passphrase
- PIN with hardware-backed rate limiting
- security key
- biometric convenience layer

Biometrics should not automatically replace a strong cryptographic unlock secret.

---

# Secrets

High-value secrets may include:

```text
disk keys

VPN keys

SIP credentials

authentication tokens

password-manager data

update credentials
```

These should receive additional protection where practical.

---

# System Partition

A future immutable or verified system partition may reduce persistence opportunities for attackers.

---

# User Data

User data may include:

- settings
- application data
- call information
- contacts
- documents
- messages

Access should follow least privilege.

---

# Removable Storage

If removable storage is supported, the security implications should be explicitly documented.

Potential risks include:

- plaintext data
- malicious filesystem data
- removable-media attacks

---

# Device Loss

The storage design should assume the physical device may eventually be stolen.

Security should therefore not depend solely on possession.

---

# Wipe

Future research should define:

- factory reset
- cryptographic erase
- key destruction
- recovery behavior

---

# Backups

Backup design should preserve encryption and owner control.

Potential models include:

- encrypted local backup
- user-selected remote storage
- offline backup

Core backup functionality should not require an ONYX-NULL cloud account.

---

# Current Status

No final NULL/OS storage layout has been selected.
