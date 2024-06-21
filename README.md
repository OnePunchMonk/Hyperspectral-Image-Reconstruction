Hyperspectral Image Reconstruction with Deep Learning
This repository contains code for a deep learning model that reconstructs hyperspectral images using a pre-trained encoder and a decoder architecture.

Project Structure
ReorganiseDataset.ipynb: Script for creating training, validation, and test sets from a provided hyperspectral image dataset.
Arch_Explained.txt: Detailed explanation of the model architecture with diagrams.
HSI.ipynb: Script containing the PyTorch implementation of the model.
Model Architecture
The model utilizes a combination of pre-trained features and reconstruction matrix processing to reconstruct hyperspectral images. Here's a high-level overview:

Pre-trained Encoder (ResNet-18): Extracts spatial features from the input image. The final fully-connected layer is removed.
Reconstruction Matrix Processing: A 3D convolution extracts relevant information from the reconstruction matrix.
Channel-Aware Feature Fusion: Encoder features and processed reconstruction matrix features are concatenated for combined information.
Decoder for Reconstruction: Upscales the fused features through decoder blocks with dropout for regularization. The final output is a reconstructed 3-channel image.
Training with Early Stopping: The model is trained using Mean Squared Error (MSE) loss and the Adam optimizer. Early stopping monitors validation loss to prevent overfitting.
Intended Architecture Diagram
A detailed architecture diagram can be found in Arch_Explained.txt.

Note: The diagram depicts the data flow through the network, including:

Input image feeding into the pre-trained encoder (ResNet-18)
Encoder feature extraction
Reconstruction matrix processing with 3D convolution
Feature fusion with concatenation
Decoder blocks for upscaling and reconstruction
Final reconstructed image output
Usage
Prepare your hyperspectral image dataset.
Run ReorganiseDataset.ipynb to create training, validation, and test sets.
Train the model using HSI.ipynb.
Additional Notes
