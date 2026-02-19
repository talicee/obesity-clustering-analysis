# Obesity Levels Clustering Project

This project analyzes the *Estimation of Obesity Levels Based on Eating Habits and Physical Condition* dataset from UCI. The objective was to segment individuals into meaningful groups using clustering techniques and evaluate the best-performing model.

## Dataset Overview

* 17 variables (numerical, categorical, ordinal)
* Demographic data (age, gender, height, weight)
* Lifestyle factors (eating habits, water consumption, physical activity, technology usage)
* No missing values
* Duplicates removed during preprocessing
  The dataset was suitable for clustering with minimal cleaning.

## Data Preparation

Steps performed:

* Duplicate removal
* Outlier filtering (Age > 50, Weight > 170 removed)
* Label encoding (binary variables)
* One-hot encoding (nominal variables)
* Feature engineering: BMI creation
* Feature scaling using StandardScaler
* Comparison between scaled and unscaled datasets
  Two datasets were used for modeling:
* Unscaled data
* Scaled data

## Modeling Approaches

### 1. K-Means Clustering

* Optimal cluster selection using Elbow Method and KneeLocator
* Evaluation using Silhouette Score and WCSS
* Compared scaled vs unscaled results
  Result: Scaled data produced 4 clusters with clearer separation and better interpretability.
  Final selected model: **K-Means (Scaled Data, 4 Clusters)**.

### 2. Hierarchical Agglomerative Clustering (HAC)

* Tested multiple linkage methods and distance metrics
* Best configuration selected using Silhouette Score
* Compared scaled and unscaled data
  Unscaled data achieved higher silhouette score, but separation was less detailed.

### 3. PCA + Hierarchical Clustering

* PCA retained 90% variance (9 principal components)
* Ward linkage with 3 clusters
* Improved visual clarity
* Slightly lower silhouette score but more balanced clusters

## Model Evaluation

Evaluation metrics:

* Silhouette Score
* WCSS
* Visual inspection of cluster distribution
  Although silhouette scores sometimes favored unscaled data, scaled K-Means provided the best balance between performance, interpretability, and practical relevance.

## Key Insights

* Obesity patterns are influenced by multiple lifestyle factors (diet, physical activity, habits)
* Feature scaling significantly impacts clustering behavior
* PCA improves visualization and cluster structure clarity
* K-Means on scaled data produced the most stable and meaningful segmentation

## Final Conclusion

The best-performing model is:
**K-Means Clustering with 4 clusters on scaled data**
This model provides clear population segmentation and meaningful interpretation for obesity-related behavioral analysis.
