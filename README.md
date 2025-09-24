🔎 Project Overview

This project focuses on crack segmentation using Convolutional Neural Networks (CNNs) for automated infrastructure monitoring. Instead of relying on traditional, time-consuming inspection methods, our approach leverages deep learning to detect and segment cracks in asphalt images at the pixel level. The end goal is to provide a robust, automated pipeline that classifies each pixel as either crack or non-crack and outputs a clear segmentation mask.

📂 Project Structure

Dataset Preparation

Collected 40 cracked and 10 undamaged asphalt images.

Annotated images using Roboflow (COCO format, polygons → masks).

Applied preprocessing: resizing, normalization, mask generation.

Split dataset: 70% train, 15% validation, 15% test.

Model Development

Implemented a custom encoder-decoder CNN (from scratch, no U-Net or pretrained weights).

Later extended with Dropout for regularization.

Explored transfer learning (e.g., ResNet, MobileNetV3 encoders).

Training

Implemented in PyTorch.

Used custom DataLoader for efficient batch processing.

Optimized with IoU-aware loss functions (e.g., Dice loss + BCE).

Evaluation

Evaluated with Intersection over Union (IoU).

Visualized predictions by overlaying masks on original images.

Pipeline

Built an end-to-end inference pipeline:

Preprocess raw input.

Predict crack mask.

Post-process and resize mask.

Visualize results.

Data Augmentation

Applied transformations with OpenCV only (rotation, scaling, brightness/contrast changes, Gaussian noise).

Generated 5x augmented dataset to enhance diversity.

🛠 Tools & Libraries

Frameworks: PyTorch 

Annotation: Roboflow (COCO JSON format)

Preprocessing & Augmentation: OpenCV, NumPy

Evaluation Metrics: IoU, Dice score, precision/recall
