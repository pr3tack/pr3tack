# Methodology

---

## ID Naming Convention

PR3TACK uses its own identifier scheme, independent of MITRE ATT&CK. This separation is intentional — PR3TACK IDs represent preemptive, forward-looking techniques that may not yet exist in established frameworks, and the numbering reflects PR3TACK's own tactic and technique taxonomy.

### Tactic IDs

Tactics are identified with a `PT` prefix followed by a two-digit number:

```
PT<NN>
```

| ID | Tactic |
|---|---|
| PT01 | Reconnaissance |
| PT02 | Resource Development |
| PT06 | Supply Chain Preparation |
| PT12 | Unix Contextual Stealth |

The tactic number is not sequential by design — gaps are reserved for tactics currently under development (e.g. Execution, Persistence, Privilege Escalation, Defense Evasion, C2, Discovery, Collection).

### Technique IDs

Techniques are identified with the parent tactic ID, a dot separator, and a three-digit sub-technique number:

```
PT<NN>.<NNN>
```

Examples:
- `PT01.001` — SaaS Tenant Footprinting (first technique under Reconnaissance)
- `PT01.005` — Vector Database Reconnaissance (fifth technique under Reconnaissance)
- `PT02.003` — Cloud Account Incubation (third technique under Resource Development)

Sub-technique numbers are assigned sequentially within each tactic as techniques are added to the framework.

### Directory and File Naming

Tactic directories and technique files follow a consistent kebab-case convention:

| Artefact | Pattern | Example |
|---|---|---|
| Tactic directory | `PT<NN>-tactic-name/` | `PT01-reconnaissance/` |
| Technique file | `PT<NN>.<NNN>-kebab-case-name.md` | `PT01.001-saas-tenant-footprinting.md` |
| Detection rule | `PT<NN>.<NNN>-kebab-case-name.md` | `PT01.001-saas-tenant-footprinting.md` |
| Sigma YAML | `pr3tack-PT<NN>.<NNN>-kebab-case-name.yml` | `pr3tack-PT01.001-saas-tenant-footprinting.yml` |

### Relationship to MITRE ATT&CK

PR3TACK IDs are **not derived from** MITRE ATT&CK technique IDs. Where a PR3TACK technique overlaps with or extends a MITRE technique, the MITRE ATT&CK `techniqueID` is recorded as metadata within the technique and navigator layer for cross-reference purposes only. The PR3TACK ID remains the canonical identifier.

---

## Technique Development Process

1. Identify a gap in existing security practices/frameworks/controls
2. Define a feasible attack path
3. Validate technical plausibility
4. Map detection opportunities
5. Define mitigation strategies

---

## Evaluation Criteria

- Feasibility
- Stealth potential
- Impact
- Detectability
- Defensive value
