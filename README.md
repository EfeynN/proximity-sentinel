# Proximity Sentinel

Proximity Sentinel is a high-performance anti-cheat and security suite developed under Proximity Systems.

It focuses on detecting unfair gameplay, abnormal behavior patterns, and unauthorized client modifications through real-time analysis and modular security layers.

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
---

## Risk Score Lifecycle (Flow)

```mermaid
flowchart TB
  A[Player Telemetry] --> B[Signal Collection]
  B --> C[Signal Normalization]
  C --> D[Feature Extraction]

  D --> E1[Behavior Signals]
  D --> E2[Integrity Signals]
  D --> E3[Network Signals]
  D --> E4[Pattern History]

  E1 --> F[Risk Scoring Engine]
  E2 --> F
  E3 --> F
  E4 --> F

  F --> G[Confidence Weighting]
  G --> H[False Positive Guard]

  H --> I{Risk Level}
  I -->|Low| J[Log Only]
  I -->|Medium| K[Shadow Monitoring]
  I -->|High| L[Soft Enforcement]
  I -->|Critical| M[Hard Enforcement]

  J --> N[(Player Profile)]
  K --> N
  L --> N
  M --> N
