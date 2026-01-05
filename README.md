# Proximity Sentinel

![Status](https://img.shields.io/badge/status-active_development-blue)
![Release](https://img.shields.io/badge/release-v0.1.0-informational)
![Security](https://img.shields.io/badge/security-policy_enabled-success)
![License](https://img.shields.io/badge/license-private-lightgrey)

Proximity Sentinel is a high-performance anti-cheat and security suite developed under Proximity Systems.

It focuses on detecting unfair gameplay, abnormal behavior patterns, and unauthorized client modifications through real-time analysis and modular security layers.

---

## Preview

![Proximity Sentinel UI Preview](./proximity-systems-sentinelv8.png)

---

## Why Proximity Sentinel?

Most anti-cheat systems rely on single-event detections and aggressive enforcement.  
Proximity Sentinel takes a different, security-first approach.

- Behavior-based detection instead of signatures  
- Cumulative risk scoring rather than instant punishment  
- Human-in-the-loop enforcement  
- Auditability and traceability by design  
- Built for long-term stability, not short-term bans  

Proximity Sentinel is designed as a **security platform**, not just an anti-cheat.

---

## Core Features
- Real-time behavior analysis  
- Modular anti-cheat architecture  
- Server-side integrity validation  
- Risk scoring and anomaly detection  
- Scalable and extensible design  

---

## Status
🚧 Active development

---

## Disclaimer
This project is intended for authorized server environments only.  
Unauthorized usage or redistribution is prohibited.

---

## Architecture Overview

```mermaid
flowchart TB
  subgraph ClientSide[Client Side]
    C1[Client Integrity Probe]
    C2[Session Heartbeat]
    C3[Hardware Fingerprint Optional]
  end

  subgraph ServerSide[Server Side]
    S0[Sentinel Core Engine]

    subgraph Detection[Detection Signals]
      D1[Behavior Monitor]
      D2[Movement Aim Heuristics]
      D3[Injection Tamper Flags]
      D4[Network Packet Anomalies]
      D5[Resource File Integrity]
    end

    subgraph Scoring[Decision Intelligence]
      A1[Risk Scoring Engine]
      A2[Rules Engine]
      A3[Behavior AI Optional]
      A4[False Positive Guard]
    end

    subgraph Actions[Actions Enforcement]
      E1[Alerting Evidence Capture]
      E2[Auto Actions Kick TempBan]
      E3[Manual Review Queue]
      E4[Staff Approve Reject Logs]
    end

    subgraph Data[Data Layer]
      DB1[(Event Store)]
      DB2[(Player Profiles)]
      DB3[(Audit Logs)]
      DB4[(Config Rules)]
    end

    subgraph Integrations[Integrations]
      I1[Admin Dashboard]
      I2[Discord Webhooks]
      I3[Game Server API Adapter]
      I4[External Security SIEM Optional]
    end
  end

  ClientSide -->|Telemetry Signals| S0
  S0 --> Detection
  Detection --> Scoring
  Scoring --> Actions
  Actions --> Data
  Scoring --> Data
  Data --> Integrations
  Integrations -->|Moderation Decisions| Actions


---

```mermaid
stateDiagram-v2
  [*] --> Idle

  Idle --> Collecting
  Collecting --> Evaluating

  Evaluating --> LowRisk
  Evaluating --> MediumRisk
  Evaluating --> HighRisk
  Evaluating --> CriticalRisk

  LowRisk --> Idle

  MediumRisk --> Observing
  Observing --> Idle
  Observing --> Escalated

  HighRisk --> Restricted
  Restricted --> ReviewQueue
  Restricted --> Idle

  CriticalRisk --> Enforced
  Enforced --> ReviewQueue

  ReviewQueue --> Approved
  ReviewQueue --> Rejected

  Approved --> Idle
  Rejected --> Idle
