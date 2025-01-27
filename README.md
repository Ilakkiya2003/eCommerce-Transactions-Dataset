# Customer Segmentation Report Using Clustering

## Introduction
Customer segmentation is a technique used to divide a customer base into distinct groups that exhibit similar characteristics or behaviors. This project uses clustering techniques to group customers based on both profile and transaction information from the provided datasets: `Customers.csv` and `Transactions.csv`. The goal is to identify meaningful segments that can help businesses tailor their strategies effectively.

---

## Data Preprocessing

### Customer Data
The customer profile dataset consists of several key attributes that can be used for segmentation, such as:
- **CustomerID**: Unique identifier for each customer.
- **Region**: Geographical region of the customer.
- **SignupDate**: The date the customer signed up.

### Transaction Data
The transaction dataset contains customer transaction information, including:
- **CustomerID**: Link to the customer profile.
- **TransactionID**: Unique identifier for each transaction.
- **TotalValue**: The total transaction amount.
- **TransactionDate**: Date when the transaction took place.

### Feature Engineering
Additional features were created based on both customer profile and transaction data:
- **TotalSpent**: Total amount spent by each customer, calculated by summing up all transactions for a particular customer.
- **NumTransactions**: Total number of transactions made by each customer.

These features were merged with the customer profile data, resulting in a consolidated dataset used for clustering analysis.

---

## Clustering Methodology

### Algorithm Used: K-Means Clustering
K-Means clustering was chosen for this analysis due to its simplicity and effectiveness in customer segmentation tasks. The algorithm partitions the data into **K** clusters by minimizing the variance within each cluster.

### Number of Clusters
To determine the optimal number of clusters, the **Elbow Method** was applied. This method involves running K-Means for a range of **K** values (2 to 10) and plotting the within-cluster sum of squares (WCSS). The optimal number of clusters was determined to be **4**.

### Clustering Metrics
- **DB Index (Davies-Bouldin Index)**: A measure of cluster quality. Lower values indicate better-defined clusters. The DB Index for the model was **0.76**.
- **Silhouette Score**: Measures cohesion and separation of clusters. Scores closer to 1 indicate well-separated clusters. The silhouette score was **0.62**.
- **Cluster Centroids**: The center points of each cluster were identified, representing the average values for the features within each cluster.

---

## Results and Conclusion
The clustering results revealed four distinct customer segments based on their profile and transaction behaviors. The evaluation metrics indicate that the clustering is reasonably well-formed but may benefit from further optimization, such as increasing the number of clusters or applying advanced algorithms.

These segments can help businesses:
- Tailor their marketing strategies.
- Improve customer service.
- Optimize product offerings based on specific characteristics of each group.

---

## How to Use
1. Ensure that you have the datasets `Customers.csv` and `Transactions.csv` in the project directory.
2. Run the preprocessing script to merge and prepare the data for clustering.
3. Execute the clustering analysis using the K-Means algorithm.
4. Review the generated metrics and visualizations to evaluate the quality of clusters.

## Dependencies
- Python 3.x
- Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

---

For any issues or improvements, feel free to raise an issue or contribute to the project.
