# Standardization

* **Standardization** → A feature-scaling technique that transforms data based on its **mean and standard deviation**.

* After standardization:

  * **Mean ≈ 0**
  * **Standard Deviation ≈ 1**
  * No fixed range like `0–1`

* **Formula:**

  $$
  Z = \frac{X-\mu}{\sigma}
  $$

* **Scikit-learn:**

  ```python
  from sklearn.preprocessing import StandardScaler
  ```

* **Create scaler:**

  ```python
  scaler = StandardScaler()
  ```

* **Training data:**

  ```python
  X_train_scaled = scaler.fit_transform(X_train)
  ```

* **Test data:**

  ```python
  X_test_scaled = scaler.transform(X_test)
  ```

* **`fit()`** → Learns the **mean and standard deviation**.

* **`transform()`** → Uses the learned values to scale the data.

* **Important:** Never fit the scaler separately on test data → prevents **data leakage**.

* **Useful for:** KNN, K-Means, SVM, Logistic Regression, Neural Networks, PCA, and gradient-descent-based algorithms.

* **Usually unnecessary for:** Decision Trees, Random Forest, XGBoost, and other tree-based algorithms.

* **Difference from Normalization:**

  * Normalization → usually `0–1`
  * Standardization → mean `0`, standard deviation `1`

* **Outliers:** Standardization is affected by outliers because mean and standard deviation are sensitive to extreme values.

### 💡 Analogy

Standardization is like comparing students' marks based on **how far they are from the class average**, rather than their raw marks.
