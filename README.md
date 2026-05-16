# Deep-Learning-project
# CIFAR-10 Image Classification using CNN and ResNet-like Models

A deep learning project for image classification using the CIFAR-10 dataset and PyTorch.

---

# Project Overview

This project implements and compares two deep learning architectures for image classification:

1. Simple CNN (Convolutional Neural Network)
2. ResNet-like Architecture with Skip Connections

The project applies:

- Data Augmentation
- CNN Feature Extraction
- Residual Learning
- Model Comparison
- Training & Validation
- Performance Visualization

The models are trained and evaluated on the CIFAR-10 dataset.

---

# Technologies Used

- Python
- PyTorch
- Torchvision
- Matplotlib
- Pandas
- NumPy

---

# Dataset

Dataset used:

- CIFAR-10 Dataset

Dataset contains:

- 50,000 Training Images
- 10,000 Test Images
- 10 Classes

Classes:

```text
Airplane
Automobile
Bird
Cat
Deer
Dog
Frog
Horse
Ship
Truck
```

Original image size:

```text
32 × 32 RGB Images
```

Resized image size:

```text
64 × 64 RGB Images
```

---

# Data Preprocessing

The following preprocessing and augmentation techniques were applied:

- Resize Images
- Random Horizontal Flip
- Random Rotation
- Convert Images to Tensor
- Normalize Pixel Values

Training Transform:

```python
transform_train = transforms.Compose([
    transforms.Resize((64, 64)),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(15),
    transforms.ToTensor(),
    transforms.Normalize(
        (0.4914, 0.4822, 0.4465),
        (0.2023, 0.1994, 0.2010)
    )
])
```

Testing Transform:

```python
transform_test = transforms.Compose([
    transforms.Resize((64, 64)),
    transforms.ToTensor(),
    transforms.Normalize(
        (0.4914, 0.4822, 0.4465),
        (0.2023, 0.1994, 0.2010)
    )
])
```

---

# Data Partitioning

Dataset split:

| Dataset | Size |
|---|---|
| Training Set | 40,000 |
| Validation Set | 10,000 |
| Test Set | 10,000 |

---

# Model Architectures

# Model A — Simple CNN

The first model is an upgraded Convolutional Neural Network with:

- 3 Convolution Blocks
- Batch Normalization
- ReLU Activation
- Max Pooling
- Dropout Regularization

Architecture:

```text
Input Image (3×64×64)
        ↓
Conv2D (32 Filters)
        ↓
BatchNorm
        ↓
ReLU
        ↓
MaxPooling
        ↓
Conv2D (64 Filters)
        ↓
BatchNorm
        ↓
ReLU
        ↓
MaxPooling
        ↓
Conv2D (128 Filters)
        ↓
BatchNorm
        ↓
ReLU
        ↓
MaxPooling
        ↓
Flatten
        ↓
Fully Connected Layer (256)
        ↓
Dropout (0.5)
        ↓
Output Layer (10 Classes)
```

---

# Model B — ResNet-like Architecture

The second model is a simplified ResNet-style architecture using:

- Residual Blocks
- Skip Connections
- Batch Normalization
- Adaptive Average Pooling

Architecture:

```text
Input Image
        ↓
Initial Conv Layer
        ↓
Residual Block 1
        ↓
Residual Block 2
        ↓
Residual Block 3
        ↓
Adaptive Average Pooling
        ↓
Dropout
        ↓
Fully Connected Layer
        ↓
Output Layer (10 Classes)
```

---

# Key Deep Learning Concepts Used

- Convolutional Neural Networks (CNN)
- Residual Learning
- Skip Connections
- Batch Normalization
- Dropout
- Backpropagation
- Gradient Descent
- Data Augmentation

---

# Experiments

## Experiment 1 — Simple CNN + Adam

| Parameter | Value |
|---|---|
| Model | Simple CNN |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Batch Size | 64 |
| Epochs | 20 |

---

## Experiment 2 — ResNet-like + SGD

| Parameter | Value |
|---|---|
| Model | ResNet-like |
| Optimizer | SGD |
| Learning Rate | 0.01 |
| Momentum | 0.9 |
| Batch Size | 64 |
| Epochs | 20 |

---

# Training Details

Loss Function:

```python
nn.CrossEntropyLoss()
```

Optimizers Used:

- Adam Optimizer
- SGD with Momentum

Training Device:

- GPU (CUDA) if available
- Otherwise CPU

---

# Evaluation Metrics

The models are evaluated using:

- Accuracy
- Loss

---

# Visualization

The project visualizes:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss

using Matplotlib.

---

# Results

The project compares the performance of both models using:

- Test Accuracy
- Test Loss

Example Output:

```text
Model A (Simple CNN + Adam)
Test Accuracy: ~80%+

Model B (ResNet-like + SGD)
Test Accuracy: ~85%+
```

(Results may vary depending on hardware and random initialization.)

---


# How to Run

## 1. Clone the repository

```bash
git clone https://github.com/habeba-abubakrmohamed12/Deep-Learning-project
```

---

## 2. Install dependencies

```bash
pip install torch torchvision matplotlib pandas numpy
```

---

## 3. Run the project

```bash
python main.py
```

---
 كدا
