# 🕳️ Crack Segmentation with CNNs  

This project implements a **deep learning–based crack segmentation pipeline** for automated infrastructure monitoring. Instead of relying on manual, time-consuming inspections, our approach leverages **Convolutional Neural Networks (CNNs)** to detect and segment cracks in asphalt images at the **pixel level**, producing clear segmentation masks.  

---

## 📂 Project Structure  

### 1. Dataset Preparation  
- **Images**: 40 cracked + 10 undamaged asphalt images  
- **Annotation**: Labeled with **Roboflow** (COCO format, polygons → masks)  
- **Preprocessing**: Resizing, normalization, mask generation  
- **Splits**:  
  - 70% → Training  
  - 15% → Validation  
  - 15% → Testing  

### 2. Model Development  
- Custom **encoder–decoder CNN** (from scratch, no U-Net or pretrained weights)  
- Added **Dropout** for regularization  
- Explored **transfer learning** with **ResNet** and **MobileNetV3 encoders**  

### 3. Training  
- Framework: **PyTorch**  
- Custom **DataLoader** for batch processing  
- Loss Functions:  
  - **Dice Loss**  
  - **Binary Cross-Entropy (BCE)**  
- Optimized for **IoU-aware performance**  

### 4. Evaluation  
- Metrics:  
  - Intersection over Union (**IoU**)  
  - Dice Score  
  - Precision & Recall  
- Visualization: Overlay predicted masks on original images  

### 5. Inference Pipeline  
1. Preprocess raw input  
2. Predict crack mask  
3. Post-process + resize mask  
4. Visualize results  

### 6. Data Augmentation  
- Implemented with **OpenCV** only  
- Techniques:  
  - Rotation  
  - Scaling  
  - Brightness/contrast adjustments  
  - Gaussian noise  
- Expanded dataset **5×** for improved diversity  

---

## 🛠 Tools & Libraries  
- **Frameworks**: PyTorch  
- **Annotation**: Roboflow (COCO JSON format)  
- **Preprocessing & Augmentation**: OpenCV, NumPy  
- **Metrics**: IoU, Dice Score, Precision, Recall  

  - DeepLabv3+  
  - Swin Transformer  
