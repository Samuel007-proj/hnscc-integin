# Multi-Target Oncology SBVS Campaign

**Structure-Based Virtual Screening for novel small-molecule chemotypes against KRAS G12D • PRMT5 (MTA-cooperative) • TEAD • SMARCA2**

---

## Overview

This repository documents a multi-target **Structure-Based Virtual Screening (SBVS)** campaign aimed at discovering novel, patentable small-molecule chemotypes against four high-value oncology targets:

| Target | Rationale |
|--------|-----------|
| **KRAS G12D** | Mutant-selective inhibition; avoid over-reliance on strongly basic amines |
| **PRMT5 (MTA-cooperative)** | Exploit MTA-cooperative binding while avoiding arylamine liabilities |
| **TEAD** | Palmitoylation-pocket / drug-like binders with improved properties |
| **SMARCA2** | Selective, orally tractable ligands suitable for degrader design |

**Strategy:** Generate a diversified portfolio of *target-specific* novel chemotypes (not one pan-target molecule), filter heavily patented scaffolds, and prioritise compounds with favourable predicted ADME properties. Expected output: ~40–80 prioritised hit candidates (~10–20 per target).

---

## Repository structure

```
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── cohort_1_seeds.csv          # Seed ligands per chemotype (K1, P1, P2, T1, S1, …)
│   ├── pdbs.txt                    # PDB / CIF IDs used for each target
│   └── jm2c01548_si_002.csv        # Supporting ligand data
├── scripts/
│   ├── ligand_retrieval.py         # ChEMBL + PubChem similarity / substructure expansion
│   └── validations.py              # Crystal ligand clean-up, Smina minimisation, RMSD
├── notebooks/
│   ├── Lig_Prep.ipynb
│   ├── Ligands_retrieval.ipynb
│   ├── ligand_conv.ipynb
│   ├── validation_runs.ipynb
│   └── validation_runs_refactored.ipynb
└── docs/
    └── project_overview.md         # Condensed project proposal summary
```

> Large structure files (PDB/CIF, prepared receptors, full cohort libraries) are kept offline / on Drive to keep this repo lightweight. Paths in the scripts assume a local `PDBs/` and `Ligands/` layout matching the working project folder.

---

## Methods (high level)

1. **Structure selection** — Target-specific PDB/CIF structures (see `data/pdbs.txt`):
   - KRAS G12D: 9TC5 (GDP), 7EWA (GTP)
   - PRMT5: 9ZL3
   - TEAD: 8Q68, 6UYB, …
   - SMARCA2: 6HAZ

2. **Ligand expansion** — Seed chemotypes expanded via ChEMBL similarity/substructure and PubChem 2D similarity (`scripts/ligand_retrieval.py`, RDKit canonicalisation, ~500 analogues per cohort).

3. **Validation / docking setup** — Co-crystal ligand cleaning, Open Babel PDBQT conversion, Smina local minimisation, heavy-atom RMSD vs crystal pose (`scripts/validations.py`).

4. **Downstream (in progress)** — Virtual screening, pose filtering, ADME/novelty filters, and prioritisation of novel hit matter.

---

## Setup

```bash
# Recommended: conda or venv
pip install -r requirements.txt
```

**Key Python dependencies:** RDKit, pandas, requests, chembl-webresource-client, Jupyter.

---

## Related documents

Full project proposal, literature review, and research report (Word) live in the project Drive folder and are summarised in `docs/project_overview.md`.

---

## Licence

Research code for academic / portfolio use. Please cite this repository if you reuse methods or scripts. Structure files and compound data remain subject to their original sources (PDB, ChEMBL, PubChem, literature).
