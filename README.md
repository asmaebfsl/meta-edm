# META-EDM

**A Validated Meta-Model for Enterprise Data Management  
with Data Catalog Hub Architecture**

*Supplementary research materials — full-resolution UML figures  
and editable PlantUML source files*

---

## What this repository contains

This repository holds the complete set of figures and source files
supporting the META-EDM research paper. The paper develops a
theoretically grounded meta-model for enterprise data management,
organizes twelve domains across four architectural layers, and
formally characterizes the data catalog as a structural hub —
a claim validated through two independent empirical studies.

All figures are provided in scalable vector format (.svg) and
as high-resolution rasters (≥ 300 dpi), meeting publication
artwork standards.

---

## Research questions

The paper addresses three questions that existing EDM frameworks
leave unanswered:

- What domains are genuinely necessary and sufficient for enterprise
  data management, and what principles justify their boundaries?
- How are these domains structurally interdependent, and what does
  that mean for implementation sequencing?
- Does the data catalog occupy a structurally distinct position
  within the EDM ecosystem — and if so, what are the implications?

---

## The META-EDM architecture

Twelve domains organized across four layers, with dependencies
flowing upward from infrastructure toward discovery:
```
┌─────────────────────────────────────────────────────────────┐
│  Layer 4 — Discovery       D10: Data Catalog   D11: Search  │
├─────────────────────────────────────────────────────────────┤
│  Layer 3 — Orchestration   D8: Governance      D9: Lineage  │
├─────────────────────────────────────────────────────────────┤
│  Layer 2 — Enrichment      D5: Metadata        D6: Quality  │
│                             D7: Security        D12: Profiling│
├─────────────────────────────────────────────────────────────┤
│  Layer 1 — Foundation      D1: Sources         D2: Processing│
│                             D3: Storage         D4: Core Assets│
└─────────────────────────────────────────────────────────────┘
```

The dependency structure matrix (12×12) captures 47 directional
relationships among the 132 possible domain pairs — a density of
35.6%. The matrix is strictly acyclic when domains are ordered
by layer, which allows phased deployment without circular
activation requirements.

D10 (Data Catalog) draws inputs from nine upstream domains while
feeding only one downstream consumer. No other domain in the model
shows a comparable asymmetry. D4 (Core Data Assets) has the highest
fan-out, with eight domains depending on it — making it the primary
architectural integration point.

---

## Validation overview

The meta-model was validated through two independent studies
conducted in parallel.

**Expert Delphi study — N=15 specialists, three rounds**

Experts assessed domain necessity and dependency validity across
three structured rounds, with full participant retention throughout.

| Criterion | Result |
|---|---|
| Domain necessity consensus (overall) | 84.0% |
| Dependency structure agreement | 91.2% |
| Invalid dependencies identified | 0 out of 47 |
| Total dependency judgments | 705 (47 deps × 15 experts) |

**Practitioner survey — N=247 professionals**

Respondents spanned large enterprises (32%), financial services
(28%), healthcare (23%), and other sectors (17%).

| Finding | Result |
|---|---|
| Dependency confirmation rate | 87.8% |
| Catalog satisfaction ↔ upstream maturity | r = 0.74, p < 0.001 |
| Satisfaction gap: mature vs. premature deployment | 3.7× (Cohen's d = 3.8) |
| Maturity: consistent vs. inconsistent sequences | 2.3× higher |
| Stakeholder satisfaction: same comparison | 1.9× higher |

**Cross-method convergence**

Expert and practitioner dependency confirmation rates differ by
3.4 percentage points (91.2% vs. 87.8%), confirming that the
dependency structure holds across both populations and evaluation
methods.

---

## Repository structure
```
meta-edm/
│
├── README.md
│
├── figures/
│   ├── EDM_METAMODEL_UML.svg          ← Complete meta-model (all 12 domains)
│   │
│   └── appendix/
│       ├── figA1_D1_data_sources.svg
│       ├── D2_Data_Processing.svg
│       ├── D3_Data_Storage.svg
│       ├── D4_Core_Data_Assets.svg
│       ├── D5_Metadata.svg
│       ├── D6_Data_Quality.svg
│       ├── D7_Data_Security.svg
│       ├── D8_Data_Governance.svg
│       ├── D9_Data_Lineage.svg
│       ├── D10_Data_Catalog.svg
│       ├── D11_Data_Search.svg
│       └── D12_Data_Profiling.svg
│
└── uml/
    └── META_EDM_UML.puml              ← Editable PlantUML source
```

---

## Rendering the UML source locally
```bash
# PNG at 300 dpi
plantuml -tpng -Sdpi=300 uml/META_EDM_UML.puml

# Scalable vector
plantuml -tsvg uml/META_EDM_UML.puml
```

Online rendering is also available at
[plantuml.com/plantuml](https://www.plantuml.com/plantuml).

---

## License

Released under **Creative Commons Attribution 4.0 International
(CC BY 4.0)**. You are free to share and adapt these materials
provided appropriate attribution is given.

