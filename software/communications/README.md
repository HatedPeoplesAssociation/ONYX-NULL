# ONYX-NULL Communications Software

This directory contains software related to voice calling, messaging, SIP, VoIP, contacts, and other communications functionality.

---

# Purpose

The communications subsystem may eventually provide:

- outgoing VoIP calls
- incoming encrypted calls
- PSTN integration
- SIP account management
- contact management
- call history
- audio routing
- secure messaging integration
- call-state handling
- programmable incoming-call behavior

---

# Communications Architecture

Conceptually:

```text
               ONYX-NULL

                   │
                   ▼
          COMMUNICATIONS APP
                   │
          ┌────────┴────────┐
          │                 │
          ▼                 ▼
       Signal           SIP / VoIP
                            │
                            ▼
                       VoIP Provider
                            │
                            ▼
                           PSTN
```

---

# SIP

SIP may be used for conventional VoIP interoperability.

Research areas include:

- SIP registration
- SIP authentication
- SIP over TLS
- NAT traversal
- call routing
- caller ID
- provider compatibility

---

# RTP / SRTP

Audio transport may use:

```text
RTP
```

or:

```text
SRTP
```

where supported.

Encrypted media should be preferred when communicating with infrastructure that supports it.

---

# PSTN Limitation

A SIP connection may be encrypted between ONYX-NULL and the VoIP provider.

Once a call enters the traditional PSTN, end-to-end encryption is generally no longer under ONYX-NULL control.

This distinction should always be documented.

---

# Incoming Call Model

ONYX-NULL may support a public-number architecture where incoming calls do not necessarily ring the handset.

Conceptually:

```text
PUBLIC NUMBER
      │
      ▼
VoIP Infrastructure
      │
      ▼
Incoming Call Logic
      │
      ├── Play Recorded Greeting
      │
      └── Disconnect
```

This behavior can be handled by server-side call logic rather than by the handset.

---

# No-Recording Greeting

A future implementation may intentionally avoid traditional voicemail.

Conceptual behavior:

```text
CALL ARRIVES
     │
     ▼
ANSWER
     │
     ▼
PLAY GREETING
     │
     ▼
DISCONNECT
     X

NO MESSAGE RECORDING
```

This should be implemented as call-routing behavior rather than relying on a normal voicemail recorder.

---

# Outgoing Calls

Outgoing architecture may look like:

```text
ONYX-NULL
     │
     ▼
VPN
     │
     ▼
SIP / TLS
     │
     ▼
VoIP Provider
     │
     ▼
PSTN
```

---

# Encrypted Communications

For trusted contacts, end-to-end encrypted communications should be preferred over PSTN where possible.

The communications subsystem may integrate or interoperate with established encrypted communication applications rather than creating new cryptography.

---

# Do Not Invent Cryptography

ONYX-NULL should not design a custom encryption protocol merely for branding.

Use established, reviewed cryptographic protocols and libraries.

---

# Contact Management

Contact access should follow least privilege.

Potential future architecture may distinguish:

```text
SYSTEM CONTACTS

APPLICATION-SPECIFIC CONTACTS

TEMPORARY CONTACTS
```

Applications should not automatically receive the complete address book.

---

# Call History

Call logs may contain sensitive metadata.

Potential entries include:

```text
Number / Identifier

Time

Duration

Direction

Account

Provider
```

Retention should be configurable.

---

# Credentials

SIP credentials should not be stored in plaintext configuration files where avoidable.

Credentials should use secure system credential storage where available.

Never commit real SIP credentials to Git.

---

# Audio Permissions

Communications applications require microphone access while making calls.

Access should be:

- explicit
- visible
- restricted to necessary periods

A physical microphone kill switch remains independent from application permissions.

---

# Hardware State

The communications application should gracefully handle states such as:

```text
MICROPHONE PHYSICALLY DISCONNECTED

WI-FI PHYSICALLY DISCONNECTED

NO NETWORK

VPN FAILURE
```

The software should not attempt to conceal these states.

---

# Failure Behavior

Important failure cases include:

- SIP registration failure
- provider outage
- VPN failure
- DNS failure
- microphone disabled
- speaker unavailable
- network disconnected
- authentication failure

Errors should be clear and actionable.

---

# Emergency Calling

PSTN and VoIP emergency-calling behavior must be explicitly documented.

The user should not assume that a custom VoIP setup provides the same emergency-calling behavior as a conventional mobile carrier.

Emergency communication support must be evaluated before ONYX-NULL is treated as a primary communications device.

---

# Communications Security

Research should document:

```text
Signaling Encryption

Media Encryption

Authentication

Credential Storage

Metadata Exposure

Provider Trust

Fallback Behavior
```

---

# Potential Components

This directory may eventually contain:

```text
communications/
├── README.md
├── dialer/
├── sip/
├── contacts/
├── call-routing/
├── audio/
└── messaging/
```

---

# Testing

Communications testing should eventually include:

- SIP registration
- SIP authentication failure
- outgoing call
- incoming call
- encrypted media
- poor network conditions
- network loss during call
- VPN loss
- microphone kill switch
- speaker failure
- call termination
- provider failure

---

# Current Status

No ONYX-NULL-specific communications application currently exists.

P0 may use existing open-source SIP clients to validate the architecture before custom software is developed.
