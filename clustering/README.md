# Clustering
# 📊 Human Activity Recognition using Time Series Clustering
📌 Project Overview

This project focuses on unsupervised human activity recognition using time series data collected from smartphone inertial sensors.
The objective is to automatically discover and group different physical activities without using the true labels during training.

The study compares several clustering algorithms, including both classical methods and techniques specifically designed for time series data, in order to analyze their ability to recover meaningful activity patterns.

# 🎯 Objectives

Apply unsupervised learning to multivariate time series data

Compare clustering algorithms with different distance measures

Evaluate clustering quality using external metrics

Understand the limitations of classical clustering methods on temporal data

# 📂 Dataset

Human Activity Recognition data from smartphone sensors

Activities include:

Walking

Walking upstairs

Walking downstairs

Sitting

Standing

Laying

Data is segmented into time windows and represented as time series

⚠️ Ground-truth labels are used only for evaluation, not for training.

# 🧠 Methods Used

Four clustering techniques were applied:

## 1️⃣ K-Means

Classical clustering algorithm

Uses Euclidean distance

Performs poorly on time series due to lack of temporal alignment

## 2️⃣ DBSCAN

Density-based clustering

Sensitive to parameters (eps, minPts)

Struggles to capture the structure of time series data

## 3️⃣ K-Shape

Time-series-specific clustering method

Uses Shape-Based Distance (SBD)

Aligns and normalizes time series before comparison

Performs well on dynamic activities

## 4️⃣ DBA-KMeans

Combines Dynamic Time Warping (DTW) with DTW Barycenter Averaging (DBA)

Captures temporal distortions and signal dynamics

Achieves the best overall performance

📈 Evaluation Metrics

To assess clustering quality, the following metrics are used:

Adjusted Rand Index (ARI)
Measures the similarity between predicted clusters and true activity labels.

Silhouette Score
Evaluates cluster separation (used mainly for K-Means).

# 🏆 Results Summary
Method	ARI Score	Observations
K-Means	0.405	Poor separation, strong confusion between static activities
DBSCAN	0.148	Many incoherent clusters, not adapted to raw time series
K-Shape	0.647	Good separation of dynamic activities, confusion between sitting/laying
DBA-KMeans	0.874	Excellent clustering, very strong agreement with true activities

👉 DBA-KMeans clearly outperforms the other methods.

# 🧠 Key Insights

Classical clustering methods based on Euclidean distance are not suitable for time series data

Accounting for temporal alignment and signal shape is crucial

Time-series-specific methods (DTW, K-Shape) significantly improve clustering quality

Dynamic activities are easier to distinguish than static postures

# 📓 Project Structure
clustering/
├── README.md
├── Projet_clustering_Anis_DELLIDJ.ipynb
└── Report.pdf

▶️ How to Run

Open the Jupyter notebook:

jupyter notebook


Run Projet_clustering_Anis_DELLIDJ.ipynb step by step
(all experiments and visualizations are included)

⚠️ Limitations

Static postures (sitting vs laying) remain difficult to separate

Results depend on distance choice and clustering assumptions

DBSCAN is highly sensitive to parameter tuning

# 🧑‍🎓 Author

Anis Dellidj
Master 2 – Machine Learning for Data Science
Unsupervised Learning & Time Series Analysis Project

# 💡 Possible Improvements

Multivariate DTW

Deep clustering approaches

Feature learning with autoencoders

Online / real-time activity clustering
