# 🧠 Efficient Machine Unlearning on CIFAR-10 — ML/DL Final Project

This project explores **selective unlearning in deep neural networks**, where specific data (the *forget set*) is removed from a trained model while preserving performance on the *retain set*. This is highly relevant in contexts such as GDPR, data privacy, and content deprecation. The system is developed using **ResNet-18** and evaluated across multiple unlearning strategies.

---


## 👤 Author

- **Dev Divyendh Dhinakaran** (G01450299)

---

## 🎯 Objective

To implement and evaluate multiple **machine unlearning algorithms** that:
- Forget specific data subsets while retaining performance on others
- Preserve generalization to unseen validation and test data
- Support scalability and transparency using metrics and visualizations

---

## 📊 Dataset & Model

### 🗂️ Dataset
- **CIFAR-10**: 60,000 32×32 images in 10 classes
- Split into:
  - Retain set
  - Forget set
  - Validation and Test sets

### 🧠 Base Model
- **ResNet-18**, pretrained and fine-tuned with custom unlearning strategies

---

## 🔁 Models Implemented

| Model | Strategy | Key Features |
|-------|----------|---------------|
| **Model 1** | Retain fine-tuning | Trained only on retain set |
| **Model 2** | Selective fine-tuning | Unfreezes only last layers |
| **Model 3** | Gradient reversal | Reverse loss on forget set |
| **Model 4** | Alternating FT + GR | Per-epoch switching with scaled gradients |
| **Model 5** | Per-batch FT + GR | Stronger forget impact |
| **Model 6** | Alternating + Final FT | Best performance-recovery tradeoff |

---

## ⚗️ Hybrid Models

| Hybrid | Description | Key Feature |
|--------|-------------|-------------|
| **Hybrid 1** | Simple alternating | Linear scaling on forget gradients |
| **Hybrid 2** | Exponential scaling + final FT | Higher retention |
| **Hybrid 3** | Periodic intermediate FT | Stable validation |
| **Hybrid 4** | Refined + metrics tracking | Visual analysis + dynamic unfreezing |

---

## 📈 Results Summary

### Individual Models

| Model | Retain (%) | Forget (%) | Validation (%) | Test (%) |
|-------|------------|------------|----------------|----------|
| M1    | 100.00     | 99.22      | 88.40          | 88.54    |
| M3    | 100.00     | 98.30      | 87.62          | 88.10    |
| M5    | 92.31      | 74.30      | 77.90          | 77.24    |

### Hybrid Models

| Hybrid | Retain (%) | Forget (%) | Validation (%) | Test (%) |
|--------|------------|------------|----------------|----------|
| H1     | 46.51      | 37.22      | 44.56          | 44.86    |
| H2     | 93.27      | 67.82      | 72.26          | 71.70    |
| H3     | 100.00     | 71.76      | 85.36          | 85.08    |
| H4     | 98.42      | 66.64      | 78.88          | 78.02    |

---

## 📊 Visualizations

- 📈 Retain vs Forget Accuracy
- 📉 Accuracy Gap trends across hybrid strategies
- 📉 Validation Accuracy over Epochs
<p align="center">
  <img src="https://github.com/user-attachments/assets/010e1780-25d5-46d7-b6a3-f40f81f62cc5" width="600"/>
  <br>
  <em>Figure 1: Performance Comparison of Hybrid Models</em>
</p>




---



---

## 💡 Key Learnings

- Hybrid unlearning strategies offer better control over forgetting and retention trade-offs
- Gradient reversal combined with dynamic fine-tuning improves model precision
- Metrics tracking is critical for interpretability and model debugging


