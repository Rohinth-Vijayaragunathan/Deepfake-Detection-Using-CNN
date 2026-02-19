# AI Image Processing Pipeline

A modular Python-based system for processing images, extracting deep learning features using a pre-trained Convolutional Neural Network (CNN), generating predictions, and storing results in a relational database.

---

## Overview

This application accepts an image as input, performs preprocessing, extracts semantic features using a CNN model, generates predictions, and stores the results along with metadata in a database.

The architecture is modular and designed for easy extension into APIs or larger machine learning workflows.

---

## Key Features

- Image preprocessing and normalization  
- CNN-based feature extraction and prediction  
- Database persistence with timestamps  
- Clean and maintainable modular design  
- Scalable for batch image processing  

---

## System Workflow

### 1. Input Layer
- Accepts image files (`.jpg`, `.png`, etc.)
- Validates file format

### 2. Preprocessing
- Resize image to model input size (e.g., 224×224)  
- Normalize pixel values  
- Convert image to NumPy array / tensor  

### 3. Model Inference
- Load pre-trained CNN model (e.g., MobileNet / ResNet)  
- Perform forward pass  
- Generate prediction and/or feature vector  

### 4. Persistence Layer
Stores the following in the database:

- File name  
- Prediction result  
- Timestamp  

---

## Project Structure

AI-Image-Processing/
│── main.py # Application entry point
│── image_processor.py # Image preprocessing and inference
│── model_loader.py # CNN model loading
│── database.py # Database connection and operations
│── utils.py # Helper utilities
│── input_images/ # Sample inputs
│── output/ # Processed outputs (optional)
│── requirements.txt
│── README.md


---

## Technologies Used

- Python  
- OpenCV  
- NumPy  
- TensorFlow / Keras  
- Scikit-learn  
- MySQL / SQLite  

---


