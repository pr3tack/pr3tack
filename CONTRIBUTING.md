# Contributing to PR3TACK

---

## Overview

PR3TACK is a community-driven framework of **feasible, forward-looking attack techniques and defensive countermeasures**.

We welcome contributions from detection engineers, red and purple teamers, threat researchers, security architects, and anyone who thinks seriously about what comes next in adversary tradecraft.

> The goal is not to document what attackers have done — it's to prepare defenders for what they haven't done yet.

---

## Contribution Areas

| Area | Description |
|---|---|
| **New techniques** | Propose a technique that is plausible, feasible, and not yet in MITRE ATT&CK |
| **Detection rules** | Add SIGMA-compatible rules, analytics, or hunting queries for existing techniques |
| **Countermeasure improvements** | Strengthen prevention, detection, or response guidance on existing techniques |
| **SIGMA YAMLs** | Add or improve standalone SIGMA `.yml` files in `detections/sigma/` |
| **Navigator updates** | Update `navigator/pr3tack-layer.json` to reflect new techniques |
| **Documentation** | Improve clarity, fix errors, add references |
| **Tooling** | Build automation, integrations, or Navigator tooling |

---

## The Four Ground Rules

Every contribution must satisfy all four principles:

### 1. Feasible, Not Fictional
The technique must be technically achievable **today** using real tools, platforms, or protocols. It does not need to have been observed in the wild — but it must be buildable.

### 2. Defensible
Every technique must include at minimum:
- At least one **prevention** control
- At least one **detection** opportunity
- At least one **response** action

Techniques without a defensive path will not be accepted.

### 3. Structured
All contributions must use the provided templates:
- Techniques → `templates/technique-template.md`
- Detections → `templates/detection-template.md`

Submissions that do not follow the template structure will be returned for revision.

### 4. Clear and Specific
No vague or purely theoretical ideas. The description must be precise enough that a capable engineer could build the technique or detection from the content alone.

---

## ID Assignment

PR3TACK uses its own identifier scheme, independent of MITRE ATT&CK. Full details are documented in [`framework/methodology.md`](./framework/methodology.md).

### Tactic IDs

Tactics use a `PT<NN>` prefix. Current active tactics:

| ID | Tactic |
|---|---|
| PT01 | Reconnaissance |
| PT02 | Resource Development |
| PT06 | Supply Chain Preparation |
| PT12 | Unix Contextual Stealth |

Gaps in numbering are intentional — they are reserved for tactics currently under development (Initial Access, Execution, Persistence, Defense Evasion, Credential Access, Discovery, Collection, C2).

### Technique IDs

Technique IDs follow the format `PT<NN>.<NNN>`:
- The tactic prefix (`PT01`, `PT02`, etc.) identifies the parent tactic
- The three-digit suffix (`.001`, `.002`, etc.) is assigned sequentially within that tactic
- PR3TACK IDs are **not** derived from or tied to MITRE ATT&CK technique numbers

> **Do not self-assign an ID for a new technique.** Propose the technique with `ID: TBD` — maintainers will assign the canonical ID on review.

---

## How to Submit a New Technique

### Step 1 — Check for duplicates
Search existing techniques in `techniques/` and open issues/PRs to avoid duplicating work.

### Step 2 — Fork and branch
```bash
git clone https://github.com/pr3tack/pr3tack.git
cd pr3tack
git checkout -b technique/your-technique-name
```

### Step 3 — Create the technique file
Copy `templates/technique-template.md` to the appropriate tactic directory:
```bash
cp templates/technique-template.md techniques/PT01-reconnaissance/PTXX.XXX-your-technique-name.md
```
Use `TBD` as the ID until assigned by a maintainer.

### Step 4 — Create a detection file (required)
Copy `templates/detection-template.md` to the appropriate detection subdirectory:
```bash
# For rule-based detections (SIEM/EDR):
cp templates/detection-template.md detections/rules/PTXX.XXX-your-technique-name.md

# For behavioural/statistical detections:
cp templates/detection-template.md detections/analytics/PTXX.XXX-your-technique-name.md

# For hypothesis-driven hunting:
cp templates/detection-template.md detections/hunting/PTXX.XXX-your-technique-name.md
```

