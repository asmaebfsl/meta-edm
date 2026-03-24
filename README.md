<div align="center">

# META-EDM
## A Validated Meta-Model for Enterprise Data Management  
### with Data Catalog Hub Architecture

[![Status](https://img.shields.io/badge/Status-Research%20Project-orange?style=flat-square)](#)
[![Method](https://img.shields.io/badge/Method-Design%20Science%20Research-green?style=flat-square)](#methodology)
[![Validation](https://img.shields.io/badge/Validated-N%3D262%20experts%20%26%20practitioners-purple?style=flat-square)](#empirical-validation)
[![UML](https://img.shields.io/badge/UML-12%20packages%20%7C%2070%2B%20classes-blue?style=flat-square)](#uml-meta-model)
[![License](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

---

*Supplementary research materials — figures, UML source files, and replication resources*

</div>

---

## 🎯 Research Motivation

The global data management market reached **USD 122 billion in 2024**, yet approximately **70% of digital transformation initiatives fail** due to inadequate data governance or fragmented architectures. Data analysts still spend **30–50% of their time** searching for, cleaning, and preparing data rather than deriving analytical value.

Existing enterprise data management frameworks — including DAMA-DMBOK 2 and DCAM — exhibit three critical limitations:

1. **No theoretical foundation** for domain decomposition
2. **No formalized interdependencies** between domains
3. **No rigorous empirical validation**

**META-EDM addresses these three gaps simultaneously.**

---

## 🔬 Research Questions

| | Question |
|---|---|
| **RQ1** | What are the necessary and sufficient domains of enterprise data management, and what theoretical principles govern their decomposition? |
| **RQ2** | How are EDM domains structurally interdependent, and how do these dependencies inform architectural design and implementation sequencing? |
| **RQ3** | What is the structural role of the data catalog within the EDM ecosystem, and does it function as an architectural hub? |

---

## 🏗️ The META-EDM Meta-Model

META-EDM proposes **twelve domains** organized into **four hierarchical layers**, with formalized dependencies derived from **modularity theory** and **Dependency Structure Matrix (DSM) methodology**.

### Four-Layer Architecture

```
┌─────────────────────────────────────────────────────────────┐
│  LAYER 4 — DISCOVERY         D10: Data Catalog   D11: Search │
├─────────────────────────────────────────────────────────────┤
│  LAYER 3 — ORCHESTRATION     D8: Governance      D9: Lineage │
├─────────────────────────────────────────────────────────────┤
│  LAYER 2 — ENRICHMENT   D5: Metadata  D6: Quality           │
│                          D7: Security  D12: Profiling        │
├─────────────────────────────────────────────────────────────┤
│  LAYER 1 — FOUNDATION   D1: Sources  D2: Processing         │
│                          D3: Storage  D4: Core Assets        │
└─────────────────────────────────────────────────────────────┘
                    ▲ Dependencies flow upward
```

### The Data Catalog as Architectural Hub

> *"Data Catalog (D10) occupies a unique structural position, aggregating information from **nine upstream domains** while providing output to only one downstream domain."*

---

## 📊 Complete UML Meta-Model

![META-EDM Full UML Meta-Model](figures/fig4_full_uml_metamodel.png)

> **Figure 4.** META-EDM Enterprise Data Catalog Meta-Model — Full UML Class Diagram  
> *12 packages · 70+ classes with methods · 7 enumerations · Complete inter-domain relationships*

📥 **PlantUML source (editable):** [`uml/META_EDM_UML.puml`](uml/META_EDM_UML.puml)

---

## 🧪 Empirical Validation

### Validation Stream 1 — Expert Delphi Study (N=15)

| Criterion | Result |
|---|---|
| Overall domain necessity consensus | **84.0%** |
| Expert agreement on dependency structures | **91.2%** |
| Catalog hub position consensus | **88.7%** |
| Inter-round stability (Kendall W) | **W = 0.73** (p < 0.001) |

### Validation Stream 2 — Practitioner Survey (N=247)

| Finding | Statistic |
|---|---|
| Catalog satisfaction ↔ upstream maturity | **r = 0.74** (p < 0.001) |
| Satisfaction: mature vs. premature deployment | **3.7× higher** (Cohen's d = 3.8) |
| Maturity: consistent vs. inconsistent sequences | **2.3× higher** |
| Stakeholder satisfaction: consistent vs. inconsistent | **1.9× higher** |

### Cross-Method Triangulation

Expert and practitioner assessments differ by only **3.4 percentage points** — confirming strong convergence.

---

## 🗂️ Repository Contents

```
meta-edm/
│
├── README.md
│
├── figures/
│   ├── fig_full_uml_metamodel.png          ← Complete meta-model 
│   │
│   └── appendix_a/                          ← Domain-level UML diagrams
│       ├── figA1_D1_data_sources.png
│       ├── figA2_D2_data_processing.png
│       ├── figA3_D3_data_storage.png
│       ├── figA4_D4_core_assets.png
│       ├── figA5_D5_metadata.png
│       ├── figA6_D6_data_quality.png
│       ├── figA7_D7_data_security.png
│       ├── figA8_D8_data_governance.png
│       ├── figA9_D9_data_lineage.png
│       ├── figA10_D10_data_catalog.png
│       ├── figA11_D11_data_search.png
│       └── figA12_D12_data_profiling.png
│
└── uml/
    └── META_EDM_UML.puml                 ← PlantUML source
```

---

## ⚙️ Rendering the UML Diagrams

```bash
# Install PlantUML
sudo apt-get install plantuml

# Render to high-resolution PNG
plantuml -tpng -Sdpi=300 uml/META_EDM_UML_V4.puml

# Render to SVG (vector)
plantuml -tsvg uml/META_EDM_UML_V4.puml
```

Or paste the `.puml` file content at [plantuml.com/plantuml](https://www.plantuml.com/plantuml)

---

## 📜 License

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

This repository is shared under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

---

<div align="center">

*All figures are provided at full resolution (≥ 300 dpi).*  
*Author information withheld pending peer review.*

</div>
