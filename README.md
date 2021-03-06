## Simple_Linear_Regression

Simple linear regression is a statistical method that allows us to study relationships between two continuous (quantitative) variables.

1. variable denoted x, is regarded as the predictor, explanatory, or independent variable.
 
2. other variable, denoted y, is regarded as the response, outcome, or dependent variable.
 
### Import libraries and dataset

import numpy as np

import matplotlib.pyplot as plt

import pandas as pd

dataset = pd.read_csv("Salary_Data.csv")

x = dataset.iloc[:, :-1].values

y = dataset.iloc[:, -1].values

### Test and Train set

from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(x, y, test_size = 1/3, random_state = 0)

### Linear Regression

from sklearn.linear_model import LinearRegression

regressor = LinearRegression()

regressor.fit(x_train, y_train)

y_pred = regressor.predict(x_test)

### Visualization 

plt.scatter(x_train, y_train, color = 'red')

plt.plot(x_train, regressor.predict(x_train), color = 'blue')

plt.title("salary vs expeience (Training set)")

plt.xlabel("years of experience")

plt.ylabel("salary")

plt.show()

plt.scatter(x_test, y_test, color = "red")

plt.plot(x_train, regressor.predict(x_train), color = "blue")

plt.title("salary vs expeience (Training set)")

plt.xlabel("years of experience")

plt.ylabel("salary")

plt.show()
