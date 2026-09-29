# 🩸 DiabetesAI

### Medical Intelligence & Diabetes Risk Assessment Dashboard

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Streamlit-Interactive%20Dashboard-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn"/>
  <img src="https://img.shields.io/badge/Pandas-Data%20Analytics-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Plotly-Interactive%20Charts-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly"/>
</p>

<p align="center">
  <strong>AI-powered healthcare analytics • Risk assessment • Interactive visualization • Machine learning</strong>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-features">Features</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-installation">Installation</a> •
  <a href="#-usage">Usage</a> •
  <a href="#-future-enhancements">Roadmap</a>
</p>

---

## 🧠 Overview

**DiabetesAI** is an interactive machine-learning dashboard designed to demonstrate how predictive analytics can be integrated into a healthcare-oriented decision-support application.

The application combines a trained **Decision Tree Classifier**, **Streamlit**, **Pandas**, **NumPy**, **Scikit-Learn**, and **Plotly** to create a professional clinical-style analytical interface.

Users can enter eight clinical measurements, execute a machine-learning assessment, visualize the resulting probability, review risk classification, explore historical predictions, inspect the training dataset, and examine the model configuration.

> ⚠️ **Educational Project:** DiabetesAI is intended for educational, portfolio, and analytical demonstration purposes. It is **not a medical diagnostic system** and must not replace evaluation by a qualified healthcare professional.

---

# 🚀 Why DiabetesAI?

DiabetesAI demonstrates a complete machine-learning application workflow:

```text
Clinical Input
      ↓
Data Validation
      ↓
Feature Preparation
      ↓
Machine Learning Model
      ↓
Prediction + Probability
      ↓
Risk Classification
      ↓
Interactive Visualization
      ↓
Prediction History
      ↓
Downloadable Report
```

Instead of presenting a machine-learning model as a notebook-only experiment, DiabetesAI integrates the model into an interactive application environment.

---

# ✨ Features

<table>
<tr>
<td width="50%">

### 🔮 Prediction Engine

Enter eight patient measurements and execute a machine-learning risk assessment.

**Includes:**

* Clinical input form
* Input validation
* Model prediction
* Probability calculation
* Risk categorization
* Confidence display
* Patient metric visualization
* Downloadable assessment report

</td>

<td width="50%">

### 📊 Interactive Analytics

Explore predictions and dataset characteristics through interactive visualizations.

**Includes:**

* Risk probability gauge
* Radar-style metric visualization
* Classification charts
* Risk-tier distribution
* Dataset statistics
* Feature distributions

</td>
</tr>

<tr>
<td>

### 📜 Prediction History

Every executed assessment can be stored locally.

```text
prediction_history.csv
```

The registry records:

* Timestamp
* Patient measurements
* Prediction
* Probability
* Risk level

</td>

<td>

### 🗂 Dataset Explorer

Inspect the training dataset directly from the application.

**Provides:**

* Dataset dimensions
* Class distribution
* Raw records
* Feature analysis
* Interactive distributions

</td>
</tr>

<tr>
<td>

### 🤖 Model Architecture

Dedicated model information page displaying:

* Algorithm
* Hyperparameters
* Target variable
* Feature count
* Feature ordering
* Serialized model information

</td>

<td>

### 📚 Clinical Insights

Educational contextual information based on selected measurements including:

* Glucose
* BMI
* Age

The purpose is to explain the displayed assessment rather than provide medical advice.

</td>
</tr>
</table>

---

# 🩺 Clinical Input Features

The prediction engine accepts **8 numerical features**.

|  # | Feature                    | Description                  |
| -: | -------------------------- | ---------------------------- |
| 01 | `Pregnancies`              | Number of times pregnant     |
| 02 | `Glucose`                  | Plasma glucose concentration |
| 03 | `BloodPressure`            | Diastolic blood pressure     |
| 04 | `SkinThickness`            | Triceps skin fold thickness  |
| 05 | `Insulin`                  | 2-hour serum insulin         |
| 06 | `BMI`                      | Body Mass Index              |
| 07 | `DiabetesPedigreeFunction` | Diabetes pedigree score      |
| 08 | `Age`                      | Patient age in years         |

---

# 🎯 Risk Classification

DiabetesAI converts the calculated probability into four presentation-level risk categories.

|   Probability | Risk Tier         |
| ------------: | ----------------- |
|    `0% – 30%` | 🟢 Low Risk       |
|  `>30% – 60%` | 🟡 Moderate Risk  |
|  `>60% – 80%` | 🟠 High Risk      |
| `>80% – 100%` | 🔴 Very High Risk |

The underlying classifier returns:

```text
0 → No diabetes classification
1 → Diabetes classification
```

