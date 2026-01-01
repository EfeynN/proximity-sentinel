# Proximity Sentinel

Proximity Sentinel is a high-performance anti-cheat and security suite developed under Proximity Systems.

It focuses on detecting unfair gameplay, abnormal behavior patterns, and unauthorized client modifications through real-time analysis and modular security layers.

---

## Core Features
- Real-time behavior analysis  
- Modular anti-cheat architecture  
- Server-side integrity validation  
- Risk scoring & anomaly detection  
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
  %% Proximity Sentinel - Modular Architecture

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


## Risk Score Lifecycle (State Diagram)

```mermaid
stateDiagram-v2
  [*] --> Idle

  Idle --> Collecting : Player Activity
  Collecting --> Normalizing : Telemetry Received
  Normalizing --> Evaluating : Signals Ready

  Evaluating --> LowRisk : Score < Threshold Low
  Evaluating --> MediumRisk : Score >= Threshold Low
  Evaluating --> HighRisk : Score >= Threshold High
  Evaluating --> CriticalRisk : Score >= Threshold Critical

  LowRisk --> Idle : Log Only

  MediumRisk --> Observing : Shadow Monitoring
  Observing --> Idle : Cooldown Passed
  Observing --> Escalated : Repeated Signals

  HighRisk --> Restricted : Soft Enforcement
  Restricted --> ReviewQueue : Manual Review
  Restricted --> Idle : Risk Decay

  CriticalRisk --> Enforced : Hard Enforcement
  Enforced --> ReviewQueue : Evidence Captured

  ReviewQueue --> Approved : Staff Approve
  ReviewQueue --> Rejected : False Positive

  Approved --> PolicyUpdate : Rule Update
  Rejected --> ModelAdjustment : Calibration

  PolicyUpdate --> Idle
  ModelAdjustment --> Idle
