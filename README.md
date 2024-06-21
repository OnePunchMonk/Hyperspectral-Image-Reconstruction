# Hyperspectral Image Reconstruction with Deep Learning

This repository implements a deep learning model for reconstructing hyperspectral images. The model leverages a pre-trained encoder and a decoder architecture to achieve this task.

## Project Structure

- `ReorganiseDataset.ipynb`: Jupyter Notebook script for preparing training, validation, and test sets from your hyperspectral image dataset.
- `Arch_Explained.txt`: Text file containing a detailed explanation of the model architecture with diagrams.
- `HSI.ipynb`: Jupyter Notebook script containing the PyTorch implementation of the model.

## Model Architecture

The model utilizes a pre-trained encoder and a decoder architecture for reconstruction. The key components are:

- **Pre-trained Encoder (ResNet-18)**: Extracts spatial features from the input image. The final fully-connected layer is excluded.
- **Reconstruction Matrix Processing**: Applies a 3D convolution to extract relevant information from the reconstruction matrix.
- **Channel-Aware Feature Fusion**: Concatenates encoder features with processed reconstruction matrix features for combined information.
- **Decoder for Reconstruction**: Upscales the fused features through decoder blocks with dropout for regularization. Reconstructs the final 3-channel image.
- **Training with Early Stopping**: Trains the model using Mean Squared Error (MSE) loss and the Adam optimizer. Early stopping monitors validation loss to prevent overfitting.

## Intended Architecture Diagram

A detailed architecture diagram can be found in the file `Arch_Explained.txt`.

**Note:** The diagram illustrates the data flow through the network, including:

- Input image feeding into the pre-trained encoder (ResNet-18)
- Encoder feature extraction
- Reconstruction matrix processing with 3D convolution
- Feature fusion with concatenation
- Decoder blocks for upscaling and reconstruction
- Final reconstructed image output

## Usage

1. **Prepare your hyperspectral image dataset.** Ensure it's in a format compatible with the code.
2. **Run `ReorganiseDataset.ipynb`** to create training, validation, and test sets from your prepared dataset.
3. **Train the model using `HSI.ipynb`.** This script defines the model architecture, training process, and hyperparameters.

