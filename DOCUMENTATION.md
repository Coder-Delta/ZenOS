# Documentation

Good documentation is an important part of ZenOS.

Documentation contributions are welcome even if you do not contribute code.

## Documentation Areas

Documentation may cover:

* Installation
* Development
* Architecture
* Kernel configuration
* Root filesystem
* Toybox
* Init
* Networking
* Security
* Build system
* Testing
* Debugging
* AI-assisted system architecture

## Markdown

Use Markdown for project documentation.

Example:

````markdown
# Heading

## Section

Explain the topic clearly.

### Example

```bash
echo "Hello ZenOS"
````

````

## Writing Guidelines

Documentation should be:

- Clear
- Accurate
- Concise
- Beginner-friendly
- Technically precise

## Commands

Always verify commands before documenting them.

Prefer:

```bash
make -j$(nproc)
````

over documenting commands that have not been tested.

## Code Examples

Code examples should be:

* Complete enough to understand.
* Properly formatted.
* Tested where practical.
* Relevant to the current project structure.

## Architecture Documentation

Architecture documentation should explain relationships between components.

Example:

```text
Bootloader
    ↓
Linux Kernel
    ↓
Init
    ↓
Root Filesystem
    ↓
Toybox
    ↓
Shell
    ↓
Services
```

Diagrams can be used when they make complex systems easier to understand.

## Updating Documentation

When changing functionality, check whether documentation needs updating.

For example:

```text
Code change
     ↓
Does behavior change?
     ↓
Yes
     ↓
Update documentation
```

## Documentation Pull Requests

Documentation-only Pull Requests are welcome.

Examples:

```text
docs: fix installation instructions
```

```text
docs: document rootfs structure
```

```text
docs: add QEMU debugging guide
```
