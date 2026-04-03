Stock Price Prediction Model 
This project implements a Stock Price Prediction Model based on investor sentiment and optimized deep learning. It uses Artificial Neural Networks (ANN) and Long Short-Term Memory (LSTM) networks to forecast stock closing prices. The application provides a graphical user interface (GUI) built with Tkinter, allowing users to upload stock datasets, preprocess data, train models, and compare performance.

Features
Upload Stock Dataset – Load CSV files containing stock price history.

Preprocess Dataset – Handle missing values, normalize data using MinMaxScaler, and split into training (80%) and testing (20%).

Train ANN Model – Train a feedforward neural network and display predicted vs actual prices.

Train LSTM Model – Train a multi‑layer LSTM network and evaluate predictions.

MSE Comparison Graph – Compare Mean Squared Error (MSE) of both models with a bar chart.

Scrollable Stock Graphs – View Open, High, Low, Close prices over time with zoom/pan tools.

Supports Multiple Stocks – Works with Apple (AAPL), Facebook (FB), Microsoft (MSFT), Tesla (TSLA), and TATA Global Beverages.

Dataset Format
The application expects a CSV file with the following columns (for multi‑stock files):

Date – in YYYY-MM-DD format

Open, High, Low, Close – daily price values

Stock – stock name (e.g., AAPL, FB, MSFT, TSLA)

For the TATA dataset (NSE-Tata-Global-Beverages-Limited.csv), only Date, Open, High, Low, Close are required.

Installation & Setup
Prerequisites
Python 3.7+

pip package manager

Install Dependencies
Run the following command to install required libraries:

bash
pip install numpy pandas matplotlib scikit-learn keras tensorflow
Run the Application
Clone the repository:

bash
git clone https://github.com/yourusername/stock-prediction-ann-lstm.git
cd stock-prediction-ann-lstm
Place your dataset files in a folder named Dataset/ (or modify the path in the code).

Execute the main script:

bash
python Main.py
Or double‑click run.bat (if created).

How to Use (Step‑by‑Step)
Select a stock from the dropdown (AAPL, FB, MSFT, TSLA).

Upload the dataset – click Upload Stock Price Dataset and choose your CSV file.

A graph will show the closing price history of the selected stock.

Preprocess the dataset – click Preprocess Dataset.

Missing values are filled, data is normalized, and split into train/test.

Train ANN – click Run ANN Algorithm.

The model trains (only 1 epoch for demonstration; increase for better accuracy).

Predicted vs actual prices are printed, and a comparison graph is shown.

Train LSTM – click Run LSTM Algorithm.

Similarly, LSTM predictions and MSE are displayed.

Compare models – click MSE Comparison Graph to see a bar chart of MSE values.

View full scrollable graphs – click View Full Graph (Scroll) to examine Open, High, Low, Close separately.

Model Details
ANN – 2 hidden layers with 50 neurons each, ReLU activation, Adam optimizer, mean squared error loss.

LSTM – 4 LSTM layers (50 units each) with Dropout (0.2) after each layer, followed by a Dense output layer.

Data Normalization – MinMaxScaler scales features to [0,1].

Evaluation Metric – Mean Squared Error (MSE). Lower MSE indicates better performance.

Note: The code uses only 1 epoch for quick demonstration. For production, increase epochs (e.g., 50–100) to improve accuracy.

Results (from testing)
ANN consistently achieves a lower MSE compared to LSTM on the tested stocks (TATA, FB, AAPL, TSLA, MSFT).

Both models produce predictions that closely overlap with actual test prices, as seen in the output graphs.

Example output:

text
ANN MSE value : 0.000234
ANN Accuracy  : 0.999766
LSTM MSE value : 0.000456
LSTM Accuracy  : 0.999544
File Structure
text
├── Main.py                 # Main application code
├── Dataset/                # Folder containing stock CSV files
│   ├── stock_data.csv      # Example multi‑stock dataset
│   └── NSE-Tata-Global-Beverages-Limited.csv
├── model/                  # Saved models (created after first run)
│   ├── ann_model.json
│   ├── ann_model_weights.h5
│   ├── lstm_model.json
│   └── lstm_model_weights.h5
├── README.md               # This file
└── run.bat                 # (Optional) Windows batch file to launch the app

Limitations & Future Work
Sentiment Analysis – Although the project title mentions investor sentiment, the current version does not incorporate sentiment data. Future work will integrate forum posts (e.g., East Money) and compute sentiment indices.

Hyperparameter Optimization – The models use fixed architectures. The Sparrow Search Algorithm (SSA) can be added to automatically tune hyperparameters.

Longer Training – Only 1 epoch is used for quick testing; increase epochs for better performance.

Additional Data Sources – News headlines, macroeconomic indicators, and social media sentiment can further improve accuracy.

License
This project is for educational and research purposes.

Acknowledgements
Dataset sources: Kaggle, Yahoo Finance.

Built with Keras, TensorFlow, scikit‑learn, and Tkinter.
