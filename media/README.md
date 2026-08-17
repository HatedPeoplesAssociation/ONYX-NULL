# ONYX-NULL Media

This directory contains visual assets used for ONYX-NULL documentation, branding, development records, diagrams, and public project presentation.

Media should support technical understanding first and branding second.

---

# Directory Structure

```text
media/
├── README.md
├── MEDIA_POLICY.md
├── ATTRIBUTION.md
├── logo/
├── diagrams/
└── photos/
```

---

# Purpose

The media directory may contain:

- project logos
- wordmarks
- icons
- architecture diagrams
- wiring diagrams
- prototype photographs
- PCB photographs
- enclosure renders
- assembly photographs
- testing photographs
- documentation graphics
- release images

---

# Source Files

Editable source files should be preserved whenever possible.

Examples:

```text
SVG
KiCad source
FreeCAD source
Blender source
Draw.io source
Mermaid source
```

Generated PNG or JPEG files should not replace the editable original.

---

# GitHub Usage

Media stored in this repository can be referenced from Markdown using relative paths.

Example:

```markdown
![ONYX-NULL Prototype](../media/photos/ONX-P0-front.jpg)
```

GitHub supports relative image paths in repository Markdown files. :contentReference[oaicite:0]{index=0}

---

# File Naming

Use descriptive filenames.

Preferred:

```text
ONX-P0-bench-front.jpg

ONX-M1-REV-A-top.png

ONX-ARCH-network-v1.svg

ONYX-NULL-logo-primary.svg
```

Avoid:

```text
IMG_2384.jpg

image.png

diagram-final-final2.png
```

---

# Revision Naming

Technical diagrams should use explicit revision numbers when architecture changes.

Example:

```text
ONX-ARCH-P0-v1.svg

ONX-ARCH-P0-v2.svg

ONX-POWER-P1-v1.svg
```

---

# Metadata

Media containing sensitive metadata should be reviewed before publication.

Potential metadata includes:

- GPS coordinates
- device model
- timestamps
- usernames
- filesystem paths
- author names
- software versions

Photographs should be checked before public release.

---

# Sensitive Information

Before publishing images, verify that they do not unintentionally expose:

- credentials
- API tokens
- Wi-Fi passwords
- SIP credentials
- IP addresses
- private keys
- QR codes containing secrets
- serial numbers where privacy matters
- personal documents
- location information
- computer notifications
- unrelated people

---

# Documentation Standard

Technical images should include enough context to remain understandable.

Where relevant, include:

- revision
- date
- component names
- signal direction
- voltage
- interface
- test state

---

# Accessibility

Images used in Markdown should include meaningful alt text.

Preferred:

```markdown
![ONX-P0 bench prototype showing compute board, display, and USB audio interface](../media/photos/ONX-P0-bench.jpg)
```

Avoid:

```markdown
![](image.jpg)
```

---

# Branding

Branding media should remain visually separate from engineering evidence.

A polished render should never be presented as though it were a photograph of working hardware.

Clearly label:

```text
CONCEPT

RENDER

PROTOTYPE

PRODUCTION
```

---

# Image Modification

Technical photographs should not be edited in ways that misrepresent hardware or test results.

Acceptable edits include:

- cropping
- exposure correction
- redaction
- labels
- arrows
- measurement annotations

Any edit affecting technical interpretation should be disclosed.

---

# Current Status

ONYX-NULL is currently in the research / Pre-P0 stage.

Media will initially focus on:

- branding
- architecture diagrams
- research diagrams
- development photographs
