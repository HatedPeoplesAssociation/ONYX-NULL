# NULL/OS Network Policy

## Purpose

This document defines the intended networking behavior of NULL/OS.

---

# Principle

The operating system should not communicate externally without a documented reason.

---

# Default Network Model

Conceptually:

```text
APPLICATION
     │
     ▼
PERMISSION / POLICY
     │
     ▼
FIREWALL
     │
     ▼
VPN POLICY
     │
     ▼
NETWORK INTERFACE
     │
     ▼
INTERNET
```

---

# Default Connections

Every default external connection should eventually be documented.

Examples include:

- update servers
- time servers
- DNS servers
- connectivity checks
- communication providers

---

# Application Network Control

NULL/OS should investigate per-application network controls.

Possible states:

```text
NO NETWORK

LOCAL NETWORK ONLY

INTERNET

VPN ONLY
```

---

# Firewall

The base system should use a firewall appropriate to the selected platform.

Policy should favor:

```text
DENY UNNECESSARY
ALLOW REQUIRED
```

---

# VPN

NULL/OS should support modern VPN protocols.

WireGuard is a candidate technology.

Potential future behavior:

```text
ALWAYS-ON VPN

BLOCK CONNECTIONS IF VPN FAILS
```

where appropriate.

---

# DNS

DNS behavior must be documented.

Research should evaluate:

- DNS leakage
- encrypted DNS
- VPN-provided DNS
- local resolver behavior

---

# Wi-Fi

Wi-Fi configuration should consider:

- MAC randomization
- saved-network behavior
- automatic connection behavior
- probe behavior
- captive portals
- untrusted networks

---

# Incoming Connections

NULL/OS should avoid unnecessary listening services.

Every listening port should have a documented purpose.

---

# SSH

SSH may be enabled for development.

Production builds should not necessarily expose SSH by default.

---

# Connectivity Checks

Automatic connectivity tests should be documented.

They should not silently introduce unnecessary third-party dependencies.

---

# Testing

Network tests should eventually include:

```text
boot with network

boot without network

VPN connected

VPN failure

DNS leakage

unexpected outbound connections

listening ports

application firewall

Wi-Fi reconnect behavior
```

---

# Documentation Goal

A user should eventually be able to answer:

> What servers does a default ONYX-NULL device contact when I turn it on?

with a complete documented list.
