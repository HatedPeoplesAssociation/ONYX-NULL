# ONYX-NULL GitHub Configuration

This directory contains GitHub-specific project configuration for ONYX-NULL.

It is used for:

- issue templates
- pull request templates
- repository automation
- code ownership
- CI workflows
- contributor guidance

---

# Directory Structure

```text
.github/
├── README.md
├── CODEOWNERS
├── PULL_REQUEST_TEMPLATE.md
├── ISSUE_TEMPLATE/
│   ├── config.yml
│   ├── bug.yml
│   ├── feature.yml
│   ├── hardware.yml
│   └── research.yml
└── workflows/
    ├── docs.yml
    ├── security.yml
    └── build.yml
```

---

# Purpose

The `.github/` directory should make contribution workflows consistent.

It should help contributors understand:

- what information is required in an issue
- how to format pull requests
- which parts of the project require additional review
- which automated checks run before changes are accepted

---

# Philosophy

GitHub automation should support development without hiding important project behavior.

Prefer:

```text
CLEAR
   +
MINIMAL
   +
AUDITABLE
   +
USEFUL
```

Avoid overly complex automation until the project actually needs it.

---

# Current Status

ONYX-NULL is currently in the research / Pre-P0 stage.

Initial GitHub automation focuses on:

- structured issue reporting
- pull request consistency
- documentation checks
- basic repository security checks

More advanced CI should be added only when real firmware, software, hardware design files, or NULL/OS builds exist.
