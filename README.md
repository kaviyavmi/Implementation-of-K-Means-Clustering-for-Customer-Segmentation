# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import the KMeans and fit the data in the model

4.Plot the cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KAVIYA V M 
RegisterNumber: 212224040154 
*/


```

```PYTHON
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Annie Anjana A
RegisterNumber: 212224040025 
*/
import pandas as pd 
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
display(data.head())
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    Kmeans=KMeans (n_clusters = i, init ="k-means++")
    Kmeans.fit(data.iloc[:,3:])
    wcss.append(Kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
display(pd.DataFrame(y_pred, columns=["Predicted Cluster"])) # Display y_pred as a DataFrame
data["clusters"]=y_pred
df0=data[data["clusters"]==0]
df1=data[data["clusters"]==1]
df2=data[data["clusters"]==2]
df3=data[data["clusters"]==3]
df4=data[data["clusters"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="clusters0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="clusters1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="clusters2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="clusters3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="clusters4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

<img width="715" height="738" alt="Screenshot 2026-02-27 104547" src="https://github.com/user-attachments/assets/fe7bf0ad-efcf-440a-9224-0ca0ab66f21f" />

<img width="816" height="774" alt="Screenshot 2026-02-27 104730" src="https://github.com/user-attachments/assets/fda9b153-117a-4a3c-89fc-906926ce3c04" />

<img width="699" height="546" alt="Screenshot 2026-02-27 104802" src="https://github.com/user-attachments/assets/78721776-c3e2-4737-83e2-f59d6d8ab593" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
