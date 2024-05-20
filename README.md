# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary  packages 
2. Insert the dataset to perform the k - means clustering
3. perform k - means clustering on the dataset 
4. Then print the centroids and labels 
5. Plot graph and display the clusters 

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: YUVASAKTHI N.C
RegisterNumber:212222240120
```
```python
import pandas as pd
import numpy as np
from sklearn.cluster import KMeans
from sklearn.metrics.pairwise import euclidean_distances
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers_EX8.csv")
data
X=data[["Annual Income (k$)","Spending Score (1-100)"]]
X
plt.figure(figsize=(4,4))
plt.scatter(data["Annual Income (k$)"],data["Spending Score (1-100)"])
plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.show()
k =5
kmeans=KMeans(n_clusters=k)
kmeans.fit(X)
centroids = kmeans.cluster_centers_
labels=kmeans.labels_
print("Centroids:")
print(centroids)
print("Labels:")
print(labels)
colors=['r','g','b','c','m']
for i in range(k):
  cluster_points = X[labels==i]
  plt.scatter(cluster_points["Annual Income (k$)"],cluster_points["Spending Score (1-100)"],
              color=colors[i],label=f'Cluster{i+1}')
  distances=euclidean_distances(cluster_points,[centroids[i]])
  radius=np.max(distances)
  circle=plt.Circle(centroids[i],radius,color=colors[i],fill=False)
  plt.gca().add_patch(circle)

plt.scatter(centroids[:,0],centroids[:,1],marker="*",s=200,color='k',label='Centroids')
plt.title("K- means Clustering")
plt.xlabel("Annual Incme (k$)")
plt.ylabel("Spending Score (1-100)")
plt.legend()
plt.grid(True)
plt.axis("equal")
plt.show()
```
## Output:
- DATASET:

![Screenshot 2024-04-16 162428](https://github.com/abinayasangeetha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393675/1891e1a2-ac5f-400d-b705-d8b8eb334c85)

- CENTROID AND LABEL VALUES:

![Screenshot 2024-04-16 162224](https://github.com/abinayasangeetha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393675/bed2bdd2-5195-4cb7-8acf-633ddc2e61ff)

- CLUSTERING:

![Screenshot 2024-04-16 162233](https://github.com/abinayasangeetha/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393675/f5a8a76e-5011-4c49-9655-44e86d2fdc06)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
