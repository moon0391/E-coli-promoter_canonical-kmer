# Canonical k-mer Encoding for E. coli Sigma70 Promoter Classification

Code and results accompanying our APBC 2026 submission, *"Canonical k-mer Encoding Resolves the Accuracy–Strand-Consistency Trade-off in Machine Learning Classification of E. coli Sigma70 Promoters."*

## Overview
We classify *E. coli* Sigma70 promoters using a balanced dataset of 1,416 sequences (708 confirmed promoters from RegulonDB, 708 non-promoter genomic fragments). We compare standard 4-mer frequency features against canonical, reverse-complement-symmetric 4-mer features, showing the latter achieves 100% strand-consistency without sacrificing accuracy, and use SHAP to confirm the resulting models learn biologically meaningful signal.

## Contents
- `Canonical k-mer Encoding for E. coli Sigma70 Promoter Classification.ipynb` — full pipeline: feature engineering (4 tracks), model training (LR/SVM/RF), evaluation (Accuracy/F1/MCC/AUROC/RC-consistency), McNemar's test, SHAP interpretability, error analysis
- `final_results_table.csv` — final metrics for all model × feature-track combinations
- `figures/` — all result figures (accuracy–RC trade-off, SHAP importance, error heatmaps, etc.)
- `regulondb promoterset-custom dataset/` — dataset files (RegulonDB-derived promoter/non-promoter sequences)

## Dataset
Positive sequences: RegulonDB v12.0, Sigma70 promoters, Confirmed/Strong evidence.
Negative sequences: random 81 bp windows from *E. coli* K-12 MG1655 (NCBI U00096.3), excluding a ±200 bp zone around known transcription start sites.

## Requirements
```
scikit-learn, numpy, pandas, matplotlib, seaborn, shap, statsmodels, logomaker
```

## Citation
If you use this code or dataset, please cite our paper (details to be added upon publication).

## Authors
Sumaiya Akhter Moon,Alok Sarker Amit — Department of Computer Science, BRAC University, Dhaka, Bangladesh.
