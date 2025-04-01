## Manufacturing Defect Prediction

### Overview
This project focuses on predicting manufacturing defects using machine learning models. The dataset consists of various production-related features, and the target variable is the defect status (binary classification). The goal is to optimize quality control by identifying patterns leading to defective products, thereby improving efficiency and reducing costs.

### Key Features
- **Exploratory Data Analysis (EDA):** Visualizations to understand feature distributions, correlations, and defect patterns.
- **Data Preprocessing:** Feature scaling using `StandardScaler` and handling class imbalance with `SMOTE`.
- **Model Training:** Multiple machine learning models evaluated for accuracy and performance.
- **Hyperparameter Tuning:** Selection of the best model before and after oversampling.
- **Evaluation Metrics:** Accuracy, confusion matrix, and ROC-AUC score for model assessment.

### Dataset
The dataset contains key production features such as:
- `ProductionVolume`
- `ProductionCost`
- `EnergyConsumption`
- `AdditiveProcessTime`
- `SafetyIncidents`

The target variable is `DefectStatus`, indicating whether a product has defects.

### Machine Learning Models Used
The following models were trained and evaluated:
- **Logistic Regression**
- **K-Nearest Neighbors (KNN)**
- **Decision Tree**
- **Random Forest**
- **Support Vector Machine (SVM)**
- **XGBoost**

### Model Performance
The best-performing model was selected based on accuracy and ROC-AUC score. Before applying SMOTE, the best model achieved:
- **Accuracy:** _Pre-SMOTE best model accuracy_
- **ROC-AUC Score:** _Pre-SMOTE best model AUC_

After applying SMOTE for class balancing, the final model performance improved with:
- **Accuracy:** 96.5%
- **Number of Correct Predictions:** 1052
- **Number of Incorrect Predictions:** 38

#### Predictions Table
Below is a sample of the true values versus predicted values:

| True Values | Predicted Values |
|-------------|-----------------|
| 1           | 1               |
| 0           | 0               |
| 1           | 1               |
| 0           | 0               |
| 1           | 1               |
| 0           | 0               |
| 1           | 1               |
| 1           | 1               |
| 0           | 0               |
| 1           | 1               |

### Installation & Usage
#### Requirements
Ensure the following libraries are installed:
```bash
pip install pandas numpy scikit-learn seaborn matplotlib xgboost imbalanced-learn joblib
```

#### Running the Model
1. Load the dataset (`Manu` DataFrame)
2. Preprocess the data (scaling, handling class imbalance)
3. Train models and evaluate performance
4. Save the best-performing model:
   ```python
   joblib.dump(best_model, 'best_model_after_XGBoost.joblib')
   ```
5. Predict new data points:
   ```python
   best_model.predict(new_data)
   ```

### Results Visualization
- Confusion matrices to analyze true vs. predicted values
- ROC curves to compare model performance
- Bar plots showing defect distributions before and after SMOTE

### Conclusion
The final model demonstrates high predictive accuracy and robustness in defect classification. By integrating this model into a manufacturing pipeline, businesses can proactively detect defects, optimize production processes, and minimize costs.

### Recommendations
Based on the analysis and feature importance from the model, we suggest the following actionable recommendations for improving the manufacturing process:

- **Maintenance Hours**: Optimize the maintenance schedule to avoid breakdowns and excess maintenance time.
- **Defect Rate**: Implement strict quality control measures to reduce the defect rate.
- **Quality Score**: Strengthen quality assurance processes to ensure high-quality products.
- **Production Volume**: Enhance quality control systems at higher production volumes to manage the increase in defects.
