# Commit Guidelines

Clear commits make ZenOS easier to maintain and review.

## Commit Format

Use:

```text
type: short description
```

Examples:

```text
kernel: update default configuration
```

```text
rootfs: add initial filesystem layout
```

```text
docs: improve build instructions
```

```text
build: add QEMU boot script
```

## Commit Types

### `feat`

New functionality.

```text
feat: add network initialization
```

### `fix`

Bug fixes.

```text
fix: correct initramfs generation
```

### `docs`

Documentation changes.

```text
docs: add kernel development guide
```

### `build`

Build-system changes.

```text
build: add Docker development environment
```

### `test`

Testing changes.

```text
test: add QEMU boot test
```

### `refactor`

Code restructuring without changing intended behavior.

```text
refactor: simplify init startup
```

### `security`

Security-related changes.

```text
security: restrict service permissions
```

### `chore`

Maintenance work.

```text
chore: update development dependencies
```

## Good Commit Messages

Good:

```text
toybox: install utilities into rootfs
```

Avoid:

```text
update
```

Avoid:

```text
changes
```

Avoid:

```text
fixed stuff
```

## One Logical Change Per Commit

Prefer:

```text
kernel: enable required filesystem support
```

followed by:

```text
build: add filesystem test
```

instead of one large unrelated commit.

## Check Before Committing

Run:

```bash
git status
```

Review:

```bash
git diff
```

Then:

```bash
git add <files>
git commit -m "type: description"
```

## Do Not Commit Secrets

Never commit:

* Passwords
* API keys
* Tokens
* Private SSH keys
* Cloud credentials
* Personal credentials

Before pushing:

```bash
git diff --cached
```

Review the staged content.

## Amending Commits

If you have not pushed the commit:

```bash
git commit --amend
```

Use history rewriting carefully on shared branches.
