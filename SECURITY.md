# Security Policy

## Overview
Proximity Sentinel is a security-focused anti-cheat and integrity monitoring system.
Security vulnerabilities are treated with the highest priority and handled through a
responsible disclosure process.

This document outlines how to report security issues and what to expect from the response process.

---

## Supported Versions

Only actively maintained versions are eligible for security support.

| Version | Supported |
|--------|-----------|
| main / development | ✅ Yes |
| archived releases | ❌ No |
| forks | ❌ No |

---

## Reporting a Vulnerability

**DO NOT** open public GitHub issues for security vulnerabilities.

If you discover a potential security issue, please report it privately using one of the following methods:

### Preferred Method
- **Email:** `info@proximitysystems.xyz` 

### Alternative
- Private message to a Proximity Systems core maintainer

Please include:
- A clear description of the issue
- Steps to reproduce (if applicable)
- Potential impact
- Proof-of-concept (if available)

---

## Response Process

Once a vulnerability report is received:

1. Acknowledgement within 48 hours
2. Initial assessment and severity classification
3. Mitigation or fix development
4. Internal verification
5. Coordinated disclosure (if applicable)

Critical vulnerabilities may result in immediate mitigations before public disclosure.

---

## Disclosure Policy

Proximity Sentinel follows responsible disclosure principles.

- Reporters are encouraged to allow reasonable time for a fix before disclosure
- Public disclosure without coordination may result in reports being ignored

We may credit reporters in release notes unless anonymity is requested.

---

## Scope

### In Scope
- Sentinel Core Engine
- Detection and scoring logic
- Client-server trust boundaries
- Admin and moderation interfaces
- Configuration and rule handling

### Out of Scope
- Forked or modified versions
- Third-party integrations not maintained by Proximity Systems
- Issues caused by improper server configuration
- Denial-of-service attacks

---

## Security Philosophy

Proximity Sentinel is designed with the following principles:

- Defense in depth
- Least privilege
- Behavior-based detection over signatures
- Human-in-the-loop enforcement
- Auditability and traceability

Security is considered an ongoing process, not a one-time implementation.

---

## Legal Notice

Unauthorized testing, reverse engineering, or exploitation of Proximity Sentinel
outside permitted environments is strictly prohibited.

All reports must comply with applicable laws and regulations.
