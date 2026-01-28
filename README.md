# [Network_Traffic_Analysis_Unsupervised_Agglomerative_Hierarchical_Clustering](https://github.com/sabasabafaraz789/Network_Traffic_Analysis_Unsupervised_Agglomerative_Hierarchical_Clustering/blob/a44137abb07d78582864abb41d232f71eb7689cb/agglomerative-hierarchical-clustering.ipynb)

This project applies **Agglomerative Hierarchical Clustering**, an unsupervised learning technique, to analyze network traffic data and uncover structural relationships between different types of network flows and cyber-attacks.

---

##  Methodology

### 1️ Data Preprocessing

* Network Intrusion dataset  from  [CIC-IDS- 2017](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset)
* Data cleaning steps include:

  * Replacing infinite values (`±inf`) with NaN
  * Removing missing values
  * Eliminating duplicate traffic flows
---

### 2️ Feature Engineering

To capture meaningful network behavior, multiple domain-driven features are engineered:

* **Fwd_Bwd_Pkts_Ratio** – Directional packet imbalance
* **Total_Bytes** – Total volume of transmitted data
* **Header_to_Data_Ratio** – Protocol overhead measurement
* **Bwd_to_Fwd_Bytes_Ratio** – Traffic asymmetry indicator
* **Flow_IAT_Range** – Inter-arrival time variability
* **Avg_IAT** – Average inter-arrival time per packet
* **Packet_Size_Spread** – Variation in packet sizes

These features enhance the model’s ability to distinguish between normal and malicious traffic.

---

### 3️ Feature Scaling & Transformation

* **PowerTransformer (Yeo-Johnson)** is applied to normalize skewed feature distributions
* **Min-Max Scaling** ensures all features contribute equally to distance calculations
* **PCA (Principal Component Analysis)** is used to:

  * Reduce dimensionality
  * Improve computational efficiency
  * Support visualization of hierarchical clusters

---

### 4️ Agglomerative Hierarchical Clustering

* The model starts with each data point as an individual cluster
* Clusters are iteratively merged based on similarity using:

  * **Euclidean distance**
  * **Linkage criteria** (e.g., Ward linkage)
* The process continues until the desired number of clusters is formed

This bottom-up approach reveals **nested relationships** between traffic patterns.

---

### 5️ Dendrogram Analysis

* A **dendrogram** is generated to visualize the hierarchical structure
* It helps determine:

  * Optimal number of clusters
  * Similarity levels at which attack patterns merge
* Provides interpretability that flat clustering methods cannot offer

---

### 6️ Cluster Evaluation

Although training is unsupervised, known labels are used for post-analysis:

* **Cluster purity** to measure dominant attack types
* **Attack distribution per cluster**
* Comparison with other clustering models (K-Means, DBSCAN)

This evaluation highlights how effectively hierarchical clustering groups related attacks.

---

### 7️ Visualization

* PCA-based cluster visualizations
* Dendrogram plots for hierarchical interpretation
* Clear separation and overlap analysis of traffic patterns

---

##  Technologies Used

* Python
* Pandas, NumPy
* Scikit-learn
* SciPy
* Matplotlib / Seaborn

---

## 👨‍💻 Author
Developed by **Saba Faraz**  
📧 Email: farazsaba96@gmail.com

---
