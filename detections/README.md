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
| [PT06.001](./rules/PT06.001-dependency-confusion-probing.md) | Public Registry Resolution of Internal Package Name | PT06 | High |
| [PT02.004](./rules/PT02.004-llm-mirroring-local-jailbreak-prep.md) | LLM Prompt Injection and Jailbreak Attempt | PT02 | Medium |
| [PT12.001](./rules/PT12.001-over-mounting-cloaking.md) | Anomalous tmpfs Mount Over Non-Standard Directory | PT12 | High |
| [PT12.002](./rules/PT12.002-proc-environmental-archaeology.md) | Cross-PID /proc/environ Access — Credential Harvesting | PT12 | High |

### Analytics — `analytics/`

Behavioural and statistical models for detecting adversary patterns that resist rule-based detection.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [PT02.001](./analytics/PT02.001-ai-generated-persona-synthesis.md) | Synthetic Identity Anomaly Scoring | PT02 | Medium |
| [PT02.002](./analytics/PT02.002-automated-social-proofing.md) | Coordinated Inauthentic Behaviour Detection | PT02 | Medium |
| [PT02.003](./analytics/PT02.003-cloud-account-incubation.md) | New Tenant Behavioural Transition Detection | PT02 | Medium |

### Hunting — `hunting/`

Hypothesis-driven threat hunting queries for proactive adversary discovery.

| Technique | Name | Tactic | Confidence |
|---|---|---|---|
| [PT01.005](./hunting/PT01.005-vector-database-reconnaissance.md) | Embedding Space Probing — Vector DB Reconnaissance Hunt | PT01 | Medium |
| [PT02.003](./hunting/PT02.003-cloud-account-incubation.md) | Aged Tenant Infrastructure Discovery | PT02 | Medium |

---

## Coverage Map

| Technique | Rule | Analytic | Hunt |
|---|---|---|---|
| PT01.001 SaaS Tenant Footprinting | ✅ | | |
| PT01.002 CSPM Signature Leakage | ✅ | | |
| PT01.003 SaaS App-to-App Permission Mining | ✅ | | |
| PT01.004 Identity Role Squatting Prep | ✅ | | |
| PT01.005 Vector Database Reconnaissance | | | ✅ |
| PT02.001 AI-Generated Persona Synthesis | | ✅ | |
| PT02.002 Automated Social Proofing | | ✅ | |
| PT02.003 Cloud Account Incubation | | ✅ | ✅ |
| PT06.001 Dependency Confusion Probing | ✅ | | |
| PT02.004 LLM Mirroring & Local Jailbreak Prep | ✅ | | |
| PT12.001 Over-Mounting Cloaking | ✅ | | |
| PT12.002 /proc Environmental Archaeology | ✅ | | |

---

Use `/templates/detection-template.md` to contribute.
