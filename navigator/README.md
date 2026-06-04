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
| PT06.001 | Dependency Confusion Probing | T1195 Supply Chain Compromise | Critical |
| PT12.001 | Over-Mounting Cloaking | T1564 Hide Artifacts | High |
| PT12.002 | /proc Environmental Archaeology | T1552 Unsecured Credentials | High |

---

## Notes

- The layer targets **ATT&CK Enterprise v14** — reload against later versions as needed
- PR3TACK techniques are annotated on their **nearest MITRE ATT&CK analogue** — the technique comment in each cell explains the specific MITRE gap being addressed
- Each cell includes metadata links to the full PR3TACK technique file, detection rule, and SIGMA YAML
- As PR3TACK grows, additional layers will be published per tactic and per release version
