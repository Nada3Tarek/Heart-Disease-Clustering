# 💓 Clustering Heart Disease Patients

## 🔍 Introduction
This project focuses on using **unsupervised learning** to group heart disease patients based on their medical characteristics. The primary objective is to detect patterns among patients that may assist in delivering more personalized medical care and early risk identification.

---

## 📚 Dataset Summary
- **Source**: Heart Disease Dataset  
- **Instances**: 306 patients  
- **Attributes**: 12 features in total

### ▶️ Types of Features:
- **Numeric**: Age, Cholesterol (Chol), Resting Blood Pressure (Trestbps), Max Heart Rate Achieved (Thalach), ST Depression (Oldpeak), and a custom feature: **Heart Rate Recovery (HRR = Thalach - 70)**
- **Categorical**: Slope (cleaned by mode imputation)

---

## 🧼 Data Processing Workflow
- Removed unnecessary columns and cleaned missing values
- Dropped duplicate rows to avoid bias
- Engineered a new feature: **HRR** (Heart Rate Recovery)
- Standardized all numerical values to improve clustering accuracy

---

## 🧪 Clustering Techniques Used

### 1. **K-Means Clustering**
- **Chosen k**: 3 (via Elbow Method)
- **Silhouette Score**: 0.241
- ✅ Clear and distinct clusters

### 2. **DBSCAN (Density-Based)**
- **ε**: 0.8, **minPts**: 5
- **Silhouette Score**: 0.029 (excluding noise)
- ⚠️ Sensitive to parameter selection

### 3. **Hierarchical Clustering**
- **Linkage**: Ward’s Method
- **Clusters**: 3 (based on dendrogram)
- **Silhouette Score**: 0.216
- 📊 Helpful visualization via dendrograms

### 4. **K-Medoids (PAM)**
- **Clusters**: 3
- **Silhouette Score**: 0.162
- 🔒 More resistant to outliers compared to K-Means

---

## 🧠 Feature Reduction Test
A minimal feature set was tested (Age, Trestbps, Chol, Thalach, HRR).  
- **Resulting Score**: 0.239  
- 💡 Slight performance drop, but simpler and easier to interpret

---

## 📈 Summary of Model Performance

| Algorithm      | Silhouette Score | Comments                                 |
|----------------|------------------|------------------------------------------|
| **K-Means**        | 0.241            | Most effective, clearly defined groups   |
| **DBSCAN**         | 0.029            | Works with irregular shapes but sensitive |
| **Hierarchical**   | 0.216            | Balanced approach with visual aid        |
| **K-Medoids**      | 0.162            | Tolerant to noise but lower performance  |

---

## ✅ Final Insights
- **K-Means** delivered the highest-quality clusters overall.
- The **engineered HRR** feature added great value to the analysis.
- Feature reduction didn't severely affect performance, making the model easier to interpret.

---

## 🛠 Tools & Libraries
- **Python**
- pandas, numpy
- scikit-learn
- seaborn, matplotlib

---

