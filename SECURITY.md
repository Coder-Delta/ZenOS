# Security Policy

Security is an important consideration for ZenOS.

Because ZenOS includes low-level system software, security issues may affect the kernel, userspace, build system, networking, or other components.

## Supported Versions

ZenOS is an experimental project.

Security support depends on the project's current development status.

Check the project's releases and documentation for currently maintained versions.

## Reporting a Vulnerability

Please do not publicly disclose a serious security vulnerability before maintainers have had an opportunity to investigate it.

Use the project's private security-reporting channel when available.

## Include

A security report should contain:

* Vulnerability description
* Affected component
* Affected version or commit
* Reproduction steps
* Security impact
* Suggested mitigation, if known

## Example

```text
## Vulnerability

Describe the issue.

## Affected Component

Example:
Network service

## Affected Version

Commit:
Version:

## Reproduction

1.
2.
3.

## Impact

Describe the security impact.

## Suggested Fix

Describe a possible mitigation if known.
```

## Do Not Include

Never publish sensitive information such as:

* Passwords
* API keys
* Access tokens
* Private keys
* Credentials
* Private user data

## Security Research

Security research and responsible testing are welcome when performed responsibly.

Do not:

* Attack systems you do not own or have permission to test.
* Attempt to access private information.
* Disrupt project infrastructure.
* Abuse project services.

## Third-Party Components

ZenOS may use third-party open-source components.

Security vulnerabilities in third-party software should be reported according to the relevant project's security policy when appropriate.

## Disclosure

After investigation and remediation, maintainers may publish security information so users and contributors can understand the issue and mitigation.

Disclosure timing may depend on:

* Severity
* Availability of a fix
* Affected versions
* Coordination with upstream projects
