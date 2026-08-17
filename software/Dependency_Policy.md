# ONYX-NULL Dependency Policy

## Purpose

Third-party dependencies are part of the ONYX-NULL software supply chain.

This document defines how dependencies should be evaluated and maintained.

---

# Principle

Every dependency introduces:

- code
- vulnerabilities
- maintainers
- update requirements
- licensing
- supply-chain trust

Dependencies should therefore be intentional.

---

# Prefer

Where practical, prefer dependencies that are:

- actively maintained
- open source
- widely reviewed
- appropriately licensed
- minimal
- well documented
- security conscious

---

# Avoid

Avoid dependencies that are:

- abandoned
- unnecessary
- binary-only
- difficult to audit
- dependent on questionable download infrastructure
- extremely large for trivial functionality

---

# Dependency Evaluation

Before adopting a significant dependency, document:

```text
Name:

Version:

Purpose:

License:

Upstream:

Maintainer Activity:

Security Advisories:

Direct Dependencies:

Network Behavior:

Privileges:

Alternatives:

Decision:
```

---

# Pinning

Build systems should pin dependency versions where appropriate.

Mutable dependency versions can break reproducibility.

---

# Lock Files

Language ecosystems supporting lock files should generally commit them when doing so improves reproducibility.

Examples may include:

```text
Cargo.lock

go.sum

package-lock.json
```

depending on project type.

---

# Vendoring

Vendoring may be appropriate when:

- long-term reproducibility requires it
- upstream availability is uncertain
- dependencies are small

But vendored code still requires security maintenance.

---

# Security Updates

Dependency updates should be evaluated for:

- security fixes
- behavior changes
- API changes
- new dependencies
- privacy changes

---

# Transitive Dependencies

Indirect dependencies are still part of the attack surface.

They should not be ignored.

---

# Proprietary Dependencies

Core ONYX-NULL software should minimize proprietary runtime dependencies.

Any unavoidable proprietary component must be documented.

---

# Automated Scanning

Future CI may include:

- vulnerability scanning
- license scanning
- dependency update alerts
- software bill of materials generation

---

# Software Bill of Materials

Future releases should investigate publishing an SBOM describing included software components and versions.

---

# Current Status

Dependency policies will evolve alongside the first ONYX-NULL software components.