### Step 5 — Add a SIGMA YAML (strongly recommended)
If your detection is rule-based, add a SIGMA-compatible `.yml` file to `detections/sigma/`:
```bash
cp detections/sigma/pr3tack-PT01.001-saas-tenant-footprinting.yml \
   detections/sigma/pr3tack-PTXX.XXX-your-technique-name.yml
```

SIGMA rules must:
- Have a unique [UUID v4](https://www.uuidgenerator.net/) `id` field (all hex chars: `0-9a-f`)
- Be `status: experimental` until validated in production
- Include at least one `falsepositives` entry
- Include a `level` of `low`, `medium`, `high`, or `critical`
- Pass basic SIGMA syntax validation:
  ```bash
  sigma check detections/sigma/your-rule.yml
  ```

### Step 6 — Update indexes
Update the following files to include your technique:
- `techniques/README.md` — add a row to the technique index table
- `detections/README.md` — add entries to the detection index and coverage map
- `detections/sigma/README.md` — add a row to the rule index (if applicable)
- `navigator/pr3tack-layer.json` — add a technique entry (maintainers can assist)

### Step 7 — Submit a pull request
```bash
git add .
git commit -m "feat: add PTXX.XXX — Your Technique Name"
git push origin technique/your-technique-name
```

Open a PR against `main` with:
- **Title:** `feat: add PTXX.XXX — [Technique Name]`
- **Description:** Brief summary of the technique, the MITRE gap it addresses, and the detection approach

---

## How to Submit a Detection

If you are adding or improving a detection for an **existing** technique:

```bash
git checkout -b detection/PTXX.XXX-detection-type
```

Use `fix:` prefix in your commit message if improving an existing detection:
```bash
git commit -m "fix: improve PT01.001 SIGMA rule to reduce false positives from EASM scanners"
```

Use `feat:` prefix if adding a net-new detection type (e.g., adding a hunt query for a technique that only has a rule):
```bash
git commit -m "feat: add PT02.003 hunt query for aged cloud tenant infrastructure discovery"
```

---

## Review Process

All PRs will be reviewed against the following criteria:

| Criterion | Description |
|---|---|
| **Technical accuracy** | Is the technique description correct? Are the procedure steps buildable? |
| **Feasibility** | Can this be executed with real tooling today? |
| **Defensive completeness** | Does the technique have prevention, detection, and response coverage? |
| **Template compliance** | Does the file follow the required structure? |
| **MITRE gap clarity** | Is the "Why It's Not in MITRE ATT&CK" section specific and accurate? |
| **Detection quality** | Is the detection logic sound? Are false positives acknowledged? |
| **SIGMA validity** | Do SIGMA YAMLs parse cleanly and have valid UUIDs? |

Maintainers aim to review PRs within **14 days**. Complex or novel techniques may require additional discussion.

---

## Commit Message Convention

PR3TACK uses [Conventional Commits](https://www.conventionalcommits.org/):

| Prefix | Use for |
|---|---|
| `feat:` | New technique, detection, or SIGMA rule |
| `fix:` | Correction to existing content (logic error, false positive, typo) |
| `docs:` | Documentation-only changes |
| `refactor:` | Restructuring without content change |
| `chore:` | Index updates, template changes, tooling |

---

## File Naming Convention

| Type | Convention | Example |
|---|---|---|
| Technique | `PTXX.XXX-kebab-case-name.md` | `PT01.001-saas-tenant-footprinting.md` |
| Detection rule | `PTXX.XXX-kebab-case-name.md` | `PT01.001-saas-tenant-footprinting.md` |
| SIGMA YAML | `pr3tack-PTXX.XXX-kebab-case-name.yml` | `pr3tack-PT01.001-saas-tenant-footprinting.yml` |

Directories are named `PTXX-tactic-name/` (e.g., `PT01-reconnaissance/`).

---

## Code of Conduct

- Be respectful and constructive in all reviews and discussions
- Critique techniques, not contributors
- The goal is to advance defensive tradecraft — ego has no place here
- If you see something wrong, raise it — accuracy is a community responsibility

---

## Getting Help

- Open an issue to discuss a technique idea before investing time in a full submission
- Join the conversation: **join@pr3tack.org**
- PR3TACK will be officially launched at **FIRST Conference 2026 — Denver, Colorado**