> **Important:** The risk tiers are application-level presentation categories and should not be interpreted as medically validated diagnostic thresholds.

---

# 📈 Interactive Visualization

DiabetesAI uses **Plotly** to transform model outputs into interactive visual information.

### 🎯 Risk Probability Gauge

A radial gauge presents the model's calculated probability between:

```text
0% ─────────────────────────────── 100%
```

Users can visually inspect the estimated probability instead of relying only on a numerical value.

### 🕸️ Relative Metric Spectrum

Selected patient measurements are normalized against predefined reference bounds and displayed through a radar-style visualization.

This provides a visual comparison of the entered measurements.

---

# 🧠 Decision Context

The dashboard can generate human-readable contextual messages based on selected measurements.

Examples of contextual variables include:

```text
Glucose
BMI
Age
```

These messages are intended to help users understand factors associated with the displayed model assessment.

They are **educational explanations, not clinical recommendations**.

---

# 🤖 Machine Learning Model

DiabetesAI uses a:

## Decision Tree Classifier

### Model Configuration

| Parameter         | Configuration            |
| ----------------- | ------------------------ |
| Algorithm         | Decision Tree Classifier |
| Max Depth         | `7`                      |
| Min Samples Leaf  | `15`                     |
| Min Samples Split | `2`                      |
| Target            | `Outcome`                |
| Input Features    | `8`                      |

The application loads the serialized artifacts:

```text
diabetes_model.pkl
diabetes_features.pkl
```

The stored feature-order information helps ensure that the model receives the expected input structure.

---

# 🏗️ System Architecture

```text
                         ┌────────────────────────┐
                         │      USER / PATIENT    │
                         └────────────┬───────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │    STREAMLIT FRONTEND  │
                         │  Forms + Validation UI │
                         └────────────┬───────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │   FEATURE PROCESSING   │
                         │  8 Clinical Features  │
                         └────────────┬───────────┘
                                      │
                                      ▼
                         ┌────────────────────────┐
                         │   DECISION TREE MODEL  │
                         │ diabetes_model.pkl     │
                         └────────────┬───────────┘
                                      │
                    ┌─────────────────┴─────────────────┐
                    ▼                                   ▼
          ┌──────────────────┐                ┌──────────────────┐
          │   CLASSIFICATION │                │   PROBABILITY    │
          │       0 / 1      │                │      0–100%      │
          └─────────┬────────┘                └─────────┬────────┘
                    │                                   │
                    └─────────────────┬─────────────────┘
                                      ▼
                         ┌────────────────────────┐
                         │    RISK ASSESSMENT    │
                         │ Low / Moderate / High │
                         │      / Very High      │
                         └────────────┬───────────┘
                                      │
               ┌──────────────────────┼──────────────────────┐
               ▼                      ▼                      ▼
      ┌────────────────┐    ┌──────────────────┐    ┌────────────────┐
      │ Plotly Charts  │    │ Prediction       │    │ CSV Report     │
      │ Visualization  │    │ History          │    │ Download       │
      └────────────────┘    └──────────────────┘    └────────────────┘
```

---

# 🖥️ Application Modules

| Module                | Purpose                                        |
| --------------------- | ---------------------------------------------- |
| 🏠 Overview           | Project introduction and system summary        |
| 🔮 Prediction Engine  | Patient assessment and model prediction        |
| 📊 Analytics Hub      | Prediction analytics and historical statistics |
| 📜 Prediction History | Stored assessment registry                     |
| 🗂 Dataset Explorer   | Dataset inspection and visualization           |
| 🤖 Model Architecture | Model configuration and feature information    |
| 📚 Clinical Insights  | Educational measurement context                |
| ℹ️ About              | Project and technology information             |

---

# 📊 Dataset

The supplied dataset contains:

```text
768 records
8 input features
1 target variable
```

### Class Distribution

| Outcome | Records |
| ------: | ------: |
|     `0` |     500 |
|     `1` |     268 |

### Dataset Columns

```text
Pregnancies
Glucose
BloodPressure
SkinThickness
Insulin
BMI
DiabetesPedigreeFunction
Age
Outcome
```

The dataset is used by the **Dataset Explorer** for basic inspection and exploratory analysis.

---

# 📜 Prediction History

Each executed assessment can be stored in:

```text
prediction_history.csv
```

### Stored Information

```text
Timestamp
Pregnancies
Glucose
BloodPressure
SkinThickness
Insulin
BMI
DiabetesPedigreeFunction
Age
Prediction
Probability
Risk Level
```

The history interface provides structured records and CSV export functionality.

---

# 📄 Downloadable Reports

After an assessment, DiabetesAI can generate a downloadable CSV summary.

