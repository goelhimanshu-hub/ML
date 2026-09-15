# Normalization — Main Points

* **Feature Scaling** → Bringing features to a comparable scale.

* **Normalization** → A feature-scaling technique that usually converts values into the range **0 to 1**.

* **Scikit-learn:**

  ```python
  from sklearn.preprocessing import MinMaxScaler
  ```

* **Create scaler:**

  ```python
  scaler = MinMaxScaler()
  ```

* **Apply normalization:**

  ```python
  X_scaled = scaler.fit_transform(X)
  ```

* **Formula:**

  $$
  X' = \frac{X-X_{min}}{X_{max}-X_{min}}
  $$

* **`fit()`** → Learns the minimum and maximum values.

* **`transform()`** → Uses those values to scale the data.

* **Training data:**

  ```python
  X_train_scaled = scaler.fit_transform(X_train)
  ```

* **Test data:**

  ```python
  X_test_scaled = scaler.transform(X_test)
  ```

* **Important:** Never `fit()` the scaler separately on test data → prevents **data leakage**.

* **Useful for:** KNN, K-Means, SVM, Neural Networks, PCA, and other scale-sensitive algorithms.

* **Usually unnecessary for:** Decision Trees, Random Forest, XGBoost, and other tree-based models.

* **Limitation:** Min-Max Normalization is sensitive to **outliers**.

### 💡 Analogy

Normalization is like putting different measurements onto the **same 0–1 ruler**, so one feature doesn't dominate simply because its numbers are larger.
