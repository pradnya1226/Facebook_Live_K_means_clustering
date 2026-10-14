Facebook Live K-Means Clustering

📌 Project Overview

This project uses the K-Means Clustering algorithm to group Facebook Live posts based on user engagement. It analyzes numerical features such as reactions, comments, likes, and shares to identify patterns in social media activity.

The project uses the Facebook Live Sellers in Thailand dataset and demonstrates how unsupervised machine learning can help analyze social media data.

🎯 Objectives

- Understand and analyze Facebook Live data.
- Clean and preprocess the dataset.
- Apply the K-Means Clustering algorithm.
- Group posts with similar engagement patterns.
- Visualize clusters using graphs.
- Identify patterns in reactions, comments, likes, and shares.

📊 Dataset

Dataset Name: Facebook Live Sellers in Thailand

The dataset contains information about Facebook posts published by sellers in Thailand.

Important features include:

- "status_type" – Type of Facebook post.
- "num_reactions" – Total reactions received.
- "num_comments" – Number of comments.
- "num_shares" – Number of shares.
- "num_likes" – Number of likes.
- "num_loves" – Number of love reactions.

Dataset source: "UCI Machine Learning Repository" (https://archive.ics.uci.edu/dataset/488/facebook+live+sellers+in+thailand)

🤖 Algorithm Used

K-Means Clustering

K-Means is an unsupervised machine learning algorithm that divides data into a specified number of clusters.

Working steps:

1. Load the dataset.
2. Clean and preprocess the data.
3. Select relevant numerical features.
4. Choose the number of clusters (K).
5. Apply the K-Means algorithm.
6. Assign each data point to a cluster.
7. Visualize and analyze the results.

🛠️ Technologies Used

- Python – Programming language.
- Pandas – Data manipulation and analysis.
- NumPy – Numerical calculations.
- Matplotlib – Data visualization.
- Seaborn – Statistical visualization.
- Scikit-learn – Machine learning and clustering.
- Jupyter Notebook – Code execution and analysis.

📁 Project Structure

Facebook_Live_K-Means_Clustering/
│
├── Live.csv
├── app.py
├── facebook_live_project.ipynb
└── README.md

⚙️ Installation and Usage

Step 1: Clone the repository

git clone https://github.com/shreyaa1827/Facebook_Live_K-Means_Clustering.git

Step 2: Open the project folder

cd Facebook_Live_K-Means_Clustering

Step 3: Install the required libraries

pip install pandas numpy matplotlib seaborn scikit-learn jupyter

Step 4: Run the Jupyter Notebook

jupyter notebook

Open "facebook_live_project.ipynb" and run the cells sequentially.

📈 Expected Results

- Identification of groups of Facebook posts with similar engagement.
- Visualization of clusters using graphs.
- Comparison of engagement patterns across posts.
- Better understanding of social media interactions.

Actual results depend on the dataset, selected features, and model configuration.

💡 Applications

- Social media data analysis.
- Facebook post engagement analysis.
- Identification of engagement patterns.
- Content performance research.
- Exploratory data analysis using machine learning.

✅ Conclusion

The Facebook Live K-Means Clustering project demonstrates how unsupervised machine learning can identify patterns in social media engagement. By grouping posts with similar characteristics, it helps analyze user interactions and understand differences in post performance.

👩‍💻 Author

Project: Facebook Live K-Means Clustering
