# VAE-LSTM for EV Charging Data (ACN-Data)

## Overview

This repository contains experimental code for modeling and reconstructing electric vehicle (EV) charging time-series data using deep learning.

The main goal of this project is to learn temporal patterns in EV charging behavior and perform sequence reconstruction / generation under missing or uncertain observations.

The workflow includes:

* data preprocessing and feature engineering
* sequence generation from time-series data
* model training and inference
* evaluation and visualization

The implementation is designed in a **notebook style**, focusing on clarity, reproducibility, and experimentation.

---

## Model Description

The core model combines:

### Variational Autoencoder (VAE)

* Learns a latent probabilistic representation of charging sequences.
* Uses the **reparameterization trick** to sample latent variables.
* Loss function combines:

  * reconstruction loss (MSE)
  * KL divergence regularization.

### LSTM (Long Short-Term Memory)

* Captures temporal dependencies in EV charging behavior.
* Encoder–decoder structure processes sequential inputs.
* Variational dropout is used for regularization.

### Overall Architecture

The model can be summarized as:

```
Input Sequence
      ↓
   LSTM Encoder
      ↓
   Latent Space (VAE)
      ↓
   LSTM Decoder
      ↓
Reconstructed / Generated Sequence
```

This allows the model to:

* learn compact latent representations of charging patterns
* reconstruct missing intervals
* perform sequence generation and inference.

---

## Dataset

This work uses **ACN-Data**, an open dataset of electric vehicle charging sessions.

**Dataset source:**

> ACN-Data: Analysis and Applications of an Open EV Charging Dataset
> https://ev.caltech.edu/dataset

The dataset provides real-world charging session data collected from adaptive charging networks, including timestamps and charging measurements.

Please refer to the official ACN-Data website for:

* data access instructions
* licensing information
* dataset documentation.

---

## Installation

Create an environment and install dependencies:

```bash
pip install -r requirements.txt
```

Main dependencies include:

* TensorFlow 2.10.0
* NumPy
* Pandas
* Scikit-learn
* Matplotlib / Seaborn

(See `requirements.txt` for full list.) 

---

## Notes

* Random seeds are set inside notebooks.
* The environment can be reproduced using `requirements.txt`.
* Notebook is organized so it can be executed sequentially from a clean kernel.

---

## Citation

If you use this repository or the ACN-Data dataset in academic work, please cite the original ACN-Data publication and dataset source.

---

## Author Notes

The code emphasizes learning and experimentation rather than production deployment.
