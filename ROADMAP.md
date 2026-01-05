# Proximity Sentinel – Roadmap

This roadmap outlines the planned development phases of Proximity Sentinel.
Dates are indicative and subject to change based on security findings and testing results.

---

## Development Roadmap

| Version | Phase | Status | Focus | Key Deliverables |
|--------|------|--------|-------|------------------|
| v0.1.0 | Architecture Foundation | ✅ Completed | Design & Security | Architecture docs, risk score design, threat model, security policy, initial UI preview |
| v0.2.0 | Telemetry Pipeline | ✅ Completed | Data Collection | Client telemetry ingestion, session heartbeat, basic integrity signals |
| v0.3.0 | Core Engine | ✅ Completed | Modularity | Modular core engine, signal routing, lifecycle management |
| v0.4.0 | Detection Expansion | ✅ Completed | Detection | Behavior detection, network anomaly detection, historical signal tracking |
| v0.5.0 | Risk Scoring System | ✅ Completed | Intelligence | Cumulative risk score, time-based decay, threshold logic |
| v0.6.0 | False Positive Guard | 🔄 In Progress | Accuracy | Confidence weighting, cross-signal correlation, FP reduction |
| v0.7.0 | Review Layer | ✅ Completed | Human-in-the-loop | Manual review queue, approve/reject workflows, audit trail |
| v0.8.0 | Enforcement Control | ✅ Completed | Enforcement | Soft vs hard enforcement, cooldowns, enforcement decay |
| v0.9.0 | Release Candidate | ✅ Completed | Stabilization | Performance optimization, noise reduction, security validation |
| v1.0.0 | Production Release | 🔄 In Progress | Stability & Security | Hardened pipeline, finalized policies, audit-grade logging |
| v2.0.0 | Intelligence Platform | 🔄 In Progress | Expansion | Adaptive behavior models, cross-server awareness, advanced analytics |

---

## Versioning Notes
- Versions below **v1.0.0** may include breaking changes
- **v1.0.0** marks the first production-ready release
- **v2.0.0** represents a strategic evolution, not a full rewrite

---

## Long-Term Vision (v2.x)
- Cross-session and cross-server intelligence
- Long-term player reputation scoring
- Advanced admin analytics and reporting
- Optional enterprise-scale deployments

---

## Summary
Proximity Sentinel follows a controlled, security-first roadmap.
Each version builds upon the previous phase with an emphasis on
accuracy, auditability, and operational reliability.
