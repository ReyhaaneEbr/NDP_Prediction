# 🧠 NDP_Prediction
Integrating Protein Sequence and PPI Networks for Neurodegenerative Disease Protein Discovery

---

## 📌 Overview

GAT‑T5 is a graph-based deep learning framework designed to identify Neurodegenerative Disease‑associated Proteins (NDPs) by jointly integrating protein–protein interaction (PPI) network topology and protein sequence-derived embeddings.

Neurodegenerative diseases (NDs) are characterized by progressive neuronal dysfunction and abnormal protein aggregation. While experimental identification of disease-associated proteins is costly and time-consuming, existing computational approaches largely rely on PPI network topology alone, overlooking informative sequence-level characteristics. To address this limitation, GAT‑T5 combines graph attention networks (GAT) to model PPI structure and ProtT5 protein language model embeddings to capture sequence-level biological information. This integrated representation enables more accurate and biologically meaningful prediction of ND-related proteins.

The framework focuses on four major neurodegenerative diseases:

 Alzheimer’s Disease (AD)
 Parkinson’s Disease (PD)
 Huntington’s Disease (HD)
 Amyotrophic Lateral Sclerosis (ALS)

---

## 🧪 Data Collection & Labeling

### 🧬 Disease-Associated Proteins

- Disease–gene associations were retrieved from **DisGeNET**
- Disease-specific proteins were curated for AD, PD, HD, and ALS
- Gene identifiers were mapped to **UniProtKB IDs** using the **UniProt ID Mapping API**

### 🧫 Housekeeping Proteins

- Housekeeping proteins were selected as negative controls
- Labels:
  - `1` → Disease-associated protein  
  - `0` → Housekeeping protein  

✅ The final labeled dataset is stored as:

data/dataset.xlsx

## ▦ Feature Representation

### 🧫 Protein Sequence Embeddings

- Protein sequences were encoded using **ProtT5 (Rostlab)**
- Each protein sequence is represented as a **1024-dimensional embedding**
- Mean pooling was applied over residue-level embeddings to obtain a fixed-length vector per protein

### 🧩 Graph Construction

- Nodes represent proteins
- Edges represent protein–protein interactions (PPI)
- Node features correspond to ProtT5 embeddings

---

## 🏛️ Model Architecture

GAT‑T5 is built upon a Graph Attention Network (GAT) architecture:

- 🔹 Input layer: 1024‑dimensional ProtT5 embeddings
- 🔹 Hidden layers: Multi‑head self‑attention over the PPI graph
- 🔹 Output layer: Binary classification (NDP vs. Housekeeping)
- 🔹 Attention mechanism: Highlights disease‑informative proteins and interactions
By explicitly modeling both sequence and network information, GAT‑T5 captures complementary biological signals essential for ND protein identification.

---

## ⚙️ Training Pipeline

- 🧬 Load protein embeddings
- 🌐 Construct the PPI graph
- 📈 Train the GAT model
- 📊 Evaluate performance using standard classification metrics

---

## 📊 Evaluation Metrics

- ✅ Accuracy
- ✅ Precision
- ✅ Recall
- ✅ F1-score
- ✅ ROC-AUC

---
💊 Drug Repurposing Analysis
Using the predicted ND‑associated proteins:

Candidate proteins were mapped to known drugs in DrugBank
Several predicted proteins are linked to existing approved or experimental drugs
These findings highlight immediate opportunities for drug repurposing in neurodegenerative diseases
