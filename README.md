# E-commerce Data Science Practice Project

This repository documents a practice project where I role-play as a data scientist at an e-commerce company. The project explores various machine learning methods to analyze purchasing behavior, predict sales, and segment customers. Each method was applied to address specific business challenges, highlighting their contributions, insights, and limitations.

---

## Machine Learning Methods

### Penalized Regression
**Purpose:**  
To identify relationships between variables and the total quantity of items purchased.

**Conclusion:**  
- Ridge regression outperformed Lasso with a lower mean squared error (MSE):  
  - **Ridge MSE:** 1.89  
  - **Lasso MSE:** 1.94  
- Key predictors: Age and Gender.  
- Limitations: Assumes linear relationships, high dimensionality from one-hot encoding, and potential biases from missing data imputation.  
- **Robustness:** Cross-validation confirmed generalizability.  
- **Future Steps:** Explore non-linear approaches (e.g., decision trees) to better handle complex interactions.

---

### Ensemble Methods: Random Forest
**Purpose:**  
To explore feature importance and predict total sales using a flexible and robust model.

**Model Overview:**  
Random Forest Regressor from `sklearn.ensemble` was used. A hyperparameter grid search was conducted to optimize model performance using `GridSearchCV` with 5-fold cross-validation.

**Parameter Grid:**  
- Number of estimators (`n_estimators`): [50, 100, 200]  
- Maximum depth (`max_depth`): [10, 20, None]  
- Minimum samples split (`min_samples_split`): [2, 5, 10]  

**Best Model:**  
- Parameters:  
  - `n_estimators`: 50  
  - `max_depth`: 10  
  - `min_samples_split`: 10  

**Feature Importances:**  
The model highlighted the following top contributors to sales:  
- Quantity: 0.5158  
- Unit Price: 0.3951  
- SKU_SMP234: 0.0518  

**Insights:**  
The Random Forest Regressor effectively identified key features driving sales while offering robustness against overfitting due to its ensemble nature. This model proved valuable for uncovering patterns and relationships in the data.

---

### PCA and Clustering
**Purpose:**  
To segment customers by reducing data dimensionality (PCA) and grouping them into meaningful clusters (Clustering).

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
**Purpose:**  
To predict customer ratings (multi-class classification problem).

**Model Overview:**  
- Multi-layer perceptron (MLP) built using TensorFlow’s `Sequential` API.  
- Architecture included ReLU activation, batch normalization, dropout layers, and a softmax output layer.

**Performance:**  
- **Training Accuracy:** ~61%  
- **Validation Accuracy:** ~59%  
- **Test Accuracy:** 61%  

**Insights:**  
The neural network effectively classified ratings with moderate accuracy. Preprocessing techniques like class balancing and scaling improved model generalizability.

**Limitations:**  
- Sensitivity to hyperparameters.  
- Information loss from categorical encoding.

**Future Steps:**  
- Experiment with convolutional or recurrent architectures.  
- Optimize hyperparameters using grid or random search.  

---

### SVM and Time Series Analysis
**Purpose:**  
- SVM: To classify data and explore its potential for prediction tasks.  
- Time Series Analysis: To forecast sales trends and patterns over time.  

**Status:**  
These methods were explored but not included in the final notebook due to computational constraints. Future work could revisit these approaches with optimized compute resources to evaluate their potential contribution.

---

## Summary
This practice project demonstrates the application of machine learning methods in an e-commerce context. Each technique provided unique insights into customer behavior and sales trends, highlighting both strengths and limitations. These findings lay the groundwork for further exploration and potential business applications.

