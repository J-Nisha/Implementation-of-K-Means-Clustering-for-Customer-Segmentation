# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1. Start the program

Step 2. Import the necessary python libraries

Step 3. Read the dataset of Mall_Customers csv file

Step 4. From sklearn libraary select the cluster and import KMeans Clustering

Step 5. Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method

Step 6. Plot the graph x and y as Number of Clusters and wcss respectively

Step 7. Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5)

Step 8. Stop the program 

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by:Nisha.J
RegisterNumber:212223040133  

```
```
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Mall_Customers.csv")
df.head()
df.info()
df.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])
y_pred = km.predict(df.iloc[:,3:])
print("Predicted values : ")
y_pred
df["cluster"] = y_pred
df0 = df[df["cluster"]==0]
df1 = df[df["cluster"]==1]
df2 = df[df["cluster"]==2]
df3 = df[df["cluster"]==3]
df4 = df[df["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer segments")
```

## Output:
## Head:
![Screenshot 2024-11-04 090012](https://github.com/user-attachments/assets/0ac8af05-e467-42c6-a2b9-2029da3c1cd6)

## Info:
![Screenshot 2024-11-04 090128](https://github.com/user-attachments/assets/162ebf9a-bf20-4425-b86c-755f5d79f76d)

## Number of null values:
![Screenshot 2024-11-04 090247](https://github.com/user-attachments/assets/bd96034b-0119-4f27-8dfc-61b954f61040)

## Graph:
![Screenshot 2024-11-04 090414](https://github.com/user-attachments/assets/f2773a89-de9e-4597-b711-3dddde60f3aa)

## Number of clusters:
![Screenshot 2024-11-04 090512](https://github.com/user-attachments/assets/3d04b8c8-5a43-476a-91e4-f3745a85295c)

## Predicted values :
![Screenshot 2024-11-04 090616](https://github.com/user-attachments/assets/1fa45c6c-c2dc-456d-930c-7841dc49281e)

## Customer Segments :
![Screenshot 2024-11-04 090700](https://github.com/user-attachments/assets/d439ffca-40a1-4773-8a09-e67b32059a54)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
