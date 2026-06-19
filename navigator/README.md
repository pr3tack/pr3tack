# PR3TACK Navigator

Interactive matrix visualisation for the PR3TACK technique set, compatible with the [MITRE ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/).

Because PR3TACK techniques map to their nearest MITRE ATT&CK analogue (rather than being independent), the Navigator layer overlays PR3TACK annotations onto the standard ATT&CK Enterprise matrix — making it easy to see **where PR3TACK extends ATT&CK coverage**.

---

## How to Load the Layer

### Option 1 — MITRE ATT&CK Navigator (Web)

1. Open [https://mitre-attack.github.io/attack-navigator/](https://mitre-attack.github.io/attack-navigator/)
2. Click **Open Existing Layer** → **Upload from local**
3. Select `navigator/pr3tack-layer.json`

### Option 2 — Direct URL Load

If the repository is public, load directly from GitHub:

1. Open [https://mitre-attack.github.io/attack-navigator/](https://mitre-attack.github.io/attack-navigator/)
2. Click **Open Existing Layer** → **Load from URL**
3. Paste:
```
https://raw.githubusercontent.com/pr3tack/pr3tack/main/navigator/pr3tack-layer.json
```

### Option 3 — Self-Hosted Navigator

```bash
git clone https://github.com/mitre-attack/attack-navigator.git
cd attack-navigator/nav-app
npm install
npm run start
```

Then load `navigator/pr3tack-layer.json` via **Open Existing Layer → Upload from local**.

---

## Colour Legend

| Colour | Meaning |
|---|---|
| 🔴 Dark Red `#e84a4a` | Critical / High response priority |
| 🟠 Orange `#e8724a` | Medium response priority |
| 🟣 Purple `#9b59b6` | Resource Development tactic (PT02) |
| 🟢 Green `#2ecc71` | Unix Contextual Stealth tactic (PT12) |

---

## Technique Coverage

| PR3TACK ID | Name | MITRE Mapping | Priority |
|---|---|---|---|
| PT01.001 | SaaS Tenant Footprinting | T1595 Active Scanning | Medium |
| PT01.002 | CSPM Signature Leakage | T1590 Gather Victim Network Info | Medium |
| PT01.003 | SaaS App-to-App Permission Mining | T1526 Cloud Service Discovery | High |
| PT01.004 | Identity Role Squatting Prep | T1078.004 Valid Accounts: Cloud | Critical |
| PT01.005 | Vector Database Reconnaissance | T1213 Data from Info Repositories | High |
| PT02.001 | AI-Generated Persona Synthesis | T1585 Establish Accounts | Medium |
| PT02.002 | Automated Social Proofing | T1585 Establish Accounts | Medium |
| PT02.003 | Cloud Account Incubation | T1583 Acquire Infrastructure | Medium |
| PT02.004 | LLM Mirroring & Local Jailbreak Prep | T1587 Develop Capabilities | Critical |
| PT03.001 | BIOS Config Trigger Payloads | T1542.001 System Firmware | Low |
| PT03.002 | Peripheral Firmware Stager | T1195.003 Compromise Hardware Supply Chain | Medium |
| PT04.001 | Abuse of Windows Atom Tables | T1055 Process Injection | High |
| PT04.002 | Hidden Service Registration | T1543 Create or Modify System Process | Medium |
| PT05.001 | Exploit Virtual Device Drivers | T1068 Exploitation for Privilege Escalation | Medium |
| PT05.002 | Credential Store Forging | T1558 Steal or Forge Kerberos Tickets | Medium |
| PT06.001 | Dependency Confusion Probing | T1195 Supply Chain Compromise | Critical |
| PT07.001 | Cloud Metadata API Overloading | T1552.005 Cloud Instance Metadata API | Medium |
| PT07.002 | Telemetry Tampering | T1562.006 Indicator Blocking | Medium |
| PT08.001 | Bluetooth HID Covert Channels | T1011 Exfiltration Over Other Network Medium | Low |
| PT08.002 | Covert DNS-over-HTTPS Tunnels | T1071.004 DNS | Medium |
| PT09.001 | Browser Extension Enumeration via IPC | T1176 Browser Extensions | Medium |
| PT09.002 | Identity Topology Mapping | T1087 Account Discovery | Medium |
| PT10.001 | Abuse of Clipboard History Services | T1115 Clipboard Data | High |
| PT10.002 | Credential Cache Scraping via Accessibility APIs | T1056.002 GUI Input Capture | Medium |
| PT11.001 | Leveraging Screen Reader APIs for Data Leak | T1113 Screen Capture | Medium |
| PT11.002 | Covert Cloud Storage Staging | T1567.002 Exfiltration to Cloud Storage | Medium |
| PT12.001 | Over-Mounting Cloaking | T1564 Hide Artifacts | High |
| PT12.002 | /proc Environmental Archaeology | T1552 Unsecured Credentials | High |
| PT13.001 | Software Update Supply Chain Piggybacking | T1195.002 Compromise Software Supply Chain | Medium |
| PT13.002 | Business-Unit Policy Propagation | T1484 Domain Policy Modification | Medium |
| PT14.001 | OSS Supply-Chain Sleeper Commit | T1195.001 Compromise Software Dependencies | Medium |
| PT14.002 | Anticipatory Brand/Domain Squatting | T1583.001 Acquire Infrastructure: Domains | High |
| PT15.001 | Backup Bit-Rot Injection | T1490 Inhibit System Recovery | Medium |
| PT15.002 | Patch-Fatigue Campaigns | T1562 Impair Defenses | Medium |
| PT16.001 | Standards/Comments Manipulation | — No MITRE mapping | Low |
| PT16.002 | Procurement Account Establishment | T1585 Establish Accounts | Medium |
| PT17.001 | Analyst Habituation Lures | T1562 Impair Defenses | High |
| PT17.002 | Adversarial Log Crafting | T1565.001 Stored Data Manipulation | Medium |
| PT18.001 | Holiday/Travel Window Triggering | — No MITRE mapping | High |
| PT18.002 | Billing/Cost Shock Forcing | T1496 Resource Hijacking | Medium |
| PT19.001 | Training-Data Seed Poisoning | AML.T0020 Poison Training Data | Medium |
| PT19.002 | Model Output Injection | AML.T0043 Craft Adversarial Data | Medium |
| PT20.001 | Investor/Media Narrative Orchestration | — No MITRE mapping | Low |
| PT20.002 | Vendor-Influence Campaigns | T1195 Supply Chain Compromise | Medium |
| PT21.001 | IOC/Telco Feed Pollution | — No MITRE mapping | High |
| PT21.002 | Telemetry Noise Flooding | T1562.006 Indicator Blocking | Medium |

---

## Notes

- The layer targets **ATT&CK Enterprise v14** — reload against later versions as needed
- PR3TACK techniques are annotated on their **nearest MITRE ATT&CK analogue** — the technique comment in each cell explains the specific MITRE gap being addressed
- Each cell includes metadata links to the full PR3TACK technique file, detection rule, and SIGMA YAML
- As PR3TACK grows, additional layers will be published per tactic and per release version
