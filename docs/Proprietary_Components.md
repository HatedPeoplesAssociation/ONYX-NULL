# ONYX-NULL Proprietary Components

## Principle

ONYX-NULL will not hide proprietary dependencies.

If closed-source hardware, firmware, drivers, or services are required, they will be documented.

## Component Template

Use this format for every relevant component:

```text
Component:
Manufacturer:
Model:
Function:

Hardware open:
Firmware open:
Driver open:
Datasheet available:

Firmware update mechanism:
Firmware signature verification:

DMA access:
Network access:
Memory access:
Secrets accessible:

Isolation mechanism:
Physical power control:

Known vulnerabilities:
Replacement available:

Notes:
```

## Current Components

No final hardware components have been selected.

## Objective

The long-term objective is to:

1. identify proprietary dependencies
2. understand what authority they have
3. isolate them
4. minimize them
5. replace them when practical
