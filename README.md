# 🌌 Adversarial Networks for B‑V Index Prediction

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)]()
[![Framework](https://img.shields.io/badge/Framework-PyTorch%20%7C%20Scikit--Learn-orange)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)]()

---

## 📌 Overview
This project evaluates **three adversarial deep learning frameworks** for generating synthetic astronomical data to predict the **B‑V colour index** — a key stellar classification metric:

- **Generative Adversarial Networks (GANs)**  
- **Conditional GANs (CGANs)**  
- **Contrastive GANs (ContraGANs)**  

The models were assessed on **predictive accuracy**, **clustering quality**, and **statistical alignment**.  
**ContraGAN** achieved the best overall performance, demonstrating the benefits of **contrastive learning** and **conditional generation** for producing high‑fidelity synthetic data in scientific applications.

---

## 🛰 Dataset
- **Source**: AAVSO Photometric All‑Sky Survey (APASS) Data Release 9  
- **Coverage**: ~62 million stars, Johnson B, V and Sloan g′, r′, i′ photometry  
- **Magnitude Range**: 7 ≤ V ≤ 17  
- **Subset Used**: 1,000 entries with RA, Dec, B‑V index, magnitude uncertainties, and quality flags  
- **Preprocessing**:
  - Median imputation for missing values (7–9% missing across bands)
  - Normalization to [0, 1]
  - K‑Means clustering (elbow method) for conditional generation
  - Train/val/test split: 70% / 15% / 15%

---

## 🧪 Methodology
Each adversarial framework was implemented with tailored architectural and training strategies:

### **1. GAN (WGAN‑GP)**
- Residual blocks in generator & discriminator
- Wasserstein loss with gradient penalty for stability
- Cosine decay learning rate schedule

### **2. CGAN**
- Conditional residual blocks with astronomical features (RA, Dec, magnitudes, errors, observation counts)
- Conditioning applied to both generator & discriminator
- AdamW optimizer with weight decay

### **3. ContraGAN**
- Builds on CGAN with **contrastive loss** to maximise feature‑space separation between real & synthetic data
- Encourages diversity and structural coherence in generated samples

**Evaluation Metrics**:
- **Predictive Accuracy**: Mean Squared Error (MSE), R²
- **Clustering Quality**: Silhouette Score, Calinski‑Harabasz Score, Davies‑Bouldin Score
- **Statistical Alignment**: Wasserstein Distance, Kolmogorov‑Smirnov Statistic

---

## 📊 Key Results

| Model       | MSE     | R²     | Silhouette (Synth) | Calinski‑Harabasz (Synth) | Davies‑Bouldin (Synth) | Wasserstein Dist. | KS Stat |
|-------------|---------|--------|--------------------|---------------------------|------------------------|-------------------|---------|
| **ContraGAN** | **0.1294** | **0.7258** | **0.3687**         | **269.1548**              | **1.0537**             | **0.1983**        | **0.3462** |
| CGAN        | 0.1498  | 0.6788 | 0.3360              | 238.9475                   | 1.2112                 | 0.2148            | 0.3535  |
| GAN         | 0.3461  | 0.2580 | 0.2992              | 224.7939                   | 1.3581                 | 0.3666            | 0.3695  |

**Highlights**:
- **ContraGAN** delivered the lowest MSE and highest R², with superior clustering and statistical alignment.
- **CGAN** improved over vanilla GAN by leveraging feature conditioning.
- **GAN** struggled to capture complex feature relationships.

---

## 🚀 Key Takeaways
- **Contrastive learning + conditional generation** significantly improves synthetic data quality and predictive performance.
- The approach is **transferable** to other domains with scarce or incomplete labelled data.
- Demonstrates a **full ML pipeline**: preprocessing → model design → training → evaluation → statistical validation.

---

## 📂 Repository Structure
- `CAN_GAN.ipynb` — Implementation of GAN, CGAN, and ContraGAN experiments  
- `apass9_cleaned.csv` — Preprocessed APASS DR9 subset  
- `figures/` — Clustering visualisations and PCA plots

---
## Flow Chart

<img width="321" height="660" alt="image" src="https://github.com/user-attachments/assets/111bf21c-6a9e-496f-ba8b-925078b72ec2" />


---

## 💡 Skills Demonstrated
- Advanced GAN architectures (WGAN‑GP, CGAN, ContraGAN)
- Conditional and contrastive learning for structured data
- Statistical and clustering evaluation of synthetic datasets
- Astronomical data preprocessing and feature engineering
- Research‑driven experimentation and result interpretation

---

## 📈 Potential Applications
- Astronomical data augmentation for rare object detection
- Synthetic dataset generation for low‑resource scientific fields
- Industrial predictive modelling with limited labelled data
- Enhancing robustness of ML models in domains with incomplete observations
