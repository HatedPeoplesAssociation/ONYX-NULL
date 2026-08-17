# ONYX-NULL Bills of Materials

This directory contains Bills of Materials for ONYX-NULL hardware.

Every reproducible hardware revision should have a corresponding BOM.

---

# Purpose

A BOM should allow another builder to identify and obtain the parts required to reproduce a specific ONYX-NULL hardware revision.

A BOM must describe what was actually used.

It should not merely describe theoretical compatible components.

---

# Naming Convention

Examples:

```text
ONX-P0-BOM.csv

ONX-P1-BOM.csv

ONX-M1-REV-A-BOM.csv

ONX-M1-REV-B-BOM.csv

ONX-R1-REV-A-BOM.csv
```

---

# Required Fields

BOM files should ideally contain:

```text
Reference
Quantity
Manufacturer
Manufacturer Part Number
Description
Value
Package
Supplier
Supplier Part Number
Unit Cost
Extended Cost
Lifecycle Status
Substitute
Datasheet
Firmware Required
Firmware Open
Driver Open
Notes
```

---

# CSV Header

```csv
Reference,Quantity,Manufacturer,Manufacturer Part Number,Description,Value,Package,Supplier,Supplier Part Number,Unit Cost,Extended Cost,Lifecycle Status,Substitute,Datasheet,Firmware Required,Firmware Open,Driver Open,Notes
```

---

# Example

```csv
Reference,Quantity,Manufacturer,Manufacturer Part Number,Description,Value,Package,Supplier,Supplier Part Number,Unit Cost,Extended Cost,Lifecycle Status,Substitute,Datasheet,Firmware Required,Firmware Open,Driver Open,Notes
U1,1,TBD,TBD,Compute Module,,TBD,TBD,TBD,0.00,0.00,TBD,TBD,TBD,TBD,TBD,TBD,Prototype placeholder
```

---

# Component Selection

Preferred components should have:

- public datasheets
- long-term availability
- Linux support
- documented electrical characteristics
- reputable manufacturers
- multiple distributors
- known lifecycle status
- accessible packaging
- reasonable minimum order quantities

Where practical, avoid components that are:

- obsolete
- end-of-life
- dependent on undocumented interfaces
- available only from questionable suppliers
- impossible for hobbyists to obtain
- dependent on unnecessary proprietary software

---

# Datasheets

Whenever redistribution permits, documentation should link to the original manufacturer datasheet.

Important electrical limits should also be documented in design notes.

---

# Lifecycle Tracking

Possible lifecycle values:

```text
ACTIVE
NRND
EOL
OBSOLETE
UNKNOWN
```

Where:

```text
NRND = Not Recommended for New Designs
EOL  = End of Life
```

Components approaching end-of-life should be reviewed for replacement.

---

# Proprietary Dependencies

If a component requires proprietary firmware, this must be indicated in the BOM and documented in:

`../../docs/PROPRIETARY_COMPONENTS.md`

---

# Substitutions

Compatible substitutes should be documented where possible.

A substitute must not automatically be considered equivalent if it changes:

- security properties
- firmware requirements
- power consumption
- radio characteristics
- driver requirements
- electrical characteristics
- physical dimensions
- availability

---

# Cost Tracking

Prototype BOMs should include approximate costs.

This allows tracking of:

```text
P0 prototype cost

P1 prototype cost

mainboard cost

assembly cost

enclosure cost

total prototype cost

estimated builder cost
```

---

# Price Disclaimer

Component pricing changes constantly.

BOM prices should record:

```text
Price:
Supplier:
Quantity:
Date Checked:
Currency:
```

---

# Manufacturing BOM

Custom PCB revisions may eventually require separate manufacturing-specific BOM information such as:

- assembly house part number
- manufacturer part number
- DNI/DNP status
- package
- placement side
- approved alternative

---

# Reproducibility

The BOM should describe exactly what was used for a tested hardware revision.

If a substitute was used during testing, document it explicitly.
