# ONYX-NULL Network Tests

This directory contains tests for ONYX-NULL networking, firewall behavior, VPN operation, DNS, Wi-Fi, SIP, VoIP, and external network exposure.

---

# Network Test Areas

Testing may include:

- default outbound connections
- listening ports
- DNS
- firewall
- VPN
- VPN failure
- Wi-Fi
- SIP
- SRTP
- TLS
- NAT traversal
- metadata exposure

---

# Suggested Structure

```text
network/
├── README.md
├── NET-001-default-connections/
├── NET-002-listening-ports/
├── NET-003-dns/
├── NET-004-vpn-kill-switch/
├── NET-005-sip-tls/
└── NET-006-srtp/
```

---

# NET-001 — Default Connections

Goal:

Identify all outbound network connections made by a fresh ONYX-NULL system.

Capture:

- destination
- protocol
- port
- DNS request
- process
- reason

---

# NET-002 — Listening Ports

Goal:

Identify all services listening for incoming connections.

Example commands may include:

```bash
ss -tulpn
```

Document why each listener exists.

Unexpected listeners should be investigated.

---

# NET-003 — DNS

Goal:

Determine where DNS queries are sent.

Test states:

```text
No VPN

VPN Active

VPN Failure

Custom DNS
```

---

# NET-004 — VPN Kill Switch

Goal:

Verify network traffic is blocked if a required always-on VPN fails.

Conceptual result:

```text
VPN ACTIVE
   │
   ▼
TRAFFIC ALLOWED


VPN DOWN
   │
   ▼
TRAFFIC BLOCKED
```

---

# NET-005 — SIP Signaling

Goal:

Verify whether SIP signaling is encrypted as configured.

Inspect:

- transport
- destination
- certificate validation
- metadata

---

# NET-006 — SRTP

Goal:

Verify that voice media uses SRTP when expected.

Do not assume encrypted signaling automatically means encrypted media.

---

# NET-007 — Wi-Fi MAC Behavior

Goal:

Document MAC-address behavior.

Test:

- first connection
- reconnection
- different networks
- reboot

---

# NET-008 — Captive Portal

Goal:

Determine system behavior on captive-portal networks.

Document any automatic connectivity-check domains.

---

# NET-009 — Network Loss During Call

Goal:

Observe VoIP behavior when connectivity is interrupted.

Record:

- timeout
- reconnection
- call termination
- error reporting

---

# NET-010 — VPN Change During Call

Goal:

Determine what happens when VPN state changes during active communication.

---

# NET-011 — IPv6

Goal:

Verify that privacy and firewall rules apply consistently to IPv4 and IPv6.

---

# NET-012 — Metadata Observation

Goal:

Document what different network observers can see.

Possible observation points:

```text
Local Access Point

Router

ISP

VPN Provider

VoIP Provider

Remote Endpoint
```

---

# Packet Captures

Packet captures may contain sensitive data.

Before publishing a capture:

- remove credentials
- remove personal IP addresses where appropriate
- remove unrelated traffic
- verify no communication content is exposed

---

# Testing Tools

Potential tools include:

```text
Wireshark

tcpdump

ss

ip

nftables

dig

traceroute

openssl

sngrep
```

Tool choice may evolve.

---

# Current Status

No final ONYX-NULL network test suite has been completed.
