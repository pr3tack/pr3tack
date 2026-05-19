# Detections

This directory contains detection strategies aligned to PR3TACK techniques.

---

## Structure

- `rules/` → SIEM / EDR style detections, SIGMA-based
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
| [T1012.001](./rules/T1012.001-saas-tenant-footprinting.md) | SaaS Tenant Footprinting — Unauthenticated Endpoint Enumeration | TA01 | Medium |
| [T1015.001](./rules/T1015.001-cspm-signature-leakage.md) | CSPM Signature Leakage — Security Stack Fingerprinting via DNS/HTTP | TA01 | Medium |
| [T1016.001](./rules/T1016.001-saas-app-to-app-permission-mining.md) | High-Privilege OAuth Consent Grant to Third-Party Application | TA01 | High |
| [T1018.001](./rules/T1018.001-identity-role-squatting-prep.md) | Decommissioned IAM Role AssumeRole Attempt | TA01 | High |
| [T1061.001](./rules/T1061.001-dependency-confusion-probing.md) | Public Registry Resolution of Internal Package Name | TA06 | High |
| [T1103.001](./rules/T1103.001-llm-mirroring-local-jailbreak-prep.md) | LLM Prompt Injection and Jailbreak Attempt | TA02 | Medium |
| [T1201.001](./rules/T1201.001-over-mounting-cloaking.md) | Anomalous tmpfs Mount Over Non-Standard Directory | TA12 | High |
| [T1202.001](./rules/T1202.001-proc-environmental-archaeology.md) | Cross-PID /proc/environ Access — Credential Harvesting | TA12 | High |

### Analytics — `analytics/`

Behavioural and statistical models for detecting adversary patterns that resist rule-based detection.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [T1025.001](./analytics/T1025.001-ai-generated-persona-synthesis.md) | Synthetic Identity Anomaly Scoring | TA02 | Medium |
| [T1025.002](./analytics/T1025.002-automated-social-proofing.md) | Coordinated Inauthentic Behaviour Detection | TA02 | Medium |
| [T1028.001](./analytics/T1028.001-cloud-account-incubation.md) | New Tenant Behavioural Transition Detection | TA02 | Medium |

### Hunting — `hunting/`

Hypothesis-driven threat hunting queries for proactive adversary discovery.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [T1101.001](./hunting/T1101.001-vector-database-reconnaissance.md) | Embedding Space Probing — Vector DB Reconnaissance Hunt | TA01 | Medium |
| [T1028.001](./hunting/T1028.001-cloud-account-incubation.md) | Aged Tenant Infrastructure Discovery | TA02 | Medium |

---

## Coverage Map

| Technique | Rule | Analytic | Hunt |
|---|---|---|---|
| T1012.001 SaaS Tenant Footprinting | ✅ | | |
| T1015.001 CSPM Signature Leakage | ✅ | | |
| T1016.001 SaaS App-to-App Permission Mining | ✅ | | |
| T1018.001 Identity Role Squatting Prep | ✅ | | |
| T1101.001 Vector Database Reconnaissance | | | ✅ |
| T1025.001 AI-Generated Persona Synthesis | | ✅ | |
| T1025.002 Automated Social Proofing | | ✅ | |
| T1028.001 Cloud Account Incubation | | ✅ | ✅ |
| T1061.001 Dependency Confusion Probing | ✅ | | |
| T1103.001 LLM Mirroring & Local Jailbreak Prep | ✅ | | |
| T1201.001 Over-Mounting Cloaking | ✅ | | |
| T1202.001 /proc Environmental Archaeology | ✅ | | |

---

Use `/templates/detection-template.md` to contribute.
