Upper-Bound Functional Group Capacity in DOM via FT-ICR MS/MS and Graph-Based Analysis
Overview

Dissolved organic matter (DOM) comprises one of the most complex molecular mixtures in the environment, yet its reactivity is governed by the distribution of functional groups embedded within individual molecules. This repository provides a reproducible computational framework to quantify upper-bound oxygen-containing functional group capacities across DOM using FT-ICR MS/MS data coupled with a graph-based traversal algorithm.

The workflow integrates precursor selection, MS/MS filtering, neutral-loss matching, and breadth-first search (BFS)–based network analysis to resolve how molecular structure and oxygen functionality vary as a function of mass across diverse environmental samples.

Conceptual Approach

The pipeline is based on three core principles:

1. Mass-resolved precursor selection:
Target precursor ions are extracted within defined m/z tolerance windows from FT-ICR MS datasets.
2. Neutral-loss–driven structural inference:
MS/MS fragment relationships are interpreted through matching of observed mass differences to a curated list of chemically meaningful neutral losses.
3. Graph-based traversal of fragmentation space:
A breadth-first search (BFS) algorithm reconstructs all accessible fragmentation pathways, enabling:

     identification of connected molecular sub-networks
      
      quantification of transformation frequencies
        
      evaluation of functional group expression limits

This framework allows estimation of formula-specific upper bounds on oxygen functionality, providing insight into convergent structural constraints in DOM across environmental gradients.

Input Data Requirements
1. FT-ICR MS (precursor data)

CSV file containing at minimum:

Measured Mass — observed m/z values

Group — molecular classification (e.g., CHO, CHOS)

2. MS/MS datasets
   
m/z — fragment masses

S/N — signal-to-noise ratio

3. Neutral loss library
   
mf — neutral-loss mass

Formula — chemical assignment




Workflow

Step 1 — Precursor Extraction

Identifies target precursor ions within a defined tolerance window.

Step 2 — Molecular Filtering

Restricts analysis to specific compositional classes (e.g., CHO-only).

Step 3 — MS/MS Filtering

Removes:

fragments above precursor mass
low signal-to-noise peaks below threshold
Step 4 — Graph Construction (BFS)

Constructs a directed network where:

nodes = fragment masses
edges = neutral-loss transformations

Step 5 — Transformation Analysis

Quantifies all pairwise mass differences and maps them to known chemical transformations.

Step 6 — Pathway Analysis

Identifies:

maximum CO₂ loss pathways (Sequential)

variant CO₂ fragmentation routes (Non-sequential)

Output

The pipeline generates:

Precursor datasets
Filtered MS/MS spectra
Fragmentation networks (edge lists)
Unique mass distributions
Transformation tables (mass differences + formulas)
Functional group statistics
CO₂ pathway analyses

All outputs are saved as .csv files for downstream statistical and visualization workflows.
