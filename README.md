# 🏠 House Price Prediction using Machine Learning

## 📌 Project Overview
This project focuses on predicting house prices using Machine Learning techniques.  
The objective is to build a regression model that learns the relationship between house features (such as area, bedrooms, parking, etc.) and the house price.

The project demonstrates a complete **end-to-end Machine Learning workflow**, from data preprocessing to model evaluation, using Python and Scikit-learn.

---

## 📊 Dataset
The dataset contains information about houses, including:
- Area
- Number of bedrooms
- Bathrooms
- Parking availability
- Furnishing status
- Other relevant features
- Target variable: **price**

---

## 🧠 Machine Learning Workflow

### 1️⃣ Data Loading
- The dataset is loaded using **Pandas**
- Initial inspection is done using `head()`, `info()`, and `describe()`

---

### 2️⃣ Data Preprocessing
The following preprocessing steps are performed:

#### 🔹 Handling Target and Features
- **Target (y):** `price`
- **Features (X):** All remaining columns

#### 🔹 Encoding Categorical Variables
- Categorical features (e.g., yes/no, furnished/unfurnished) are converted into numeric form using **One-Hot Encoding** (`pd.get_dummies`)
- `drop_first=True` is used to avoid multicollinearity

#### 🔹 Feature Scaling
- Numerical features are scaled using **StandardScaler**
- Scaling ensures all features contribute equally to the model

---

### 3️⃣ Train–Test Split
- The dataset is split into:
  - **Training set (80%)**
  - **Test set (20%)**
- This helps evaluate model performance on unseen data

---

## 🤖 Model Building

### 🔹 Linear Regression
- Linear Regression is used as the **baseline model**
- It assumes a linear relationship between input features and house prices

### 🔹 Ridge Regression
- Ridge Regression is applied to handle multicollinearity
- It adds regularization to control large coefficients and improve stability

### 🔹 Lasso Regression
- Lasso Regression is used for feature selection
- It can reduce some feature coefficients to zero

---

## 📈 Model Evaluation

The models are evaluated using the following regression metrics:

- **MAE (Mean Absolute Error)**  
  → Average prediction error

- **RMSE (Root Mean Squared Error)**  
  → Penalizes large prediction errors

- **R² Score**  
  → Measures how much variance in house prices is explained by the model

### 🔢 Results
- Train R² ≈ **0.69**
- Test R² ≈ **0.65**

The small difference between training and test performance indicates good generalization.

---

## 📉 Visualization
- A scatter plot of **Actual vs Predicted Prices** is used to visualize model performance
- The upward trend in the plot shows the model has learned the overall relationship, though some scatter remains due to real-world complexity

---

## ⚠️ Limitations of the Model

1. **Assumes linear relationship**  
   House prices do not always change linearly with features.

2. **Sensitive to outliers**  
   Extremely expensive houses can affect predictions.

3. **Multicollinearity**  
   Highly correlated features (e.g., area and bedrooms) make coefficient interpretation unstable.

4. **Missing real-world factors**  
   The dataset does not include location quality, market demand, or negotiation factors.

5. **Underfitting**  
   Linear models cannot capture complex non-linear patterns in housing data.

Because of these limitations, achieving very high accuracy (e.g., 95%) is unrealistic for this dataset.

---

## 🛠 Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib

---

## 🚀 How to Run the Project

```bash
pip install -r requirements.txt
python house_price_model.py
