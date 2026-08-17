# ONYX-NULL API Policy

## Purpose

This document defines general principles for software interfaces used within ONYX-NULL.

---

# Principle

Interfaces between security boundaries should remain:

- small
- explicit
- documented
- versioned
- validated

---

# Privileged APIs

APIs exposed by privileged services should provide only necessary operations.

Avoid interfaces equivalent to:

```text
execute arbitrary command

read arbitrary file

write arbitrary file

access arbitrary device
```

unless absolutely required.

---

# Input Validation

All externally controlled input should be treated as untrusted.

This includes input from:

- applications
- network services
- USB
- firmware
- hardware controllers
- configuration files

---

# Authentication

Sensitive APIs may require:

- process identity
- permission checks
- cryptographic authentication
- local credentials

depending on architecture.

---

# Authorization

Authentication answers:

> Who is calling?

Authorization answers:

> What are they allowed to do?

Both should be considered.

---

# Versioning

Stable APIs should use explicit versioning where practical.

Example:

```text
api/v1/
```

---

# Error Handling

Errors should:

- fail safely
- avoid exposing secrets
- provide useful diagnostics
- avoid undefined behavior

---

# Network APIs

Network-facing APIs should be minimized.

Local-only services should not accidentally bind to all interfaces.

---

# Serialization

Structured formats may include:

- JSON
- CBOR
- Protocol Buffers

Selection should consider:

- complexity
- parser safety
- compatibility
- attack surface

---

# Secrets

APIs should not return cryptographic secrets unless absolutely necessary.

Where possible, APIs should perform operations using protected keys rather than exposing the key itself.

---

# Logging

API logs should not record:

- passwords
- tokens
- private keys
- sensitive communication contents

---

# Documentation

Every privileged API should document:

```text
Endpoint / Method:

Caller:

Privileges Required:

Input:

Output:

Failure Modes:

Security Impact:

Privacy Impact:
```

---

# Current Status

No stable ONYX-NULL internal API currently exists.
