# GAN Implementations

A curated, notebook-first collection of GAN projects covering **Vanilla GAN**, **DCGAN**, **Conditional GAN (CGAN)**, and **WGAN-GP**. This repository shows a practical progression from a basic adversarial baseline to more stable, controllable, and visually compelling image generation methods.

This project is designed to be easy to browse, easy to reproduce, and easy to present on GitHub.

---

## Highlights

- **Vanilla GAN** as the baseline adversarial model
- **DCGAN** for a stronger convolutional image synthesis pipeline
- **CGAN** for class-conditioned generation on marine species
- **WGAN-GP** for more stable training with gradient penalty
- Checkpoint saving, training resumption, and sample visualization
- Curated dataset preprocessing pipelines inside the notebooks
- A clear progression from simple generation to conditional and stabilized GAN variants

---

## Repository Overview

This repository is intentionally kept **notebook-first**. The notebooks at the root capture the full experiments, training flow, and generated results.

```text
GAN-Implementations/
├── README.md
├── marine-cgan.ipynb
├── May_vGAN_Implementation.ipynb
└── may-wgan-implementation.ipynb
```

### Notebook Index

- [May_vGAN_Implementation.ipynb](May_vGAN_Implementation.ipynb) - Vanilla GAN and DCGAN experiments on AFHQ animal faces
- [marine-cgan.ipynb](marine-cgan.ipynb) - Conditional GAN for marine animal classification and generation
- [may-wgan-implementation.ipynb](may-wgan-implementation.ipynb) - WGAN-GP implementation on AFHQ v2 / animal faces

---

## Project Story

The repository demonstrates a deliberate evolution in GAN modeling:

1. **Vanilla GAN** establishes the core adversarial training setup.
2. **DCGAN** improves image quality using convolutional architecture and batch normalization.
3. **CGAN** introduces class conditioning for controllable generation.
4. **WGAN-GP** stabilizes training with Wasserstein loss and gradient penalty.

That progression makes the repository useful both as a learning resource and as a portfolio project.

---

## Implementations

### 1. Vanilla GAN + DCGAN

**Dataset:** AFHQ animal faces from the official StarGAN v2 ecosystem.

What this notebook covers:

- Vanilla GAN as the baseline generator-discriminator setup
- DCGAN as the improved convolutional architecture
- Training loops with loss tracking and sample generation
- Checkpoint saving and resuming
- Comparison of generated outputs across training stages

Why it matters:

- Shows the limitations of the simplest GAN setup
- Demonstrates how convolutional design improves stability and image sharpness
- Provides a clean comparison between baseline and improved adversarial modeling

---

### 2. Conditional GAN (CGAN)

**Dataset:** Marine Image Dataset for Classification.

Classes include:

- Dolphin
- Fish
- Lobster
- Octopus
- Sea Horse

What this notebook covers:

- Label-conditioned generator inputs
- Label-aware discriminator training
- Dataset preprocessing and class handling
- Training on marine species with conditional outputs
- Class-wise image generation and inspection

Why it matters:

- Demonstrates controllable generation rather than unconditional sampling
- Makes the architecture useful for structured class-based synthesis
- Adds a practical real-world dataset with multiple categories

---

### 3. WGAN-GP

**Dataset:** AFHQv2 / animal faces.

What this notebook covers:

- Critic-based training instead of a probability classifier
- Wasserstein objective for improved gradient behavior
- Gradient penalty for Lipschitz regularization
- Multiple critic updates per generator update
- Checkpointing and resumed training support

Why it matters:

- Addresses training instability common in vanilla GANs
- Produces smoother optimization and more reliable convergence
- Represents a stronger modern GAN training recipe

---

## Datasets

- **StarGAN v2 / AFHQ source**: [clovaai/stargan-v2](https://github.com/clovaai/stargan-v2)
- **Marine Image Dataset for Classification**: [Kaggle dataset by ananya12verma](https://www.kaggle.com/datasets/ananya12verma/marine-image-dataset-for-classification)
- **AFHQv2 512**: [Kaggle dataset by dimensi0n](https://www.kaggle.com/datasets/dimensi0n/afhq-512)

---

## Model Summary

### Vanilla GAN

- **Generator input:** random noise vector
- **Output:** generated image tensor or flattened image representation depending on notebook implementation
- **Discriminator:** real/fake classifier
- **Loss:** binary cross-entropy with logits
- **Optimizer:** Adam

### DCGAN

- **Generator:** transpose convolutions with batch normalization
- **Discriminator:** convolutional feature extractor
- **Output activation:** `tanh`
- **Loss:** binary cross-entropy with logits
- **Optimizer:** Adam

### CGAN

- **Generator input:** noise plus class embedding
- **Discriminator input:** image plus class label
- **Generation style:** class-conditioned marine species synthesis
- **Loss:** binary cross-entropy with logits

### WGAN-GP

- **Generator:** noise-to-image synthesis
- **Critic:** scalar score output, not a probability
- **Loss:** Wasserstein objective
- **Regularization:** gradient penalty enabled
- **Optimizer:** Adam with WGAN-friendly betas

---

## Training Features

- Checkpoint saving and loading
- Training resumption from saved state
- Sample generation during training
- Loss curve tracking
- Visual comparison of generated images over epochs
- Mixed precision where supported in the notebook implementation
- Class imbalance handling for CGAN via weighted sampling

---

## Visual Results to Include

For the strongest GitHub presentation, add or export the following visuals from the notebooks:

- Early, mid, and final epoch generated samples
- Generator and discriminator or critic loss curves
- Architecture diagrams for each GAN variant
- Side-by-side comparison of Vanilla GAN vs DCGAN vs WGAN-GP outputs
- Class-conditioned CGAN samples for each marine species

A well-arranged results gallery can make this repository stand out immediately.

---

## Setup

### Clone the repository

```bash
git clone https://github.com/Shrey-Panwala/GAN-Implementations-Vanilla-GAN-DCGAN-CGAN-and-WGAN-GP.git
cd GAN-Implementations-Vanilla-GAN-DCGAN-CGAN-and-WGAN-GP
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Launch Jupyter

```bash
jupyter notebook
```

If you do not use a `requirements.txt` yet, install the packages referenced by the notebooks manually before running the experiments.

---

## Suggested Requirements

A typical environment for these notebooks would include:

```text
torch
torchvision
numpy
pandas
matplotlib
seaborn
Pillow
scikit-learn
jupyter
```

Depending on your notebook implementation, you may also need:

- `tqdm`
- `opencv-python`
- `albumentations`
- `torchinfo`
- `ipykernel`

---

## Why This Project Stands Out

- It covers a clean progression from baseline GANs to more advanced and stable formulations.
- It includes both unconditional and conditional generation.
- It demonstrates real training practice, not just model definitions.
- It shows checkpointing, resuming, and sample visualization.
- It uses multiple datasets and problem settings.
- It is concise enough to explore quickly, but deep enough to show strong understanding.

---

## Future Improvements

- Add FID and Inception Score evaluation
- Add a comparison table across all models
- Export notebooks into clean Python scripts
- Add an architecture gallery in the README
- Add a small demo page or static gallery for generated samples
- Experiment with StyleGAN variants for higher fidelity output

---

## Credits

- DeepLearning.AI GAN course
- StarGAN v2 project by Clova AI
- Kaggle marine dataset contributor
- Kaggle AFHQv2 512 contributor

---