Example:

```text
DiabetesAI_Report_20260929_233000.csv
```

The report can contain:

```text
Patient Classification
Diabetes Probability
Assessed Risk Category
Glucose
Blood Pressure
BMI
Insulin
Age
Pedigree Function
Assessment Timestamp
```

---

# 🧰 Technology Stack

<div align="center">

| Technology          | Role                        |
| ------------------- | --------------------------- |
| 🐍 **Python**       | Application development     |
| 🎈 **Streamlit**    | Interactive web application |
| 🐼 **Pandas**       | Data manipulation           |
| 🔢 **NumPy**        | Numerical computation       |
| 🤖 **Scikit-Learn** | Machine learning            |
| 📊 **Plotly**       | Interactive visualization   |
| 🎨 **CSS / HTML**   | UI customization            |
| 📦 **Pickle**       | Model artifact loading      |

</div>

---

# 📁 Project Structure

```text
DiabetesAI/
│
├── 📄 app.py
│
├── 📊 diabetes.csv
│
├── 🤖 diabetes_model.pkl
│
├── 🧩 diabetes_features.pkl
│
├── 📜 prediction_history.csv
│
├── 📘 README.md
│
└── 📂 assets/
    └── screenshots/
```

### File Responsibilities

| File                     | Responsibility                                 |
| ------------------------ | ---------------------------------------------- |
| `app.py`                 | Main Streamlit application                     |
| `diabetes.csv`           | Training dataset / dataset exploration         |
| `diabetes_model.pkl`     | Serialized Decision Tree model                 |
| `diabetes_features.pkl`  | Stored model feature ordering                  |
| `prediction_history.csv` | Local prediction registry                      |
| `README.md`              | Project documentation                          |
| `assets/`                | Optional project screenshots and visual assets |

`prediction_history.csv` is automatically created when it does not already exist.

---

# ⚙️ Installation

## 1️⃣ Clone Repository

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
cd DiabetesAI
```

## 2️⃣ Create Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate:

```bash
venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install streamlit pandas numpy scikit-learn plotly
```

Or create a `requirements.txt`:

```text
streamlit
pandas
numpy
scikit-learn
plotly
```

Then:

```bash
pip install -r requirements.txt
```

---

# ▶️ Run DiabetesAI

Start the application:

```bash
streamlit run app.py
```

The terminal will provide a local address similar to:

```text
http://localhost:8501
```

Open that address in your browser.

---

# 🔐 Required Model Artifacts

Before launching the application, verify that these files exist beside `app.py`:

```text
diabetes_model.pkl
diabetes_features.pkl
```

Expected structure:

```text
DiabetesAI/
├── app.py
├── diabetes_model.pkl
└── diabetes_features.pkl
```

If the model artifacts cannot be loaded, the application should display a model-loading error rather than attempting to generate an invalid prediction.

---

# 🧪 Example Workflow

```text
┌─────────────────────┐
│ Launch DiabetesAI   │
└──────────┬──────────┘
           ▼
┌─────────────────────┐
│ Prediction Engine   │
└──────────┬──────────┘
           ▼
┌─────────────────────┐
│ Enter Measurements  │
└──────────┬──────────┘
           ▼
┌─────────────────────┐
│ Execute Assessment  │
└──────────┬──────────┘
           ▼
┌─────────────────────┐
│ Decision Tree Model │
└──────────┬──────────┘
           ▼
     ┌─────┴─────┐
     ▼           ▼
┌──────────┐ ┌────────────┐
│Classify  │ │Probability │
└────┬─────┘ └──────┬─────┘
     └──────┬───────┘
            ▼
┌─────────────────────┐
│ Risk Classification │
└──────────┬──────────┘
           ▼
┌─────────────────────┐
│ Interactive Charts  │
└──────────┬──────────┘
           ▼
     ┌─────┴──────┐
     ▼            ▼
