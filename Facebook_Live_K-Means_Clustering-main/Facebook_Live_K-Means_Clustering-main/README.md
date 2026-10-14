# Facebook Live K-Means Clustering

## 📌 Project Overview

This project applies **K-Means Clustering**, an unsupervised machine learning algorithm, to the **Facebook Live Sellers in Thailand** dataset.

The main objective is to group Facebook Live posts into different clusters based on their engagement-related characteristics such as reactions, comments, shares, and other numerical features.

K-Means clustering works by assigning data points to the nearest cluster centroid and repeatedly updating the centroids until the clusters become stable.

---

## 🎯 Objectives

* Understand the Facebook Live dataset.
* Perform data preprocessing and cleaning.
* Select relevant numerical features for clustering.
* Apply the K-Means clustering algorithm.
* Determine a suitable number of clusters.
* Visualize the resulting clusters.
* Analyze the characteristics of different Facebook Live post groups.
* Understand how clustering can be used for social-media data analysis.

---

## 📊 Dataset

**Dataset:** Facebook Live Sellers in Thailand

The dataset contains information related to Facebook Live posts and their engagement.

Typical features include:

* `status_id`
* `status_type`
* `num_reactions`
* `num_comments`
* `num_shares`
* `num_likes`
* `num_loves`
* `num_wows`
* `num_hahas`
* `num_sads`
* `num_angrys`

The exact columns used for clustering may depend on the preprocessing performed in the project.

---

## 🤖 Machine Learning Algorithm

### K-Means Clustering

K-Means is an **unsupervised learning algorithm** used to divide observations into `K` clusters.

The basic process is:

1. Select the number of clusters `K`.
2. Initialize cluster centroids.
3. Assign each data point to its nearest centroid.
4. Calculate new centroids using the mean of points in each cluster.
5. Repeat the assignment and centroid-update steps until convergence.

Scikit-learn's implementation supports K-Means initialization such as `k-means++` and provides metrics such as **inertia** for evaluating the clustering objective.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** – Data manipulation
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Visualization
* **Scikit-learn** – Machine learning
* **Jupyter Notebook / Google Colab**

---

## 📁 Project Structure

```text
Facebook_Live_K-Means_Clustering/
│
├── Facebook_Live_K-Means_Clustering.ipynb
├── dataset/
│   └── dataset.csv
├── README.md
└── images/
    └── clustering_result.png
```

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Feature Selection
   ↓
Data Scaling
   ↓
Finding Optimal K
   ↓
K-Means Clustering
   ↓
Cluster Visualization
   ↓
Cluster Analysis
   ↓
Conclusion
```

---

## 🧹 Data Preprocessing

The dataset is first inspected for:

* Missing values
* Duplicate records
* Incorrect data types
* Unnecessary columns
* Numerical and categorical features

Only suitable numerical features are selected for K-Means clustering.

Feature scaling may be performed because K-Means uses distance between observations and centroids, so features with larger numerical ranges can otherwise dominate the clustering.

---

## 📈 Finding the Optimal Number of Clusters

The **Elbow Method** can be used to select a suitable value of `K`.

The algorithm is run for different values of `K`, and the **inertia** is recorded.

```python
from sklearn.cluster import KMeans

inertia = []

for k in range(2, 11):
    model = KMeans(n_clusters=k, random_state=42, n_init="auto")
    model.fit(X)
    inertia.append(model.inertia_)
```

The inertia values can then be plotted:

```python
import matplotlib.pyplot as plt

plt.plot(range(2, 11), inertia, marker='o')
plt.xlabel("Number of Clusters (K)")
plt.ylabel("Inertia")
plt.title("Elbow Method")
plt.show()
```

The point where the decrease in inertia starts becoming less significant is commonly considered the **elbow point**. Scikit-learn describes inertia as the within-cluster sum of squared distances to the nearest centroid.

---

## 🚀 Applying K-Means

Example:

```python
from sklearn.cluster import KMeans

kmeans = KMeans(
    n_clusters=3,
    random_state=42,
    n_init="auto"
)

kmeans.fit(X)

labels = kmeans.labels_
```

The cluster labels can then be added to the dataset:

```python
df["Cluster"] = labels
```

---

## 📊 Visualization

For two selected features, clusters can be visualized using a scatter plot:

```python
plt.scatter(
    df["num_reactions"],
    df["num_comments"],
    c=df["Cluster"]
)

