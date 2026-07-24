# Security Policy

Thank you for helping improve the security of BMASS.

Because BMASS explores AI operating system interfaces, privilege boundaries, and model-driven execution, security is a fundamental design objective.

---

# Reporting a Vulnerability

Please **do not** disclose security vulnerabilities publicly before they have been reviewed.

Instead, report them privately through GitHub's security reporting feature or by contacting the project maintainer.

Please include:

- Description of the issue
- Steps to reproduce
- Potential impact
- Suggested mitigation (if known)

We will acknowledge reports as quickly as possible.

---

# Scope

We are particularly interested in reports involving:

- Privilege escalation
- Shell execution vulnerabilities
- Command injection
- Prompt injection
- Filesystem isolation failures
- Sandbox escapes
- Authentication and authorisation
- Model safety
- Unsafe tool execution
- Data leakage
- Memory safety
- Denial-of-service attacks

---

# Security Philosophy

BMASS combines adaptive AI models with deterministic software.

Our design principles include:

- Least privilege
- Human oversight
- Defence in depth
- Transparent execution
- Deterministic safety layers
- Local-first operation
- Privacy by default
- Explicit permission boundaries

The AI model should never be assumed to be inherently trustworthy.

Deterministic controls should enforce safety independently of model behaviour.

---

# Responsible Disclosure

We appreciate responsible disclosure and will work with researchers to investigate and address legitimate security concerns.

Where appropriate, contributors who responsibly disclose significant vulnerabilities will be acknowledged in project release notes or documentation.

---

# Experimental Status

BMASS is an active research project.

Interfaces, security boundaries, and architecture may evolve rapidly.

Users should not deploy BMASS in safety-critical or production environments without appropriate evaluation and risk assessment.

---

Thank you for helping build a safer BMASS.
