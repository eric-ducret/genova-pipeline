# Genova
 
A pipeline for clinical genetic variant analysis, powered by Small Language Models (SLMs).
 
Created by **Eric Ducret** — supervised by **Federico Santoni**

University of Lausanne (UNIL) & Lausanne University Hospital (CHUV)
 
---

Genetic sequencing generates more data than clinical teams can interpret manually. Variant databases, literature, and splicing predictors each live in different formats and classical rule-based tools can't bridge them.

Cloud-based LLMs could help, but hospitals can't send patient data to external servers. Privacy policies, compliance requirements, and cost make cloud dependence impractical for routine clinical use. LLMs can be deployed locally, but they demand expensive GPU infrastructure that most clinical settings don't have. 

Genova uses **locally deployable SLMs** (≤10B parameters, runs on standard hardware) to do the interpretation on-site. No patient data leaves the institution. No cloud costs.

---

## Details

**Input:** a textual description of the patient + a CSV of genetic variants.
 
```
Patient description + Variant CSV
                │
                ▼
        ┌───────────────┐
        │ Normalization │
        └───────┬───────┘
                │
                ▼
     ┌─────────────────────┐
     │Per-variant analysis │  ← database lookups, splicing
     │                     │    prediction, literature search
     └──────────┬──────────┘
                │
                ▼
     ┌─────────────────────┐
     │ Clinical reasoning  │  ← integrates all evidence
     └──────────┬──────────┘
                │
                ▼
     ┌─────────────────────┐
     │ Structured report   │
     └─────────────────────┘
```
 
**Output:** a structured clinical report with per-variant interpretation.
 
Each variant is analyzed independently using specialized tools (literature retrieval, splicing prediction, pathogenicity assessment), then all evidence is synthesized into a final report.
 
## Status
 
Under active development — not publicly available yet.
 
Contact: eric.ducret@unil.ch
