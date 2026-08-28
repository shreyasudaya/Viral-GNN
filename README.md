# Frequency Chaos Game Representation–Based Deep Learning for SARS-CoV-2 Variant Classification
By Sunil Kumar, Shreyas Udaya, Harsha N.P., Kiran Reddy R, Biswajit Bhowmik.


![image](https://github.com/user-attachments/assets/656ad792-ff95-4844-89e1-91c94b75ffcc)

This repository contains the source code, prepared datasets, feature representations, accession-level information, and experimental resources associated with the study: **“Frequency Chaos Game Representation–Based Deep Learning for SARS-CoV-2
Variant Classification.”**

The repository is intended to support transparency and reproducibility of the experiments reported in the associated manuscript.

---

## Repository Contents

The repository contains the following principal resources:

| Resource | Description |
|---|---|
| `gnn_classifier.ipynb` | GNN model implementation, training, and evaluation |
| `splitset.py` | Dataset splitting procedure |
| `final_accession_list_FINAL.csv` | Accession-level information for the dataset |
| `Dataset/` | Prepared FCGR, k-mer, and one-hot feature representations |
| `Feature Ext/` | Feature extraction and preprocessing scripts |
| `Result/` | Experimental results |
| `log.txt` | Experimental/training log |
| `requirements.txt` | Python package dependencies |
| `preprocessing_flow_table_FINAL 3.numbers` | Preprocessing workflow documentation |

---

## Requirements
Pytorch,
Seaborn,
Torch Geometric,
Matplotlib,
Sklearn,
Torchvision

## Dataset

The study uses **9,234 SARS-CoV-2 genomic nucleotide sequences** distributed across 11 variant classes:

- B.1.1.519
- B.1.1.529 (Omicron)
- B.1.1.7 (Alpha)
- B.1.351 (Beta)
- B.1.427
- B.1.429
- B.1.525
- B.1.526
- B.1.621
- C.37 (Lambda)
- P.1 (Gamma)

The original genomic sequences were obtained from the **NCBI Virus SARS-CoV-2 Data Hub**: [https://www.ncbi.nlm.nih.gov/labs/virus/vssi/](https://www.ncbi.nlm.nih.gov/labs/virus/vssi/#/virus?SeqType_s=Nucleotide&VirusLineage_ss=Severe%20acute%20respiratory%20syndrome%20coronavirus%202,%20taxid:2697049&Lineage_s=B.1.1.519&Lineage_s=B.1.1.7&Lineage_s=B.1.1.529&Lineage_s=B.1.351&Lineage_s=B.1.427&Lineage_s=B.1.429&Lineage_s=B.1.525&Lineage_s=B.1.526&Lineage_s=C.37&Lineage_s=P.1&Lineage_s=B.1.621&HostLineage_ss=Homo%20sapiens,%20taxid:9606&Completeness_s=complete)

The accession-level information associated with the dataset is provided in: `final_accession_list_FINAL.csv`

---


## FCGR Dataset

Frequency Chaos Game Representation (FCGR) heatmaps were generated using \(k=3\). The prepared FCGR dataset used in the experiments is available at: https://www.kaggle.com/datasets/shreyasudaya/fcgr-covid-variants. The FCGR dataset follows the **75:25 training/validation split** adopted in the study.

---

## Feature Representations

The repository contains the following feature representations:

1. One-hot encoding
2. k-mer representation
3. Frequency Chaos Game Representation (FCGR)

The corresponding feature-extraction scripts are located in:

```text
Feature Ext/
├── kprocheatmap.py
├── kproc.py
└── proc.py

```

## Implementation

The framework evaluates multiple graph neural network architectures, including Vision GCN, GraphSAGE, Graph U-Net, EdgeCNN, and GAT. The
architectures use the FCGR-derived feature representations and the corresponding graph construction procedure described in the manuscript.

Hyperparameter tuning is performed before the final evaluation. After selection of the final configuration, the models are evaluated using
five independent runs with different random seeds.

## Evaluation and Train Code

Data preparation follows the algorithm

- Run code:
    1. Take gnn-classifier.ipynb either on colab or kaggle
    2. Select a GPU runtime.
    3. Ensure that the required dataset paths are correctly configured.
    4. Run the notebook to reproduce the feature extraction, graph construction, model training, and evaluation procedures.



## Directory Structure

The dataset is also available in the directory Dataset, which consists of k-mers, one-hot, and FCGR heatmap encoded feature extractions. Alongside this is Feature Ext, which contains the files in order to extract the feature and convert it.

```

project/
│
├── Dataset/
│   ├── FCGR/
│   ├── kmer/
│   └── one-hot/
│
├── Feature Ext/
│   ├── kprocheatmap.py
│   ├── kproc.py
│   └── proc.py
│
├── Result/
│
├── .gitignore
├── README.md
├── final_accession_list_FINAL.csv
├── gnn_classifier.ipynb
├── log.txt
├── preprocessing_flow_table_FINAL 3.numbers
├── requirements.txt
└── splitset.py
```
