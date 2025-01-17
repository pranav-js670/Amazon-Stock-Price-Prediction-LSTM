# Amazon-Stock-Price-Prediction-LSTM

# Amazon Stock Price Prediction using LSTM

This project demonstrates time series analysis and prediction of Amazon stock prices using a Long Short-Term Memory (LSTM) neural network. Built with PyTorch, the model leverages historical stock data to forecast future prices, enabling stock trend prediction based on past performance.

## Dataset

The dataset used in this project consists of historical stock prices of Amazon, containing the following columns:

- **Date**: Date of the stock data
- **Open**: Opening price
- **High**: Highest price
- **Low**: Lowest price
- **Close**: Closing price
- **Adj Close**: Adjusted closing price
- **Volume**: Trading volume

The dataset ranges from 1997-05-15 to 2023-04-05 with 6516 rows and 7 columns.

## Project Workflow

1. **Data Preprocessing**  
   - Date column is converted to `datetime` format.
   - Features are shifted to create time steps for training (lookback of 7 days).
   - MinMax scaling is applied to normalize data to the range (-1, 1).

2. **Model Creation**  
   - LSTM model is created with a specified number of stacked layers and hidden units.
   - The model is trained to predict the next day's closing price based on the past 7 days.

3. **Training and Evaluation**  
   - The data is split into training and testing sets.
   - The model is trained using the Mean Squared Error (MSE) loss function and Adam optimizer.
   - The training process runs for a set number of epochs (10 in this case).

## Files

- **`stock_price_prediction.py`**: Main file where the LSTM model is built, trained, and evaluated.
- **`data.csv`**: The historical stock price data (CSV format).
- **`README.md`**: Project documentation.

## Requirements

- Python 3.x
- PyTorch
- Pandas
- NumPy

You can install the required dependencies using:

```bash
pip install -r requirements.txt
```

## Model Architecture

The LSTM model used in this project consists of:

- Input Layer: 1 feature (the previous day's closing price).
- LSTM Layer: 1 stacked layer with 4 hidden units.
- Fully Connected Layer: Output the predicted price.

## License

This project is licensed under the MIT License.
