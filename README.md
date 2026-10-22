# Learning Generative Models

A collection of practical assignments exploring generative modeling, deep learning architectures, and representation learning using Python, PyTorch, and PyTorch Lightning.

This repository documents my coursework, implementations, experiments, and findings as I progress through the **Learning Generative Models** course.

## Assignments
| Assignment | Topic | Description |
|---|---|---|
| [01](./assignment-01-autoencoder/) | Autoencoders | Image reconstruction, latent representation learning, architecture comparisons, and latent-space exploration |

Additional assignments will be added throughout the course.

## Assignment 01: Autoencoders

Implemented and evaluated three autoencoder configurations on the MNIST handwritten digit dataset:
- Fully connected autoencoder with a 16-dimensional latent space.
- Fully connected autoencoder with a 64-dimensional latent space.
- Convolutional autoencoder with a 16-dimensional latent space.

### Key Results

| Model | Latent Dimension | Validation MSE |
|---|---:|---:|
| Fully Connected Autoencoder | 16 | 0.011822 |
| Fully Connected Autoencoder | 64 | **0.008654** |
| Convolutional Autoencoder | 16 | 0.010346 |

The best-performing model achieved a test MSE of **0.008390**.

Additional experiments investigated random latent sampling and interpolation between encoded handwritten digits.

[Explore Assignment 01](./assignment-01-autoencoder/)

## Technologies

- Python
- PyTorch
- PyTorch Lightning
- Torchvision
- NumPy
- Matplotlib
- Jupyter Notebook

## Repository Structure

```text
learning-generative-models/
├── README.md
├── .gitignore
├── assignment-01-autoencoder/
│   └── AutoEncoder_SunkraTusharRao.ipynb
└── ...
```

## About

This repository is maintained as part of my university coursework in generative modeling. Each assignment focuses on understanding the underlying concepts, implementing models, evaluating results, and documenting experimental findings.
