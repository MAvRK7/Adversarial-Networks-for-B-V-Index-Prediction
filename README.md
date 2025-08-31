# 🌌 Adversarial Networks for B‑V Index Prediction

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)]() [![Framework](https://img.shields.io/badge/Framework-PyTorch%20%7C%20Scikit--Learn-orange)]() [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)]()

## 📌 Overview
This project explores **three adversarial deep learning frameworks**:  
- **Generative Adversarial Networks (GANs)**  
- **Conditional GANs (CGANs)**  
- **Contrastive GANs (ContraGANs)**  

The goal is to generate **synthetic astronomical data** for predicting the **B‑V colour index**, a key stellar classification metric.  
We evaluate how advanced adversarial techniques can improve **data quality, predictive accuracy, and statistical alignment** in scientific datasets.

---

## 🧪 Methodology
Models were trained and evaluated on an astronomical dataset (`apass9_cleaned.csv`) using:

- **Predictive Accuracy**: Mean Squared Error (MSE), R² Score  
- **Clustering Quality**: Silhouette Score, Calinski‑Harabasz Score, Davies‑Bouldin Score  
- **Statistical Alignment**: Wasserstein Distance, Kolmogorov‑Smirnov Statistic  

---

## 📊 Key Results

| Model       | MSE     | R²     | Silhouette | Calinski‑Harabasz | Davies‑Bouldin |
|-------------|---------|--------|------------|-------------------|----------------|
| **ContraGAN** | **0.1250** | **0.7320** | **0.3723** | **272.0709** | **1.0491** |
| CGAN        | Higher MSE, lower clustering scores than ContraGAN, but strong overall performance due to feature conditioning |
| GAN         | Weakest performance across all metrics |

**Highlights:**
- **ContraGAN** significantly outperformed both GAN and CGAN across all evaluation metrics.
- **CGAN** benefited from conditioning on input features, improving predictive accuracy over standard GANs.
- **Standard GANs** struggled with both prediction and clustering quality.

---

## 🚀 Key Takeaways
- **Contrastive learning + conditional generation** can dramatically improve synthetic data quality in scientific applications.
- The approach is **transferable** to other domains where labelled data is scarce or expensive to obtain.
- Demonstrates **end‑to‑end ML workflow**: data preprocessing, model design, training, evaluation, and result interpretation.

---

## 📂 Repository Structure
- `CAN_GAN.ipynb` — Full implementation of GAN, CGAN, and ContraGAN experiments  
- `apass9_cleaned.csv` — Original cleaned astronomical dataset  

---

## 💡 Skills Demonstrated
- Deep learning model development (PyTorch/TensorFlow)
- Adversarial training techniques (GAN, CGAN, ContraGAN)
- Statistical and clustering evaluation
- Scientific data preprocessing and feature engineering
- Research‑driven experimentation and result analysis

---

## 📈 Potential Applications
- Astronomical data augmentation for rare object detection
- Synthetic dataset generation for low‑resource scientific fields
- Industrial predictive modelling with limited labelled data