plt.xlabel("Number of Reactions")
plt.ylabel("Number of Comments")
plt.title("Facebook Live Posts - K-Means Clustering")
plt.show()
```

This visualization helps identify groups of Facebook Live posts with similar engagement patterns.

---

## 🔍 Cluster Analysis

After clustering, each cluster can be analyzed based on its average engagement.

For example:

| Cluster   | Possible Interpretation |
| --------- | ----------------------- |
| Cluster 0 | Low engagement posts    |
| Cluster 1 | Medium engagement posts |
| Cluster 2 | High engagement posts   |

The actual interpretation should be based on the calculated cluster statistics from the dataset.

Example:

```python
df.groupby("Cluster").mean(numeric_only=True)
```

This helps compare the average reactions, comments, shares, and other engagement metrics across clusters.

---

## 💡 Key Insights

The project can help identify:

* Groups of posts with similar engagement.
* Posts with high reaction activity.
* Posts receiving more comments.
* Posts with higher sharing activity.
* Differences between low-, medium-, and high-engagement posts.
* Potential patterns in Facebook Live content.

---

## ✅ Advantages

* Simple and easy-to-understand clustering algorithm.
* Useful for exploratory data analysis.
* Works well with numerical data.
* Can handle relatively large datasets efficiently.
* Helps discover hidden patterns without predefined labels.

---

## ⚠️ Limitations

* The number of clusters must be selected beforehand.
* Results can depend on centroid initialization.
* K-Means works best when clusters have reasonably suitable shapes and scales.
* Outliers can influence cluster centroids.
* Cluster labels do not automatically have meaningful real-world names.

K-Means can converge to a local minimum, so initialization and the selected number of clusters are important considerations.

---

## 🏆 Conclusion

The **Facebook Live K-Means Clustering** project demonstrates how unsupervised machine learning can be used to discover patterns in social-media engagement data.

By applying preprocessing, feature selection, scaling, the Elbow Method, and K-Means clustering, Facebook Live posts can be grouped according to similarities in their engagement behavior.

This project provides practical experience with **Python, data preprocessing, visualization, unsupervised machine learning, and cluster analysis**.

---

## 👨‍💻 Author

# Facebook Live K-Means Clustering

## 📌 Project Overview

This project applies **K-Means Clustering**, an unsupervised machine learning algorithm, to the **Facebook Live Sellers in Thailand** dataset.

The main objective is to group Facebook Live posts into different clusters based on their engagement-related characteristics such as reactions, comments, shares, and other numerical features.

K-Means clustering works by assigning data points to the nearest cluster centroid and repeatedly updating the centroids until the clusters become stable.

---

## 🎯 Objectives

* Understand the Facebook Live dataset.
* Perform data preprocessing and cleaning.
* Select relevant numerical features for clustering.
* Apply the K-Means clustering algorithm.
* Determine a suitable number of clusters.
* Visualize the resulting clusters.
* Analyze the characteristics of different Facebook Live post groups.
* Understand how clustering can be used for social-media data analysis.

---

## 📊 Dataset

**Dataset:** Facebook Live Sellers in Thailand

The dataset contains information related to Facebook Live posts and their engagement.

Typical features include:

* `status_id`
* `status_type`
* `num_reactions`
* `num_comments`
* `num_shares`
* `num_likes`
* `num_loves`
* `num_wows`
* `num_hahas`
* `num_sads`
* `num_angrys`

The exact columns used for clustering may depend on the preprocessing performed in the project.

---

## 🤖 Machine Learning Algorithm

### K-Means Clustering

K-Means is an **unsupervised learning algorithm** used to divide observations into `K` clusters.

The basic process is:

1. Select the number of clusters `K`.
2. Initialize cluster centroids.
3. Assign each data point to its nearest centroid.
4. Calculate new centroids using the mean of points in each cluster.
5. Repeat the assignment and centroid-update steps until convergence.

Scikit-learn's implementation supports K-Means initialization such as `k-means++` and provides metrics such as **inertia** for evaluating the clustering objective.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** – Data manipulation
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Visualization
* **Scikit-learn** – Machine learning
* **Jupyter Notebook / Google Colab**

---

## 📁 Project Structure

```text
Facebook_Live_K-Means_Clustering/
│
├── Facebook_Live_K-Means_Clustering.ipynb
├── dataset/
│   └── dataset.csv
├── README.md
└── images/
    └── clustering_result.png
```

---

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Feature Selection
   ↓
Data Scaling
   ↓
Finding Optimal K
   ↓
K-Means Clustering
   ↓
Cluster Visualization
   ↓
Cluster Analysis
   ↓
Conclusion
```

