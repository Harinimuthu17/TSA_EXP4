### Name:M.Harini
### Reg No: 212222240035.
### Date:

# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES

### AIM:
To implement ARMA model in python.

### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('microsoft_Stock.csv', nrows =200)

# Use the 'Close' price column
model = data['Open'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)
```
### OUTPUT:

#### SIMULATED ARMA(1,1) PROCESS:
![Screenshot 2024-09-20 094904](https://github.com/user-attachments/assets/44e58354-4bb2-4834-8a4c-bc361ed68dc9)

#### Partial Autocorrelation:
![Screenshot 2024-09-20 094949](https://github.com/user-attachments/assets/46be7f63-85d9-4f9c-9c66-597b887f1411)

#### Autocorrelation:
![Screenshot 2024-09-20 094926](https://github.com/user-attachments/assets/216c458b-4fba-4f2e-800b-193e51a41c1c)


#### SIMULATED ARMA(2,2) PROCESS:
![Screenshot 2024-09-20 094940](https://github.com/user-attachments/assets/ebe15d79-dfd8-45e1-a398-99f45db4d522)

#### Partial Autocorrelation


![Screenshot 2024-09-20 105324](https://github.com/user-attachments/assets/6192646a-2e34-4a9d-a563-44a8fb8567ee)

#### Autocorrelation
![Screenshot 2024-09-20 105310](https://github.com/user-attachments/assets/63e2b0b3-fcbd-424a-b901-ac8b0e1ae98c)

### RESULT:
Thus, a python program is created to fit ARMA Model successfully.




