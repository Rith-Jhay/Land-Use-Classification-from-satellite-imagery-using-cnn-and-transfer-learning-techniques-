# Land Use Classification from satellite imagery using cnn and transfer learning techniques.

## Project Overview
This project focuses on solving a remote sensing problem using Convolutional Neural Networks (CNNs). The goal is to classify satellite images into 10 different land use categories such as forest, river, residential, industrial, and agricultural areas.

The project explores how deep learning models can process and analyze satellite imagery to automatically extract meaningful patterns and perform classification.

Two models were implemented and compared:
- Custom Convolutional Neural Network (CNN)
- Pretrained EfficientNet-B0 (Transfer Learning)

---

## Problem Definition
Satellite image classification is a challenging task due to:
- Similar visual patterns between classes
- Variations in lighting and environmental conditions
- Complex spatial features in satellite images

This project aims to develop an efficient CNN-based solution to accurately classify land use from satellite imagery.

---

## Dataset
- Dataset: EuroSAT RGB
- Total Images: ~27,000
- Number of Classes: 10
- Image Size: 64 × 64

Classes include:
Annual Crop, Forest, Herbaceous Vegetation, Highway, Industrial, Pasture, Permanent Crop, Residential, River, Sea/Lake

Dataset Source:
https://zenodo.org/records/7711810

---

## Data Preprocessing
The dataset was preprocessed using the following steps:
- Image resizing and normalization
- Data augmentation:
  - Horizontal flipping
  - Rotation
  - Color transformations
- Dataset split:
  - 70% Training
  - 15% Validation
  - 15% Testing

These steps improve model generalization and performance.

---

## Model Design

### Custom CNN
- Built from scratch
- Convolutional layers for feature extraction
- Batch Normalization and ReLU activation
- Max Pooling for dimensionality reduction
- Dropout for overfitting prevention
- Fully connected layers for classification

### EfficientNet-B0
- Pretrained deep learning model
- Transfer learning approach
- Initial layers frozen
- Final layers fine-tuned for classification

---

## Training Approach
- Optimizer: Adam
- Loss Function: CrossEntropyLoss
- Early stopping applied for Custom CNN
- EfficientNet trained for fixed epochs

---

## Evaluation Metrics
The models were evaluated using:
- Accuracy
- Precision
- Recall
- F1-score

Additional analysis:
- Confusion matrix
- Prediction visualization

---

## Results

| Model | Validation Accuracy | Test Accuracy |
|------|--------------------|--------------|
| Custom CNN | ~95% | ~93–94% |
| EfficientNet-B0 | ~92% | ~91% |

The custom CNN outperformed the pretrained model, indicating better adaptation to domain-specific data.

---

## How to Run the Project

### Step 1: Install Dependencies
pip install torch torchvision matplotlib seaborn pandas

### Step 2: Download Dataset 
wget https://zenodo.org/records/7711810/files/EuroSAT_RGB.zip
unzip EuroSAT_RGB.zip

### Step 3: Open Notebook

Open the Jupyter Notebook or Google Colab file:

Code-file_Group_36.ipynb

### Step 4: Run the Code

Run all cells sequentially to:

Load dataset
Train models
Evaluate performance
Generate visualizations
