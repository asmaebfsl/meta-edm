<div align="center">

# META-EDM
## A Validated Meta-Model for Enterprise Data Management  
### with Data Catalog Hub Architecture

[![Method](https://img.shields.io/badge/Method-Design%20Science%20Research-green?style=flat-square)](#methodology)
[![Validation](https://img.shields.io/badge/Validation-N%3D262%20(Delphi%20%2B%20Survey)-purple?style=flat-square)](#empirical-validation)
[![License](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

---

*Supplementary research materials submitted to the*  
**International Journal of Information Management** *(Elsevier, ISSN 0268-4012)*

</div>

---

## 🎯 Research Motivation

The global data management market reached **USD 122 billion in 2024**, yet approximately **70% of digital transformation initiatives fail** due to inadequate data governance or fragmented architectures. Data analysts still spend **30–50% of their time** searching for, cleaning, and preparing data rather than deriving analytical value.

A fundamental reason for this paradox is structural: existing enterprise data management frameworks — including industry standards such as DAMA-DMBOK 2 and DCAM — exhibit three critical limitations:

1. **No theoretical foundation** for domain decomposition — boundaries emerge from practitioner consensus, not systematic principles
2. **No formalized interdependencies** — frameworks provide minimal architectural guidance for implementation sequencing
3. **No rigorous empirical validation** — frameworks are not tested through established scientific methods

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

This hub structure has critical implementation implications:
- Organizations deploying catalogs **before** maturing upstream domains report **disappointing results** — the interface functions but discovers minimal content
- Organizations with mature metadata, quality, and lineage capabilities report **substantial catalog ROI** through effective aggregation of rich upstream content

---

## 📊 Complete UML Meta-Model

The complete UML class diagram below presents META-EDM across all 12 domains, 70+ classes, 7 enumerations, and all inter-package relationships.

![META-EDM Full UML Meta-Model](figures/fig4_full_uml_metamodel.png)

> **Figure 4.** META-EDM Enterprise Data Catalog Meta-Model — Full UML Class Diagram  
> *12 packages · 70+ classes with methods · 7 enumerations · Complete inter-domain relationship model*

📥 **PlantUML source:** [`uml/META_EDM_UML_V4.puml`](uml/META_EDM_UML_V4.puml) — fully editable, renderable with any PlantUML-compatible tool.

---

## 🧪 Empirical Validation

META-EDM was validated through a **multi-method Design Science Research** approach combining two independent validation streams.

### Validation Stream 1 — Expert Delphi Study (N=15)

Three-round Delphi study with senior data management practitioners and academics:

| Criterion | Result |
|---|---|
| Overall domain necessity consensus | **84.0%** |
| Expert agreement on dependency structures | **91.2%** |
| Catalog hub position consensus | **88.7%** |
| Inter-round stability (Kendall W) | **W = 0.73** (p < 0.001) |

### Validation Stream 2 — Practitioner Survey (N=247)

Large-scale quantitative survey across industries and organization sizes:

| Finding | Statistic |
|---|---|
| Catalog satisfaction ↔ upstream maturity correlation | **r = 0.74** (p < 0.001) |
| Satisfaction: mature vs. premature catalog deployment | **3.7× higher** (Cohen's d = 3.8) |
| Maturity: dependency-consistent vs. inconsistent sequences | **2.3× higher** |
| Stakeholder satisfaction: consistent vs. inconsistent sequences | **1.9× higher** |

### Cross-Method Triangulation

Expert and practitioner assessments differ by only **3.4 percentage points** — confirming strong convergence between theoretical design and field reality.

---

## 🗂️ Repository Contents

```
meta-edm/
│
├── README.md                          ← This file
│
├── figures/                           ← All paper figures (≥300 dpi, IJIM-compliant)
│   ├── fig1_publications_temporal.png        Figure 1 — Temporal evolution of publications
│   ├── fig2_dsr_process.png                  Figure 2 — Design Science Research process
│   ├── fig3_four_layer_architecture.png      Figure 3 — META-EDM four-layer architecture
│   ├── fig4_full_uml_metamodel.png           Figure 4 — Complete UML meta-model ★
│   │
│   └── appendix_a/                           Appendix A — Domain-level UML diagrams
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
└── uml/                               ← Editable UML source files
    └── META_EDM_UML_V4.puml                  PlantUML source — complete meta-model
```

---

## ⚙️ Rendering the UML Diagrams

The PlantUML source file can be rendered locally or online:

**Local rendering (high resolution):**
```bash
# Install PlantUML
sudo apt-get install plantuml

# Render to PNG at 300 dpi (IJIM-compliant)
plantuml -tpng -Sdpi=300 uml/META_EDM_UML_V4.puml

# Render to SVG (vector, infinitely scalable)
plantuml -tsvg uml/META_EDM_UML_V4.puml
```

**Online rendering:**  
Paste the contents of `META_EDM_UML_V4.puml` into [plantuml.com/plantuml](https://www.plantuml.com/plantuml)

---

## 🤝 Theoretical Contributions

This research makes three categories of contribution:

**To Theory**
- First theoretically grounded EDM domain decomposition derived from modularity theory
- Formal acyclic dependency architecture enabling mathematical proof of implementation sequencing
- Theoretical model of catalog architectural positioning as system integrator

**To Practice**
- Actionable implementation roadmap based on dependency-consistent sequencing
- Diagnostic framework for assessing organizational EDM maturity
- Technology substitution guidelines preserving architectural integrity

**To Methodology**
- Multi-method validation combining Delphi and survey in an IS Design Science context
- Cross-method triangulation protocol for meta-model validation
- Replicable empirical validation procedure for future IS meta-models

---

## 📖 How to Cite

> Anonymous Authors (under review). *META-EDM: A Validated Meta-Model for Enterprise Data Management with Data Catalog Hub Architecture*. International Journal of Information Management. Elsevier.

*Full citation will be updated upon acceptance.*

---

## 📜 License

This repository is shared under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.  
You are free to share and adapt the materials, provided appropriate credit is given.

[![CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

---

## 📬 Contact

For questions regarding methodology, data, or supplementary materials, please contact the corresponding author through the **IJIM journal submission system**.  
Author details are withheld pending double-blind peer review.

---

<div align="center">

*This repository is maintained as part of an active peer-review submission.*  
*All figures comply with Elsevier/IJIM artwork standards (≥ 300 dpi, single-column format).*

</div>
