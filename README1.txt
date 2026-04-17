# YOLO Object Detection on VisDrone

## Overview
This project evaluates different YOLO models on the VisDrone dataset.

## Dataset
VisDrone dataset with small objects and dense scenes.

## Models
- YOLO11n
- YOLOv8n
- YOLOv5nu
- YOLOv10n

## Experiments
Baseline (mAP50-95: 0.158)
Higher Resolution (0.199)
Augmentation (0.131)

## Model Comparison
YOLO11n: 0.118
YOLOv8n: 0.116
YOLOv10n: 0.108
YOLOv5nu: 0.106

## How to Run
pip install ultralytics

from ultralytics import YOLO
model = YOLO("yolo11n.pt")
model.train(data="VisDrone.yaml", epochs=30)
