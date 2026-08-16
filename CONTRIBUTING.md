# Contributing to ONYX-NULL

ONYX-NULL is an experimental open-source hardware and software project focused on building an owner-controlled mobile communications platform with explicit trust boundaries, hardware isolation, transparent documentation, and reproducible designs.

Contributions are welcome.

## Areas of Interest

Contributions are especially useful in:

* electrical engineering
* embedded Linux
* Android/AOSP
* PCB design
* hardware security
* RF engineering
* power electronics
* networking
* VoIP
* cryptography
* privacy engineering
* threat modeling
* reproducible builds
* industrial design
* technical documentation

## Before Contributing

Please review:

* `README.md`
* `ROADMAP.md`
* `docs/THREAT_MODEL.md`
* `docs/TRUST_MODEL.md`
* `docs/SECURITY_GOALS.md`
* `docs/NON_GOALS.md`

## Design Philosophy

ONYX-NULL favors:

1. verifiable controls over software promises
2. explicit trust boundaries
3. minimal proprietary dependencies
4. transparency when proprietary components are unavoidable
5. documented security assumptions
6. reproducible designs
7. repairability
8. open standards
9. measurable security claims

## Pull Requests

Pull requests should:

* clearly explain the problem being addressed
* describe the proposed solution
* document security implications
* document privacy implications
* include testing where applicable
* avoid undocumented proprietary dependencies
* update documentation when architecture changes

## Hardware Contributions

Hardware changes should include, where applicable:

* native KiCad source files
* schematic changes
* PCB layout changes
* BOM changes
* component datasheets
* voltage and current requirements
* firmware requirements
* trust implications
* test results

## Software Contributions

Software changes should include:

* source code
* build instructions
* dependencies
* security implications
* privacy implications
* test procedures

## Documentation

Documentation changes are treated as first-class contributions.

If you discover an undocumented assumption, limitation, proprietary component, build requirement, or security concern, please document it.

## Security

Do not publicly disclose exploitable security vulnerabilities through normal GitHub Issues.

See `SECURITY.md`.

## Project Status

ONYX-NULL is currently experimental.

Security properties described in design documents should be considered goals until they have been implemented, tested, and independently reviewed.
