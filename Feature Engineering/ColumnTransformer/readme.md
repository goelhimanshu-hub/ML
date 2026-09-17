# ColumnTransformer — Scikit-learn

This repository contains my practice and implementation of **ColumnTransformer** using Python and Scikit-learn.

## 📚 What I Learned

* Applying different preprocessing techniques to different columns.
* Applying `StandardScaler` to numerical features.
* Applying `OneHotEncoder` to categorical features.
* Combining multiple transformations using `ColumnTransformer`.
* Using `remainder='passthrough'` to keep untransformed columns.
* Using `fit_transform()` on training data and `transform()` on test data.

## 🛠️ Technologies Used

* Python
* Pandas
* Scikit-learn
* Google Colab

## 💻 Example

```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder

preprocessor = ColumnTransformer([
    ('num', StandardScaler(), ['Age', 'Salary']),
    ('cat', OneHotEncoder(handle_unknown='ignore'), ['Gender', 'City'])
])

X_train_transformed = preprocessor.fit_transform(X_train)
X_test_transformed = preprocessor.transform(X_test)
```

## 🎯 Key Concept

**ColumnTransformer allows different preprocessing techniques to be applied to different columns of the same dataset.**

```text
Numerical Columns
       ↓
StandardScaler

Categorical Columns
       ↓
OneHotEncoder

       ↓
ColumnTransformer
       ↓
Transformed Dataset
```
