👁️ Diabetic Retinopathy Detection: Classification & Segmentation
This repository contains a deep learning pipeline for the automated analysis of retinal fundus images. The project is divided into two main tasks: Severity Classification using EfficientNet-B3 and Lesion Segmentation using a U-Net architecture.
🚀 Project Overview
Diabetic Retinopathy (DR) is a leading cause of vision loss. This project aims to assist clinicians by:
Classifying the severity of DR (Grades 0-4) using state-of-the-art CNNs.
Segmenting critical pathological features (like microaneurysms and hemorrhages) to provide explainable AI results.
🧠 Model Architectures
1. Severity Classification (EfficientNet-B3)
For the classification task, I implemented EfficientNet-B3.
Compound Scaling: Unlike traditional models, EfficientNet scales width, depth, and resolution uniformly, leading to better accuracy with fewer parameters.
Transfer Learning: The model was initialized with ImageNet weights and fine-tuned on the eye dataset, allowing for high performance even with limited medical data.
Performance: EfficientNet-B3 provides a perfect balance between computational efficiency and high precision for detecting subtle retinal changes.
2. Lesion Segmentation (U-Net)
For precise pixel-level detection, I utilized the U-Net architecture:
Encoder-Decoder Structure: The "U" shape allows the model to capture global context (what is in the image) and local features (where the lesions are).
Skip Connections: These bridge the gap between the encoder and decoder, preserving fine spatial details that are often lost in deep networks.
Output: Generates binary masks that highlight exactly where abnormalities exist in the retina.
💻 Technical Implementation
Framework: TensorFlow / Keras (or PyTorch)
Environment: Developed and tested on Google Colab to utilize Tesla T4/P100 GPUs.
Dataset: Retinal Fundus Images (pre-processed with CLAHE and resizing for optimal feature extraction).
📂 Repository Structure
DR_Classification.ipynb: Notebook for training and testing the EfficientNet-B3 classifier.
UNet_Testing.ipynb: Notebook for the U-Net segmentation pipeline and mask visualization.
README.md: Project documentation.
📊 Results
The models were evaluated based on:
Classification: Accuracy, F1-Score, and Quadratic Weighted Kappa.
Segmentation: Dice Coefficient and Intersection over Union (IoU).
