# CMPE401 Project 1

## Overview
This project focuses on object detection using deep learning models based on the YOLO (You Only Look Once) framework. The main objective is to evaluate a baseline YOLO model on a challenging dataset and analyze the impact of different improvements such as image resolution and data augmentation.

The project also includes a comparison of multiple YOLO model variants under controlled training conditions.

---

## Dataset

### VisDrone Dataset
- Aerial object detection dataset
- High object density and cluttered scenes
- Contains many small objects (e.g., pedestrians, bicycles)
- Multiple object categories including vehicles and people

---

## Model

### Baseline Model (YOLO11n)
- Lightweight YOLO architecture
- Input image size: 640 × 640
- Trained for 30 epochs
- Evaluated using:
  - mAP@50
  - mAP@50-95
  - Precision
  - Recall

---

## Results

### Baseline Performance
- mAP@50 ≈ 0.282  
- mAP@50-95 ≈ 0.158  
- Precision ≈ 0.407  
- Recall ≈ 0.317  

The model shows stable training behavior with decreasing loss and improving performance metrics. However, it struggles with small object detection, particularly for classes such as bicycles.

---

## Model Evaluation

### Precision-Recall Analysis
- Strong performance on large objects (e.g., cars)
- Weak performance on small objects (e.g., bicycles)
- Indicates imbalance in detection capability

### Confusion Matrix
- Good classification for dominant classes (cars)
- Significant confusion between similar classes (e.g., pedestrian vs people)
- High false positives from background predictions

### Detection Results
- Model detects multiple objects in complex scenes
- Produces excessive bounding boxes
- Many predictions have low confidence scores
- Indicates over-detection behavior

---

## Experiments

### Experiment 1: Image Resolution
- Increased image size from 640 → 960
- mAP@50-95 improved to ≈ 0.199  
- mAP@50 improved to ≈ 0.338  

✔ Conclusion:
Higher resolution improves small object detection by preserving more visual details.

---

### Experiment 2: Data Augmentation
- Applied HSV changes, rotation, and transformations
- mAP@50-95 dropped to ≈ 0.131  
- mAP@50 dropped to ≈ 0.238  

✔ Conclusion:
Data augmentation negatively affected performance due to distortion of important features.

---

## Model Comparison

Four YOLO variants were compared:
- YOLO11n
- YOLOv8n
- YOLOv5nu
- YOLOv10n

### Results
- YOLO11n achieved the best performance (mAP@50-95 ≈ 0.118 under equal conditions)
- Simpler models performed better under limited training

---

## Key Findings

- Small object detection remains a major challenge  
- Increasing image resolution significantly improves performance  
- Data augmentation can negatively impact results if not carefully designed  
- Model complexity does not guarantee better performance  
- Simpler architectures can outperform larger ones under constrained training  

---

## How to Run

1. Open the notebook in Google Colab  
2. Enable GPU (Tesla T4 recommended)  
3. Install dependencies (Ultralytics YOLO)  
4. Run all cells sequentially  

---

## Conclusion

This project demonstrates that YOLO-based models can be effectively applied to aerial object detection tasks, but performance is highly dependent on training configuration. Among all tested factors, increasing image resolution provides the most consistent improvement, while improper data augmentation can degrade performance. The YOLO11n model achieves the best balance between efficiency and accuracy under limited training conditions.
