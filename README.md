# Stock-Price-Prediction-and-Forecasting
- LSTM Model for predicting and forecasting the stock price predictions
#
- This project focuses on predicting stock prices using a deep learning model, specifically a Long Short-Term Memory (LSTM) neural network. LSTM is a type of recurrent neural network (RNN) designed to handle sequence prediction problems by learning from historical time series data. The goal is to predict future stock prices based on past trends, offering valuable insights for investors and traders.
- Predicting stock prices is inherently difficult due to market volatility and the complex interactions of various external factors. Traditional statistical methods struggle with long-range dependencies in time series data. LSTM networks, however, excel at capturing both short and long-term trends, making them highly effective for time series forecasting.
- The objective of this project is to:
  - Build and train an LSTM model using historical stock price data.
  - Evaluate the performance of the model in predicting stock prices.
  - Plot and compare actual vs. predicted stock prices to analyze the model’s accuracy.
#
Data Preprocessing
- Dataset: The dataset used is the historical stock price data (e.g., daily closing prices) which may contain columns such as Date, Open, Close, High, Low, and Volume.
- Scaling: The stock prices are scaled between 0 and 1 using Min-Max scaling to ensure that the data is normalized and prepared for the LSTM model, which is sensitive to the scale of input data.
- Splitting Data: The dataset is split into training (80%) and testing (20%) sets. The testing data is used to validate the model's ability to predict future stock prices.
- Creating Time Steps: Time steps are created to represent a sliding window over the time series data. For example, a time step of 60 means that the model will predict the next stock price based on the previous 60 days of stock prices.
#
LSTM Model
- Architecture:
  - The model consists of two LSTM layers with 50 units each.
  - A Dropout layer with a dropout rate of 20% is added after each LSTM layer to prevent overfitting.
  - A Dense layer with 25 neurons is used for further abstraction.
  - The output layer is a single Dense neuron that predicts the stock price.
  - Input Shape: The input to the LSTM is a 3D tensor of shape [samples, time steps, features], where samples are the number of sequences, time steps represent the number of days used for prediction (e.g., 60 days), features represent the dimensions of the input data (in this case, 1 feature, which is the stock price).
- Training:
  - The model is trained on the training set for 10 epochs using the Adam optimizer and the Mean Squared Error (MSE) loss function.
  - A batch size of 64 is used to train the model in mini-batches, improving training efficiency.
- Model Evaluation and Prediction
  - Inverse Transform: After making predictions on the test data, the predicted values are inverse transformed to return them to the original scale.
  - R² Score: The coefficient of determination (R² score) is computed to evaluate the model’s performance. The R² score gives an indication of how well the model captures the variance in the stock prices.
 #
 ## LIBRARIES USED
- NumPy, Pandas for data manipulation.
- Matplotlib for data visualization.
- TensorFlow/Keras for building and training the LSTM model.
- sklearn for scaling the data and calculating performance metrics.
