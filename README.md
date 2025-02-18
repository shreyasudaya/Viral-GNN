# COVID-19 Variant Classification Using GNN
By Sunil Kumar, Shreyas Udaya, Harsha N.P., Kiran Reddy R.


![image](https://github.com/user-attachments/assets/656ad792-ff95-4844-89e1-91c94b75ffcc)

This code implements a deep learning model for classifying COVID-19 variants using DNA sequences. The GNN model is specified in the gnn_classifier.ipynb file. Training is conducted using the train_test_split function from the sklearn.model_selection module in the splitset.py file, while the dataset is loaded through the kprocheatmap.py file.



## Requirements
Pytorch,
Seaborn,
Torch Geometric,
Matplotlib,
Sklearn,
Torchvision

## Dataset
The dataset comprises 10,334 complete genomic sequences of SARS-CoV-2, spanning 11 distinct variants. The DNA sequences are stored in the data/genomic.fna files. The dataset can be accessed from the NCBI website (https://www.ncbi.nlm.nih.gov/) by using the following keywords SARS-CoV-2 in the search.

B.1.1.519, B.1.1.529 (Omnicron), B.1.1.7 (Alpha), B.1.351 (Beta), B.1.427, B.1.429, B.1.525, B.1.526, B.1.621, C.37 (Lambda), P.1 (Gamma).

## Dataset Preparation and Feature Extraction
Preprocessing steps, including data cleaning, formatting, and organization, were performed to ensure high-quality input for model training. The NCBI dataset initially contained 10,334 samples, which, after preprocessing, was reduced to 9,234 nucleotide sequences. Each genomic sequence is represented as a string comprising four nucleotide bases: A, C, G, and T. To facilitate feature extraction, the dataset was encoded using three distinct methods: one-hot encoding, K-mers, and Frequency Chaos Game Representation (FCGR) heatmaps. These transformations were applied to 11 COVID-19 variants stored in the Dataset folder. The Feature Ext folder contains the corresponding extracted features, which are loaded by the code to support conversion into various encoding formats.

## Used FCGR Heatmap Encoded
The Dataset consists of FCGR Encoded heatmap (K=3) images split into the image-net format, i.e., split into the train and test directories in the ratio of 3:1 for train and test. A separately prepared FCGR Heatmap split dataset can be found at https://www.kaggle.com/datasets/shreyasudaya/fcgr-covid-variants. 

## Implementation
Various Graph Neural Network (GNN) models, including Graph Convolution Networks (GCN), GraphSAGE, GraphUNet, EdgeCNN, and Graph Attention Transformer (GAT), were implemented and evaluated. Each model was executed 10 times to optimize performance through fine-tuning.

## Evaluation and Train Code

Data preparation follows the algorithm

- Run code:
    1. Take gnn-classifier.ipynb either on colab or kaggle
    2. Run the notebook and convert runtime type to GPU


## Directory Structure

The dataset is also available in the directory Dataset, which consists of k-mers, one-hot, and FCGR heatmap encoded feature extractions. Alongside this is Feature Ext, which contains the files in order to extract the feature and convert it.

```
project
│   README.md
│   gnn_classifier.ipynb
|   splitset.py    
│
└───Dataset
│   │   
│   └───FCGR
|   └───kmer  
│   └───one-hot    
│        
└───Feature Ext
    │   kprocheatmap.py
    │   kproc.py
    |   proc.py
└───Result
```
