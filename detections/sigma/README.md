# PR3TACK — SIGMA Rules

Standalone SIGMA-compatible detection rules for all PR3TACK techniques.

These files can be used directly with:
- **[sigma-cli](https://github.com/SigmaHQ/sigma-cli)** to convert to Splunk SPL, KQL, Elastic DSL, and more
- **[pySigma](https://github.com/SigmaHQ/pySigma)** for programmatic pipeline integration
- **Panther, Elastic SIEM, Microsoft Sentinel, Splunk ES** via native SIGMA import

---

## Usage

### Convert to Splunk SPL
```bash
sigma convert -t splunk detections/sigma/pr3tack-PT01.001-saas-tenant-footprinting.yml
```

### Convert to KQL (Microsoft Sentinel)
```bash
sigma convert -t kusto detections/sigma/pr3tack-PT01.001-saas-tenant-footprinting.yml
```

### Convert all PR3TACK rules
```bash
sigma convert -t splunk detections/sigma/pr3tack-*.yml
```

---

## Rule Index

| File | Technique | Tactic | Level |
|---|---|---|---|
| [pr3tack-PT01.001-saas-tenant-footprinting.yml](./pr3tack-PT01.001-saas-tenant-footprinting.yml) | PT01.001 SaaS Tenant Footprinting | PT01 | medium |
| [pr3tack-PT01.002-cspm-signature-leakage.yml](./pr3tack-PT01.002-cspm-signature-leakage.yml) | PT01.002 CSPM Signature Leakage | PT01 | medium |
| [pr3tack-PT01.003-saas-app-to-app-permission-mining.yml](./pr3tack-PT01.003-saas-app-to-app-permission-mining.yml) | PT01.003 SaaS App-to-App Permission Mining | PT01 | high |
| [pr3tack-PT01.004-identity-role-squatting-prep.yml](./pr3tack-PT01.004-identity-role-squatting-prep.yml) | PT01.004 Identity Role Squatting Prep | PT01 | high |
| [pr3tack-PT01.005-vector-database-reconnaissance.yml](./pr3tack-PT01.005-vector-database-reconnaissance.yml) | PT01.005 Vector Database Reconnaissance | PT01 | high / critical |
| [pr3tack-PT02.001-ai-generated-persona-synthesis.yml](./pr3tack-PT02.001-ai-generated-persona-synthesis.yml) | PT02.001 AI-Generated Persona Synthesis | PT02 | medium / high |
| [pr3tack-PT02.003-cloud-account-incubation.yml](./pr3tack-PT02.003-cloud-account-incubation.yml) | PT02.003 Cloud Account Incubation (activation spike) | PT02 | medium |
| [pr3tack-PT02.003-cloud-account-incubation-new-tenant.yml](./pr3tack-PT02.003-cloud-account-incubation-new-tenant.yml) | PT02.003 Cloud Account Incubation (new tenant signals) | PT02 | medium / high |
| [pr3tack-PT02.004-llm-mirroring-jailbreak-prep.yml](./pr3tack-PT02.004-llm-mirroring-jailbreak-prep.yml) | PT02.004 LLM Mirroring & Local Jailbreak Prep | PT02 | high |
| [pr3tack-PT03.001-bios-config-trigger-payloads.yml](./pr3tack-PT03.001-bios-config-trigger-payloads.yml) | PT03.001 BIOS Config Trigger Payloads | PT03 | critical |
| [pr3tack-PT03.002-peripheral-firmware-stager.yml](./pr3tack-PT03.002-peripheral-firmware-stager.yml) | PT03.002 Peripheral Firmware Stager | PT03 | high |
| [pr3tack-PT04.001-windows-atom-table-abuse.yml](./pr3tack-PT04.001-windows-atom-table-abuse.yml) | PT04.001 Abuse of Windows Atom Tables | PT04 | high |
| [pr3tack-PT04.002-hidden-service-registration.yml](./pr3tack-PT04.002-hidden-service-registration.yml) | PT04.002 Hidden Service Registration | PT04 | high |
| [pr3tack-PT05.001-virtual-device-driver-exploitation.yml](./pr3tack-PT05.001-virtual-device-driver-exploitation.yml) | PT05.001 Exploit Virtual Device Drivers | PT05 | critical |
| [pr3tack-PT05.002-credential-store-forging.yml](./pr3tack-PT05.002-credential-store-forging.yml) | PT05.002 Credential Store Forging | PT05 | high |
| [pr3tack-PT06.001-dependency-confusion-probing.yml](./pr3tack-PT06.001-dependency-confusion-probing.yml) | PT06.001 Dependency Confusion Probing | PT06 | critical |
| [pr3tack-PT07.001-cloud-metadata-api-overloading.yml](./pr3tack-PT07.001-cloud-metadata-api-overloading.yml) | PT07.001 Cloud Metadata API Overloading | PT07 | high |
| [pr3tack-PT07.002-telemetry-tampering.yml](./pr3tack-PT07.002-telemetry-tampering.yml) | PT07.002 Telemetry Tampering | PT07 | critical |
| [pr3tack-PT08.001-bluetooth-hid-covert-channels.yml](./pr3tack-PT08.001-bluetooth-hid-covert-channels.yml) | PT08.001 Bluetooth HID Covert Channels | PT08 | medium |
| [pr3tack-PT08.002-covert-doh-tunnels.yml](./pr3tack-PT08.002-covert-doh-tunnels.yml) | PT08.002 Covert DNS-over-HTTPS Tunnels | PT08 | medium |
| [pr3tack-PT09.001-browser-extension-enumeration-ipc.yml](./pr3tack-PT09.001-browser-extension-enumeration-ipc.yml) | PT09.001 Browser Extension Enumeration via IPC | PT09 | medium |
| [pr3tack-PT09.002-identity-topology-mapping.yml](./pr3tack-PT09.002-identity-topology-mapping.yml) | PT09.002 Identity Topology Mapping | PT09 | high |
| [pr3tack-PT10.001-clipboard-history-abuse.yml](./pr3tack-PT10.001-clipboard-history-abuse.yml) | PT10.001 Abuse of Clipboard History Services | PT10 | high |
| [pr3tack-PT10.002-accessibility-api-credential-scraping.yml](./pr3tack-PT10.002-accessibility-api-credential-scraping.yml) | PT10.002 Credential Cache Scraping via Accessibility APIs | PT10 | high |
| [pr3tack-PT11.001-screen-reader-api-data-leak.yml](./pr3tack-PT11.001-screen-reader-api-data-leak.yml) | PT11.001 Screen Reader API Data Leak | PT11 | high |
| [pr3tack-PT11.002-covert-cloud-storage-staging.yml](./pr3tack-PT11.002-covert-cloud-storage-staging.yml) | PT11.002 Covert Cloud Storage Staging | PT11 | medium |
| [pr3tack-PT12.001-over-mounting-cloaking.yml](./pr3tack-PT12.001-over-mounting-cloaking.yml) | PT12.001 Over-Mounting Cloaking | PT12 | high |
| [pr3tack-PT12.002-proc-environmental-archaeology.yml](./pr3tack-PT12.002-proc-environmental-archaeology.yml) | PT12.002 /proc Environmental Archaeology | PT12 | high |
| [pr3tack-PT13.001-software-update-supply-chain-piggybacking.yml](./pr3tack-PT13.001-software-update-supply-chain-piggybacking.yml) | PT13.001 Software Update Supply Chain Piggybacking | PT13 | high |
| [pr3tack-PT13.002-business-unit-policy-propagation.yml](./pr3tack-PT13.002-business-unit-policy-propagation.yml) | PT13.002 Business-Unit Policy Propagation | PT13 | medium |
| [pr3tack-PT14.001-oss-supply-chain-sleeper-commit.yml](./pr3tack-PT14.001-oss-supply-chain-sleeper-commit.yml) | PT14.001 OSS Supply-Chain Sleeper Commit | PT14 | high |
| [pr3tack-PT14.002-anticipatory-domain-squatting.yml](./pr3tack-PT14.002-anticipatory-domain-squatting.yml) | PT14.002 Anticipatory Brand/Domain Squatting | PT14 | critical |
| [pr3tack-PT15.001-backup-bit-rot-injection.yml](./pr3tack-PT15.001-backup-bit-rot-injection.yml) | PT15.001 Backup Bit-Rot Injection | PT15 | critical |
| [pr3tack-PT15.002-patch-fatigue-campaigns.yml](./pr3tack-PT15.002-patch-fatigue-campaigns.yml) | PT15.002 Patch-Fatigue Campaigns | PT15 | critical |
| [pr3tack-PT16.002-procurement-account-establishment.yml](./pr3tack-PT16.002-procurement-account-establishment.yml) | PT16.002 Procurement Account Establishment | PT16 | critical |
| [pr3tack-PT17.001-analyst-habituation-lures.yml](./pr3tack-PT17.001-analyst-habituation-lures.yml) | PT17.001 Analyst Habituation Lures | PT17 | medium |
| [pr3tack-PT17.002-adversarial-log-crafting.yml](./pr3tack-PT17.002-adversarial-log-crafting.yml) | PT17.002 Adversarial Log Crafting | PT17 | high |
| [pr3tack-PT18.001-holiday-window-triggering.yml](./pr3tack-PT18.001-holiday-window-triggering.yml) | PT18.001 Holiday/Travel Window Triggering | PT18 | high |
| [pr3tack-PT18.002-billing-cost-shock-forcing.yml](./pr3tack-PT18.002-billing-cost-shock-forcing.yml) | PT18.002 Billing/Cost Shock Forcing | PT18 | high |
| [pr3tack-PT19.001-training-data-seed-poisoning.yml](./pr3tack-PT19.001-training-data-seed-poisoning.yml) | PT19.001 Training-Data Seed Poisoning | PT19 | critical |
| [pr3tack-PT19.002-model-output-injection.yml](./pr3tack-PT19.002-model-output-injection.yml) | PT19.002 Model Output Injection | PT19 | high |
| [pr3tack-PT20.001-investor-media-narrative-orchestration.yml](./pr3tack-PT20.001-investor-media-narrative-orchestration.yml) | PT20.001 Investor/Media Narrative Orchestration | PT20 | low |
| [pr3tack-PT20.002-vendor-influence-campaigns.yml](./pr3tack-PT20.002-vendor-influence-campaigns.yml) | PT20.002 Vendor-Influence Campaigns | PT20 | high |
| [pr3tack-PT21.001-ioc-feed-pollution.yml](./pr3tack-PT21.001-ioc-feed-pollution.yml) | PT21.001 IOC/Telco Feed Pollution | PT21 | critical |
| [pr3tack-PT21.002-telemetry-noise-flooding.yml](./pr3tack-PT21.002-telemetry-noise-flooding.yml) | PT21.002 Telemetry Noise Flooding | PT21 | high |

---

## Log Source Requirements

| Rule | Required Log Source |
|---|---|
| PT01.001 | Web server / WAF / SaaS access logs |
| PT01.002 | DNS query logs (internal recursive resolver or passive DNS) |
| PT01.003 | Google Workspace Admin audit logs / M365 CloudAppEvents |
| PT01.004 | AWS CloudTrail / GCP Audit Logs |
| PT01.005 | Vector DB access logs / API gateway logs (Qdrant, Weaviate, pgvector) |
| PT02.001 | Identity governance / HR system event logs (requires scoring model integration) |
| PT02.003 | API Gateway / Proxy logs with cloud tenant metadata enrichment |
| PT02.004 | LLM API gateway / application logs |
| PT03.001 | Firmware integrity platform (Eclypsium, HP Sure Start) / TPM PCR logs |
| PT03.002 | Windows USB device driver events (Event ID 2003/2004) / EDR |
| PT04.001 | ETW-based API call monitoring / EDR (GlobalAddAtom) |
| PT04.002 | Sysmon Event ID 19/20/21 (WMI) / Windows Event ID 7045 |
| PT05.001 | Sysmon Event ID 6 (driver load) / LOLDrivers blocklist feed |
| PT05.002 | Windows Security Event Log (Event ID 4769) / EDR credential API monitoring |
| PT06.001 | Artifactory / Nexus artefact proxy access logs |
| PT07.001 | Host network connection logs / iptables / cloud instance logs |
| PT07.002 | Sysmon Event ID 11 (FileCreate) / FIM on agent config paths |
| PT08.001 | Bluetooth management logs / MDM device pairing events |
| PT08.002 | Network flow logs / proxy logs (port 443 to DoH provider IPs) |
| PT09.001 | Sysmon Event ID 11/15 (file access) / EDR file access telemetry |
| PT09.002 | Okta System Log / Entra ID audit logs / OIDC metadata endpoint access logs |
| PT10.001 | Sysmon Event ID 11 / FIM on Windows Clipboard History paths |
| PT10.002 | ETW UI Automation API monitoring / macOS TCC database events |
| PT11.001 | ETW UI Automation API monitoring / EDR process access telemetry |
| PT11.002 | AWS CloudTrail (PutBucketAcl, PutObject, GetObject) / GCP Audit Logs |
| PT12.001 | Linux auditd (`mount` syscall) / CrowdStrike Falcon / Wiz Runtime |
| PT12.002 | Linux auditd (`open`/`openat` on `/proc/*/environ`) / CrowdStrike Falcon |
| PT13.001 | Software inventory platform / EDR post-update network connection logs |
| PT13.002 | Cloud IAM access logs / SaaS audit logs with business unit enrichment |
| PT14.001 | EDR network connection monitoring / CI/CD build anomaly logs |
| PT14.002 | Certificate transparency log monitoring / email gateway with domain similarity scoring |
| PT15.001 | FIM on backup catalogue paths / backup platform modification event logs |
| PT15.002 | Vulnerability management platform / CISA KEV JSON feed integration |
| PT16.002 | Procurement system audit logs / vendor management platform |
| PT17.001 | SOAR platform alert closure statistics / SIEM alert management metrics |
| PT17.002 | SIEM ingestion pipeline metrics / Sysmon process creation (anomalous field lengths) |
| PT18.001 | Windows Security Event Log (Event ID 4624/4672) / IAM audit logs |
| PT18.002 | AWS CloudTrail (RunInstances) / cloud billing and cost management APIs |
| PT19.001 | FIM on ML dataset storage paths / ML platform data pipeline audit logs |
| PT19.002 | ML API gateway inference logs with semantic similarity scoring |
| PT20.001 | Media monitoring platform with sentiment analysis and account age metadata |
| PT20.002 | SaaS integration platform scope access logs / procurement evaluation records |
| PT21.001 | Threat intelligence platform with own-asset monitoring capability |
| PT21.002 | SIEM ingestion pipeline metrics (events/hour per host) |

---

## Notes

- All rules are `status: experimental` — validate and tune in your environment before production deployment
- Rules requiring **metadata enrichment** (PT02.003, PT01.002) need additional data pipeline configuration — see the linked markdown detection file for details
- Filter lists (approved OAuth apps, decommissioned role ARNs, known tenant IDs) **must be populated** with environment-specific values before deployment
- See `/detections/rules/` for the full markdown version of each rule with tuning notes, platform-specific queries, and validation procedures
