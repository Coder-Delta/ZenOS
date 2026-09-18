# Reporting Bugs

Bug reports help improve ZenOS.

A useful bug report should be reproducible and contain enough information to investigate the problem.

## Before Reporting

First check:

* Existing issues
* Closed issues
* Pull Requests
* Current documentation

The problem may already be known.

## Include Your Environment

Provide:

```text
Host OS:
Architecture:
Kernel version:
Docker version:
QEMU version:
Git commit:
```

Example:

```text
Host OS: Fedora Linux
Architecture: x86_64
Docker: 29.x
QEMU: 10.x
Commit: abc1234
```

## Describe the Problem

Explain:

1. What happened?
2. What did you expect?
3. How can the problem be reproduced?

## Reproduction Steps

Example:

```text
1. Clone the repository.
2. Enter the Docker container.
3. Build the kernel.
4. Build Toybox.
5. Generate the initramfs.
6. Start QEMU.
7. Observe the failure.
```

## Include Logs

Include relevant output:

```text
<error output here>
```

For kernel problems, include relevant kernel messages.

For example:

```bash
dmesg
```

or QEMU output.

## Avoid Huge Logs

Only include relevant logs when possible.

If a log is very large:

* Attach it as a file.
* Provide the relevant section.
* Explain where the failure occurs.

## Bug Report Template

````text
## Description

Describe the problem.

## Environment

Host OS:
Architecture:
Docker:
QEMU:
Git commit:

## Steps to Reproduce

1.
2.
3.

## Expected Behavior

What should happen?

## Actual Behavior

What happens instead?

## Logs

```text
paste logs here
````

## Additional Information

Anything else that may help.

````

## Security Vulnerabilities

Do not publicly disclose sensitive security vulnerabilities through a normal issue.

Follow the project's security reporting process described in:

```text
SECURITY.md
````
