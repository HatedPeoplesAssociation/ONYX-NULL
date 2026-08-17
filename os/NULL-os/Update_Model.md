# NULL/OS Update Model

## Purpose

NULL/OS updates must preserve system integrity while allowing security vulnerabilities to be corrected reliably.

---

# Goals

The update system should eventually provide:

- authenticated updates
- integrity verification
- atomic installation
- rollback or recovery
- rollback protection against vulnerable releases where appropriate
- transparent version information
- reproducible release artifacts

---

# Conceptual Architecture

```text
SOURCE
  │
  ▼
BUILD
  │
  ▼
SYSTEM IMAGE
  │
  ▼
SIGN
  │
  ▼
UPDATE SERVER
  │
  ▼
DEVICE
  │
  ▼
VERIFY
  │
  ▼
INSTALL
```

---

# Update Trust

The system should verify authorization before installing an update.

A valid signature proves that an accepted signing key authorized the image.

It does not prove the image contains no vulnerabilities.

---

# Atomic Updates

A partial update should not leave the operating system in an inconsistent state.

Potential strategies include:

```text
A/B SYSTEM PARTITIONS

IMMUTABLE SYSTEM IMAGES

SNAPSHOT / ROLLBACK
```

---

# A/B Example

```text
ACTIVE SYSTEM A
       │
       ▼
INSTALL UPDATE TO B
       │
       ▼
VERIFY B
       │
       ▼
BOOT B
       │
    SUCCESS?
     │     │
    YES    NO
     │     │
     ▼     ▼
 USE B   RETURN A
```

---

# Rollback Protection

Security-sensitive releases may need protection against installation of older vulnerable versions.

Recovery requirements must remain possible.

---

# Signing Keys

Update signing should eventually define:

- root signing key
- release key
- key rotation
- revocation
- backups
- compromise procedure

Private keys must never be stored in the public repository.

---

# Update Metadata

Each release should record:

```text
Version:

Commit:

Build Environment:

Build Hash:

Release Hash:

Signing Key:

Supported Hardware:

Security Changes:

Known Issues:
```

---

# Failure Testing

Test scenarios should include:

- valid update
- corrupted image
- invalid signature
- interrupted download
- power loss
- insufficient storage
- wrong hardware revision
- failed boot
- rollback attempt

---

# Network Privacy

Update checks should minimize unnecessary identifying information.

Update infrastructure should not require a personal user account.

---

# Current Status

No final NULL/OS update system has been selected.
