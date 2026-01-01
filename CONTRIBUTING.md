# Contributing to Proximity Sentinel

Thank you for your interest in contributing to Proximity Sentinel.
We welcome responsible contributions that align with the project’s
security-focused design and quality standards.

This document outlines the rules, expectations, and workflow for contributors.

---

## Guiding Principles

Proximity Sentinel is a **security-critical system**.
All contributions must prioritize:

- Security and correctness over speed
- Maintainability and clarity
- Minimal trust assumptions
- Defense against abuse and misuse

Contributions that weaken detection, enforcement, or auditability
will not be accepted.

---

## Who Can Contribute

### Allowed Contributors
- Core maintainers
- Approved collaborators
- Trusted community contributors (by invitation)

### Not Accepted
- Anonymous large feature drops
- Contributions intended to bypass or weaken detection
- Cheat-related proof-of-concepts
- Reverse engineering tools or guides

---

## Contribution Types

We currently accept contributions in the following areas:

### Documentation
- README improvements
- Architecture and threat model updates
- Security clarifications

### Tooling & Infrastructure
- Build tooling
- Testing utilities
- Developer experience improvements

### Detection & Scoring (Restricted)
- Only via prior discussion
- Requires design review
- Must include rationale and risk assessment

---

## Before You Start

Before opening a pull request:

1. Review `README.md`, `ARCHITECTURE.md`, and `THREAT_MODEL.md`
2. Open a discussion or issue describing:
   - What you want to change
   - Why it is needed
   - Potential risks or side effects
3. Wait for maintainer feedback

Pull requests without prior discussion may be closed.

---

## Pull Request Guidelines

### General Rules
- Keep changes focused and minimal
- One logical change per pull request
- Do not include unrelated refactors

### Code Quality
- Follow existing project structure
- Prefer clarity over cleverness
- Avoid hard-coded values
- Ensure changes are auditable

### Security Requirements
- Do not expose sensitive logic
- Do not log sensitive data
- Do not add client-side trust assumptions

---

## Commit Message Format

Use clear and descriptive commit messages.

Examples:
