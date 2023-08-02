# Remaining useful life prediction of turbofan engines

As the prediction of Remaining Useful Life (RUL) is a crucial part of preventive maintenance, the goal of this project is to forecast the RUL of turbofan jet engines. The project utilizes the C-MAPSS dataset provided by NASA, which consists of four different datasets (FD001-FD004) representing various combinations of operational conditions and failure modes. For this project, the dataset FD001, which pertains to High-Pressure Compressor (HPC) failures, is used. The training dataset contains a total of 20,631 samples, each with features from 100 engines and 21 sets of sensors, making it a multivariate time series forecasting problem.

## Data Visualization:

1. Maximum life chart and engine life distribution chart for each unit.
2. Correlation coefficient chart between sensors and RUL.
3. Line chart showing the relationship between sensors and RUL for each engine.
4. Value distribution chart for each sensor.

## Feature Engineering:

1. Based on the line chart showing the relationship between sensors and engine RUL, sensors 1, 5, 10, 16, 18, and 19 are found to be constant. Hence, these features are removed. Finally, the data is normalized.

## Machine Learning Model:

1. "Rolling mean feature" is added to the data, representing the average value of features over 10 time periods.
2. Seven models are built: Linear regression, Light GBM, Random Forest, KNN, XGBoost, SVR, and Extra Tree.
3. MAE, RMSE, and R2 are used as evaluation metrics. SVR performs the best with an R2 of 0.61 and RMSE = 25.7.

## Deep Learning Model:

1. The time window length is set to 30, and the shift length is set to 1. The training and test data are processed to be in a three-dimensional format for input to the models.
2. Six deep learning models are built: CNN, LSTM, Stacked LSTM, Bi-LSTM, GRU, and a hybrid model combining CNN and LSTM.
3. Convergence charts and evaluation of test data predictions are plotted. Each model has an R2 higher than 0.85, with Bi-LSTM achieving an R2 of 0.89 and RMSE of 13.5.
