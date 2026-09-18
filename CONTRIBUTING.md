# Contributing to ZenOS

Thank you for your interest in contributing to **ZenOS**!

ZenOS is an experimental operating system project focused on learning, systems programming, Linux kernel development, CLI tooling, security, and eventually AI-assisted system interaction.

Contributions of all sizes are welcome — from fixing documentation to working on the kernel, userspace, boot process, networking, security tools, and automation.

---

## Table of Contents

* [Code of Conduct](#code-of-conduct)
* [Getting Started](#getting-started)
* [Development Environment](#development-environment)
* [Project Structure](#project-structure)
* [Building ZenOS](#building-zenos)
* [Making Changes](#making-changes)
* [Commit Guidelines](#commit-guidelines)
* [Pull Requests](#pull-requests)
* [Reporting Bugs](#reporting-bugs)
* [Feature Requests](#feature-requests)
* [Documentation](#documentation)
* [Security](#security)
* [Questions](#questions)
* [License](#license)

---

## Code of Conduct

Please be respectful and constructive when participating in the project.

Contributors should:

* Treat others with respect.
* Provide constructive feedback.
* Avoid harassment or discrimination.
* Keep technical discussions focused on improving the project.
* Help beginners learn when possible.

---

## Getting Started

### 1. Fork the Repository

Fork the ZenOS repository to your GitHub account.

### 2. Clone Your Fork

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 3. Add the Upstream Repository

```bash
git remote add upstream https://github.com/Coder-Delta/YOUR_REPOSITORY.git
```

Check your remotes:

```bash
git remote -v
```

### 4. Create a Branch

Create a separate branch for your work:

```bash
git checkout -b feature/my-feature
```

For bug fixes:

```bash
git checkout -b fix/my-bug
```

---

## Development Environment

ZenOS development can be performed inside a container to avoid damaging the host operating system.

Recommended tools:

* Linux
* Docker
* Git
* GCC
* Make
* Binutils
* Linux kernel build tools
* Toybox
* QEMU

On Ubuntu/Debian:

```bash
sudo apt update
sudo apt install -y \
    build-essential \
    git \
    bc \
    bison \
    flex \
    libssl-dev \
    libelf-dev \
    libncurses-dev \
    qemu-system-x86
```

On Fedora:

```bash
sudo dnf install -y \
    gcc \
    gcc-c++ \
    make \
    git \
    bc \
    bison \
    flex \
    openssl-devel \
    elfutils-libelf-devel \
    ncurses-devel \
    qemu-system-x86
```

---

## Container Development

Building an operating system can involve experimental kernel, filesystem, bootloader, and userspace changes.

Using Docker is recommended during development.

Example:

```bash
docker run --rm -it \
    -v "$PWD:/workspace" \
    ubuntu:latest \
    bash
```

Inside the container:

```bash
cd /workspace
```

Install the required development packages before building.

---

## Project Structure

The project may contain components such as:

```text
ZenOS/
├── linux/          # Linux kernel source
├── toybox/         # Userspace utilities
├── zenos/          # ZenOS root filesystem
│   ├── bin/
│   ├── sbin/
│   ├── etc/
│   ├── dev/
│   ├── proc/
│   ├── sys/
│   └── tmp/
├── scripts/        # Build and automation scripts
├── docs/           # Documentation
├── README.md
├── CONTRIBUTING.md
└── LICENSE
```

The exact structure may change as ZenOS develops.

---

## Building ZenOS

Always check the project's current build instructions in `README.md` before building.

For kernel development, a typical workflow may look like:

```bash
cd linux
make menuconfig
make -j$(nproc)
```

Build the userspace:

```bash
cd ../toybox
make defconfig
make -j$(nproc)
```

Install Toybox into the ZenOS root filesystem:

```bash
make CONFIG_PREFIX=../zenos/rootfs install
```

The build process may change as the project evolv
