# Getting Started

Welcome to ZenOS.

ZenOS is an experimental operating system project focused on learning and developing low-level system software.

The project currently explores areas such as:

* Linux kernel development
* Userspace
* Toybox
* Root filesystems
* Boot processes
* System initialization
* Networking
* Security tooling
* Automation
* AI-assisted system interaction

## Prerequisites

Recommended knowledge:

* Basic Linux command line
* Git
* C programming
* Shell scripting
* Basic operating-system concepts

You do not need to be an expert to contribute.

## Required Tools

The recommended development environment includes:

* Git
* Docker
* GCC
* Make
* Binutils
* QEMU
* Linux kernel build dependencies
* Toybox build dependencies

## Clone the Repository

Fork the repository on GitHub and clone your fork:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Add the upstream repository:

```bash
git remote add upstream https://github.com/Coder-Delta/YOUR_REPOSITORY.git
```

Verify:

```bash
git remote -v
```

## Create a Development Branch

Never perform development directly on `main`.

Create a branch:

```bash
git checkout -b feature/my-feature
```

For bug fixes:

```bash
git checkout -b fix/my-bug
```

## Development Container

ZenOS development is recommended inside Docker.

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

## First Contribution

A good first contribution could be:

* Fixing documentation
* Improving build instructions
* Adding a test
* Fixing a build script
* Improving error handling
* Reporting a reproducible bug
* Adding a small userspace utility
* Improving QEMU testing

## Before Starting Large Work

For significant changes:

1. Check existing issues.
2. Check existing Pull Requests.
3. Search the repository.
4. Discuss architectural changes with maintainers.
5. Create a design proposal when appropriate.

This helps prevent duplicated work and incompatible implementations.

## Getting Help

If you are stuck:

1. Read the README.
2. Read the relevant documentation.
3. Search existing issues.
4. Search Pull Requests.
5. Ask a focused question.

Include commands, errors, and relevant logs when asking for help.
