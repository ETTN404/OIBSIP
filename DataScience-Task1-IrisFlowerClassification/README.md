# 🌸 Task 1: Iris Flower Classification

## 📌 Internship Task Overview
- **Objective**: Build a machine learning classification pipeline to identify the species of an Iris flower (`Setosa`, `Versicolor`, or `Virginica`) from physical measurements: Sepal Length, Sepal Width, Petal Length, and Petal Width.
- **Location**: `C:\Users\hp\Desktop\Qiyas\OASIS\Task_1_Iris_Classification\`
- **Primary Deliverable**: [`Task_1_Iris_Classification.ipynb`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_1_Iris_Classification/Task_1_Iris_Classification.ipynb) (Fully Executed Jupyter Notebook with inline outputs, graphs, tables, and metric reports)

---

## 📋 Feature Checklist Verification
- [x] **Data Loading**: Loaded directly from `sklearn.datasets.load_iris()` into a structured Pandas DataFrame with target species names.
- [x] **Exploratory Data Analysis (EDA)**: Verified dataset shape (150 rows × 5 cols), data types, missing/null values check (0 missing values), target class balance (50 samples per class), and detailed descriptive statistics.
- [x] **Visualizations**:
  - **Pairplot**: Pairwise scatter matrix with KDE density distribution curves per species.
  - **Box Plots & Swarm Plots**: Detailed distribution, spread, medians, and IQRs for each feature across species.
  - **Pearson Correlation Heatmap**: Linear correlation matrix between physical measurements.
- [x] **Feature Selection Discussion**: Analyzed discriminative power visually and confirmed quantitatively using **ANOVA F-statistic (`f_classif`)**. Petal length and petal width were identified as the most discriminative features.
- [x] **Train/Test Split**: 80/20 Stratified Split (`train_test_split`, `stratify=y`, `random_state=42`) with feature scaling via `StandardScaler`.
- [x] **Classifier Training**: Trained 4 classifiers:
  1. Logistic Regression
  2. K-Nearest Neighbors (KNN, $K=5$)
  3. Decision Tree Classifier (`max_depth=3`)
  4. Random Forest Classifier (`n_estimators=100`)
- [x] **Evaluation**: Evaluated each classifier with Train Accuracy, Test Accuracy, 5-Fold Stratified Cross-Validation (Mean ± Std Dev), Seaborn Confusion Matrix Heatmaps, and Classification Reports (Precision, Recall, F1-Score).
- [x] **Best Model Declaration**: Selected **Logistic Regression / K-Nearest Neighbors** with full technical rationale balancing test accuracy (100%), cross-validation score (96.7% ± 2.1%), macro F1-score (1.00), low model variance, and Occam's razor simplicity.
- [x] **Model Serialization & Live Inference**: Saved trained model (`best_iris_model.pkl`) and scaler (`iris_scaler.pkl`) with `joblib`, and tested real-time inference on new measurement inputs.

---

## 📊 Summary Model Comparison Table

| Model | Train Accuracy | Test Accuracy | 5-Fold CV Mean | 5-Fold CV Std | Macro Precision | Macro Recall | Macro F1-Score |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Logistic Regression** 🏆 | **1.0000** | **1.0000** | **0.9667** | **±0.0211** | **1.0000** | **1.0000** | **1.0000** |
| **K-Nearest Neighbors** | 0.9750 | 1.0000 | 0.9667 | ±0.0211 | 1.0000 | 1.0000 | 1.0000 |
| **Decision Tree** | 0.9833 | 0.9667 | 0.9600 | ±0.0327 | 0.9697 | 0.9667 | 0.9665 |
| **Random Forest** | 1.0000 | 0.9667 | 0.9600 | ±0.0327 | 0.9697 | 0.9667 | 0.9665 |

---

## 🏆 Best Model Declaration & Rationale
**Selected Model**: **Logistic Regression** (with `StandardScaler`)

### Rationale:
1. **Linear Separability**: EDA showed that `Setosa` is completely linearly separable from other species, and `Versicolor`/`Virginica` are well-partitioned along normalized feature dimensions.
2. **High Generalization Stability**: Reached top cross-validation mean score (**96.7%**) with the lowest variance (**±2.1%**).
3. **Occam's Razor & Low Overfitting Risk**: On small dataset sizes ($N=150$), simpler linear log-odds classifiers are far less susceptible to variance and overfitting compared to deep decision trees or complex ensemble models.

---

## 📁 Artifacts Produced in `OASIS\Task_1_Iris_Classification\`
- [`Task_1_Iris_Classification.ipynb`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_1_Iris_Classification/Task_1_Iris_Classification.ipynb): Fully executed Jupyter notebook containing step-by-step code, output tables, markdown, and embedded seaborn plots.
- [`best_iris_model.pkl`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_1_Iris_Classification/best_iris_model.pkl): Serialized Logistic Regression model.
- [`iris_scaler.pkl`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_1_Iris_Classification/iris_scaler.pkl): Serialized `StandardScaler` transformer.
- [`generate_task1_notebook.py`](file:///C:/Users/hp/Desktop/Qiyas/OASIS/Task_1_Iris_Classification/generate_task1_notebook.py): Python builder script used to build and execute the notebook.
