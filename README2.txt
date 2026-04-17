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
