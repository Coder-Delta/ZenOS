# Pull Requests

Pull Requests are used to review and merge changes into ZenOS.

## Before Opening a Pull Request

Make sure:

* Your branch contains only relevant changes.
* The project builds.
* Relevant tests pass.
* Documentation has been updated when necessary.
* No secrets are included.
* Generated files are not accidentally committed.

Check:

```bash
git status
git diff
```

## Update Your Branch

Update your local main branch:

```bash
git checkout main
git pull upstream main
```

Then update your feature branch:

```bash
git checkout feature/my-feature
git rebase main
```

Resolve conflicts if necessary.

## Push Your Branch

```bash
git push origin feature/my-feature
```

## Pull Request Title

Use a clear title.

Examples:

```text
kernel: improve boot configuration
```

```text
docs: add ZenOS development guide
```

```text
build: add QEMU helper script
```

## Pull Request Description

Include:

```text
## What changed?

Describe the change.

## Why?

Explain the reason for the change.

## Testing

Explain how the change was tested.

## Limitations

Describe known limitations.

## Related Issues

Closes #123
```

## Review Process

Maintainers may:

* Ask questions.
* Request changes.
* Suggest alternative implementations.
* Request additional tests.
* Request documentation updates.

Respond to review comments and update your branch.

## Review Checklist

### Code

* [ ] Code is readable.
* [ ] No unnecessary changes.
* [ ] Error handling is appropriate.
* [ ] No secrets are included.

### Testing

* [ ] Build succeeds.
* [ ] Relevant tests pass.
* [ ] QEMU testing completed when appropriate.

### Documentation

* [ ] Documentation updated where required.
* [ ] Commands have been verified.

## Draft Pull Requests

Use a Draft Pull Request when the work is not ready for final review.

Draft PRs are useful for:

* Architecture discussions
* Early implementations
* Experimental features
* Requesting feedback

## Maintainer Review

A Pull Request may be merged when maintainers determine that it is ready according to the project's current requirements.

Not every Pull Request will be merged immediately.

Some may require additional design work or changes.
