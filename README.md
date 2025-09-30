# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset  
2.check for null values   
3.Import kmeans and fit it to the dataset    
4.Plot the graph using elbow method    
5.Print the predicted array    
6.Plot the customer segments    

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRIYANKA P
RegisterNumber:  212224230212
*/
```
```python

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
<img width="647" height="221" alt="image" src="https://github.com/user-attachments/assets/ec6d5855-273d-4685-9471-03c23743e070" />


### 2.DATA.INF0():
<img width="620" height="272" alt="image" src="https://github.com/user-attachments/assets/c1cac68e-0e8b-4fcc-94ea-759866e10dbe" />


### 3.DATA.ISNULL().SUM():

<img width="467" height="149" alt="image" src="https://github.com/user-attachments/assets/165f297c-8b5e-48ea-aba5-94eb90a8e2ca" />


### 4.PLOT USING ELBOW METHOD:
<img width="897" height="614" alt="image" src="https://github.com/user-attachments/assets/e595a499-4fa0-41b2-8679-97464731af41" />


### 5.K-MEANS CLUSTERING:
<img width="385" height="146" alt="image" src="https://github.com/user-attachments/assets/d2ea68e3-9cae-4f88-8f79-8ef62e6e00f9" />

### 6.Y_PRED ARRAY:
<img width="880" height="237" alt="image" src="https://github.com/user-attachments/assets/50c4e363-2769-4067-b0d0-feb385d6dfd2" />

### 7.CUSTOMER SEGMENT:

<img width="939" height="592" alt="image" src="https://github.com/user-attachments/assets/744eb684-82a0-4a15-8ba4-7925a2348996" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
