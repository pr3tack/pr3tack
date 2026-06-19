# PR3TACK Roadmap

---

## Phase 1 — Foundation `v0.1`

> Establishing the core framework, seed technique set, and detection library ahead of the FIRST Conference 2026 launch.

- [x] Core technique structure and templates
- [x] Seed matrix — 11 techniques across 4 tactics (PT01, PT02, PT06, PT12)
- [x] Detection library — rules, analytics, and hunting queries for all techniques
- [x] SIGMA-compatible standalone detection rules (`detections/sigma/`)
- [x] ATT&CK Navigator layer (`navigator/pr3tack-layer.json`)
- [x] Contribution guidelines (`CONTRIBUTING.md`)
- [ ] Community onboarding — Expression of Interest process live
- [ ] Official release — **FIRST Conference 2026, Denver, Colorado**

---

## Phase 2 — Expansion `v0.2`

> Growing the technique set and detection library through community contributions.

- [x] Technique coverage expansion — **46 techniques across 21 tactics**
- [x] Additional tactics: PT03 Execution, PT04 Persistence, PT05 Privilege Escalation, PT07 Defense Evasion, PT08 C2, PT09 Discovery, PT10 Collection, PT11 Exfiltration, PT13 Lateral Movement, PT14 Pre-Positioning, PT15 Resilience Erosion, PT16 Governance Subversion, PT17 Cognitive Manipulation, PT18 Operational Tempo Manipulation, PT19 AI/ML Subversion, PT20 Sociotechnical Pressure, PT21 Digital Exhaust Manipulation
- [x] Detection engineering library growth — **44 SIGMA rules, 25 detection rules, 14 analytics, 18 hunting docs**
- [x] Hunting playbook expansion — structured hunt queries for all 46 techniques
- [x] PT naming convention — independent ID scheme decoupled from MITRE ATT&CK (`PT<NN>.<NNN>`)
- [ ] Community working groups — tactic-specific contributor groups
- [ ] Peer review pipeline — structured technique review process

---

## Phase 3 — Operationalisation `v0.3`

> Making PR3TACK directly usable in security operations tooling.

- [ ] Navigator — hosted interactive matrix at navigator.pr3tack.org
- [ ] Detection-as-code examples — Terraform/IaC for deploying PR3TACK detections
- [ ] SIEM integration packages — Splunk ES, Microsoft Sentinel, Elastic SIEM
- [ ] API — machine-readable technique and detection export
- [ ] STIX/TAXII export — for threat intel platform integration
- [ ] CI/CD integration — GitHub Actions for SIGMA rule validation on PRs

---

## Phase 4 — Maturity `v1.0`

> Establishing PR3TACK as a recognised, cited framework in the security community.

- [ ] Industry adoption — integrations with major SIEM and TIP vendors
- [ ] Research publications — peer-reviewed analysis of PR3TACK technique coverage
- [ ] Conference integrations — workshops and exercises at FIRST, DEF CON, RSA
- [ ] Training material — detection engineering courses aligned to PR3TACK
- [ ] Versioned releases — stable, citable framework versions with changelogs
- [ ] Attribution model — recognising community contributors formally

---

## Technique Coverage Target

| Tactic | v0.1 | v0.2 (current) | v1.0 target |
|---|---|---|---|
| PT01 Reconnaissance | 5 | 5 | 15 |
| PT02 Resource Development | 4 | 4 | 12 |
| PT03 Execution | 0 | 2 | 8 |
| PT04 Persistence | 0 | 2 | 8 |
| PT05 Privilege Escalation | 0 | 2 | 8 |
| PT06 Supply Chain Preparation | 1 | 1 | 8 |
| PT07 Defense Evasion | 0 | 2 | 10 |
| PT08 Command & Control | 0 | 2 | 8 |
| PT09 Discovery | 0 | 2 | 8 |
| PT10 Collection | 0 | 2 | 8 |
| PT11 Exfiltration | 0 | 2 | 8 |
| PT12 Unix Contextual Stealth | 2 | 2 | 8 |
| PT13 Lateral Movement | 0 | 2 | 8 |
| PT14 Pre-Positioning | 0 | 2 | 8 |
| PT15 Resilience Erosion | 0 | 2 | 6 |
| PT16 Governance Subversion | 0 | 2 | 6 |
| PT17 Cognitive Manipulation | 0 | 2 | 6 |
| PT18 Operational Tempo Manipulation | 0 | 2 | 6 |
| PT19 AI/ML Subversion | 0 | 2 | 8 |
| PT20 Sociotechnical Pressure | 0 | 2 | 6 |
| PT21 Digital Exhaust Manipulation | 0 | 2 | 6 |
| **Total** | **12** | **46** | **161** |

---

> PR3TACK will be officially launched at **FIRST Conference 2026 — Denver, Colorado**
>
> 📩 **join@pr3tack.org**
