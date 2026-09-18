# Project Structure

This document describes the organization of the ZenOS repository.

## Repository Layout

A typical ZenOS repository may look like:

```text
ZenOS/
├── linux/
├── toybox/
├── zenos/
│   └── rootfs/
│       ├── bin/
│       ├── sbin/
│       ├── etc/
│       ├── dev/
│       ├── proc/
│       ├── sys/
│       └── tmp/
├── scripts/
├── docs/
├── README.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── LICENSE
```

## Linux Kernel

```text
linux/
```

Contains the Linux kernel source used by ZenOS.

Kernel changes should be made carefully and tested through QEMU whenever possible.

## Toybox

```text
toybox/
```

Contains Toybox userspace utilities.

Toybox provides many standard Unix/Linux command-line utilities in a single executable.

## Root Filesystem

```text
zenos/rootfs/
```

Contains the initial ZenOS userspace filesystem.

Important directories include:

### `/bin`

Essential executable programs.

### `/sbin`

System administration utilities.

### `/etc`

System configuration files.

### `/dev`

Device nodes.

### `/proc`

Proc filesystem mount point.

### `/sys`

Sysfs mount point.

### `/tmp`

Temporary files.

## Scripts

```text
scripts/
```

Contains build, packaging, testing, and automation scripts.

Scripts should be kept portable where practical.

## Documentation

```text
docs/
```

Contains project documentation.

Documentation should explain:

* Architecture
* Development
* Build process
* Testing
* Contribution workflow
* Design decisions

## Root Files

### `README.md`

Provides the main project overview.

### `CONTRIBUTING.md`

Explains how contributors can participate in ZenOS.

### `CODE_OF_CONDUCT.md`

Defines expected community behavior.

### `LICENSE`

Defines the project's licensing terms.

## Structure Changes

Large structural changes should be discussed before implementation.

If you introduce a new major directory, document its purpose.
