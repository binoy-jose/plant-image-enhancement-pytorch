# Plant Leaf Super Resolution using PyTorch

This project focuses on reconstructing high-resolution crop leaf images from severely degraded low-resolution images using deep learning techniques in PyTorch.

The objective was to improve image quality for agricultural disease analysis systems by generating high-resolution outputs from compressed and noisy low-resolution inputs.

---

## Project Overview

In many Agri-Tech applications, drones and low-cost sensors capture crop leaf images under challenging conditions such as:

- Low-quality sensors
- Thermal noise
- Compression artifacts
- Limited network bandwidth

These degraded images reduce the accuracy of automated disease detection systems.

This project implements a Super-Resolution model that enhances low-resolution crop leaf images into higher-quality reconstructed outputs.

---

## Dataset Information

The dataset contains:

- `train_Low_Resolution/`
  - 32×32 degraded crop leaf images

- `train_High_Resolution/`
  - 128×128 ground truth images

- `test_Low_Resolution/`
  - Test images used for prediction and submission

---

## Technologies Used

- Python
- PyTorch
- NumPy
- Pandas
- PIL
- Torchvision

---

## Model Architecture

The project uses a custom Super-Resolution CNN consisting of:

- Convolutional layers
- Residual blocks
- PReLU activations
- Residual learning strategy

The model was trained entirely from scratch without using pretrained weights.

---

## Training Strategy

The model was trained in multiple stages using different learning rates:

| Stage | Learning Rate | Epochs |
|------|------|------|
| Stage 1 | 1e-4 | 40 |
| Stage 2 | 2e-5 | 30 |
| Stage 3 | 1e-5 | 20 |

Loss Function:
- L1 Loss (Mean Absolute Error)

---

## Inference Improvements

The following techniques were used during inference:

- Bicubic upscaling
- Test Time Augmentation (TTA)
- Weighted averaging
- Pixel value clipping and rounding

---

## Evaluation Metric

The competition evaluated submissions using:

- Mean Absolute Error (MAE)

Lower MAE indicates better reconstruction quality.

---

## Results

The model successfully generated high-resolution crop leaf images from degraded low-resolution inputs and achieved competitive leaderboard performance on the Kaggle evaluation system.

---

## How to Run

1. Clone the repository
2. Install required libraries
3. Open the notebook in Kaggle or Jupyter
4. Train the model
5. Generate `submission.csv`

---

## Future Improvements

Possible future enhancements include:

- ESRGAN-based architecture
- Attention mechanisms
- Perceptual loss tuning
- Larger datasets
- Advanced super-resolution techniques

---
