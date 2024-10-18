# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary packages using import statement.


2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().


3.Import KMeans and use for loop to cluster the data.


4.Predict the cluster and plot data graphs.


5.Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: GOPIKA K
RegisterNumber: 212222040046
*/
```

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Dataset-20230524.zip")
data

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

## DATA.HEAD():
![image](https://github.com/user-attachments/assets/910facc4-7530-4eab-a825-d0d0d467496b)
## DATA.info():
![image](https://github.com/user-attachments/assets/e6bf0144-881c-4130-80ca-e98e7e1848ff)
## NULL VALUES:
![image](https://github.com/user-attachments/assets/1f1824a5-da99-404d-98d9-771b45355b23)
## ELBOW GRAPH:
![image](https://github.com/user-attachments/assets/de36cc00-066f-4b67-a192-d63365f06c6a)
## CLUSTER FORMATION:
![image](https://github.com/user-attachments/assets/01ebf846-5f4e-4743-8d11-0881abe13101)
## PREDICICTED VALUE:
![image](https://github.com/user-attachments/assets/0c7b7d4c-2885-4730-9bd5-170758c5bc77)
## FINAL GRAPH(D/O):
![image](https://github.com/user-attachments/assets/e06bf1b2-6d12-4acc-bd78-cd8c19eb0ab3)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
