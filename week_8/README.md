# PM2.5 AIR QUALITY FORECASTING

### Table of contents
 - Introduction
 - Dataset
 - Exploratory Data Analysis
 - Data Preprocessing and Feature Engineering
 - Modeling and Forecasting
 - Evaluation and Results
 - Conclusion
 - Dependencies
 - Usage
 
### Introduction
- This project aims to forecast PM2.5 air pollutant levels using various time series modeling techniques. The forecasting of PM2.5 levels can assist in mitigating health risks by providing early warnings to the public and policymakers.

### Dataset
- The dataset used in this project contains hourly measurements of air quality, focusing on PM2.5 and other related pollutants, along with meteorological data.
- The dataset was provided in ARFF format and includes features such as:

    - NO2: Nitrogen Dioxide levels
    - CO: Carbon Monoxide levels
    - O3: Ozone levels
    - TEMP: Temperature
    - PM2.5: Particulate Matter with a diameter of less than 2.5 micrometers

### Exploratory Data Analysis
- Missingness Check: Identified and handled missing values using linear interpolation.
- Rolling Statistics: Generated rolling mean and standard deviation to understand trends and seasonal behavior.
- Stationarity Test: Applied the Augmented Dickey-Fuller test to verify stationarity.
- Seasonal Decomposition: Used seasonal decomposition to separate trend, seasonal, and residual components.

### Data Preprocessing and Feature Engineering
- Added a Date column and set it as the index for easier time-based operations.
- Generated lagged features for PM2.5 to aid in time series modeling.
- Created rolling statistics for important features like PM2.5, TEMP, NO2, and O3 to enhance the model's ability to learn temporal patterns.

### Modeling and Forecasting
1. ARIMA Model
- Built an ARIMA(2, 0, 2) model to capture the trend in PM2.5.
The model did not capture seasonal variations effectively.

2. SARIMA Model
- Built a SARIMA(1, 0, 1)(1, 1, 0, 7) model to capture weekly seasonality.
Performed better than ARIMA by capturing periodic variations.

3. SARIMAX Model with Exogenous Variables
- Added exogenous variables (NO2, CO, O3) to improve the model's predictive capability.
- The model showed improvement by considering the effects of other pollutants on PM2.5 levels.

### Evaluation and Results
- Mean Squared Error (MSE) was used to evaluate the models.
- SARIMAX performed the best, accurately capturing seasonal trends and relationships with exogenous variables.
- Residual Analysis:

    -Residuals from SARIMAX indicated that most autocorrelation was eliminated.

    -Residuals showed some skewness, indicating slight model limitations.

### Dependencies
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- pmdarima