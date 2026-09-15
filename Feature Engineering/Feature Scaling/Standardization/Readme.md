Standardization

What is Standardization?

Standardization is a feature scaling technique that transforms numerical features so they are centered around 0 with a standard deviation of approximately 1.

Why?

It prevents features with larger numerical ranges from dominating algorithms that are sensitive to feature scale.

Common examples:

KNN

K-Means

SVM

Logistic Regression

Neural Networks

StandardScaler

from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

Important Rule

Split first → fit scaler only on training data → transform both train and test.

Train-Test Split
      ↓
fit(X_train)
      ↓
transform(X_train)
transform(X_test)

This prevents data leakage.

Key Points

Training data: mean ≈ 0, std ≈ 1

Test data does not have to have mean 0 and std 1.

Standardization does not restrict values to 0–1.

Each feature is standardized separately.

scaler.mean_ → learned feature means.

scaler.scale_ → learned scaling values.



Quick Revision

Standardization = Z-score scaling = (x - mean) / std

Fit only on X_train; transform X_train and X_test.
