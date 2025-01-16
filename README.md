# E-commerce Data Science Practice Project, Exploring Different ML Models on One Dataset

This repository documents a practice project where I role-play as a data scientist at an e-commerce company. The project explores various machine learning methods to analyze purchasing behavior, predict sales, and segment customers. Each method was applied to address specific business challenges, highlighting their contributions, insights, and limitations.

---

## Machine Learning Methods

### Penalized Regression
**Conclusion:**  
- Ridge regression outperformed Lasso with a lower mean squared error (MSE):  
  - **Ridge MSE:** 1.89  
  - **Lasso MSE:** 1.94  
- Key predictors: Age and Gender.  
- Limitations: Assumes linear relationships, high dimensionality from one-hot encoding, and potential biases from missing data imputation.  
- **Robustness:** Cross-validation confirmed generalizability.  
- **Future Steps:** Explore non-linear approaches (e.g., decision trees) to better handle complex interactions.

---

### Ensemble Methods
**Performance Summary:**  
- **Cross-Validation RMSE Scores:** `[nan nan nan nan nan]`  
- **Mean Cross-Validation RMSE:** `nan`  
- **Test RMSE:** `7.58e-12`  

**Feature Importances:**  
- **Top Influencers:**  
  - Quantity: 0.5158  
  - Unit Price: 0.3951  
  - SKU_SMP234: 0.0518  
- Minimal impact from other features.  

**Insights:**  
Ensemble methods effectively identified key factors driving sales, with Quantity and Unit Price being dominant predictors. 

---

### PCA and Clustering
**PCA Analysis and Dimensionality Reduction:**  
- PCA reduced the dataset to 4 components, capturing over 90% of variance.  
- Facilitated insights by focusing on significant data variations.

**Clustering:**  
- Conducted on raw and PCA-transformed datasets.  
- Optimal clusters (`k=3`) identified using the Elbow Method.  
- PCA-transformed clusters showed better separation and reduced noise.

**Key Insights:**  
- Enhanced customer segmentation.  
- PCA-based clustering provided more interpretable and robust results.  

**Limitations:**  
- Excluded categorical/binary features in PCA may limit segmentation depth.  
- Subjectivity in selecting the number of clusters.

---

### Neural Networks
**Preprocessing:**  
- Missing values in Add-ons Purchased were filled with `0`.  
- Features scaled using `StandardScaler`.  

**Model Architecture:**  
- Multi-layer perceptron (MLP) with:  
  - ReLU activation and L2 regularization.  
  - Batch normalization and dropout for stability.  
  - Final softmax layer for multiclass classification.  

**Performance:**  
- **Training Accuracy:** ~61%  
- **Validation Accuracy:** ~59%  
- **Test Accuracy:** 61%  

**Insights:**  
- Moderate success in rating classification, with difficulties in distinguishing adjacent ratings.  
- Improvements from class balancing and scaling.  

**Limitations:**  
- Sensitivity to hyperparameters.  
- Information loss from categorical encoding.

**Future Steps:**  
- Experiment with convolutional or recurrent architectures.  
- Optimize hyperparameters using grid or random search.  
- Explore hybrid models combining neural networks and traditional methods.

---

### SVM and Time Series Analysis
Support Vector Machines (SVM) and time series analysis were also explored during this project. However, these methods were not included in the final notebook due to computational constraints. Future work could revisit these approaches with optimized compute resources to evaluate their potential contribution.

---

## Summary
This practice project demonstrates the application of machine learning methods in an e-commerce context. Each technique provided unique insights into customer behavior and sales trends, highlighting both strengths and limitations. These findings lay the groundwork for further exploration and potential business applications.
