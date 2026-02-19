#  Deepfake Face Detection using MobileNetV2, EfficientNetV2 & Ensemble Learning

A deep learning–based web application that detects whether a face image is **REAL or FAKE (AI-generated)** using an **ensemble of MobileNetV2 and EfficientNetV2**.  
The project includes **model training, transfer learning, Grad-CAM explainability, Gradio UI**, and **prediction logging**.

---

#  Features

- Binary classification: **Real vs Fake faces**
- Transfer learning using:
  - MobileNetV2
  - EfficientNetV2B0
- **Ensemble model** (averaging predictions from both models)
- **Grad-CAM visualization** for model explainability
- **Gradio web interface** for real-time predictions
- **Prediction logging to CSV**
- Training with **data augmentation** and **learning rate scheduling**

---

#  Project Workflow

## 1️ Dataset Preparation

- Images stored in Google Drive
- Structured into:

train/
├── real/
└── fake/


- Automatic file organization using Python (`os`, `shutil`)

---

## 2️ Data Preprocessing

- Image resizing → `224 × 224`
- Normalization → pixel values scaled to `[0,1]`
- Data augmentation:
  - Horizontal flip
- Train/validation split → **80/20**

---

## 3 Model Training

### 🔹 MobileNetV2

- Pretrained on ImageNet
- Frozen base layers
- Custom classification head:
  - GlobalAveragePooling
  - Dropout
  - Dense (Sigmoid)

### 🔹 EfficientNetV2B0

- Transfer learning with custom top layers
- Binary output using sigmoid activation

---

## 4️ Ensemble Learning

- Shared input layer
- Predictions from:
  - MobileNetV2
  - EfficientNetV2
- Combined using **Average layer**
- Final sigmoid output

- Improves robustness and accuracy.

---

## 5️ Model Explainability (Grad-CAM)

- Generates heatmaps highlighting:
  - Regions influencing prediction
- Helps visualize **why** the model predicts fake/real

---

## 6️ Web Application (Gradio)

Users can:

- Upload a face image
- Get:
  - Prediction (Real/Fake)
  - Confidence score
  - Grad-CAM heatmap

---

## 7️ Prediction Logging

Each prediction is saved to:

Fields:

- Timestamp  
- Image name  
- Prediction  
- Confidence  

---

#  Tech Stack

- Python  
- TensorFlow / Keras  
- MobileNetV2  
- EfficientNetV2B0  
- OpenCV  
- NumPy / Pandas  
- Matplotlib  
- Gradio  
- Google Colab  

---

# 📂 Project Structure

deepfake-face-detection/
│
├── models/
│ ├── mobilenet_model.keras
│ ├── efficientnet_model.h5
│ └── safe_ensemble_model.keras
│
├── prediction_logs.csv
├── app.py
├── train.py
├── gradcam.py
├── requirements.txt
└── README.md

Sample Output

Prediction: Fake
Confidence: 94.27%
