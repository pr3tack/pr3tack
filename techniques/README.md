# Techniques

This directory contains all PR3TACK techniques, organised by tactic.

Each technique represents:
- A plausible attack path
- Associated detections
- Mitigation strategies

---

## Technique Index

### PT01 — Reconnaissance

| ID | Name | Response Priority |
|---|---|---|
| [PT01.001](./PT01-reconnaissance/PT01.001-saas-tenant-footprinting.md) | SaaS Tenant Footprinting | Medium |
| [PT01.002](./PT01-reconnaissance/PT01.002-cspm-signature-leakage.md) | CSPM Signature Leakage | Medium |
| [PT01.003](./PT01-reconnaissance/PT01.003-saas-app-to-app-permission-mining.md) | SaaS App-to-App Permission Mining | High |
| [PT01.004](./PT01-reconnaissance/PT01.004-identity-role-squatting-prep.md) | Identity Role Squatting Prep | Critical |
| [PT01.005](./PT01-reconnaissance/PT01.005-vector-database-reconnaissance.md) | Vector Database Reconnaissance | High |

### PT02 — Resource Development

| ID | Name | Response Priority |
|---|---|---|
| [PT02.001](./PT02-resource-development/PT02.001-ai-generated-persona-synthesis.md) | AI-Generated Persona Synthesis | Medium |
| [PT02.002](./PT02-resource-development/PT02.002-automated-social-proofing.md) | Automated Social Proofing | Medium |
| [PT02.003](./PT02-resource-development/PT02.003-cloud-account-incubation.md) | Cloud Account Incubation | Medium |
| [PT02.004](./PT02-resource-development/PT02.004-llm-mirroring-local-jailbreak-prep.md) | LLM Mirroring & Local Jailbreak Prep | Critical |

### PT06 — Supply Chain Preparation

| ID | Name | Response Priority |
|---|---|---|
| [PT06.001](./PT06-supply-chain-preparation/PT06.001-dependency-confusion-probing.md) | Dependency Confusion Probing | Critical |

### PT12 — Unix Contextual Stealth

| ID | Name | Response Priority |
|---|---|---|
| [PT12.001](./PT12-unix-contextual-stealth/PT12.001-over-mounting-cloaking.md) | Over-Mounting Cloaking | High |
| [PT12.002](./PT12-unix-contextual-stealth/PT12.002-proc-environmental-archaeology.md) | /proc Environmental Archaeology | High |

---

Use the template in `/templates/technique-template.md` to contribute.
