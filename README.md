# Ex.No: 1B CONVERSION OF NON STATIONARY TO STATIONARY DATA
## Date:17/08/2024
## Name:H.Berjin Shabeck
## Reg no:212222240018

### AIM:
To perform regular differncing,seasonal adjustment and log transformation on studenyt study hour marks data.
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Data
df=pd.read_csv('/content/score.csv')
hours = df['Hours']
scores = df['Scores']

# Create a DataFrame
data = pd.DataFrame({'Hours': hours, 'Scores': scores})

# Regular differencing
data['Scores_Diff'] = data['Scores'].diff()

# Log transformation
data['Scores_Log'] = np.log(data['Scores'])

# Differencing the log-transformed data
data['Scores_Log_Diff'] = data['Scores_Log'].diff()

# Plotting the results
plt.figure(figsize=(14, 10))

# Original Scores
plt.subplot(4, 1, 1)
plt.plot(data['Scores'], marker='o', linestyle='-', color='b')
plt.title('Original Scores Series')
plt.grid(True)

# Regular Differencing
plt.subplot(4, 1, 2)
plt.plot(data['Scores_Diff'], marker='o', linestyle='-', color='r')
plt.title('Differenced Scores Series')
plt.grid(True)

# Log Transformation
plt.subplot(4, 1, 3)
plt.plot(data['Scores_Log'], marker='o', linestyle='-', color='g')
plt.title('Log-Transformed Scores Series')
plt.grid(True)

# Differencing after Log Transformation
plt.subplot(4, 1, 4)
plt.plot(data['Scores_Log_Diff'], marker='o', linestyle='-', color='purple')
plt.title('Differenced Log-Transformed Scores Series')
plt.grid(True)

plt.tight_layout()
plt.show()
```


### OUTPUT:
![download](https://github.com/user-attachments/assets/ae35fba9-a1bc-424e-9511-b6d5b02c0e77)

### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on student study hours score data
