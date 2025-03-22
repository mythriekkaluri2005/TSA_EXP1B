# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 22-03-2025
## NAME:E.MYTHRI
## REG.NO:212223240034

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:

### Import the necessary Packages

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
### Load the dataset
```
df=pd.read_csv('seattle-weather.csv')
```

### PLot the data without Conversion

```
x=df['date']
y=df['temp_max']
plt.xlabel('Date')
plt.ylabel('Max temp')
plt.plot(x,y)
```

### REGULAR DIFFERENCING

```
df1=df
df1['diff']=df1['temp_max'].diff()
df1=df1.dropna()
x=df1['date']
y=df1['diff']
plt.xlabel('Date')
plt.ylabel('Temperature')
plt.plot(x,y)
```

### SEASONAL ADJUSTMENT
```
df2=df
df2['SeasonalAdjustment'] = df2['temp_max'].rolling(window=3).mean()
df2['SeasonalAdjustment'].dropna()
x=df2['date']
y=df2["SeasonalAdjustment"]
plt.xlabel('Date')
plt.ylabel('Temperature')
plt.plot(x,y)
```

### LOG TRANSFORMATION

```
df3=df
df3['log']=np.log(df3['diff']).dropna()
df3=df3.dropna()
x=df3['date']
y=df3['log']
plt.xlabel('Date')
plt.ylabel('Max temp')
plt.plot(x,y)
```


### OUTPUT:


### WITHOUT CONVERSION:

![image](https://github.com/user-attachments/assets/2a99b6bf-56b5-4656-aff9-1826755a362c)


### REGULAR DIFFERENCING:

![image](https://github.com/user-attachments/assets/0399c7c0-6d8c-4f0f-9988-1cbe80dec75e)


### SEASONAL ADJUSTMENT:

![image](https://github.com/user-attachments/assets/b2fa33bb-db29-40f9-ada9-9c909fc0c212)


### LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/b8cd0788-c1fb-45ba-ba92-8f2303b5d58c)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
