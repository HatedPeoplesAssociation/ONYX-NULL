# ONYX-NULL Manufacturing Tools

This directory contains helper tooling used to prepare ONYX-NULL hardware for fabrication and assembly.

---

# Purpose

Potential tooling may generate or validate:

- Gerbers
- drill files
- BOMs
- pick-and-place files
- assembly drawings
- manufacturing packages
- component reports
- board revision metadata

---

# Principle

Manufacturing artifacts should be generated from authoritative source files.

Do not manually modify generated Gerbers or placement files unless the change is explicitly documented.

---

# Manufacturing Package

A future tool may produce:

```text
ONX-M1-REV-A-manufacturing.zip
```

containing:

```text
Gerbers

Drill Files

BOM

Pick-and-Place

Assembly Drawing

Fabrication Notes

README
```

---

# Validation

Manufacturing preparation should verify:

- hardware revision
- BOM revision
- PCB revision
- component availability
- correct filenames
- required layers
- board dimensions

---

# Hashes

Released manufacturing packages should include checksums.

Example:

```text
SHA-256:
```

---

# Automation

Generation should eventually be scriptable to reduce accidental differences between releases.

---

# Current Status

Manufacturing automation will be developed when ONX-M1 PCB work begins.
