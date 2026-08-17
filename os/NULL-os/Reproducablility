# NULL/OS Reproducibility

## Purpose

The long-term objective is to allow independent builders to verify that distributed NULL/OS artifacts correspond to public source.

---

# Reproducible Build Goal

```text
SOURCE REVISION X
       │
       ├──────────────┐
       ▼              ▼
 BUILDER A         BUILDER B
       │              │
       ▼              ▼
 ARTIFACT A        ARTIFACT B
       │              │
       └──────┬───────┘
              ▼
           SAME HASH
```

---

# Why Reproducibility Matters

A public source repository alone does not prove that a distributed binary was produced from that source.

Independent reproduction helps verify that relationship.

---

# Sources of Nondeterminism

Potential problems include:

- timestamps
- random identifiers
- filesystem ordering
- compiler differences
- host paths
- locale
- dependency versions
- archive metadata

These should be documented and removed where practical.

---

# Build Manifest

Each release should eventually publish:

```text
Source Commit:

Toolchain:

Dependencies:

Build Container:

Build Command:

Artifact:

SHA-256:

Signature:
```

---

# Independent Verification

Release testing should eventually involve more than one independent environment.

Record:

```text
Builder:

Environment:

Artifact Hash:

Expected Hash:

Result:
```

---

# Signed Releases

Reproducibility and signing solve different problems.

```text
REPRODUCIBILITY
      =
Does binary match source?

SIGNATURE
      =
Was binary authorized by key holder?
```

Both may be valuable.

---

# Current Status

NULL/OS reproducible builds do not yet exist.

Reproducibility is a design objective.
