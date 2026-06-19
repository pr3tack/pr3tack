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

### PT03 — Execution

| ID | Name | Response Priority |
|---|---|---|
| [PT03.001](./PT03-execution/PT03.001-bios-config-trigger-payloads.md) | BIOS Config Trigger Payloads | Low |
| [PT03.002](./PT03-execution/PT03.002-peripheral-firmware-stager.md) | Peripheral Firmware Stager | Medium |

### PT04 — Persistence

| ID | Name | Response Priority |
|---|---|---|
| [PT04.001](./PT04-persistence/PT04.001-abuse-of-windows-atom-tables.md) | Abuse of Windows Atom Tables | High |
| [PT04.002](./PT04-persistence/PT04.002-hidden-service-registration.md) | Hidden Service Registration | Medium |

### PT05 — Privilege Escalation

| ID | Name | Response Priority |
|---|---|---|
| [PT05.001](./PT05-privilege-escalation/PT05.001-exploit-virtual-device-drivers.md) | Exploit Virtual Device Drivers (VDDs) | Medium |
| [PT05.002](./PT05-privilege-escalation/PT05.002-credential-store-forging.md) | Credential Store Forging | Medium |

### PT07 — Defense Evasion

| ID | Name | Response Priority |
|---|---|---|
| [PT07.001](./PT07-defense-evasion/PT07.001-cloud-metadata-api-overloading.md) | Cloud Metadata API Overloading | Medium |
| [PT07.002](./PT07-defense-evasion/PT07.002-telemetry-tampering.md) | Telemetry Tampering | Medium |

### PT08 — Command & Control

| ID | Name | Response Priority |
|---|---|---|
| [PT08.001](./PT08-command-and-control/PT08.001-bluetooth-hid-covert-channels.md) | Bluetooth HID Covert Channels | Low |
| [PT08.002](./PT08-command-and-control/PT08.002-covert-dns-over-https-tunnels.md) | Covert DNS-over-HTTPS Tunnels | Medium |

### PT09 — Discovery

| ID | Name | Response Priority |
|---|---|---|
| [PT09.001](./PT09-discovery/PT09.001-browser-extension-enumeration-ipc.md) | Browser Extension Enumeration via IPC Abuse | Medium |
| [PT09.002](./PT09-discovery/PT09.002-identity-topology-mapping.md) | Identity Topology Mapping | Medium |

### PT10 — Collection

| ID | Name | Response Priority |
|---|---|---|
| [PT10.001](./PT10-collection/PT10.001-clipboard-history-service-abuse.md) | Abuse of Clipboard History Services | High |
| [PT10.002](./PT10-collection/PT10.002-credential-cache-scraping-accessibility-apis.md) | Credential Cache Scraping via Accessibility APIs | Medium |

### PT11 — Exfiltration

| ID | Name | Response Priority |
|---|---|---|
| [PT11.001](./PT11-exfiltration/PT11.001-screen-reader-api-data-leak.md) | Leveraging Screen Reader APIs for Data Leak | Medium |
| [PT11.002](./PT11-exfiltration/PT11.002-covert-cloud-storage-staging.md) | Covert Cloud Storage Staging | Medium |

### PT13 — Lateral Movement

| ID | Name | Response Priority |
|---|---|---|
| [PT13.001](./PT13-lateral-movement/PT13.001-software-update-supply-chain-piggybacking.md) | Software Update Supply Chain Piggybacking | Medium |
| [PT13.002](./PT13-lateral-movement/PT13.002-business-unit-policy-propagation.md) | Business-Unit Policy Propagation | Medium |

### PT14 — Pre-Positioning

| ID | Name | Response Priority |
|---|---|---|
| [PT14.001](./PT14-pre-positioning/PT14.001-oss-supply-chain-sleeper-commit.md) | OSS Supply-Chain Sleeper Commit | Medium |
| [PT14.002](./PT14-pre-positioning/PT14.002-anticipatory-brand-domain-squatting.md) | Anticipatory Brand/Domain Squatting | High |

### PT15 — Resilience Erosion

| ID | Name | Response Priority |
|---|---|---|
| [PT15.001](./PT15-resilience-erosion/PT15.001-backup-bit-rot-injection.md) | Backup Bit-Rot Injection | Medium |
| [PT15.002](./PT15-resilience-erosion/PT15.002-patch-fatigue-campaigns.md) | Patch-Fatigue Campaigns | Medium |

### PT16 — Governance Subversion

| ID | Name | Response Priority |
|---|---|---|
| [PT16.001](./PT16-governance-subversion/PT16.001-standards-comments-manipulation.md) | Standards/Comments Manipulation | Low |
| [PT16.002](./PT16-governance-subversion/PT16.002-procurement-account-establishment.md) | Procurement Account Establishment | Medium |

### PT17 — Cognitive Manipulation

| ID | Name | Response Priority |
|---|---|---|
| [PT17.001](./PT17-cognitive-manipulation/PT17.001-analyst-habituation-lures.md) | Analyst Habituation Lures | High |
| [PT17.002](./PT17-cognitive-manipulation/PT17.002-adversarial-log-crafting.md) | Adversarial Log Crafting | Medium |

### PT18 — Operational Tempo Manipulation

| ID | Name | Response Priority |
|---|---|---|
| [PT18.001](./PT18-operational-tempo-manipulation/PT18.001-holiday-travel-window-triggering.md) | Holiday/Travel Window Triggering | High |
| [PT18.002](./PT18-operational-tempo-manipulation/PT18.002-billing-cost-shock-forcing.md) | Billing/Cost Shock Forcing | Medium |

### PT19 — AI/ML Subversion

| ID | Name | Response Priority |
|---|---|---|
| [PT19.001](./PT19-ai-ml-subversion/PT19.001-training-data-seed-poisoning.md) | Training-Data Seed Poisoning | Medium |
| [PT19.002](./PT19-ai-ml-subversion/PT19.002-model-output-injection.md) | Model Output Injection | Medium |

### PT20 — Sociotechnical Pressure

| ID | Name | Response Priority |
|---|---|---|
| [PT20.001](./PT20-sociotechnical-pressure/PT20.001-investor-media-narrative-orchestration.md) | Investor/Media Narrative Orchestration | Low |
| [PT20.002](./PT20-sociotechnical-pressure/PT20.002-vendor-influence-campaigns.md) | Vendor-Influence Campaigns | Medium |

### PT21 — Digital Exhaust Manipulation

| ID | Name | Response Priority |
|---|---|---|
| [PT21.001](./PT21-digital-exhaust-manipulation/PT21.001-ioc-telco-feed-pollution.md) | IOC/Telco Feed Pollution | High |
| [PT21.002](./PT21-digital-exhaust-manipulation/PT21.002-telemetry-noise-flooding.md) | Telemetry Noise Flooding | Medium |

---

Use the template in `/templates/technique-template.md` to contribute.
