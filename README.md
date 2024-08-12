# Biological Sequence Prediction Using Transformers

## Authors

- [ShirelSch](https://github.com/ShirelSch)
- [Talya88](https://github.com/Talya88)

**Project Overview**

This project explores the application of transformer models in the field of biology. We utilized transformers to analyze various biological datasets and predict outcomes based on molecular and protein sequences. The transformer models used in this project include ChemBERTa and ProtT5 from Hugging Face, as well as ProteinBERT developed by researchers at the Hebrew University.

**Table of Contents**

- [Introduction](#introduction)
- [Datasets and Experiments](#datasets-and-experiments)
  - [Chemical Toxicity Prediction](#chemical-toxicity-prediction)
  - [Molecular Solubility Prediction](#molecular-solubility-prediction)
  - [HIV Patient Outcome Prediction](#hiv-patient-outcome-prediction)
  - [Signal Peptide Classification](#signal-peptide-classification)
  - [Protein Family Classification](#protein-family-classification)
- [Results](#results)
- [Conclusion](#conclusion)

## Introduction

Transformers, originally designed for natural language processing tasks, have shown remarkable performance in understanding and generating human language. In this project, we extend their application to the biological domain, leveraging their ability to learn complex patterns and relationships in biological sequences. Our experiments span several tasks, including toxicity prediction, solubility prediction, patient outcome prediction, signal peptide classification, and protein family classification.

## Datasets and Experiments

### Chemical Toxicity Prediction

**Dataset:** Clintox  
**Description:** The dataset contains two columns: chemical molecules in SMILES format and a classification column indicating toxicity (1 for toxic, 0 for non-toxic).  
**Size:** 1184 molecules in the training set, 148 molecules in the test set.  
**Challenge:** The dataset is imbalanced, with significantly more non-toxic molecules than toxic ones.  
**Approach:** We used ChemBERTa, a BERT-based model adapted for chemical data, to learn from the molecular language without relying on clinical characteristics.  
**Results:** Achieved an accuracy of 96%, with a confusion matrix showing only 5 misclassifications.

### Molecular Solubility Prediction

**Dataset:** Solubility Data  
**Description:** Contains molecules in SMILES format with their solubility values in water.  
**Challenge:** Regression task to predict continuous solubility values.  
**Approach:** ChemBERTa was utilized to emphasize functional groups affecting solubility, such as hydroxyl or carboxyl groups.  
**Results:** Achieved an R² score of 0.88, explaining 88% of the variance in solubility.

### HIV Patient Outcome Prediction

**Dataset:** Kaggle HIV Progression Prediction  
**Description:** The task is to predict which HIV patients will improve (1) and which will not (0). The dataset includes PR and RT sequences and clinical data.  
**Challenge:** Transforming nucleotide sequences to protein sequences and combining them with clinical data.  
**Approach:** We used ProtT5 to extract embeddings for the sequences and applied machine learning models to evaluate their contribution to clinical features.  
**Results:** The dataset was highly skewed, and the results showed limited improvement over using clinical data alone.

### Signal Peptide Classification

**Dataset:** Signal Peptides  
**Description:** The goal is to classify protein sequences as signal peptides (1) or non-signal peptides (0).  
**Challenge:** Handling large amounts of data and emphasizing sequence regions related to signal peptides' functions.  
**Approach:** We used ProtT5 for embedding the sequences and performed PCA for dimensionality reduction.  
**Results:** Achieved an accuracy of 98%, demonstrating clear separation of the two categories. Comparisons with ProteinBERT yielded similarly high accuracy.

### Protein Family Classification

**Dataset:** Protein Families  
**Description:** Classify protein sequences into one of seven families.  
**Challenge:** Initial embedding and dimensionality reduction produced suboptimal accuracy.  
**Approach:** Using ProtT5 for embeddings and PCA initially resulted in 0.29 accuracy, while switching to ProteinBERT improved accuracy to 0.88.  
**Results:** Significant improvement with ProteinBERT, highlighting its effectiveness for this task.

## Results

The transformer models demonstrated high accuracy and strong performance across various biological prediction tasks. The ability to understand and predict outcomes based solely on sequence data showcases the potential of transformers in biological research.

## Conclusion

This project underscores the versatility and power of transformer models in biological sequence analysis. By leveraging pre-trained models like ChemBERTa, ProtT5, and ProteinBERT, we achieved notable results in toxicity prediction, solubility prediction, patient outcome prediction, signal peptide classification, and protein family classification.

The project is being conducted by Shirel Schreiber and Talya Herrmann.
