# Techniques

This directory contains all PR3TACK techniques, organised by tactic.

Each technique represents:
- A plausible attack path
- Associated detections
- Mitigation strategies

---

## Technique Index

### TA01 — Reconnaissance

| ID | Name | Response Priority |
|---|---|---|
| [T1012.001](./TA01-reconnaissance/T1012.001-saas-tenant-footprinting.md) | SaaS Tenant Footprinting | Medium |
| [T1015.001](./TA01-reconnaissance/T1015.001-cspm-signature-leakage.md) | CSPM Signature Leakage | Medium |
| [T1016.001](./TA01-reconnaissance/T1016.001-saas-app-to-app-permission-mining.md) | SaaS App-to-App Permission Mining | High |
| [T1018.001](./TA01-reconnaissance/T1018.001-identity-role-squatting-prep.md) | Identity Role Squatting Prep | Critical |
| [T1101.001](./TA01-reconnaissance/T1101.001-vector-database-reconnaissance.md) | Vector Database Reconnaissance | High |

### TA02 — Resource Development

| ID | Name | Response Priority |
|---|---|---|
| [T1025.001](./TA02-resource-development/T1025.001-ai-generated-persona-synthesis.md) | AI-Generated Persona Synthesis | Medium |
| [T1025.002](./TA02-resource-development/T1025.002-automated-social-proofing.md) | Automated Social Proofing | Medium |
| [T1028.001](./TA02-resource-development/T1028.001-cloud-account-incubation.md) | Cloud Account Incubation | Medium |
| [T1103.001](./TA02-resource-development/T1103.001-llm-mirroring-local-jailbreak-prep.md) | LLM Mirroring & Local Jailbreak Prep | Critical |

### TA06 — Supply Chain Preparation

| ID | Name | Response Priority |
|---|---|---|
| [T1061.001](./TA06-supply-chain-preparation/T1061.001-dependency-confusion-probing.md) | Dependency Confusion Probing | Critical |

### TA12 — Unix Contextual Stealth

| ID | Name | Response Priority |
|---|---|---|
| [T1201.001](./TA12-unix-contextual-stealth/T1201.001-over-mounting-cloaking.md) | Over-Mounting Cloaking | High |
| [T1202.001](./TA12-unix-contextual-stealth/T1202.001-proc-environmental-archaeology.md) | /proc Environmental Archaeology | High |

---

Use the template in `/templates/technique-template.md` to contribute.
