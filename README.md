# CMPE401_Project1&2

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

 # CMPE401 Project 2

    ## Overview
    This project explores time-series modeling using deep learning. Two tasks are implemented:
    
    - Transformer model for time-series classification (FordA dataset)
    - LSTM model for time-series forecasting (Jena Climate dataset)
    
    The objective is to evaluate baseline models and analyze the impact of different model improvements.
    
    ---
    
    ## Datasets
    
    ### FordA Dataset
    - Time-series classification task
    - Each sample contains 500 time steps
    - Binary classification problem
    
    ### Jena Climate Dataset
    - Time-series forecasting task
    - Predict future temperature based on historical weather data
    
    ---
    
    ## Models
    
    ### Transformer (Classification)
    - Multi-head attention
    - Feed-forward layers
    - Residual connections
    
    ### LSTM (Forecasting)
    - Single-layer LSTM baseline
    - Predicts future temperature values
    
    ---
    
    ## Results
    
    ### Transformer
    - Test Accuracy ≈ 0.51  
    - Model failed to learn meaningful patterns
    
    ### LSTM Baseline
    - Test MAE ≈ 0.2502  
    - Shows overfitting (train ↓, val ↑)
    
    ---
    
    ## Improvements
    
    Three modifications were applied to the LSTM model:
    
    1. Increased hidden size (32 → 64)  
       → MAE ≈ 0.2648 (worse)
    
    2. Stacked LSTM layers  
       → MAE ≈ 0.2589 (still worse)
    
    3. Adjusted learning rate and batch size  
       → MAE ≈ 0.2492 (**best result**)
    
    ---
    
    ## Key Findings
    
    - Increasing model complexity did not improve performance  
    - Larger models led to overfitting  
    - Optimization parameters (learning rate & batch size) had the biggest impact  
    
    ---
    
    ## How to Run
    
    1. Open the notebook in Google Colab  
    2. Enable GPU  
    3. Run all cells sequentially  
    
    ---
    
    ## Conclusion
    
    This project demonstrates that proper hyperparameter tuning is more effective than increasing model complexity for time-series modeling.
