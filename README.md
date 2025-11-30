# NDP_Prediction

Prediction of Neurodegenerative Disease–Associated Proteins using Graph Attention Networks (GAT)

## Overview
This repository contains the code and datasets used to identify proteins associated with major neurodegenerative diseases (NDs), including Alzheimer’s disease (AD), Parkinson’s disease (PD), Huntington’s disease (HD), and Amyotrophic Lateral Sclerosis (ALS).  
The core model is a Graph Attention Network (GAT) trained on sequence‑based embeddings and network‑derived features.

## Data Acquisition Summary
Gene lists for AD, PD, HD, and ALS were retrieved from DisGeNET (curated disease–gene associations).

Each gene set was mapped to UniProtKB using the UniProt ID Mapping API (gene → UniProtKB).

Housekeeping proteins were obtained from a curated housekeeping gene resource and mapped to UniProt in the same manner.

Only human proteins were retained across all sets.

Final labels:  
• label = 1 → disease‑associated proteins  
• label = 0 → housekeeping proteins

Final CSV files included in this repository: `data/dataset.xlsx`
