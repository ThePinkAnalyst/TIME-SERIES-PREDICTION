# SARIMA TIME SERIES PREDICTION
## Introduction
The cryptocurrency market is known for its volatility, making forecasting critical for traders, investors, and financial institutions. This project focuses on predicting Litecoin (LTC) exchange rates using the Seasonal Autoregressive Integrated Moving Average (SARIMA) model. SARIMA is an effective tool for time series forecasting, particularly when data exhibit both trends and seasonal patterns.

The purpose of this report is to detail the steps taken to build and evaluate a SARIMA model to predict future Litecoin exchange rates based on historical data.

## Objectives
* To provide accurate predictions of Litecoin exchange rates.
* To assist market participants in making informed trading decisions.
* To explore the seasonal and non-seasonal patterns of Litecoin exchange rates.
* To assess the performance of SARIMA in predicting future values.
  
## Data Overview
The dataset used in this project consists of weekly historical data of Litecoin (LTC) against the US Dollar (USD), spanning from December 2017 to June 2023. The data was obtained from Yahoo Finance, and it includes key variables such as the date and closing price of Litecoin.

## Data Preprocessing
### Handling Missing Values
The dataset was checked for any missing or null values. If any were present, they were removed to ensure the data's integrity.

### Date Formatting
The date column was converted to a standard format for better temporal analysis. This allowed us to extract features such as the year and month for additional insights.

### Outlier Detection
Significant price swings were identified, and any extreme outliers were examined to ensure that they represented real market behavior and not data errors.

## Exploratory Data Analysis
### Trend Analysis
A time series plot of Litecoin’s exchange rate was generated to visualize the overall trend. This revealed the long-term increase and decrease patterns of Litecoin's value. Significant volatility was observed, typical of cryptocurrency markets.

### Seasonality
To explore any recurring patterns in the data, the time series was decomposed into three main components:
* Trend: The general movement of Litecoin’s price over time.
* Seasonality: Repeating short-term cycles within the data, such as annual or monthly fluctuations.
* Residual: The noise or random fluctuations in the data that cannot be explained by the trend or seasonality.
The decomposition showed that Litecoin’s exchange rate exhibits clear seasonal variations, with peaks and troughs occurring at specific intervals, suggesting potential periodic behavior.

## Annual and Monthly Growth Analysis
### Annual Growth
The yearly change in Litecoin's price was calculated to provide insight into how the cryptocurrency's value evolved each year. The growth was found to be highly variable, with some years showing significant gains while others showed notable declines.

### Monthly Growth
Monthly growth rates were also analyzed to detect any regular patterns across the months. This analysis helped in identifying which months tended to show higher or lower growth rates, potentially signaling optimal periods for trading.

# Model Selection: SARIMA
Why SARIMA?
The SARIMA model was chosen due to its ability to handle both trend and seasonality in time series data. SARIMA extends the ARIMA model by including additional seasonal components, making it ideal for data with periodic fluctuations, as seen in Litecoin's historical prices.

## Parameter Selection
The auto_arima function was used to automatically identify the best parameters for the SARIMA model. This function tested various combinations of parameters to optimize the model’s performance. The parameters selected were based on minimizing the Akaike Information Criterion (AIC) and Bayesian Information Criterion (BIC), ensuring a balance between goodness-of-fit and model complexity.

The identified parameters for the SARIMA model included:
* p (autoregressive terms): Captures the relationship between an observation and a specified number of lagged observations.
* d (differencing): Used to make the time series stationary by removing trends.
* q (moving average terms): Models the dependency between an observation and a residual error from a moving average model applied to lagged observations.
* Seasonal order: This includes seasonal counterparts to p, d, and q, as well as the length of the seasonality (weekly in this case).

## Model Training
The SARIMA model was trained using the historical Litecoin exchange rate data. After fitting the model, the residuals were analyzed to ensure that they followed a normal distribution, indicating that the model successfully captured most of the structure in the data.

## Model Evaluation
Forecasting Future Exchange Rates
The SARIMA model was used to predict Litecoin’s future exchange rates over a 90-day horizon. The predicted values were compared against the actual historical data to evaluate the model’s accuracy.

## Visualization of Predictions
A line chart was generated to compare the predicted exchange rates with the actual historical values. The forecasted values followed the overall trend of the historical data, indicating that the model successfully captured both seasonal and non-seasonal variations.

## Model Performance
The performance of the SARIMA model was assessed based on the following criteria:
* Mean Absolute Error (MAE): Measures the average magnitude of errors in the predictions.
* Root Mean Squared Error (RMSE): Provides a measure of the standard deviation of the prediction errors.
* Residual Analysis: The residuals were examined for autocorrelation to ensure that there were no patterns left unexplained by the model.

# Conclusion
This project successfully applied a SARIMA model to forecast the Litecoin (LTC) exchange rate using historical weekly data. The model was able to capture both the trend and seasonality inherent in the cryptocurrency's price movements, making it a valuable tool for short-term predictions.

# Key Findings
SARIMA Effectiveness: The model provided reliable forecasts by accounting for both seasonal and non-seasonal components.
Volatility: As expected, Litecoin's exchange rates are highly volatile, with frequent fluctuations. However, the SARIMA model successfully handled this volatility and produced reasonable predictions.
Seasonal Patterns: Clear seasonal patterns were identified, with specific months showing more significant growth or decline, providing potential trading signals for market participants.
