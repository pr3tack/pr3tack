# Detections

This directory contains detection strategies aligned to PR3TACK techniques.

---

## Structure

- `rules/` → SIEM / EDR style detections, SIGMA-based (full markdown with tuning notes)
- `sigma/` → standalone SIGMA `.yml` files for direct import into detection platforms
- `analytics/` → behavioural / statistical detections
- `hunting/` → hypothesis-driven threat hunting

---

## Philosophy

PR3TACK detections are:

- Proactive (built before widespread abuse)
- Behaviour-driven (not signature-only)
- Mapped to techniques

---

## Detection Index

### Rules — `rules/`

SIGMA-compatible, SIEM/EDR deployable detection rules.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [PT01.001](./rules/PT01.001-saas-tenant-footprinting.md) | SaaS Tenant Footprinting — Unauthenticated Endpoint Enumeration | PT01 | Medium |
| [PT01.002](./rules/PT01.002-cspm-signature-leakage.md) | CSPM Signature Leakage — Security Stack Fingerprinting via DNS/HTTP | PT01 | Medium |
| [PT01.003](./rules/PT01.003-saas-app-to-app-permission-mining.md) | High-Privilege OAuth Consent Grant to Third-Party Application | PT01 | High |
| [PT01.004](./rules/PT01.004-identity-role-squatting-prep.md) | Decommissioned IAM Role AssumeRole Attempt | PT01 | High |
| [PT01.005](./rules/PT01.005-vector-database-reconnaissance.md) | Vector DB Systematic Query Probing / Unauthenticated Access | PT01 | High |
| [PT02.003](./rules/PT02.003-cloud-account-incubation.md) | New Cloud Tenant with Anomalous Risk Signals | PT02 | Medium |
| [PT02.004](./rules/PT02.004-llm-mirroring-local-jailbreak-prep.md) | LLM Prompt Injection and Jailbreak Attempt | PT02 | Medium |
| [PT06.001](./rules/PT06.001-dependency-confusion-probing.md) | Public Registry Resolution of Internal Package Name | PT06 | High |
| [PT12.001](./rules/PT12.001-over-mounting-cloaking.md) | Anomalous tmpfs Mount Over Non-Standard Directory | PT12 | High |
| [PT12.002](./rules/PT12.002-proc-environmental-archaeology.md) | Cross-PID /proc/environ Access — Credential Harvesting | PT12 | High |

### Analytics — `analytics/`

Behavioural and statistical models for detecting adversary patterns that resist rule-based detection.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [PT02.001](./analytics/PT02.001-ai-generated-persona-synthesis.md) | Synthetic Identity Anomaly Scoring | PT02 | Medium |
| [PT02.002](./analytics/PT02.002-automated-social-proofing.md) | Coordinated Inauthentic Behaviour Detection | PT02 | Medium |
| [PT02.003](./analytics/PT02.003-cloud-account-incubation.md) | New Tenant Behavioural Transition Detection | PT02 | Medium |
| [PT02.004](./analytics/PT02.004-llm-mirroring-local-jailbreak-prep.md) | Prompt Injection Classifier Drift & Canary Token Replay | PT02 | Medium |
| [PT12.001](./analytics/PT12.001-over-mounting-cloaking.md) | Anomalous Mount Syscall Frequency Baseline Deviation | PT12 | Medium |
| [PT12.002](./analytics/PT12.002-proc-environmental-archaeology.md) | Cross-PID /proc/environ Read Pattern Anomaly | PT12 | Medium |

### Hunting — `hunting/`

Hypothesis-driven threat hunting queries for proactive adversary discovery.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [PT01.001](./hunting/PT01.001-saas-tenant-footprinting.md) | SaaS Tenant Footprinting — Passive Enumeration Signal Correlation | PT01 | Medium |
| [PT01.002](./hunting/PT01.002-cspm-signature-leakage.md) | CSPM Signature Leakage — Cloud Audit Log Enumeration Cadence | PT01 | Medium |
| [PT01.003](./hunting/PT01.003-saas-app-to-app-permission-mining.md) | SaaS App-to-App Permission Mining — OAuth Scope Enumeration | PT01 | Medium |
| [PT01.004](./hunting/PT01.004-identity-role-squatting-prep.md) | Identity Role Squatting Prep — Dormant IAM Namespace Registration | PT01 | Medium |
| [PT01.005](./hunting/PT01.005-vector-database-reconnaissance.md) | Embedding Space Probing — Vector DB Reconnaissance Hunt | PT01 | Medium |
| [PT02.001](./hunting/PT02.001-ai-generated-persona-synthesis.md) | AI-Generated Persona Synthesis — Synthetic Identity Signal Correlation | PT02 | Low–Medium |
| [PT02.003](./hunting/PT02.003-cloud-account-incubation.md) | Aged Tenant Infrastructure Discovery | PT02 | Medium |
| [PT02.004](./hunting/PT02.004-llm-mirroring-local-jailbreak-prep.md) | LLM Mirroring — Offline Rehearsal Signal Detection | PT02 | Medium |
| [PT06.001](./hunting/PT06.001-dependency-confusion-probing.md) | Dependency Confusion Probing — Package Namespace Enumeration | PT06 | Medium |

