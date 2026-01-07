# 🧠 NDP_Prediction
Graph Attention Network for Neurodegenerative Disease Protein Classification

---

## 📌 Overview

NDP_Prediction is a graph-based deep learning project that applies **Graph Attention Networks (GAT)** to identify **Neurodegenerative Disease‑Related Proteins (NDPs)**.

The model distinguishes disease-related proteins from **Housekeeping proteins**, focusing on four major neurodegenerative diseases:

-  Alzheimer’s Disease (AD)
-  Parkinson’s Disease (PD)
-  Huntington’s Disease (HD)
-  Amyotrophic Lateral Sclerosis (ALS)

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

The prediction model is based on a **Graph Attention Network (GAT)**:

- 🔹 Input layer: ProtT5 embeddings (1024 features)
- 🔹 Hidden layers: Multi-head self-attention
- 🔹 Output layer: Binary classification (NDP vs. Housekeeping)
- 🔹 Attention mechanism highlights disease-informative proteins

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

