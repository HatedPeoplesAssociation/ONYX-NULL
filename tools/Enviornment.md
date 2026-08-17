# ONYX-NULL Development Environment

## Purpose

This document defines the supported development environment for ONYX-NULL tooling.

The objective is to reduce undocumented machine-specific dependencies.

---

# Primary Development Platform

The project should initially target a documented Linux development environment.

Exact supported distributions will be determined later.

Potential environments include:

- Arch Linux
- Debian
- Ubuntu
- Fedora

Containerized development environments may be used where practical.

---

# Required Tools

Potential development dependencies include:

```text
git

gcc

clang

make

cmake

ninja

python

rust

cargo

go

docker / podman

kicad

openocd
```

The final list will depend on the chosen hardware and software stack.

---

# Version Tracking

Important tools should record their versions.

Example:

```bash
git --version
gcc --version
clang --version
python --version
rustc --version
```

---

# Environment Setup

The long-term objective is to provide a setup script or container definition.

Conceptually:

```bash
./tools/setup-development-environment
```

The setup process should be documented and reviewable.

---

# Containers

Containerized build environments may improve reproducibility.

Potential structure:

```text
tools/
└── environment/
    ├── Dockerfile
    ├── Containerfile
    └── README.md
```

---

# Environment Variables

Required environment variables should be documented.

Example:

```text
ONX_BUILD_DIR

ONX_TARGET

ONX_TOOLCHAIN
```

Secrets must not be placed in repository-tracked environment files.

---

# Hardware Access

Some tools may require access to:

- USB devices
- serial ports
- JTAG
- SWD
- removable storage

Required permissions should be documented.

---

# udev Rules

If Linux udev rules are required, they should be stored and documented in the repository.

Avoid requiring users to run all hardware tools as root solely because permissions were never configured correctly.

---

# Supported Architectures

The project may eventually support:

```text
x86_64 development host

ARM64 development host
```

Support should be documented rather than assumed.

---

# Build Storage

Large builds may require substantial disk space.

Each build system should eventually document estimated:

- disk usage
- RAM
- CPU requirements
- build duration class

---

# Current Status

No official ONYX-NULL development environment has been finalized.
