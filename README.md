# Autoencoder-Implementation
A simple Autoencoder built with TensorFlow/Keras to perform dimensionality reduction and data reconstruction using unsupervised learning.
## 📌 Overview
This project implements a Convolutional Autoencoder trained on the MNIST handwritten digits dataset.
The model learns to compress 28×28 grayscale images into a 32‑dimensional latent vector, and then reconstruct them back to their original form.

The notebook includes:

Encoder & decoder architecture design

MNIST preprocessing

Model training with MSE loss

Reconstruction visualization

Training/validation loss curves

Final evaluation on test data

## 🏗️ Model Architecture
Encoder
Input: 28×28×1 grayscale image

Conv2D → 32 filters, stride 2

Conv2D → 64 filters, stride 2

Flatten

Dense → latent_dim = 32

This compresses the image into a 32‑dimensional latent space.

Decoder
Dense → reshape to 7×7×64

Conv2DTranspose → upsampling

Conv2DTranspose → upsampling

Final Conv2D → sigmoid activation (output image)

The decoder reconstructs the original 28×28 image.

## 📚 Dataset
The model uses the MNIST dataset, loaded from tf.keras.datasets.mnist.

Preprocessing steps:

Normalize pixel values to [0,1]

Add channel dimension → (28, 28, 1)

Training set: 60,000 images  
Test set: 10,000 images

## ⚙️ Training
The autoencoder is compiled with:

Optimizer: Adam

Loss: Mean Squared Error (MSE)

Training configuration:

Epochs: 10

Batch size: 128

Validation: MNIST test set

Training shows a steady decrease in both training and validation loss.

## 📊 Results
Final Test Loss
Code
Test Loss (MSE): ~0.0044
Reconstruction Quality
The reconstructed images closely resemble the originals, with slight smoothing — expected for convolutional autoencoders.

The notebook visualizes:

Original vs reconstructed images

Training vs validation loss curves

## 🖼️ Visualizations
1. Original vs Reconstructed Images
The notebook displays 10 sample digits:

Top row → original images

Bottom row → reconstructed outputs

2. Loss Curves
A plot showing:

Training loss

Validation loss

Smooth downward trend indicating good learning

## 🧩 Project Structure
Code
Autoencoder_Implementation.ipynb
README.md
## 🚀 How to Run
Open the notebook in Google Colab

Install dependencies (TensorFlow, matplotlib)

Run all cells

View reconstruction results and loss plots

## 📝 Conclusion
This project demonstrates how a convolutional autoencoder can effectively learn compressed representations of handwritten digits. The model achieves low reconstruction error and produces visually accurate reconstructions, showing strong learning of MNIST features.
