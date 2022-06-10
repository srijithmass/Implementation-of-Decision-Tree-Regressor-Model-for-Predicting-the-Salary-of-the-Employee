# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries.
2. Upload the csv file and read the dataset.
3. Check for any null values using the isnull() function.
4. From sklearn.tree inport DecisionTreeRegressor.
5. Import metrics and calculate the Mean squared error.
6. Apply metrics to the dataset, and predict the output.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SRIJITH R
RegisterNumber:  212221240054
*/
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"] = le.fit_transform(data["Position"])
data.head()
x = data[["Position","Level"]]
y = data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2 = metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## Output:
### Read Data:
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s1.png)
### Data Info:
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s2.png)
### Null values:
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s3.png)
### After applying LabelEncoder:
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s4.png)
### Mean Square Error(MSE):
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s5.png)
### R square(r^2):
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s6.png)
### Data Prediction:
![Decision Tree Regressor Model for Predicting the Salary of the Employee](./output/s7.png)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
