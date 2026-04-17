# CMPE401_Project1&2

# CMPE401_Project1
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

  # CMPE401_Project2

    This project explores time-series modeling using deep learning. It includes:
    1. Transformer model for time-series classification (FordA dataset)
    2. LSTM model for time-series forecasting (Jena Climate dataset)
    
    How to run:
    1. Open the notebook in Google Colab
    2. Enable GPU
    3. Run all cells sequentially
    
    Results:
    - Transformer baseline accuracy ~0.51
    - LSTM baseline MAE ~0.25
    - Best improvement achieved using adjusted learning rate and batch size
    
    Improvements:
    1. Increased LSTM hidden size
    2. Stacked LSTM layers
    3. Adjusted learning rate and batch size
    
    Conclusion:
    Optimization parameters had more impact than increasing model complexity.
