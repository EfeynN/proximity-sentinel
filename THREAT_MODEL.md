# Proximity Sentinel – Threat Model

## Overview
This document describes the threat model for Proximity Sentinel.
It identifies potential adversaries, attack surfaces, threat vectors,
and the mitigation strategies used by the system.

The threat model is designed to evolve alongside the architecture
and is reviewed as new features are introduced.

---

## Assets to Protect

Proximity Sentinel is designed to protect the following critical assets:

- Game integrity and fair play
- Server authority and decision logic
- Detection and scoring algorithms
- Player risk profiles and audit data
- Configuration and enforcement rules
- Administrative and moderation interfaces

---

## Adversary Model

### Primary Adversaries
- Cheat developers
- Script kiddies using public tools
- Malicious insiders abusing permissions
- Automated attack tools and bots

### Adversary Capabilities
- Client-side memory manipulation
- Network packet interception or replay
- Obfuscation and evasion techniques
- Reverse engineering attempts
- Timing and behavior randomization

The system assumes that adversaries have **full control over the client**.

---

## Trust Boundaries

### Untrusted Zones
- Game clients
- Client-side telemetry
- Network paths between client and server

### Trusted Zones
- Sentinel Core Engine
- Server-side detection and scoring logic
- Data persistence layer
- Administrative review interfaces

No trust boundary exists between the client and enforcement logic.

---

## Attack Surfaces

### Client-Side
- Memory and process manipulation
- Injection and hook-based attacks
- Telemetry suppression or falsification
- Timing and heartbeat spoofing

### Network
- Packet replay attacks
- Latency manipulation
- Traffic shaping and flooding
- Man-in-the-middle attempts

### Server-Side
- Configuration abuse
- Privilege escalation via admin tools
- Logic manipulation through malformed data
- Resource exhaustion attempts

---

## Threat Categories

### Integrity Violations
- Client tampering
- Resource modification
- Unauthorized injections

**Mitigation:**
- Server-side validation
- Integrity signal weighting
- Cross-signal correlation

---

### Evasion Techniques
- Humanized cheat behavior
- Randomized input patterns
- Low-frequency abuse

**Mitigation:**
- Long-term behavior analysis
- Risk accumulation over time
- Historical pattern tracking

---

### False Positive Exploitation
- Triggering bans on legitimate players
- Environmental manipulation

**Mitigation:**
- False Positive Guard
- Manual review queue
- Risk decay and confidence calibration

---

### Insider Threats
- Abuse of administrative privileges
- Manual enforcement misuse

**Mitigation:**
- Role-based access control
- Audit logging
- Approve/reject enforcement workflows

---

### Denial of Service
- Telemetry flooding
- Resource exhaustion

**Mitigation:**
- Rate limiting
- Backpressure mechanisms
- Non-blocking processing pipelines

---

## Risk-Based Design

Proximity Sentinel does not rely on binary decisions.
All detections contribute to a **continuous risk score**.

Key properties:
- Signals are weighted
- Scores decay over time
- Enforcement thresholds are configurable
- Human review is mandatory for high-impact actions

This design reduces both evasion success and false positives.

---

## Detection Failures

### False Negatives
Some sophisticated attacks may evade detection temporarily.

**Mitigation:**
- Longitudinal analysis
- Cross-session correlation
- Adaptive rule updates

### False Positives
Legitimate behavior may be misclassified.

**Mitigation:**
- Confidence multipliers
- Manual review
- Enforcement rollback capability

---

## Logging and Auditability

All critical actions are logged:
- Detection signals
- Risk score changes
- Enforcement decisions
- Administrative actions

Logs are designed to support:
- Incident investigation
- Post-mortem analysis
- Accountability and compliance

---

## Assumptions and Limitations

- Client-side security cannot be fully trusted
- No system can detect all cheats instantly
- Security is an ongoing process, not a static state

The threat model is reviewed continuously as new threats emerge.

---

## Review Process

This threat model is reviewed:
- On major architectural changes
- When new detection modules are added
- After security incidents
- Periodically during active development

---

## Summary

Proximity Sentinel is built under the assumption of active and capable adversaries.
By combining behavior-based detection, risk accumulation, and human review,
the system aims to provide robust protection while minimizing collateral damage
to legitimate players.
