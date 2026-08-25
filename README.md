# Frequency Chaos Game Representation–Based Deep Learning for SARS-CoV-2 Variant Classification
By Sunil Kumar, Shreyas Udaya, Harsha N.P., Kiran Reddy R, Biswajit Bhowmik.


![image](https://github.com/user-attachments/assets/656ad792-ff95-4844-89e1-91c94b75ffcc)

This code implements a deep learning framework for SARS-CoV-2 variant classification using genomic nucleotide sequences. The GNN implementation
is provided in `gnn_classifier.ipynb`. Data splitting and preprocessing are implemented through the corresponding Python scripts and notebooks
provided in this repository.


## Requirements
Pytorch,
Seaborn,
Torch Geometric,
Matplotlib,
Sklearn,
Torchvision

## Dataset

The dataset comprises 9,234 complete SARS-CoV-2 genomic sequences spanning 11 distinct variant classes. The genomic nucleotide sequences are stored
in the `data/genomic.fna` files. The original genomic sequences can be accessed through the NCBI repository (https://www.ncbi.nlm.nih.gov/) using SARS-CoV-2-related search terms.

The evaluated variant classes are:

B.1.1.519, B.1.1.529 (Omicron), B.1.1.7 (Alpha), B.1.351 (Beta), B.1.427, B.1.429, B.1.525, B.1.526, B.1.621, C.37 (Lambda), P.1 (Gamma).

## Dataset Preparation and Feature Extraction

Preprocessing steps, including data cleaning, formatting, and organization, were performed to prepare the genomic nucleotide sequences for model
processing. Each genomic sequence is represented using the nucleotide alphabet A, C, G, and T. Feature representations include one-hot encoding,
k-mer representations, and Frequency Chaos Game Representation (FCGR) heatmaps. These representations are organized according to the 11
SARS-CoV-2 variant classes stored in the Dataset folder. The Feature Ext folder contains the corresponding extracted features, which are loaded by the code to support conversion into various encoding formats.

## Used FCGR Heatmap Encoded

The dataset consists of FCGR-encoded heatmap images generated using \(k=3\). The FCGR dataset is organized into training and validation
directories using the adopted 75:25 split.

A separately prepared FCGR heatmap dataset is available at: https://www.kaggle.com/datasets/shreyasudaya/fcgr-covid-variants.

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

project
│   README.md
│   gnn_classifier.ipynb
│   splitset.py
│
├── Dataset
│   ├── FCGR
│   ├── kmer
│   └── one-hot
│
├── Feature Ext
│   ├── kprocheatmap.py
│   ├── kproc.py
│   └── proc.py
│
└── Result

└───Result
```
