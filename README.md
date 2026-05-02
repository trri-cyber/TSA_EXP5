# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 02-05-2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for post covid inflation.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose # Import seasonal_decompose

print("Columns in dataset:", data.columns)

# The 'date' column is already in datetime format from the previous cell.
# Set 'date' as the index for time series analysis
data.set_index('date', inplace=True)

# Remove missing values
data = data.dropna()

series = data['food_price_index']   # Use 'food_price_index' instead of 'Accuracy'

period_value = 12 # Changed to 12 for monthly data seasonality

# Seasonal decomposition
decomposition = seasonal_decompose(
    series,
    model='additive',
    period=period_value
)

# Plot results
plt.figure(figsize=(10, 12))

plt.subplot(411)
plt.plot(data['food_price_index'], label='Original data') # Use 'food_price_index'
plt.legend(loc='upper left')
plt.title('Food Price Index - Original Data') # Update title
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Food Price Index - Trend Plot') # Update title
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Food Price Index - Seasonality Plot') # Update title
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Food Price Index - Residual Plot') # Update title

plt.tight_layout()
plt.show()
```














### OUTPUT:
FIRST FIVE ROWS:
<img width="270" height="192" alt="image" src="https://github.com/user-attachments/assets/c81526b2-93c1-4c09-860c-bc6f9603e6d0" />



PLOTTING THE DATA:

<img width="987" height="303" alt="image" src="https://github.com/user-attachments/assets/e2b2af42-68e2-4e2b-8783-440e70e3249f" />

SEASONAL PLOT REPRESENTATION :

<img width="987" height="301" alt="image" src="https://github.com/user-attachments/assets/4e068cf3-e99e-4bd6-bc12-4014a60f3a76" />


TREND PLOT REPRESENTATION :

<img width="984" height="303" alt="image" src="https://github.com/user-attachments/assets/a3244170-34ae-4208-843a-74dbe02519b1" />


RESIDUAL REPRESENTATION:

<img width="985" height="290" alt="image" src="https://github.com/user-attachments/assets/73bb105b-fe9e-454f-969b-fce59f827632" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
