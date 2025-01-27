# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1.start the program. 
2.import pandas. 
3.Read the csv file . 
4.print the program. 
5.Display the proram. 
6.Stop the program.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: M.GUNASEKHAR
RegisterNumber:  212221240014
*/

import pandas as pd
data = pd.read_csv("Placement_Data.csv")
print(data.head())
data1 = data.copy()
data1= data1.drop(["sl_no","salary"],axis=1)
print(data1.head())
data1.isnull().sum()
data1.duplicated().sum()
from sklearn.preprocessing import LabelEncoder
lc = LabelEncoder()
data1["gender"] = lc.fit_transform(data1["gender"])
data1["ssc_b"] = lc.fit_transform(data1["ssc_b"])
data1["hsc_b"] = lc.fit_transform(data1["hsc_b"])
data1["hsc_s"] = lc.fit_transform(data1["hsc_s"])
data1["degree_t"]=lc.fit_transform(data["degree_t"])
data1["workex"] = lc.fit_transform(data1["workex"])
data1["specialisation"] = lc.fit_transform(data1["specialisation"])
data1["status"]=lc.fit_transform(data1["status"])
print(data1)
x = data1.iloc[:,:-1]
print(x)
y = data1["status"]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(solver="liblinear")
print(lr.fit(x_train,y_train))
y_pred = lr.predict(x_test)
print(y_pred)
from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test,y_pred)
print(accuracy)
from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
print(confusion)
from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test,y_pred)
print(classification_report1)
print(lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]]))
```

## Output:
![1](https://user-images.githubusercontent.com/95043391/174114891-27ce9ee7-8fa9-4f55-8ce0-d3d4c0ad6c6b.PNG)
![2](https://user-images.githubusercontent.com/95043391/174114923-2f3d623a-c5ff-4356-af2e-4181d7777820.PNG)
![3](https://user-images.githubusercontent.com/95043391/174114941-5f62ad6c-d88b-4289-ade1-c1c096d8b3d0.PNG)
![4](https://user-images.githubusercontent.com/95043391/174114984-5758d293-d7c0-4cb4-aaa1-895414a9737a.PNG)
![5](https://user-images.githubusercontent.com/95043391/174114999-3efce097-cbcd-44ec-83e4-38ae1642bc3e.PNG)
![6](https://user-images.githubusercontent.com/95043391/174115032-fc75c3a1-46c6-477e-aa11-0f6d8efe969c.PNG)
![7](https://user-images.githubusercontent.com/95043391/174115064-079c6b0a-622f-40a9-b7a5-7d3796a83c49.PNG)
![8](https://user-images.githubusercontent.com/95043391/174115132-53e4c767-cddc-48a6-848f-73d155560d01.PNG)


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