---

## Coverage Map

| Technique | Rule | Analytic | Hunt | Sigma |
|---|:---:|:---:|:---:|:---:|
| PT01.001 SaaS Tenant Footprinting | ✅ | | ✅ | ✅ |
| PT01.002 CSPM Signature Leakage | ✅ | | ✅ | ✅ |
| PT01.003 SaaS App-to-App Permission Mining | ✅ | | ✅ | ✅ |
| PT01.004 Identity Role Squatting Prep | ✅ | | ✅ | ✅ |
| PT01.005 Vector Database Reconnaissance | ✅ | | ✅ | ✅ |
| PT02.001 AI-Generated Persona Synthesis | | ✅ | ✅ | ✅ |
| PT02.002 Automated Social Proofing | | ✅ | | |
| PT02.003 Cloud Account Incubation | ✅ | ✅ | ✅ | ✅ |
| PT02.004 LLM Mirroring & Local Jailbreak Prep | ✅ | ✅ | ✅ | ✅ |
| PT03.001 BIOS Config Trigger Payloads | ✅ | | | |
| PT03.002 Peripheral Firmware Stager | ✅ | | | ✅ |
| PT04.001 Abuse of Windows Atom Tables | ✅ | | | |
| PT04.002 Hidden Service Registration | ✅ | | | ✅ |
| PT05.001 Exploit Virtual Device Drivers | | | ✅ | |
| PT05.002 Credential Store Forging | | ✅ | | |
| PT06.001 Dependency Confusion Probing | ✅ | | ✅ | ✅ |
| PT07.001 Cloud Metadata API Overloading | ✅ | | | |
| PT07.002 Telemetry Tampering | ✅ | | | ✅ |
| PT08.001 Bluetooth HID Covert Channels | | | ✅ | |
| PT08.002 Covert DNS-over-HTTPS Tunnels | ✅ | | | ✅ |
| PT09.001 Browser Extension Enumeration via IPC | | | ✅ | |
| PT09.002 Identity Topology Mapping | ✅ | | | |
| PT10.001 Abuse of Clipboard History Services | ✅ | | | ✅ |
| PT10.002 Credential Cache Scraping via Accessibility | ✅ | | | |
| PT11.001 Screen Reader API Data Leak | | | ✅ | |
| PT11.002 Covert Cloud Storage Staging | ✅ | | | ✅ |
| PT12.001 Over-Mounting Cloaking | ✅ | ✅ | | ✅ |
| PT12.002 /proc Environmental Archaeology | ✅ | ✅ | | ✅ |
| PT13.001 Software Update Supply Chain Piggybacking | | ✅ | | |
| PT13.002 Business-Unit Policy Propagation | | | ✅ | |
| PT14.001 OSS Supply-Chain Sleeper Commit | | | ✅ | |
| PT14.002 Anticipatory Brand/Domain Squatting | ✅ | | | ✅ |
| PT15.001 Backup Bit-Rot Injection | | ✅ | | |
| PT15.002 Patch-Fatigue Campaigns | | ✅ | | |
| PT16.001 Standards/Comments Manipulation | — | — | — | — |
| PT16.002 Procurement Account Establishment | | | ✅ | |
| PT17.001 Analyst Habituation Lures | ✅ | | | |
| PT17.002 Adversarial Log Crafting | ✅ | | | ✅ |
| PT18.001 Holiday/Travel Window Triggering | ✅ | | | ✅ |
| PT18.002 Billing/Cost Shock Forcing | | ✅ | | |
| PT19.001 Training-Data Seed Poisoning | | ✅ | | |
| PT19.002 Model Output Injection | | ✅ | | |
| PT20.001 Investor/Media Narrative Orchestration | | | ✅ | |
| PT20.002 Vendor-Influence Campaigns | | | ✅ | |
| PT21.001 IOC/Telco Feed Pollution | | ✅ | | |
| PT21.002 Telemetry Noise Flooding | ✅ | | | ✅ |

---

Use `/templates/detection-template.md` to contribute.
