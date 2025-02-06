# COVID-19 Variant Classification Using GNN
By Shreyas Udaya, Harsha N.P., Kiran Reddy R, Sunil Kumar.


![image](https://github.com/user-attachments/assets/656ad792-ff95-4844-89e1-91c94b75ffcc)

This code implements a deep learning model for classifying COVID-19 variants using DNA sequences. The GNN model is specified in the gnn_classifier.ipynb file. Training is conducted using the train_test_split function from the sklearn.model_selection module in splitset.py file, while the dataset is loaded through the kprocheatmap.py file.

## Requirements
Pytorch,
Seaborn,
Torch Geometric,
Matplotlib,
Sklearn,
Torchvision




## Dataset
The dataset utilized for training and testing the model comprises 10,334 complete genomic sequences of SARS-CoV-2, spanning 11 distinct variants. The DNA sequences are stored in the data/genomic.fna files. The dataset can be accessed from the NCBI website (https://www.ncbi.nlm.nih.gov/) by using the following keywords in the search.

B.1.1.519, B.1.1.529 (Omnicron), B.1.1.7 (Alpha), B.1.351 (Beta), B.1.427, B.1.429, B.1.525, B.1.526, B.1.621, C.37 (Lambda), P.1 (Gamma).

## Dataset Preparation and Feature Extraction
To ensure high-quality data for model training, preprocessing steps such as data cleaning, formatting, and organization were performed. In genomic sequence encoding, nucleotide sequences are represented as character strings consisting of A, C, G, and T. The dataset was preprocessed using one-hot encoding, K-mers, and FCGR-encoded heatmaps for 11 different SARS-CoV-2 variants available in the Dataset folder. The Feature Ext folder contains the respective feature, which is loaded through the code to facilitate conversion into different encoding formats. 

## Used
The Dataset consists of FCGR Encoded heatmap (K=3) images split into the image-net format, i.e., split into the train and test directories in the ratio of 3:1 for train and test. A separately prepared FCGR Heatmap split dataset can be found at https://www.kaggle.com/datasets/shreyasudaya/fcgr-covid-variants. 

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
```
