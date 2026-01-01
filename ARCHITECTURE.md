# Proximity Sentinel – Architecture

## Overview
Proximity Sentinel is a modular, behavior-driven anti-cheat and security system designed for
modern multiplayer server environments. The architecture emphasizes scalability, auditability,
and human-in-the-loop decision making.

Rather than relying on single-event detections, Sentinel evaluates player behavior as a
continuous risk spectrum.

---

## High-Level Architecture

At a high level, Proximity Sentinel is composed of the following layers:

1. Client Telemetry
2. Core Processing Engine
3. Detection & Signal Layer
4. Risk Scoring & Intelligence
5. Enforcement & Review
6. Data Persistence
7. Integrations & Interfaces

Each layer is isolated by responsibility and communicates through well-defined interfaces.

---

## Client Side

### Responsibilities
- Collect runtime telemetry
- Perform basic integrity self-checks
- Maintain session heartbeat
- Forward signals to the server securely

### Characteristics
- Lightweight
- Minimal trust assumptions
- No direct enforcement authority

The client is treated as **untrusted** and is never considered a source of truth.

---

## Sentinel Core Engine

The Sentinel Core Engine is the central orchestrator of the system.

### Responsibilities
- Signal ingestion and routing
- Module coordination
- Configuration loading
- Lifecycle management

The core engine does not make enforcement decisions itself; it delegates analysis and decisions
to specialized modules.

---

## Detection & Signals Layer

This layer is responsible for transforming raw telemetry into meaningful signals.

### Signal Categories
- **Behavior Signals**  
  Movement anomalies, aim irregularities, impossible actions
- **Integrity Signals**  
  Memory tampering, invalid resource hashes, unauthorized injections
- **Network Signals**  
  Packet manipulation, abnormal latency patterns, replay anomalies
- **Historical Signals**  
  Repeated medium-risk events over time

Each signal is timestamped, contextualized, and forwarded to the scoring system.

---

## Risk Scoring & Intelligence

### Risk Scoring Engine
The Risk Scoring Engine aggregates signals into a cumulative risk score.

Key characteristics:
- Weighted signals
- Confidence-based multipliers
- Time-based decay
- Threshold-based evaluation

No single signal is sufficient to trigger high-severity enforcement.

### False Positive Guard
A dedicated component evaluates:
- Signal consistency
- Environmental context
- Historical player behavior

This component reduces accidental enforcement and escalations.

---

## Enforcement & Review

### Automated Actions
Based on risk thresholds:
- **Low:** Log only
- **Medium:** Shadow monitoring
- **High:** Temporary restriction
- **Critical:** Immediate enforcement

### Manual Review
High and critical cases are routed to a review queue where staff can:
- Approve enforcement
- Reject as false positive
- Trigger policy updates

Human review is considered a first-class system component.

---

## Data Layer

### Stored Data
- Event logs
- Player risk profiles
- Audit trails
- Configuration and rules

### Design Principles
- Append-only logs
- Tamper-resistant storage
- Clear separation between operational and audit data

---

## Integrations

Proximity Sentinel integrates with external systems through adapters.

### Supported Integrations
- Admin dashboards
- Discord and webhook notifications
- Game server APIs
- External security or monitoring platforms

Integrations never bypass core decision logic.

---

## Security Boundaries

- Client is always untrusted
- Enforcement logic is server-only
- Configuration changes are audited
- All actions are traceable

The system assumes active adversaries and is designed accordingly.

---

## Design Principles

- Defense in depth
- Modular isolation
- Behavior over signatures
- Human-in-the-loop enforcement
- Auditability by default

---

## Future Extensions

The architecture supports future extensions such as:
- Advanced behavior models
- Cross-server reputation systems
- External SIEM integration
- Adaptive rule learning

---

## Summary
Proximity Sentinel is designed not as a simple anti-cheat, but as a
security platform that evaluates player behavior continuously,
balances automation with human judgment, and prioritizes reliability
over aggressive enforcement.
