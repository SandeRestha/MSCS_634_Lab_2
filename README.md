# MSCS 634 — Lab 2: Classification Using KNN and RNN Algorithms

## Purpose
The purpose of this lab was to explore and compare the performance of two distance-based classification algorithms — **K-Nearest Neighbors (KNN)** and **Radius Neighbors (RNN)** — using the **Wine dataset** from scikit-learn.  
By systematically varying the parameters (*k* for KNN and *radius* for RNN), this experiment aimed to analyze how these hyperparameters affect model accuracy and to visualize the resulting performance trends.

---

## Key Insights
- **KNN Performance:**  
  The KNN classifier achieved strong and consistent accuracy across all tested *k* values, with the best performance at moderate *k* values such as 5–15. Accuracy stabilized near 0.97–1.00, indicating excellent generalization on the standardized dataset.  
  Small *k* values (e.g., 1) led to slight overfitting, while larger *k* values smoothed predictions and improved stability.

- **RNN Performance:**  
  The RNN classifier showed much lower and nearly constant accuracy when tested with large radius values (350–600).  
  These values were extremely large relative to the standardized feature space, causing nearly all training points to be included as neighbors. As a result, the model acted like a majority-class predictor with flat accuracy around 0.38–0.40.  
  With more practical radius ranges (e.g., 0.5–5.0 on standardized data), RNN would likely demonstrate more meaningful variation and improved results.

- **Overall Comparison:**  
  KNN outperformed RNN under the given parameters. KNN is generally easier to tune and interpret, while RNN requires more careful radius selection to balance local sensitivity and global coverage.

---

## Challenges and Decisions
- **Scaling:**  
  Because both models rely on distance measurements, all features were standardized using `StandardScaler()` to prevent features with large numeric ranges from dominating the distance metric.

- **Parameter Choices:**  
  The lab instructions specified very large radius values for RNN. These values were intentionally kept as-is to follow the assignment directions, even though they result in almost uniform neighborhoods.  
  For a more realistic analysis, smaller radii (e.g., 0.3–5.0) could be explored in future experiments.

- **Model Robustness:**  
  The use of scikit-learn’s `Pipeline` ensured that scaling and classification steps were handled together, maintaining a clean and reproducible workflow.

---

**Author:** Sandesh Shrestha 
**Course:** MSCS 634  
**Assignment:** Lab 2 — Classification Using KNN and RNN Algorithms
