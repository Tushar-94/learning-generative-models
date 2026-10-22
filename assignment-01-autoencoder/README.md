# Assignment 01 — Autoencoders

## Overview
This assignment explores representation learning and image reconstruction using autoencoders implemented with PyTorch and PyTorch Lightning.

Three autoencoder configurations were trained and evaluated on the MNIST handwritten digit dataset to investigate how latent dimensionality and network architecture influence reconstruction quality.

## Dataset

**MNIST**
- 60,000 training-set images
- 10,000 test images
- Grayscale images with a resolution of 28 × 28 pixels
- 10 handwritten digit classes (0–9)

The original training set was divided into 54,000 training images and 6,000 validation images.

## Model Architectures

### Fully Connected Autoencoder

The encoder compresses each 28 × 28 image into a latent representation.

Architecture:

Input (784) → 256 → 64 → Latent Representation

The decoder reconstructs the image:

Latent Representation → 64 → 256 → Output (784)

Two latent dimensions were investigated: 16 and 64.

### Convolutional Autoencoder

The convolutional architecture uses convolutional layers for spatial feature extraction and transposed convolutions for reconstruction.

The model uses a 16-dimensional latent representation.

## Training Configuration

- Framework: PyTorch Lightning
- Optimizer: Adam
- Learning rate: 0.001
- Loss function: Mean Squared Error (MSE)
- Batch size: 64
- Training epochs: 10
- Dataset: MNIST

## Experimental Results

| Model | Latent Dimension | Parameters | Validation MSE |
|---|---:|---:|---:|
| Fully Connected Autoencoder | 16 | 437,664 | 0.011822 |
| Fully Connected Autoencoder | 64 | 443,856 | **0.008654** |
| Convolutional Autoencoder | 16 | 61,329 | 0.010346 |

The fully connected autoencoder with a 64-dimensional latent representation achieved the lowest validation reconstruction error.

**Final test MSE: 0.008390**

## Key Findings

1. Increasing latent dimensionality from 16 to 64 improved reconstruction quality.
2. The convolutional autoencoder outperformed the fully connected 16-dimensional baseline while using substantially fewer parameters.
3. Random latent sampling produced distorted images because the standard autoencoder was not trained to match a predefined latent distribution.
4. Interpolation between encoded digit representations produced gradual transitions between handwritten digit shapes.

## Bonus: Latent Space Exploration

Additional experiments investigated:

- Image generation from randomly sampled latent vectors
- Statistical properties of encoder-produced latent representations
- Reconstruction from encoded training images
- Linear interpolation between latent representations of different digits

These experiments demonstrate the distinction between image reconstruction and unconditional image generation.

## Limitations and Future Work

The experiments were conducted on MNIST with one training run per configuration.

Potential extensions include:
- Evaluating additional datasets
- Investigating alternative architectures
- Repeating experiments across multiple random seeds
- Implementing Variational Autoencoders (VAEs)

## Notebook

[Open the complete Jupyter Notebook](./AutoEncoder_SunkraTusharRao.ipynb)

The notebook contains the implementation, training procedures, evaluation metrics, visualizations, and experimental discussion.
