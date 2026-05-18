# 📡 Telco Customer Churn Prediction

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-Model-F7931E)
![Status](https://img.shields.io/badge/status-active-success)

## 📌 Project Overview
This repository contains an end-to-end Machine Learning pipeline and an interactive web application designed to predict **Telco Customer Churn**. By leveraging demographic data, account information, and service usage, the project accurately identifies customers who are at a high risk of leaving the company. 

The interactive **Streamlit web application** allows business users to input customer details and receive real-time churn probability predictions, empowering proactive customer retention strategies.

---

## 🚀 Features
- **End-to-End ML Pipeline**: From raw data ingestion, cleaning, and feature engineering to model training and hyperparameter optimization.
- **Advanced Feature Engineering**: Derives new meaningful features such as `Tenure_Group`, `TotalAddon_Count`, `Monthly_vs_Average_Diff`, and `Customer_Value_Tier` to improve model accuracy.
- **Robust Machine Learning Model**: Uses an optimized **Random Forest Classifier** trained via `RandomizedSearchCV` for peak performance.
- **Interactive Web App**: A fully functional Streamlit application providing real-time predictions and churn risk assessment (Low, Medium, High).
- **Interpretability**: Highlights engineered features during inference for full transparency on what the model uses to make predictions.

---

## 📂 Project Structure

```text
📦 Teleco-churn-boxbox
 ┣ 📂 datasets/              # Raw data files
 ┣ 📂 output/                # Saved models and exported figures
 ┃ ┗ 📂 models/              # Contains the serialized `.joblib` models
 ┣ 📜 clean.py               # Handles initial data cleaning and preprocessing
 ┣ 📜 EDA.py                 # Exploratory Data Analysis scripts and visualizations
 ┣ 📜 create_feat.py         # Script for basic feature engineering
 ┣ 📜 features_new.py        # Advanced feature engineering logic
 ┣ 📜 model.py               # Base Random Forest model training pipeline
 ┣ 📜 optimal_model.py       # Hyperparameter tuning using RandomizedSearchCV
 ┣ 📜 pred.py                # Standalone prediction script for batch inference
 ┣ 📜 app.py                 # Interactive Streamlit Web Application
 ┗ 📜 README.md              # Project documentation
```

---

## 🛠️ Tech Stack
- **Language**: Python 3.8+
- **Data Manipulation**: Pandas, NumPy
- **Machine Learning**: Scikit-Learn
- **Model Serialization**: Joblib
- **Web Framework**: Streamlit
- **Visualization**: Matplotlib, Seaborn (within EDA)

---

## ⚙️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/teleco-churn-boxbox.git
   cd teleco-churn-boxbox
   ```

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install the dependencies:**
   *(Ensure you have a `requirements.txt` file or install the following manually)*
   ```bash
   pip install pandas numpy scikit-learn joblib streamlit
   ```

---

## 🏃‍♂️ Usage Guide

### 1. Training the Model
If you want to retrain the model from scratch, execute the pipeline scripts in the following order:

```bash
# 1. Clean the raw data
python clean.py

# 2. Engineer features
python features_new.py

# 3. Train the optimized model (RandomizedSearchCV)
python optimal_model.py
```
*This will generate and save `random_forest_model_optimized.joblib` inside the `output/models/` directory.*

### 2. Running the Streamlit Web App
To launch the interactive dashboard for real-time predictions:

```bash
streamlit run app.py
```
*The app will automatically open in your default web browser.*

---

## 📊 Model Performance
The final model is an optimized **Random Forest Classifier** trained with class balancing (`class_weight='balanced'`) to handle the inherent imbalance in churn datasets. 
* Hyperparameters were tuned using `RandomizedSearchCV` optimizing for **ROC-AUC**.
* Preprocessing includes `StandardScaler` for numerical features and `OneHotEncoder` for categorical variables.

---

## 🤝 Contributing
Contributions, issues, and feature requests are welcome!
Feel free to check the [issues page](https://github.com/your-username/teleco-churn-boxbox/issues).

---

## 📝 License
This project is licensed under the MIT License.
