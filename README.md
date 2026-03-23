# AI4TumorMicroenvironment

### Deep Learning-Based Representation Learning for Cell-Type Classification in Tumor Microenvironment scRNA-seq Data

---

## 1. Problem Statement

The tumor microenvironment (TME) consists of heterogeneous cell populations whose composition critically influences cancer progression and therapeutic response.

Single-cell RNA sequencing (scRNA-seq) enables profiling at cellular resolution, but introduces challenges:

* High dimensionality (~20,000 genes)
* Large-scale datasets (400K+ cells)
* Complex, non-linear biological variability

Traditional linear methods (e.g., PCA) may fail to capture this structure effectively.

---

## 2. Objective

To evaluate whether **non-linear latent representations learned via deep learning** can improve cell-type classification compared to conventional dimensionality reduction techniques.

---

## 3. Methodology

### 3.1 Data Acquisition

* Dataset: Triple-Negative Breast Cancer (TNBC) scRNA-seq
* Source: CZ CELLxGENE
* Scale: ~427,000 cells

Due to memory constraints, analysis is performed using:

* Backed data loading (`scanpy`)
* Subsampling (20,000 cells)

---

### 3.2 Preprocessing Pipeline

The following standard scRNA-seq preprocessing steps were applied:

* Mitochondrial gene filtering
* Library size normalization
* Log-transformation
* Highly variable gene selection (2,000 genes)
* Z-score scaling

---

### 3.3 Unsupervised Analysis

* Principal Component Analysis (PCA)
* Neighborhood graph construction
* Leiden clustering
* UMAP visualization

Clusters were annotated using marker-based scoring.

---

### 3.4 Representation Learning

Two feature spaces were constructed:

#### (A) Linear Representation

* PCA embeddings

#### (B) Non-linear Representation

* Autoencoder (PyTorch-based)
* Learned latent embeddings

---

### 3.5 Classification Framework

* Model: Random Forest Classifier
* Input:

  * PCA features
  * Latent embeddings
* Evaluation:

  * Accuracy
  * Classification report (Precision, Recall, F1-score)

---

## 4. Results

Both representations achieved high classification accuracy:

| Feature Type | Accuracy |
| ------------ | -------- |
| PCA          | ~1.0     |
| Latent       | ~1.0     |

### Interpretation

Although classification performance appears comparable, latent representations:

* Capture non-linear gene expression structure
* Provide biologically meaningful embedding space
* Offer improved representation of cellular heterogeneity

---

## 5. Discussion

The comparable performance suggests that:

* For well-separated cell populations, PCA remains competitive
* However, deep learning embeddings provide a more expressive feature space

This becomes particularly relevant for:

* Rare cell populations
* Subtle transcriptional differences
* Cross-dataset generalization

---

## 6. Limitations

* Subsampling may reduce representation of rare cell types
* Evaluation limited to a single dataset
* No external validation performed

> Further validation across independent datasets is required to establish generalizability.

---

## 7. Reproducibility

### Environment Setup

```bash
conda env create -f environment.yml
conda activate scRNA_env
```

### Execution

```bash
python notebooks/01_pipeline.py
```

---

## 8. Project Structure

```text
AI4TumorMicroenvironment/
│
├── data/raw/                 # Input dataset (.h5ad)
├── notebooks/               # Main pipeline
├── results/                 # Outputs (figures, metrics)
├── src/                     # Modular code (future expansion)
├── environment.yml          # Conda environment
├── requirements.txt         # Pip dependencies
└── README.md
```

---

## 9. Technical Stack

* Scanpy (single-cell analysis)
* PyTorch (representation learning)
* Scikit-learn (classification)
* NumPy / Pandas (data handling)

---

## 10. Future Directions

* Cell–cell interaction analysis (ligand–receptor modeling)
* Integration with spatial transcriptomics
* Cross-cohort validation
* Graph-based deep learning (GNNs)

---

## 11. Author

Keerthana Reddy
B.Tech Bioinformatics

---

## 12. Summary

This work demonstrates a structured comparison between linear and non-linear representations in scRNA-seq analysis, highlighting the role of deep learning in capturing complex biological variability within the tumor microenvironment.

---
