# Building ZenOS

This document describes the general ZenOS build process.

> The exact commands may change as the project develops.

## Build Components

ZenOS currently consists of several major components:

```text
Linux Kernel
     +
Toybox
     +
Root Filesystem
     +
Init
     +
Initramfs
     +
QEMU
```

## 1. Enter the Development Environment

Start the Docker container:

```bash
docker run --rm -it \
    -v "$PWD:/workspace" \
    ubuntu:latest \
    bash
```

Then:

```bash
cd /workspace
```

## 2. Build the Linux Kernel

Enter the kernel source:

```bash
cd linux
```

Configure the kernel:

```bash
make menuconfig
```

Build:

```bash
make -j$(nproc)
```

The resulting kernel image is typically located under:

```text
arch/x86/boot/
```

For x86_64:

```text
arch/x86/boot/bzImage
```

## 3. Build Toybox

Enter Toybox:

```bash
cd ../toybox
```

Configure:

```bash
make defconfig
```

Build:

```bash
make -j$(nproc)
```

Install into the ZenOS root filesystem:

```bash
make CONFIG_PREFIX=../zenos/rootfs install
```

## 4. Prepare the Root Filesystem

Create required directories:

```bash
mkdir -p ../zenos/rootfs/{bin,sbin,etc,dev,proc,sys,tmp}
```

Additional directories may be required as the project grows.

## 5. Configure Init

ZenOS requires an initialization process.

The initial process is responsible for setting up userspace and starting the shell or other services.

The init executable should be available inside the root filesystem.

For example:

```text
zenos/rootfs/
└── init
```

## 6. Create an Initramfs

The root filesystem can be packaged as an initramfs.

Example:

```bash
cd ../zenos
```

Create the archive:

```bash
find rootfs -print0 | cpio --null -ov --format=newc | gzip -9 > initramfs.img
```

## 7. Test With QEMU

Boot the kernel and initramfs:

```bash
qemu-system-x86_64 \
    -kernel ../linux/arch/x86/boot/bzImage \
    -initrd initramfs.img \
    -append "console=ttyS0" \
    -nographic
```

## Debugging

If ZenOS fails to boot, check:

* Kernel configuration
* Kernel command line
* Init executable
* Root filesystem structure
* File permissions
* Required device nodes
* `/proc` and `/sys` setup
* Initramfs contents

## Clean Build

For the kernel:

```bash
make clean
```

For a more complete kernel cleanup:

```bash
make mrproper
```

Be careful with `mrproper` because it removes configuration files and generated files.

## Important

Do not commit large generated build artifacts unless the repository specifically requires them.

Examples:

```text
bzImage
*.o
*.a
*.ko
initramfs.img
temporary build files
```

Use `.gitignore` where appropriate.
