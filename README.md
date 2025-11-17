# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: EZHILARASI N
RegisterNumber:  212224040088
*/

PROGRAM :

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
kmeans=KMeans(n_clusters=i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No_of_Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segment")

```

## Output:
### 1.DATA.HEAD():
<img width="786" height="256" alt="image" src="https://github.com/user-attachments/assets/43b436ce-2a7e-474c-acc9-26bfd8ab8754" />



### 2.DATA.INF0():
<img width="707" height="387" alt="image" src="https://github.com/user-attachments/assets/9e1258f4-c340-4ab4-981e-fd98676e993f" />



### 3.DATA.ISNULL().SUM():
<img width="436" height="211" alt="image" src="https://github.com/user-attachments/assets/8e330a69-7780-45cc-bb7b-c6fb9f84dbbe" />



### 4.PLOT USING ELBOW METHOD:
<img width="1061" height="787" alt="image" src="https://github.com/user-attachments/assets/f0d21d61-3bc6-48c0-97bf-1847c6c60c05" />



### 5.K-MEANS CLUSTERING:
<img width="575" height="172" alt="image" src="https://github.com/user-attachments/assets/43fb6f28-0168-4221-a04e-d3f3382ad149" />


### 6.Y_PRED ARRAY:
<img width="937" height="287" alt="image" src="https://github.com/user-attachments/assets/d49cace0-d8a1-4c27-a266-b03c47d53868" />


### 7.CUSTOMER SEGMENT:
<img width="1006" height="746" alt="image" src="https://github.com/user-attachments/assets/2ec34259-df90-4ee7-b8bb-97d8e9b2e5e3" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
