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
sigma convert -t splunk detections/sigma/pr3tack-T1012.001-saas-tenant-footprinting.yml
```

### Convert to KQL (Microsoft Sentinel)
```bash
sigma convert -t kusto detections/sigma/pr3tack-T1012.001-saas-tenant-footprinting.yml
```

### Convert all PR3TACK rules
```bash
sigma convert -t splunk detections/sigma/pr3tack-*.yml
```

---

## Rule Index

| File | Technique | Tactic | Level |
|---|---|---|---|
| [pr3tack-T1012.001-saas-tenant-footprinting.yml](./pr3tack-T1012.001-saas-tenant-footprinting.yml) | T1012.001 SaaS Tenant Footprinting | TA01 | medium |
| [pr3tack-T1015.001-cspm-signature-leakage.yml](./pr3tack-T1015.001-cspm-signature-leakage.yml) | T1015.001 CSPM Signature Leakage | TA01 | medium |
| [pr3tack-T1016.001-saas-app-to-app-permission-mining.yml](./pr3tack-T1016.001-saas-app-to-app-permission-mining.yml) | T1016.001 SaaS App-to-App Permission Mining | TA01 | high |
| [pr3tack-T1018.001-identity-role-squatting-prep.yml](./pr3tack-T1018.001-identity-role-squatting-prep.yml) | T1018.001 Identity Role Squatting Prep | TA01 | high |
| [pr3tack-T1028.001-cloud-account-incubation.yml](./pr3tack-T1028.001-cloud-account-incubation.yml) | T1028.001 Cloud Account Incubation | TA02 | medium |
| [pr3tack-T1061.001-dependency-confusion-probing.yml](./pr3tack-T1061.001-dependency-confusion-probing.yml) | T1061.001 Dependency Confusion Probing | TA06 | critical |
| [pr3tack-T1103.001-llm-mirroring-jailbreak-prep.yml](./pr3tack-T1103.001-llm-mirroring-jailbreak-prep.yml) | T1103.001 LLM Mirroring & Local Jailbreak Prep | TA02 | high |
| [pr3tack-T1201.001-over-mounting-cloaking.yml](./pr3tack-T1201.001-over-mounting-cloaking.yml) | T1201.001 Over-Mounting Cloaking | TA12 | high |
| [pr3tack-T1202.001-proc-environmental-archaeology.yml](./pr3tack-T1202.001-proc-environmental-archaeology.yml) | T1202.001 /proc Environmental Archaeology | TA12 | high |

---

## Log Source Requirements

| Rule | Required Log Source |
|---|---|
| T1012.001 | Web server / WAF / SaaS access logs |
| T1015.001 | DNS query logs (internal recursive resolver or passive DNS) |
| T1016.001 | Google Workspace Admin audit logs / M365 CloudAppEvents |
| T1018.001 | AWS CloudTrail / GCP Audit Logs |
| T1028.001 | API Gateway / Proxy logs with cloud tenant metadata enrichment |
| T1061.001 | Artifactory / Nexus artefact proxy access logs |
| T1103.001 | LLM API gateway / application logs |
| T1201.001 | Linux auditd (`mount` syscall) / CrowdStrike Falcon / Wiz Runtime |
| T1202.001 | Linux auditd (`open`/`openat` on `/proc/*/environ`) / CrowdStrike Falcon |

---

## Notes

- All rules are `status: experimental` — validate and tune in your environment before production deployment
- Rules requiring **metadata enrichment** (T1028.001, T1015.001) need additional data pipeline configuration — see the linked markdown detection file for details
- Filter lists (approved OAuth apps, decommissioned role ARNs, known tenant IDs) **must be populated** with environment-specific values before deployment
- See `/detections/rules/` for the full markdown version of each rule with tuning notes, platform-specific queries, and validation procedures
