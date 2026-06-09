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
| [pr3tack-PT06.001-dependency-confusion-probing.yml](./pr3tack-PT06.001-dependency-confusion-probing.yml) | PT06.001 Dependency Confusion Probing | PT06 | critical |
| [pr3tack-PT02.004-llm-mirroring-jailbreak-prep.yml](./pr3tack-PT02.004-llm-mirroring-jailbreak-prep.yml) | PT02.004 LLM Mirroring & Local Jailbreak Prep | PT02 | high |
| [pr3tack-PT12.001-over-mounting-cloaking.yml](./pr3tack-PT12.001-over-mounting-cloaking.yml) | PT12.001 Over-Mounting Cloaking | PT12 | high |
| [pr3tack-PT12.002-proc-environmental-archaeology.yml](./pr3tack-PT12.002-proc-environmental-archaeology.yml) | PT12.002 /proc Environmental Archaeology | PT12 | high |

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
| PT06.001 | Artifactory / Nexus artefact proxy access logs |
| PT02.004 | LLM API gateway / application logs |
| PT12.001 | Linux auditd (`mount` syscall) / CrowdStrike Falcon / Wiz Runtime |
| PT12.002 | Linux auditd (`open`/`openat` on `/proc/*/environ`) / CrowdStrike Falcon |

---

## Notes

- All rules are `status: experimental` — validate and tune in your environment before production deployment
- Rules requiring **metadata enrichment** (PT02.003, PT01.002) need additional data pipeline configuration — see the linked markdown detection file for details
- Filter lists (approved OAuth apps, decommissioned role ARNs, known tenant IDs) **must be populated** with environment-specific values before deployment
- See `/detections/rules/` for the full markdown version of each rule with tuning notes, platform-specific queries, and validation procedures
