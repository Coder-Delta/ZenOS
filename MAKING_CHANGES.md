# Making Changes

ZenOS contains low-level system software, so changes should be made carefully and incrementally.

## Before You Change Code

Before starting:

1. Understand the existing implementation.
2. Search for related code.
3. Check existing issues.
4. Check existing Pull Requests.
5. Determine whether the change affects other components.
6. Consider how the change will be tested.

## Keep Changes Focused

A Pull Request should generally solve one problem.

Avoid combining unrelated changes such as:

```text
Kernel change
+
Documentation rewrite
+
Unrelated shell script
+
Formatting changes
```

unless they are directly connected.

## Small Changes

Small contributions are encouraged.

Examples:

* Fix a typo.
* Improve an error message.
* Fix a build command.
* Add documentation.
* Add a test.
* Correct a shell script.
* Improve a configuration.

## Kernel Changes

Kernel changes require additional care.

Before submitting:

```bash
make -j$(nproc)
```

Test the resulting kernel using QEMU whenever possible.

Document:

* What changed
* Why it changed
* Kernel configuration changes
* How it was tested
* Any limitations

## Root Filesystem Changes

When modifying the root filesystem, check:

```text
/etc
/bin
/sbin
/dev
/proc
/sys
/tmp
```

Make sure required permissions and executables are present.

## Build Script Changes

Build scripts should:

* Fail clearly when required tools are missing.
* Avoid unnecessary destructive commands.
* Use quoted variables.
* Provide useful error messages.
* Be reproducible when possible.

## Testing Changes

Every functional change should have an appropriate test.

Examples:

```text
Kernel → QEMU boot test
Toybox → command execution test
Init → userspace startup test
Networking → connectivity test
Build script → clean build test
Documentation → command verification
```

## Backward Compatibility

Consider whether your change breaks:

* Existing build commands
* Existing scripts
* Existing configuration
* Root filesystem layout
* Boot parameters
* Developer workflows

If something intentionally changes, document it.

## Generated Files

Do not commit generated artifacts unless they are explicitly required.

Check:

```bash
git status
```

before committing.

## Review Your Changes

Use:

```bash
git diff
```

and:

```bash
git status
```

Review every changed file before committing.

## Large Architectural Changes

For major changes, open an issue or design discussion before implementation.

Examples:

* Changing the init architecture
* Replacing userspace components
* Introducing a package manager
* Changing the boot architecture
* Adding a new security subsystem
* Introducing an AI service architecture
