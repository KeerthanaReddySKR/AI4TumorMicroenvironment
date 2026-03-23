# AI4TumorMicroenvironment
Decoding tumor microenvironment using single-cell RNA sequencing and deep learning. This project integrates bioinformatics, machine learning, and AI to identify cellular heterogeneity, classify cell types, and uncover tumor-immune interactions.
# 🧬 AI4TumorMicroenvironment

### Understanding Tumor Cells Using AI + Single-Cell RNA Sequencing

---

## 🚀 What did we actually do?

In simple terms 👇

👉 Tumors are made of **many different types of cells** (immune cells, cancer cells, etc.)
👉 Using **single-cell RNA sequencing (scRNA-seq)**, we can study each cell individually

But…

❌ The data is **huge (400K+ cells)**
❌ Hard to analyze manually

---

### 💡 So what did we do?

We built an **AI-powered pipeline** that:

1. 📥 Loads large scRNA-seq data
2. 🧹 Cleans and processes it
3. 🔍 Identifies different cell types
4. 🧠 Uses deep learning to learn better features
5. 🤖 Trains a model to classify cell types
6. 📊 Compares:

   * Traditional method (**PCA**)
   * AI-based method (**Autoencoder**)

---

## 🧠 Why is this important?

👉 Helps understand **tumor microenvironment (TME)**
👉 Improves **cell-type classification**
👉 Supports **cancer research + drug discovery**

---

## 🔥 Key Idea

Instead of using normal statistical features (PCA),
we used **deep learning (Autoencoder)** to learn hidden patterns in the data.

👉 Then we checked:

“Does AI give better features than traditional methods?”

---

## 📊 Final Result (Simple)

Both methods performed very well, but:

👉 **Latent (AI) features captured biological patterns better**

---

## ⚠️ Real-world note

This is a research-style project, so:

> Further validation on independent datasets is required.

---

## 📦 What makes this project strong?

✔ Handles very large biological data
✔ Combines Bioinformatics + AI
✔ Uses deep learning (not just basic ML)
✔ Fully reproducible setup
✔ Clean project structure

---

## 🧪 Tech Stack

* Python
* Scanpy (scRNA-seq analysis)
* PyTorch (Deep Learning)
* Scikit-learn (ML)

---

## ▶️ How to Run

```bash
conda env create -f environment.yml
conda activate scRNA_env
python notebooks/01_pipeline.py
```

---

## 👩‍💻 Author

**Keerthana Reddy**
Bioinformatics Student | AI + Genomics

---
