# Combinatorial Virtual Library: Design, Chemical Space Analysis & Property Prediction

**M1 Research Internship Project** — UFAZ / Université de Strasbourg partnership, April–June 2026  
Supervised by Dr. Farah Asgarkhanova

## Overview

This project implements an end-to-end computational pipeline for the design and evaluation 
of a focused combinatorial chemical library. Starting from a curated set of building blocks, 
it enumerates drug-like molecules, maps their distribution in high-dimensional chemical 
space, and evaluates a target property using an ensemble QSPR model — without any 
predefined knowledge of which structural features will matter.

The pipeline demonstrates the full cycle: from raw molecular data → descriptor generation → 
unsupervised space mapping → supervised property prediction → applicability domain analysis.

## Pipeline
ChEMBL (>1M structures)

>
Building block curation
(RDKit Morgan fingerprint similarity → 470 prioritised scaffolds)

>
Library enumeration
(Synt-On reaction-based enumeration → 1,047 drug-like molecules)

>
Chemical space mapping
(Bemis–Murcko scaffold analysis + Generative Topographic Mapping)

>
Property prediction
(ISIDA fragment descriptors → ensemble QSPR model for skin permeability)

>
Applicability domain analysis
(88.7% coverage · scaffold–property trade-off analysis)


## Key results

| Step | Result |
|------|--------|
| ChEMBL structures curated | >1,000,000 |
| Building blocks prioritised | 470 |
| Library size (enumerated) | 1,047 molecules |
| Applicability domain coverage | 88.7% |

## Why Generative Topographic Mapping?

GTM projects a high-dimensional descriptor space onto a 2D grid in a principled, 
probabilistic way — without requiring a predefined order parameter or clustering criterion. 
Each molecule gets a position on the map based purely on its descriptor vector. 
This makes it possible to identify structural diversity, detect redundancy, and spot 
outliers in a library without knowing in advance which features will separate clusters. 
The approach is analogous to dimensionality reduction techniques used in polymer simulation 
analysis (e.g., for scattering profiles or trajectory embeddings) where no obvious 
collective variable exists.

## Repository structure
├── data/ Raw and processed molecular data
├── notebooks/ Jupyter notebooks (pipeline steps, analysis, visualisation)
├── results/ Output files: enumerated library, GTM maps, QSPR predictions
├── workflows/knime/ KNIME workflow files for descriptor generation and filtering
└── .gitignore


## Tools & dependencies

| Tool | Purpose |
|------|---------|
| Python (NumPy, Pandas, Matplotlib, Seaborn) | Data processing and visualisation |
| RDKit | Molecular manipulation, Morgan fingerprints, Bemis–Murcko scaffolds |
| Synt-On | Reaction-based combinatorial library enumeration |
| KNIME | Workflow automation for descriptor generation and filtering |
| ISIDA | Fragment-based molecular descriptor generation for QSPR |
| GTM | Generative Topographic Mapping for chemical space visualisation |

## Context

Developed as an M1 research internship project within the UFAZ–Université de Strasbourg 
double-degree programme. The methods (descriptor-based property prediction, unsupervised 
space mapping, applicability domain analysis) are general and transferable to any 
molecular or materials design context where structure–property relationships need to 
be learned from data.
