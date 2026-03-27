<div align="center">

# META-EDM

### A Validated Meta-Model for Enterprise Data Management
### with Data Catalog Hub Architecture

<p>
  <img src="https://img.shields.io/badge/Method-Design%20Science%20Research-2E86AB?style=for-the-badge" alt="DSR"/>
  <img src="https://img.shields.io/badge/Delphi-N%3D15%20Experts-8B5CF6?style=for-the-badge" alt="N=15"/>
  <img src="https://img.shields.io/badge/Survey-N%3D247%20Practitioners-8B5CF6?style=for-the-badge" alt="N=247"/>
  <img src="https://img.shields.io/badge/Domains-12-F59E0B?style=for-the-badge" alt="12 Domains"/>
  <img src="https://img.shields.io/badge/Dependencies-47-16A34A?style=for-the-badge" alt="47 Dependencies"/>
  <img src="https://img.shields.io/badge/License-CC%20BY%204.0-6B7280?style=for-the-badge" alt="License"/>
</p>

*Supplementary research materials — full-resolution figures and UML source files*

</div>

---

## Overview

Enterprise data management lacks explicit theoretical foundations
for domain decomposition and formalized structural
interdependencies. This research develops **META-EDM**, a
theoretically grounded meta-model comprising **twelve domains**
organized in **four hierarchical layers**, with dependencies
formalized through **modularity theory** and **Dependency
Structure Matrix (DSM) methodology**.

Validated through a multi-method Design Science Research approach
combining an expert Delphi study (N=15, three rounds) and a
large-scale practitioner survey (N=247).

---

## Research Questions

| | Question |
|:---:|---|
| **RQ1** | What are the necessary and sufficient domains of enterprise data management, and what theoretical principles govern their decomposition? |
| **RQ2** | How are EDM domains structurally interdependent, and how do these dependencies inform architectural design and implementation sequencing? |
| **RQ3** | What is the structural role of the data catalog within the EDM ecosystem, and does it function as an architectural hub? |

---

## META-EDM Four-Layer Architecture
```
╔══════════════════════════════════════════════════════════════════╗
║  LAYER 4 — DISCOVERY       D10: Data Catalog    D11: Search     ║
╠══════════════════════════════════════════════════════════════════╣
║  LAYER 3 — ORCHESTRATION   D8: Governance       D9: Lineage     ║
╠══════════════════════════════════════════════════════════════════╣
║  LAYER 2 — ENRICHMENT      D5: Metadata         D6: Quality     ║
║                             D7: Security         D12: Profiling  ║
╠══════════════════════════════════════════════════════════════════╣
║  LAYER 1 — FOUNDATION      D1: Sources          D2: Processing  ║
║                             D3: Storage          D4: Core Assets ║
╚══════════════════════════════════════════════════════════════════╝
                       ▲ Dependencies flow upward
```

The dependency structure matrix captures **47 directional
relationships** among 132 possible domain pairs (35.6% density).
The matrix is strictly acyclic when domains are ordered by layer,
enabling phased deployment without circular activation
requirements.

**Key structural findings:**

- **D10 (Data Catalog)** draws inputs from nine upstream domains
  while providing output to only one downstream consumer — a 9:1
  asymmetry unmatched by any other domain in the model.
- **D4 (Core Data Assets)** shows the highest fan-out (8
  consuming domains), making it the primary architectural
  integration point.
- **D11 (Data Search)** is a terminal node: it consumes from the
  catalog but feeds nothing downstream.

---

## Complete UML Meta-Model

**[View full UML diagram →](figures/EDM_METAMODEL_UML.svg)**

> META-EDM Enterprise Data Catalog Meta-Model — Full UML Class
> Diagram. All 12 domains, inter-package relationships, and
> dependency flows.

📐 **Editable PlantUML source:** [`uml/META_EDM_UML.puml`](uml/META_EDM_UML.puml)

---

## Domain Specifications (Appendix)

Each domain is formally specified as a UML class diagram,
organized by architectural layer.

### Layer 1 — Foundation

