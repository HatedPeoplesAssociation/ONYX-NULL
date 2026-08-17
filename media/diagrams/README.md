# ONYX-NULL Diagrams

This directory contains architecture diagrams, data-flow diagrams, trust-boundary diagrams, wiring diagrams, power diagrams, and other technical visualizations.

---

# Purpose

Diagrams should make complex ONYX-NULL systems easier to understand.

Potential topics include:

- system architecture
- boot chain
- trust boundaries
- network architecture
- VoIP architecture
- power domains
- radio isolation
- microphone isolation
- update flow
- storage encryption
- hardware layout

---

# Preferred Source

Where practical, diagrams should use text-based or editable source formats.

Possible formats include:

```text
Mermaid

SVG

Draw.io

Graphviz
```

---

# Source and Export

Recommended structure:

```text
diagrams/
├── source/
└── exports/
```

Example:

```text
source/ONX-network-v1.mmd

exports/ONX-network-v1.svg
```

---

# Naming Convention

Use:

```text
ONX-<SUBSYSTEM>-<DESCRIPTION>-v<NUMBER>
```

Examples:

```text
ONX-NET-architecture-v1.svg

ONX-POWER-domains-v2.svg

ONX-SEC-trust-boundaries-v1.svg

ONX-BOOT-chain-v1.svg
```

---

# Diagram Metadata

Technical diagrams should record:

```text
Title:

Revision:

Date:

Related Hardware:

Related Software:

Status:
```

---

# Status

Use:

```text
CONCEPT

DRAFT

CURRENT

SUPERSEDED
```

---

# Architecture Diagrams

Architecture diagrams should clearly distinguish:

- trusted components
- restricted-trust components
- untrusted components
- physical boundaries
- network boundaries

---

# Trust Boundaries

Example:

```text
┌─────────────────────────┐
│ TRUSTED COMPUTE         │
│                         │
│ CPU                     │
│ RAM                     │
│ Storage                 │
└────────────┬────────────┘
             │
      TRUST BOUNDARY
             │
┌────────────▼────────────┐
│ RESTRICTED RADIO        │
└─────────────────────────┘
```

---

# Signal Direction

Where relevant, arrows should indicate data or power flow.

Avoid ambiguous diagrams where direction matters.

---

# Legends

Complex diagrams should include a legend.

Example:

```text
Solid line:
Data

Dashed line:
Control

Double line:
Power
```

---

# Security Accuracy

Diagrams must not depict a security boundary that does not actually exist in hardware or software.

Conceptual designs should be labeled as conceptual.

---

# Current Status

Initial diagrams will document the P0 architecture and ONYX-NULL trust model.
