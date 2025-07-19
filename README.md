# 🍄 Mushroom Edibility Prediction

This project aims to build a robust machine learning model to classify mushrooms as **edible** or **poisonous** based on their physical characteristics. The work is part of the [Kaggle Playground Series S4E8 competition](https://www.kaggle.com/competitions/playground-series-s4e8/data).

---

## 🧠 Problem Statement

Determine whether a mushroom is edible or poisonous based on features like cap color, odor, and habitat. Misclassification can have severe consequences, so accurate predictions are essential.

---

## 📊 Dataset

- Source: [Kaggle Competition Dataset](https://www.kaggle.com/competitions/playground-series-s4e8/data)
- `train.csv`: ~3.1 million rows
- `test.csv`: ~2 million rows
- Target: `class` (edible or poisonous)

---

## 🔁 Pipeline Overview

### ✅ Data Preprocessing
- Drop features with more than 40% missing values
- Clean noisy categorical data (e.g., combine rare values to 'other', then impute)
- Encode nominal categorical variables using **Target Encoding**
- Impute missing values using **Simple Imputer** (mean strategy)

### 📊 Data Visualization
- Univariate and bivariate analysis of categorical & numerical features
- Feature correlation and multicollinearity checks

### 🔍 Feature Selection
- Drop highly correlated features (e.g., cap-diameter due to correlation with stem-width)

### 🚫 Outlier Removal
- Applied **IQR method** for numerical features

---

## 🤖 Models Applied

### 1. **Logistic Regression**
- With and without polynomial features
- Limitations: high bias even with feature expansion

### 2. **Support Vector Machines (SVM)**
- Linear and RBF kernels
- Applied on data samples due to high training time
- RBF kernel improved bias-variance trade-off

### 3. **Decision Tree**
- Effective but prone to overfitting
- Pruned using `max_depth` and `ccp_alpha`

### 4. **Random Forest**
- More stable and robust
- Tuned number of estimators

### 5. **Ensemble Models**
- **Bagging** with Decision Trees (performed well)
- **AdaBoost** (limited performance, high bias)
- **XGBoost** (best overall performance)

---

## 🏆 Best Model

- **XGBoost** with 500–1000 estimators and custom MCC evaluation
- Provided the best generalization with low bias and variance
- Outperformed other models on the leaderboard with <0.5% difference from AutoML top solutions

---

## 📝 Conclusion

- Tree-based models were far more effective for this binary classification task.
- Proper encoding, stratified splitting, and hyperparameter tuning were crucial for performance.
- Removing outliers was optional; tree models handled them well.
- Target encoding and ensemble techniques significantly boosted performance.

---

## 📚 Related Files

- 📄 [`MushroomsPrediction_Project_Documentation.pdf`](./MushroomsPrediction_Project_Documentation.pdf): Full project documentation with visuals, metrics, and insights
- 📓 `Notebooks/`: Jupyter Notebooks for:
  - Data Cleaning & Visualization
  - Logistic Regression and SVM with Cross-Validation
  - Tree-Based Models, Bagging, Boosting

---

## ⚙️ Tools & Libraries

- Python (Pandas, NumPy, Scikit-learn, XGBoost)
- Jupyter Notebook
- Matplotlib & Seaborn for visualization

---

## 🚀 How to Use

1. Clone the repository
2. Navigate to the `Notebooks/` directory
3. Run the notebooks in order:
   - `DataCleaning_Visualization_def_treeBased.ipynb`
   - `LogReg_SVM_CV.ipynb`
   - `treeBased_bagging_boosting.ipynb`

---

## 📌 License

This project is for educational and research purposes only.

