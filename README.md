# ZenOS

> A minimal, terminal-first operating system built for learning, experimentation, and security-focused computing.

ZenOS is an experimental operating system project built around the Linux kernel and Toybox. The goal is to understand how an operating system is assembled from the kernel, userspace, filesystem, initialization system, and command-line tools.

## Architecture

```text
                    ┌───────────────────────┐
                    │      ZenOS CLI        │
                    │   Shell • Tools       │
                    └───────────┬───────────┘
                                │
                    ┌───────────▼───────────┐
                    │       Toybox          │
                    │   Unix Userland Tools  │
                    └───────────┬───────────┘
                                │
                    ┌───────────▼───────────┐
                    │      ZenOS Init       │
                    │   PID 1 / Services    │
                    └───────────┬───────────┘
                                │
                    ┌───────────▼───────────┐
                    │     Linux Kernel      │
                    │ Drivers • Memory •    │
                    │ Processes • Networking│
                    └───────────────────────┘
