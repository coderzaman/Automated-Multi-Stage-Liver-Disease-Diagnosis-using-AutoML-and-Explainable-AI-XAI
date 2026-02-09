# 🏥 Automated Multi-Stage Liver Disease Diagnosis using AutoML and XAI

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyCaret](https://img.shields.io/badge/PyCaret-AutoML-yellow)
![XGBoost](https://img.shields.io/badge/XGBoost-95.38%25_Acc-green)
![SHAP](https://img.shields.io/badge/XAI-SHAP-orange)

## 📜 Overview

This project presents a robust machine learning pipeline for the **multi-stage diagnosis of liver disease** (specifically Hepatitis C progression). Unlike traditional binary classification (Healthy vs. Disease), this system predicts the specific stage of the disease, ranging from blood donors to fibrosis and cirrhosis.

We utilized the **PyCaret AutoML** framework to benchmark **14 different classification algorithms** and integrated **Explainable AI (SHAP)** to provide transparent, interpretable results for medical professionals.

## 🚀 Key Features

* **Multi-Class Classification:** Diagnoses 5 distinct stages of liver disease (e.g., Blood Donor, Suspect, Hepatitis, Fibrosis, Cirrhosis).
* **AutoML Benchmarking:** Automated comparison of classifiers including XGBoost, LightGBM, Random Forest, and SVM to find the optimal model.
* **High Accuracy:** The top-performing **XGBoost** model achieved a **95.38% Test Accuracy**.
* **Explainable AI (XAI):**
    * **Global Interpretability:** Identifies which biomarkers (AST, ALB, ALP) are most critical across the entire dataset.
    * **Local Interpretability:** Explains individual patient predictions using **SHAP Waterfall plots**, showing exactly how a patient's enzyme levels contributed to their diagnosis.

## 📊 Model Performance Evaluation

We evaluated 14 models using PyCaret. **XGBoost** emerged as the best performer, balancing accuracy and recall effectively.

| Model | Accuracy | AUC | Recall | Precision | F1-Score |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **XGBoost** | **0.9538** | **0.9538** | **0.9346** | **0.9424** | **0.9538** |
| LightGBM | 0.9466 | 0.9466 | 0.9230 | 0.9333 | 0.9466 |
| Random Forest | 0.9418 | 0.9418 | 0.9167 | 0.9268 | 0.9418 |
| SVM (Linear) | 0.9417 | 0.9417 | 0.9151 | 0.9256 | 0.9417 |
| Gradient Boosting | 0.9368 | 0.9368 | 0.9249 | 0.9295 | 0.9368 |

*(See full benchmark results in the project notebooks)*

## 🧠 Explainable AI (XAI) Analysis

To ensure trust in clinical settings, we used **SHAP (SHapley Additive exPlanations)** to uncover the "black box" decisions of the model.

### 1. Global Feature Importance
The summary plot below reveals the most influential biomarkers for predicting liver disease.
* **Top Biomarkers:** AST (Aspartate Transaminase), ALB (Albumin), and ALP (Alkaline Phosphatase).
* **Insight:** High levels of AST are strongly correlated with advanced disease stages (Class 4).

![SHAP Summary Plot](path/to/your/image_3fb7f6.png)
*(Add your SHAP summary image here)*

### 2. Local Interpretation (Patient-Level)
The waterfall plot demonstrates a single prediction instance (Class 4).
* **Observation:** In this specific case, low levels of **CHE** (-0.308) and **AST** (-0.273) were the primary drivers pushing the prediction toward the specific disease class.

![SHAP Waterfall Plot](path/to/your/image_3fb816.png)
*(Add your SHAP waterfall image here)*

## 🛠️ Tech Stack

* **Language:** Python 3.8+
* **AutoML Framework:** PyCaret
* **Algorithms:** XGBoost, LightGBM, Random Forest, Scikit-Learn
* **Explainability:** SHAP (Shapley Additive Explanations)
* **Data Processing:** Pandas, NumPy, Matplotlib, Seaborn

## ⚙️ Installation & Usage

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/coderzaman/Automated-Multi-Stage-Liver-Disease-Diagnosis-using-AutoML-and-Explainable-AI-XAI.git
    cd Automated-Multi-Stage-Liver-Disease-Diagnosis-using-AutoML-and-Explainable-AI-XAI
    ```

2.  **Install Dependencies**
    ```bash
    pip install pycaret shap xgboost
    ```

3.  **Run the Notebook**
    Open the Jupyter Notebook to replicate the training and analysis:
    ```bash
    jupyter notebook
    ```

## 👨‍💻 Contributors

* **Aktaruzzaman** - Lead Developer & Researcher

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
