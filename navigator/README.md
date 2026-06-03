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
| 🟣 Purple `#9b59b6` | Resource Development tactic (TA02) |
| 🟢 Green `#2ecc71` | Unix Contextual Stealth tactic (TA12) |

---

## Technique Coverage

| PR3TACK ID | Name | MITRE Mapping | Priority |
|---|---|---|---|
| T1012.001 | SaaS Tenant Footprinting | T1595 Active Scanning | Medium |
| T1015.001 | CSPM Signature Leakage | T1590 Gather Victim Network Info | Medium |
| T1016.001 | SaaS App-to-App Permission Mining | T1526 Cloud Service Discovery | High |
| T1018.001 | Identity Role Squatting Prep | T1078.004 Valid Accounts: Cloud | Critical |
| T1101.001 | Vector Database Reconnaissance | T1213 Data from Info Repositories | High |
| T1025.001 | AI-Generated Persona Synthesis | T1585 Establish Accounts | Medium |
| T1025.002 | Automated Social Proofing | T1585 Establish Accounts | Medium |
| T1028.001 | Cloud Account Incubation | T1583 Acquire Infrastructure | Medium |
| T1103.001 | LLM Mirroring & Local Jailbreak Prep | T1587 Develop Capabilities | Critical |
| T1061.001 | Dependency Confusion Probing | T1195 Supply Chain Compromise | Critical |
| T1201.001 | Over-Mounting Cloaking | T1564 Hide Artifacts | High |
| T1202.001 | /proc Environmental Archaeology | T1552 Unsecured Credentials | High |

---

## Notes

- The layer targets **ATT&CK Enterprise v14** — reload against later versions as needed
- PR3TACK techniques are annotated on their **nearest MITRE ATT&CK analogue** — the technique comment in each cell explains the specific MITRE gap being addressed
- Each cell includes metadata links to the full PR3TACK technique file, detection rule, and SIGMA YAML
- As PR3TACK grows, additional layers will be published per tactic and per release version
