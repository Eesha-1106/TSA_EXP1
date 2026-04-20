# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date:20-04-26

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```py
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv("/content/Chocolate Sales (2).csv")
df.head()
df['Date']=pd.to_datetime(df['Date'], dayfirst=True)
df.dtypes
df.set_index('Date',inplace=True)
df_daily_sales = df['Boxes Shipped'] .groupby(df.index).sum()
df_resampled = df_daily_sales.resample('D').interpolate()
df_resampled.plot(kind='line',label='Total sales',color='black')
plt.title("Time series plot of number of sales each day")
plt.xlabel("Date")
plt.ylabel("Number of sales")
plt.legend()
plt.grid(True)
plt.show()

```

# OUTPUT:

<img width="580" height="471" alt="download" src="https://github.com/user-attachments/assets/925057a6-c5ee-4a40-8eb1-673a05cb0c2a" />





# RESULT:
Thus we have created the python code for plotting the time series of given data.
