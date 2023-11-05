# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Import the required libraries,read the data set.find the number of null data.

2.Find the number of null data.

3.Import sklearn library.

4.Find y predict and plot the graph.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: R.Thivakar
RegisterNumber:  212222240109

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
    kmeans=KMeans(n_clusters = i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")

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
plt.title("Customer Segmets")
```

## Output:
data.head():

![Screenshot 2023-10-26 090836](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/e8063e36-d893-4068-9d58-c5ec3fe51e10)

data.info():

![Screenshot 2023-10-26 090842](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/8e58a45e-d81b-4999-9ee7-3a49dd97f2a9)

data.isnull().sum():

![Screenshot 2023-10-26 090849](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/24dd320e-6b21-430d-a23e-6bd52f6b1314)

Elbow method:

![Screenshot 2023-10-26 090911](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/0ffb48c0-ad45-4c8d-82f1-00c0c5e66b2d)

K-Means:

![Screenshot 2023-10-26 091504](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/c5c3e48c-8a0e-4f18-bc58-6d360f3148d3)

Array value of Y:

![Screenshot 2023-10-26 091643](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/5396b134-9ac1-431e-9f73-a579e0f5c4e8)

Customer Segmentation:

![Screenshot 2023-10-26 091656](https://github.com/premalatha-sureshbabu/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120620842/797e5e9d-a35e-42d2-8bd9-d30c15f7eb0f)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
