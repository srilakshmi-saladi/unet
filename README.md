👁️ Diabetic Retinopathy: Classification & Lesion Detection
This repository features a dual-stage deep learning pipeline for analyzing retinal fundus images. It combines high-accuracy Classification to grade disease severity and precise Semantic Segmentation (U-Net) for automated lesion detection.
🚀 Project Overview
The goal of this project is to provide an end-to-end tool for Diabetic Retinopathy (DR) screening:
Severity Classification: Categorizing retinal images into stages (e.g., No DR, Mild, Moderate, Severe, Proliferative).
Lesion Detection: Identifying and masking specific pathological features like microaneurysms, hemorrhages, and exudates.
🧠 Model Architectures
1. Severity Classification: EfficientNet-B3
For the classification task, I implemented EfficientNet-B3.
Why EfficientNet? It uses "Compound Scaling" to balance network depth, width, and resolution. This makes it more accurate and computationally efficient than older models like ResNet or VGG.
Transfer Learning: I utilized pre-trained ImageNet weights and fine-tuned the model on the eye dataset to achieve high sensitivity for subtle retinal changes.
Input Resolution: Optimized for 

 pixel inputs to capture fine-grained vascular details.
2. Lesion Detection: U-Net
For the detection of specific lesions, I used the U-Net architecture to perform pixel-level segmentation.
Symmetric Design: The contracting path (encoder) captures context, while the expanding path (decoder) enables precise localization of tiny lesions.
Skip Connections: These allow the model to retain high-resolution spatial information, which is critical for detecting very small microaneurysms that might otherwise be lost during downsampling.
Output: The model generates a binary mask where white pixels represent detected lesions.
💻 Implementation Details
Development Environment: Developed entirely in Google Colab to leverage GPU acceleration.
Preprocessing: Images were preprocessed using CLAHE (Contrast Limited Adaptive Histogram Equalization) to enhance the visibility of blood vessels and lesions.
Framework: TensorFlow/Keras (or PyTorch).
📂 Repository Structure
DR_Classification.ipynb: Severity grading using EfficientNet-B3.
UNet_Lesion_Detection.ipynb: Lesion segmentation and mask generation.
README.md: Project documentation and architecture overview.
📊 Evaluation Metrics
To ensure clinical relevance, the models were evaluated using:
Classification: Accuracy, Sensitivity, and Quadratic Weighted Kappa.
Segmentation: Dice Coefficient and Intersection over Union (IoU).