---

## 🧹 Data Preprocessing

The dataset is first inspected for:

* Missing values
* Duplicate records
* Incorrect data types
* Unnecessary columns
* Numerical and categorical features

Only suitable numerical features are selected for K-Means clustering.

Feature scaling may be performed because K-Means uses distance between observations and centroids, so features with larger numerical ranges can otherwise dominate the clustering.

---

## 📈 Finding the Optimal Number of Clusters

The **Elbow Method** can be used to select a suitable value of `K`.

The algorithm is run for different values of `K`, and the **inertia** is recorded.

```python
from sklearn.cluster import KMeans

inertia = []

for k in range(2, 11):
    model = KMeans(n_clusters=k, random_state=42, n_init="auto")
    model.fit(X)
    inertia.append(model.inertia_)
```

The inertia values can then be plotted:

```python
import matplotlib.pyplot as plt

plt.plot(range(2, 11), inertia, marker='o')
plt.xlabel("Number of Clusters (K)")
plt.ylabel("Inertia")
plt.title("Elbow Method")
plt.show()
```

The point where the decrease in inertia starts becoming less significant is commonly considered the **elbow point**. Scikit-learn describes inertia as the within-cluster sum of squared distances to the nearest centroid.

---

## 🚀 Applying K-Means

Example:

```python
from sklearn.cluster import KMeans

kmeans = KMeans(
    n_clusters=3,
    random_state=42,
    n_init="auto"
)

kmeans.fit(X)

labels = kmeans.labels_
```

The cluster labels can then be added to the dataset:

```python
df["Cluster"] = labels
```

---

## 📊 Visualization

For two selected features, clusters can be visualized using a scatter plot:

```python
plt.scatter(
    df["num_reactions"],
    df["num_comments"],
    c=df["Cluster"]
)

plt.xlabel("Number of Reactions")
plt.ylabel("Number of Comments")
plt.title("Facebook Live Posts - K-Means Clustering")
plt.show()
```

This visualization helps identify groups of Facebook Live posts with similar engagement patterns.

---

## 🔍 Cluster Analysis

After clustering, each cluster can be analyzed based on its average engagement.

For example:

| Cluster   | Possible Interpretation |
| --------- | ----------------------- |
| Cluster 0 | Low engagement posts    |
| Cluster 1 | Medium engagement posts |
| Cluster 2 | High engagement posts   |

The actual interpretation should be based on the calculated cluster statistics from the dataset.

Example:

```python
df.groupby("Cluster").mean(numeric_only=True)
```

This helps compare the average reactions, comments, shares, and other engagement metrics across clusters.

---

## 💡 Key Insights

The project can help identify:

* Groups of posts with similar engagement.
* Posts with high reaction activity.
* Posts receiving more comments.
* Posts with higher sharing activity.
* Differences between low-, medium-, and high-engagement posts.
* Potential patterns in Facebook Live content.

---

## ✅ Advantages

* Simple and easy-to-understand clustering algorithm.
* Useful for exploratory data analysis.
* Works well with numerical data.
* Can handle relatively large datasets efficiently.
* Helps discover hidden patterns without predefined labels.

---

## ⚠️ Limitations

* The number of clusters must be selected beforehand.
* Results can depend on centroid initialization.
* K-Means works best when clusters have reasonably suitable shapes and scales.
* Outliers can influence cluster centroids.
* Cluster labels do not automatically have meaningful real-world names.

K-Means can converge to a local minimum, so initialization and the selected number of clusters are important considerations.

---

## 🏆 Conclusion

The **Facebook Live K-Means Clustering** project demonstrates how unsupervised machine learning can be used to discover patterns in social-media engagement data.

By applying preprocessing, feature selection, scaling, the Elbow Method, and K-Means clustering, Facebook Live posts can be grouped according to similarities in their engagement behavior.

This project provides practical experience with **Python, data preprocessing, visualization, unsupervised machine learning, and cluster analysis**.

---

## 👨‍💻 Author

**Your Name**

BE – Artificial Intelligence & Data Science
Varhadi Shreya.

## ⭐ Skills Demonstrated

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Scikit-learn` `Machine Learning` `K-Means` `Clustering` `Data Analysis` `Data Visualization`

## ⭐ Skills Demonstrated

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Scikit-learn` `Machine Learning` `K-Means` `Clustering` `Data Analysis` `Data Visualization`
