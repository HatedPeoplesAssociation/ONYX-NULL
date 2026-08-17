# ONYX-NULL Power Controller Firmware

This directory is reserved for firmware associated with a future programmable power-management controller.

---

# Possible Responsibilities

The power controller may coordinate:

- charging
- battery monitoring
- thermal limits
- peripheral power domains
- sleep state
- wake state
- orderly shutdown
- hardware fault response

---

# Security Considerations

A power controller can potentially affect the availability of the entire device.

Its privileges should therefore be carefully limited and documented.

Potential risks include:

- forced shutdown
- disabling privacy hardware
- unexpected wake behavior
- unsafe battery behavior
- manipulating power-state reporting

---

# Safety Priority

Battery and thermal safety take priority over convenience.

The controller should respond safely to:

- over-temperature
- under-voltage
- over-voltage
- over-current
- charger faults
- battery faults

---

# Privacy Power Domains

If privacy-sensitive peripherals depend on the power controller, the architecture must determine whether firmware can override physical switches.

Where possible, physical switch authority should remain independent.

---

# Logging

Power-controller logging should avoid collecting unnecessary user information.

Useful logs may include:

- voltage
- temperature
- fault codes
- charge state

It should not require access to user communications.

---

# Current Status

No programmable ONYX-NULL power controller has been selected.
