# Development Environment

This document describes the recommended environment for ZenOS development.

## Recommended Host

A Linux system is recommended.

Supported development environments may include:

* Fedora
* Ubuntu
* Debian
* Other Linux distributions

Docker can be used to isolate the build environment.

## Required Software

Install:

```text
Git
Docker
GCC
Make
Binutils
QEMU
Linux kernel build dependencies
Toybox build dependencies
```

## Fedora

Install common dependencies:

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

## Ubuntu / Debian

Install:

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

## Docker

Check Docker:

```bash
docker --version
```

Run a development container:

```bash
docker run --rm -it \
    -v "$PWD:/workspace" \
    ubuntu:latest \
    bash
```

The repository is mounted at:

```text
/workspace
```

## QEMU

Check:

```bash
qemu-system-x86_64 --version
```

QEMU is useful for testing ZenOS without installing it on physical hardware.

## Why Use Docker?

Operating-system development can involve:

* Kernel configuration
* Initramfs generation
* Root filesystem changes
* Cross-compilation
* Build tools
* Experimental system software

Docker provides an isolated development environment and reduces the risk of changing the host system.

## Recommended Workflow

```text
Host Linux
    │
    └── Docker
          │
          ├── Linux kernel
          ├── Toybox
          ├── Root filesystem
          └── Build tools
                    │
                    ▼
                  QEMU
                    │
                    ▼
                  ZenOS
```
