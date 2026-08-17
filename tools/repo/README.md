# ONYX-NULL Repository Tools

This directory contains helper tools used to maintain repository consistency and quality.

---

# Possible Responsibilities

Repository tooling may validate:

- directory structure
- file naming
- documentation links
- SPDX identifiers
- BOM formatting
- Markdown formatting
- required files
- revision naming
- release metadata

---

# Example Tools

Potential commands:

```bash
onx-repo-check
```

```bash
onx-doc-check
```

```bash
onx-license-check
```

```bash
onx-bom-check
```

---

# Repository Validation

A repository validation tool may eventually check for required files such as:

```text
README.md

SECURITY.md

CONTRIBUTING.md

ROADMAP.md

LICENSES/
```

---

# Link Checking

Documentation should eventually be checked for:

- broken internal links
- missing referenced files
- invalid relative paths

---

# License Checking

Repository tooling may detect:

- missing license identifiers
- incompatible licenses
- undocumented third-party source

---

# Hardware Naming

Tools may validate naming conventions such as:

```text
ONX-M1-REV-A
```

and reject inconsistent revision naming.

---

# CI Integration

Repository tools should eventually run automatically in CI.

---

# Current Status

No ONYX-NULL repository-validation tool currently exists.
