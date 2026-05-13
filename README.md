# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 09/05/2026

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf

data = pd.read_excel('/content/Hyderabad-AirQ.xlsx')

data['Date'] = pd.to_datetime(data['Date'])

data.set_index('Date', inplace=True)

pm25 = data['PM2.5'].dropna()

plt.figure(figsize=(10,6))

plot_acf(
    pm25,
    lags=min(35, len(pm25)-1),
    alpha=0.05
)

plt.title('AutoCorrelation Function (ACF) for PM2.5')

plt.xlabel('Lags')

plt.ylabel('ACF Value')

plt.grid(True)

plt.show()
```

### OUTPUT:
<img width="587" height="455" alt="image" src="https://github.com/user-attachments/assets/570cbdd1-6ba2-4111-8b5c-4859001fa256" />

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