┌──────────┐ ┌───────────┐
│ History  │ │ CSV Report│
└──────────┘ └───────────┘
```

---

# 🎯 Project Objectives

DiabetesAI was developed to demonstrate:

* Integration of machine learning into an interactive application
* Healthcare-oriented predictive analytics
* Model inference through Streamlit
* Interactive data visualization
* Local prediction-history management
* Dataset exploration
* Model configuration transparency
* Downloadable analytical reports
* Professional ML application design

---

# 🔮 Future Roadmap

The project can be extended with:

### 🤖 Machine Learning

* [ ] Random Forest comparison
* [ ] Logistic Regression comparison
* [ ] XGBoost experimentation
* [ ] Cross-validation
* [ ] Hyperparameter optimization
* [ ] ROC-AUC analysis
* [ ] Precision / Recall / F1 analysis
* [ ] Confusion matrix

### 🧠 Explainable AI

* [ ] SHAP explanations
* [ ] Feature importance dashboard
* [ ] Individual prediction explanation
* [ ] Model decision-path visualization

### 🏗️ Engineering

* [ ] REST API model serving
* [ ] Database-backed prediction history
* [ ] User authentication
* [ ] Role-based access
* [ ] Cloud deployment
* [ ] Automated testing
* [ ] CI/CD pipeline
* [ ] Model monitoring
* [ ] Data drift detection

### 📄 Reporting

* [ ] PDF assessment reports
* [ ] Automated report generation
* [ ] Advanced patient trend analytics

---

# 📸 Screenshots

Add your actual application screenshots here:

### 🏠 Dashboard

```text
assets/screenshots/dashboard.png
```

### 🔮 Prediction Engine

```text
assets/screenshots/prediction-engine.png
```

### 📊 Analytics Hub

```text
assets/screenshots/analytics.png
```

### 🤖 Model Architecture

```text
assets/screenshots/model.png
```

Once uploaded to GitHub, you can display them using:

```markdown
![DiabetesAI Dashboard](assets/screenshots/dashboard.png)
```

---

# 🔬 Machine Learning Pipeline

```text
                 ┌─────────────────┐
                 │ Diabetes Dataset│
                 └────────┬────────┘
                          ▼
                ┌──────────────────┐
                │ Data Preparation │
                └────────┬─────────┘
                         ▼
                ┌──────────────────┐
                │ Feature Selection│
                └────────┬─────────┘
                         ▼
                ┌──────────────────┐
                │ Decision Tree    │
                │   Classifier     │
                └────────┬─────────┘
                         ▼
                ┌──────────────────┐
                │ Model Serialization
                └────────┬─────────┘
                         ▼
                ┌──────────────────┐
                │ Streamlit App    │
                └────────┬─────────┘
                         ▼
                ┌──────────────────┐
                │ User Assessment  │
                └────────┬─────────┘
                         ▼
             ┌───────────┴───────────┐
             ▼                       ▼
      Classification          Probability
             │                       │
             └───────────┬───────────┘
                         ▼
                 Risk Presentation
```

---

# 🛡️ Medical Disclaimer

> **DiabetesAI is an educational and portfolio project.**

The predictions produced by this application are generated by a machine-learning model and **must not be interpreted as a medical diagnosis, treatment recommendation, or clinical decision**.

The application has not been presented here as a clinically validated diagnostic tool.

Do not use DiabetesAI to make decisions regarding:

* Medication
* Treatment
* Diagnosis
* Emergency care
* Personal medical management

For real-world medical concerns, consult a qualified healthcare professional.

---

# 📌 Project Information

| Property            | Details                                 |
| ------------------- | --------------------------------------- |
| **Project**         | DiabetesAI                              |
| **Category**        | Machine Learning / Healthcare Analytics |
| **Application**     | Interactive Web Dashboard               |
| **Framework**       | Streamlit                               |
| **Language**        | Python                                  |
| **Model**           | Decision Tree Classifier                |
| **Input Features**  | 8                                       |
| **Target**          | `Outcome`                               |
| **Visualization**   | Plotly                                  |
| **Data Processing** | Pandas / NumPy                          |

---

# 🌟 Learning Outcomes

This project demonstrates practical experience with:

```text
Python
   │
   ├── Data Processing
   ├── Machine Learning
   ├── Model Serialization
   ├── Prediction Pipelines
   │
   └── Streamlit
          │
          ├── Interactive UI
          ├── Session State
          ├── Data Visualization
          ├── File Downloads
          └── Application Architecture
```

It bridges the gap between a trained ML model and a usable application interface.

---

# 📜 License

This project is intended primarily for educational and portfolio use.

If distributing the project publicly, an appropriate open-source license such as **MIT** can be added.

---

# 👨‍💻 Author

### Hadi Inamdar

**AI & Data Science | Machine Learning | Python | Data Analytics**

Interested in building practical AI/ML applications that transform machine-learning models into usable software systems.

---

# ⭐ Support the Project

If you find this project useful:

⭐ Star the repository
🍴 Fork the repository
🐛 Report issues
💡 Suggest improvements
🔧 Contribute enhancements

---

<p align="center">

### 🩸 DiabetesAI

**Machine Learning × Healthcare Analytics × Interactive Visualization**

<br>

`Built with Python • Streamlit • Scikit-Learn • Pandas • NumPy • Plotly`

</p>

---

<p align="center">
  <sub>
    Built as an educational machine-learning application.
    <br>
    Not intended for clinical diagnosis or medical decision-making.
  </sub>
</p>
