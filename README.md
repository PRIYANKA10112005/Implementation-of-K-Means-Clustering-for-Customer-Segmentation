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

<img width="647" height="221" alt="image" src="https://github.com/user-attachments/assets/813c394b-351c-4b83-9fcd-8d1bdf3f8002" />


### 2.DATA.INF0():

<img width="620" height="272" alt="image" src="https://github.com/user-attachments/assets/f9e98331-377c-42c9-a45f-9c159c6e6930" />


### 3.DATA.ISNULL().SUM():


<img width="467" height="149" alt="image" src="https://github.com/user-attachments/assets/8482e694-d979-417d-a51d-33c9b94a0a50" />


### 4.PLOT USING ELBOW METHOD:

<img width="897" height="614" alt="image" src="https://github.com/user-attachments/assets/c127ff15-85b1-4805-a7ab-d5dcbca28a2f" />


### 5.K-MEANS CLUSTERING:

<img width="385" height="146" alt="image" src="https://github.com/user-attachments/assets/1bba2609-8e76-422c-bd47-7b820c805d84" />


### 6.Y_PRED ARRAY:

<img width="880" height="237" alt="image" src="https://github.com/user-attachments/assets/7e1bb5f4-0074-4161-8af9-3659e283ff66" />






### 7.CUSTOMER SEGMENT:


<img width="939" height="592" alt="image" src="https://github.com/user-attachments/assets/3dd40769-188a-43d0-8d18-b20716713210" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
