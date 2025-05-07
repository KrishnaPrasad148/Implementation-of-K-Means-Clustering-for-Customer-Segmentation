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

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Krishna Prasad S
RegisterNumber:  212223230108

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

### DATASET:
![Dataset](https://github.com/user-attachments/assets/248f51cd-7c1d-4cef-9137-76bcf58eb5e5)


### DATASET INF0:
![Dataset info](https://github.com/user-attachments/assets/5601b911-48af-4e01-b0f7-8ba38bb52a02)

![isnull](https://github.com/user-attachments/assets/c5c89d78-8f8b-420b-834d-a3f0483aa594)


### PLOT USING ELBOW METHOD:
![Plot_elbow_method](https://github.com/user-attachments/assets/8723b3f7-955c-40d4-850b-14ddbac02457)



### K-MEANS CLUSTERING:
![K-mean cluster](https://github.com/user-attachments/assets/a7d2b59f-70ca-412c-8e3f-91c41d202838)


### Y PREDICTED ARRAY:
![Y_predicted](https://github.com/user-attachments/assets/d9fb8d50-906e-46c0-ad5b-63d528b5a15e)


### CUSTOMER SEGMENTATION:
![Customer segment](https://github.com/user-attachments/assets/332e5a3d-1113-4a70-9838-92d2e841e1e5)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
