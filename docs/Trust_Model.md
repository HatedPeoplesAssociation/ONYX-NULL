# ONYX-NULL Trust Model

## Principle

Trust should be minimized, documented, and isolated.

A component should not receive more authority than necessary.

## Trust Categories

### Trusted

Components that currently require significant trust.

Examples may include:

* main CPU
* memory controller
* kernel
* boot verification mechanism
* storage encryption implementation

### Restricted Trust

Components that are necessary but should be isolated.

Examples may include:

* Wi-Fi firmware
* Bluetooth firmware
* cellular modem firmware
* GPU firmware
* USB peripherals

### Untrusted

Components that should be treated as potentially hostile.

Examples may include:

* external networks
* public Wi-Fi
* remote servers
* downloaded files
* third-party applications
* external USB devices

## Design Requirement

For each hardware and software component, ONYX-NULL should document:

```text
Component:
Function:
Open source:
Firmware:
Privileges:
DMA access:
Network access:
Secrets accessible:
Isolation:
Physical power control:
Failure impact:
Replacement options:
```

## Trust Reduction

Preferred strategies include:

* hardware isolation
* IOMMU protection
* sandboxing
* least privilege
* physical power removal
* process isolation
* explicit permissions
* cryptographic verification
* compartmentalization

## Rule

The project should continuously ask:

> What happens if this component is completely malicious?

The architecture should attempt to contain the answer.
