# TSAF-Ex-2-Time-Series-Analysis-and-Decomposition

## AIM:
To perform time series analysis and decomposition on the monthly average temperature of a
city using Python.

We will use simple sample temperature data for 12 months and decompose it into:

Observed = Trend + Seasonal + Residual

## PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Dataset 2: Monthly Solar Power Output (12 Months)
solar_output = [
 310, 350, 420, 500, 580, 620,
 610, 560, 480, 400, 330, 290
]

# Create date index for 2025
dates = pd.date_range(start="2025-01-01", periods=12, freq="ME")

# Create time series
data = pd.Series(solar_output, index=dates)
print("Monthly Solar Energy Production (kWh):")
print(data)

# Plot original series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="s", color="orange")
plt.title("Monthly Solar Power Output")
plt.xlabel("Month")
plt.ylabel("Energy (kWh)")
plt.grid(True)
plt.show()

# Decompose time series
result = seasonal_decompose(data, model="additive", period=12)
result.plot()
plt.show()
```

## OUTPUT:

<img width="757" height="598" alt="image" src="https://github.com/user-attachments/assets/c692962b-c911-4912-9097-61b4e0c074de" />
