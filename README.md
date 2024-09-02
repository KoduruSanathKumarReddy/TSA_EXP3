# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 

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
import matplotlib.pyplot as plt

import numpy as np

data = [3, 16, 156, 47, 246, 176, 233, 140, 130,
101, 166, 201, 200, 116, 118, 247,
209, 52, 153, 232, 128, 27, 192, 168, 208,
187, 228, 86, 30, 151, 18, 254,
76, 112, 67, 244, 179, 150, 89, 49, 83, 147, 90,
33, 6, 158, 80, 35, 186, 127]

lags = range(35)


# Pre-allocate autocorrelation table
~~~
autocorr = np.zeros(len(lags))
~~~

# Mean
~~~
mean = np.mean(data)
~~~

# Variance
~~~
variance = np.var(data)
~~~

# Normalized data
~~~
normalized_data = (data - mean) / np.sqrt(variance)
~~~
#Go through lag components one-by-one
~~~
for i, lag in enumerate(lags):
    if lag == 0:
        autocorr[i] = 1.0
    else:
        autocorr[i] = np.sum(normalized_data[:-lag] * normalized_data[lag:]) / len(data)
~~~

# display the graph
plt.figure(figsize=(10, 5))
plt.stem(lags, autocorr)
plt.title('Autocorrelation')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()

### OUTPUT:
<img width="875" alt="image" src="https://github.com/user-attachments/assets/91618dd5-ae23-4720-b07f-adbc982b1727">

### RESULT:
        Thus the python code is successfully implemented the auto correlation function in python.
