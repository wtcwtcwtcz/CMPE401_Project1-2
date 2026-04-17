CMPE 401 Project 2 - Time Series Modeling

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
