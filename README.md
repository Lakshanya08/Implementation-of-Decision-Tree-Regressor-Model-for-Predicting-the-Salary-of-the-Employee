# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas.
2. Calculate the null values present in the dataset and apply label encoder. 
3. Determine test and training data set and apply decison tree regression in dataset.
4. Calculate Mean square error,data prediction and r2

## Program:
```
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeRegressor
from sklearn import metrics
from sklearn.preprocessing import LabelEncoder
```
```
data = pd.read_csv("/content/Salary.csv")
```
```
print(data.head())
print(data.info())
print(data.isnull().sum())
```
```
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
print(data.head())
```
```
x = data[["Position", "Level"]]
y = data["Salary"]
```
```
x_train, x_test, y_train, y_test = train_test_split(
x, y, test_size=0.2, random_state=2
)
```
```
dt = DecisionTreeRegressor()
dt.fit(x_train, y_train)
```
```
y_pred = dt.predict(x_test)
mse = metrics.mean_squared_error(y_test, y_pred)
print("Mean Squared Error:", mse)
```
```
r2 = metrics.r2_score(y_test, y_pred)
print("R2 Score:", r2)
```
```
print("Predicted Salary for [5,6]:", dt.predict([[5, 6]]))
```
```
plt.figure(figsize=(20, 8))
plot_tree(dt, feature_names=x.columns, filled=True)
plt.show()
```
Developed by: N.Lakshanya
RegisterNumber: 212224230136

## Output:

![image](https://github.com/user-attachments/assets/7d19542b-77e1-49dd-97fb-7a53c026d901)
![image](https://github.com/user-attachments/assets/ae45f9bb-2621-41fa-98de-94fd9c8e64d7)
![image](https://github.com/user-attachments/assets/478cc635-76d9-4852-8c27-2eaa483f890a)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
