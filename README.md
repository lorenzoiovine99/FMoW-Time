# Streaming Land Use Classification of Satellite Images with Temporal Distribution Shifts

This repository contains the implementation and experiments associated with the paper **"Towards Streaming Land Use Classification of Images with Temporal Distribution Shifts"**, authored by Lorenzo Iovine, Giacomo Ziffer, Andrea Proia, and Emanuele Della Valle, presented at **ESANN 2025**.

---

## 📖 Overview

This study integrates **Streaming Machine Learning (SML)** models with **Momentum Contrastive Learning (MoCo)** to classify satellite images under temporal distribution shifts. The proposed pipeline improves generalization and robustness over time compared to traditional methods.

### Key Contributions:

- Experimental integration of MoCo embeddings and SML.
- Preliminary evaluation using the Functional Map of the World-Time (FMoW-Time) dataset.
- Comparison with state-of-the-art Continual Learning (CL) methods.

---

## 🚀 Pipeline Structure

The pipeline has three main components:

1. **Embedding Extraction (MoCo)**:
   - ResNet-18 backbone pre-trained on ImageNet.
   - Features projected using an MLP.

2. **Streaming Data Preparation**:
   - Gaussian Random Projection (GRP).
   - Noise and Normalization transformers.

3. **Streaming Classification**:
   - Hoeffding Tree (HT)
   - Hoeffding Adaptive Tree (HAT)
   - Extremely Fast Decision Tree (EFDT)
   - Naive Bayes (NB)
   - Softmax Regression (SR, from River library)

Implemented using the [CapyMOA](https://capymoa.org) library.

---

## 📊 Experimental Settings

### Dataset

- **FMoW-Time**:
  - **141,696 RGB images** (224x224 pixels, 2002–2017)
  - **62 categories** (land use/buildings)

### Evaluation Methods

- **Eval-Stream (EA)**: Train 90% / Test 10% yearly.
- **Prequential Evaluation**: Test before training incrementally.

### Metrics:

- **In-Distribution (ID)** Accuracy
- **Out-of-Distribution (OOD)** Accuracy


## 📚 Citation

If you find this work useful or use this code for your own research, please cite our paper as follows:

```bibtex
@inproceedings{iovine2025towards,
  title={Towards Streaming Land Use Classification of Images with Temporal Distribution Shifts},
  author={Iovine, Lorenzo and Ziffer, Giacomo and Proia, Andrea and Della Valle, Emanuele},
  booktitle={ESANN 2025},
  year={2025}
}