| Domain | Figure | Description |
|---|---|---|
| D1 — Data Sources | [Fig. A.1 →](figures/appendix/figA1_D1_data_sources.svg) | All external and internal data origins (structured, semi-structured, unstructured) |
| D2 — Data Processing | [Fig. A.2 →](figures/appendix/D2_Data_Processing.svg) | Ingestion pipelines, transformations, batch and streaming processes |
| D3 — Data Storage | [Fig. A.3 →](figures/appendix/D3_Data_Storage.svg) | Storage infrastructure: lakes, warehouses, lakehouses, object storage |
| D4 — Core Data Assets | [Fig. A.4 →](figures/appendix/D4_Core_Data_Assets.svg) | Central abstraction layer defining all typed data assets |

### Layer 2 — Enrichment

| Domain | Figure | Description |
|---|---|---|
| D5 — Metadata | [Fig. A.5 →](figures/appendix/D5_Metadata.svg) | Technical, business, operational, and custom metadata |
| D6 — Data Quality | [Fig. A.6 →](figures/appendix/D6_Data_Quality.svg) | Quality dimensions, rules, and automated checks (ISO 25012) |
| D7 — Data Security | [Fig. A.7 →](figures/appendix/D7_Data_Security.svg) | Access control, sensitivity classification, roles, audit trails |
| D12 — Data Profiling | [Fig. A.8 →](figures/appendix/D12_Data_Profiling.svg) | Statistical analysis and column-level profiling |

### Layer 3 — Orchestration

| Domain | Figure | Description |
|---|---|---|
| D8 — Data Governance | [Fig. A.9 →](figures/appendix/D8_Data_Governance.svg) | Ownership, stewardship, policies, compliance enforcement |
| D9 — Data Lineage | [Fig. A.10 →](figures/appendix/D9_Data_Lineage.svg) | Provenance, transformation history, impact analysis |

### Layer 4 — Discovery

| Domain | Figure | Description |
|---|---|---|
| D10 — Data Catalog | [Fig. A.11 →](figures/appendix/D10_Data_Catalog.svg) | Hub domain aggregating nine upstream domains for enterprise discovery |
| D11 — Data Search | [Fig. A.12 →](figures/appendix/D11_Data_Search.svg) | Full-text indexing, semantic search, glossary management |

---

## Empirical Validation Results

### Expert Delphi Study — N=15 specialists, 3 rounds

| Criterion | Result |
|---|:---:|
| Domain necessity consensus (overall) | **84.0%** |
| Dependency structure agreement | **91.2%** |
| Invalid dependencies identified | **0 / 47** |
| Total dependency judgments | **705** *(47 deps × 15 experts)* |

All twelve domains achieved necessity scores above 4.0/5.0 across
all three rounds, with consensus strengthening progressively from
round one to round three.

### Practitioner Survey — N=247 professionals

Sample: large enterprises (32%), financial services (28%),
healthcare (23%), other sectors (17%).

| Finding | Result |
|---|:---:|
| Dependency confirmation rate | **87.8%** |
| Catalog satisfaction ↔ upstream maturity | **r = 0.74** *(p < 0.001)* |
| Satisfaction: mature vs. premature deployment | **3.7× higher** *(Cohen's d = 3.8)* |
| Maturity: consistent vs. inconsistent sequences | **2.3× higher** |
| Stakeholder satisfaction: same comparison | **1.9× higher** |

### Cross-Method Triangulation

Expert and practitioner dependency confirmation rates differ by
only **3.4 percentage points** (91.2% vs. 87.8%), confirming
strong convergent validity across independent methods and
stakeholder populations.

---

## Repository Structure
```
meta-edm/
│
├── README.md
│
├── figures/
│   ├── EDM_METAMODEL_UML.svg              ← Complete UML meta-model
│   │
│   └── appendix/                          ← Domain-level diagrams
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
    └── META_EDM_UML.puml                  ← PlantUML editable source
```

---

## Rendering the UML Source
```bash
# High-resolution PNG (300 dpi)
plantuml -tpng -Sdpi=300 uml/META_EDM_UML.puml

# Scalable vector (SVG)
plantuml -tsvg uml/META_EDM_UML.puml
```

Online rendering: [plantuml.com/plantuml](https://www.plantuml.com/plantuml)

---

## License

Released under **Creative Commons Attribution 4.0 International
(CC BY 4.0)**. You are free to share and adapt these materials
with appropriate attribution.

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

---

<div align="center">
<sub>
All figures meet publication artwork standards (≥ 300 dpi) ·
Author information withheld pending peer review
</sub>
</div>
