# Project overview — Multi-Target Oncology SBVS

**Title:** Discovery of Novel Small-Molecule Chemotypes Against KRAS G12D • PRMT5 (MTA-cooperative) • TEAD • SMARCA2  

**Author:** Samuel Damilare Oyelami  
**Date:** October 2026  

## Executive summary

This campaign uses structure-based virtual screening (SBVS) to generate a diversified portfolio of novel, target-specific small-molecule chemotypes against four high-value oncology targets. It does **not** seek a single multi-target molecule; dual-target hits are welcomed only where they support rational combination strategies. Heavily patented scaffolds are filtered out. Expected deliverable: 40–80 prioritised hit candidates (~10–20 per target) with favourable predicted ADME and clear IP space.

## Problem context (selected)

- **KRAS G12D:** Many current inhibitors depend on strongly basic amines for Asp12 engagement → poor permeability, limited oral bioavailability, signalling rebound.
- **PRMT5 (MTA-cooperative):** Arylamine motifs drive metabolic clearance and N-nitrosamine concerns.
- **TEAD:** Excessive lipophilicity; incomplete degradation / isoform selectivity issues.
- **SMARCA2:** Selective inhibition hard; PROTACs often high MW / poor oral absorption.

## Research gaps addressed

- Limited chemical diversity beyond dominant scaffolds  
- Non-basic / lower-pKa solutions for KRAS G12D Asp12  
- MTA-cooperative PRMT5 chemotypes without arylamine liabilities  
- More drug-like TEAD binders and monovalent degrader approaches  
- Selective, orally tractable SMARCA2 ligands suitable for degrader design  

## Aim

Discover novel, drug-like small-molecule chemotypes against these four targets through a rigorous multi-target SBVS campaign, establishing a proprietary foundation for next-generation oncology therapeutics.

## Computational workflow (this repo)

1. Structure selection and preparation (PDB/CIF → cleaned / prepared receptors)  
2. Seed chemotype definition and library expansion (ChEMBL + PubChem + RDKit)  
3. Validation of docking protocol (crystal ligand RMSD after minimisation)  
4. Virtual screening, filtering (novelty, ADME, IP), and prioritisation *(ongoing)*  

See repository `scripts/` and `notebooks/` for implementation details.
