# Credit Risk Prediction using Machine Learning

## 📌 Project Overview

This project is a **Credit Risk Prediction** system built using Machine Learning classification techniques. The model uses applicant financial and demographic information to classify a loan applicant as a **Good Customer** or a **Bad Customer**, helping lenders make more informed lending decisions.

The project demonstrates a complete machine learning workflow, including data cleaning, feature encoding, feature selection, data balancing, model training, evaluation, and deployment as a web application.

### Key Features

* Data manipulation using **Pandas**
* Data cleaning and handling of missing values
* Categorical feature encoding
* Feature selection
* Class balancing using SMOTE
* Feature scaling using StandardScaler
* Classification model training
* Model evaluation
* Model serialization using **Pickle**
* Flask-based web application
* Responsive HTML/CSS frontend with input validation
* Deployment using **Render**

---

## 🛠️ Technologies Used

| Technology | Purpose |
| --- | --- |
| **Python** | Programming language |
| **Pandas** | Data manipulation and preprocessing |
| **NumPy** | Numerical operations |
| **Scikit-learn** | Machine learning, preprocessing and evaluation |
| **Imbalanced-learn** | Data balancing using SMOTE |
| **Matplotlib** | Data visualization |
| **Flask** | Web application and backend |
| **HTML/CSS** | Frontend development |
| **Pickle** | Saving and loading the trained model |
| **Render** | Application deployment |

---

## 📊 Dataset

The dataset contains **150,002 applicant records** with financial, demographic, and credit history information. The target variable is `Good_Bad`, which labels each customer as Good or Bad.

| Class | Count |
| --- | --- |
| Good | 139,974 |
| Bad | 10,026 |

The dataset is **imbalanced**, with far fewer Bad customers than Good ones. This is why class balancing was important.

### Main Columns

| Column | Description |
| --- | --- |
| `age` | Age of the applicant |
| `Gender` | Gender of the applicant |
| `Region` | Region of residence (Central, East, North, South, West) |
| `MonthlyIncome` | Monthly income of the applicant |
| `Rented_OwnHouse` | Housing status (Ownhouse or Rented) |
| `Occupation` | Occupation category (Self_Emp, Non-officer, Officer1, Officer2, Officer3) |
| `Education` | Education level (Matric, Graduate, Post-Grad, Professional, PhD) |
| `NumberOfOpenCreditLinesAndLoans` | Number of open credit lines and loans |
| `NumberRealEstateLoansOrLines` | Number of real estate loans or lines |
| `NumberOfTime30-59DaysPastDueNotWorse` | Count of 30–59 day late payments |
| `NumberOfTime60-89DaysPastDueNotWorse` | Count of 60–89 day late payments |
| `NumberOfTimes90DaysLate` | Count of payments 90+ days late |
| `DebtRatio` | Monthly debt payments divided by monthly income |
| `RevolvingUtilizationOfUnsecuredLines` | Credit card balance relative to credit limit |
| `NumberOfDependents` | Number of dependents |
| `Good_Bad` | **Target variable** (Good or Bad customer) |

---

## 🧹 Data Cleaning

Data cleaning was performed before training the machine learning models.

The cleaning process included:

* Checking the dataset structure and data types
* Handling missing values
* Removing duplicate records
* Resetting the dataset index
* Encoding categorical variables into numeric values

---

## 🔧 Feature Engineering

### Categorical Encoding

Text categories were converted into numeric codes so the model could process them:

| Feature | Encoded Values |
| --- | --- |
| `Gender_Male` | 1 = Male, 0 = Female |
| `Region` | One-hot encoded as `Region_East`, `Region_North`, `Region_South`, `Region_West` (all 0 means Central) |
| `Rented_OwnHouse_con` | 0 / 1 mapping |
| `Occupation_con` | 0 to 4 mapping |
| `Education_con` | 0 to 4 mapping |

---

## 🔍 Feature Selection

Feature selection was applied to keep the most useful columns for predicting the target.

---

## ⚖️ Data Balancing

The training data was balanced using **SMOTE (Synthetic Minority Over-sampling Technique)**, which generates synthetic examples of the Bad customer class.

```text
Training Data
      ↓
    SMOTE
      ↓
Balanced Training Data
```

---

## 📏 Feature Scaling

Feature scaling was performed using **StandardScaler**, which transforms each feature using its mean and standard deviation.

```text
z = (x - μ) / σ
```

---

## 🔄 Machine Learning Workflow

```text
                 Dataset
                    ↓
              Data Cleaning
                    ↓
          Categorical Encoding
                    ↓
            Feature Selection
                    ↓
            Train-Test Split
                    ↓
              Data Balancing
                 (SMOTE)
                    ↓
             Feature Scaling
           (StandardScaler)
                    ↓
              Model Training
                    ↓
             Model Evaluation
                    ↓
          Model Serialization
                 (Pickle)
                    ↓
         Flask Web Application
                    ↓
                Deployment
```

---

## 🤖 Machine Learning Model

The model used for prediction is **[Model name, e.g. Random Forest Classifier]**.

[Briefly explain why this model was chosen, or mention the models you compared and which performed best.]

---

## 📋 Input Features

The web application accepts the following applicant details:

| Field | Description |
| --- | --- |
| **Age** | Age of the applicant |
| **Open Credit Lines and Loans** | Number of open credit lines and loans |
| **Real Estate Loans or Lines** | Number of real estate loans or lines |
| **Monthly Income** | Monthly income of the applicant |
| **Gender: Male** | 1 = Male, 0 = Female |
| **Region** | East, North, South, West (all 0 means Central) |
| **Rented / Own House** | Encoded housing status |
| **Occupation** | Encoded occupation category |
| **Education** | Encoded education level |

Each input has a defined minimum and maximum so that invalid values are rejected before they reach the model.

---

## 🌐 Web Application

A **Flask web application** provides a form where users enter applicant details. The backend processes the values, passes them to the trained model, and displays the result as **Good Customer** or **Bad Customer**.

### Application Flow

```text
User enters applicant details
            ↓
         HTML Form
            ↓
           Flask
            ↓
       Data Processing
            ↓
       Feature Scaling
            ↓
    Trained ML Model
            ↓
   Good / Bad Customer Prediction
            ↓
 Display Prediction Result
```

---

## 🚀 Live Deployment

The application is deployed using **Render**.

### 🔗 Live Demo

**[Credit Risk Prediction – Live Application](https://creditcard-1ne1.onrender.com/)**

Enter the applicant details and generate a Good or Bad customer prediction directly through the web application.

---

## 📁 Project Structure

```text
Credit-Risk-Prediction/
│
├── app.py
├── main.py
├── creditcard.csv
├── model.pkl
├── scaler.pkl
├── requirements.txt
│
├── templates/
│   └── index.html
│
└── README.md
```

### File Description

| File/Folder | Description |
| --- | --- |
| `app.py` | Flask application and prediction logic |
| `main.py` | Main machine learning workflow |
| `creditcard.csv` | Dataset used for model development |
| `model.pkl` | Saved trained classification model |
| `scaler.pkl` | Saved feature scaler |
| `requirements.txt` | List of required Python libraries |
| `templates/index.html` | Frontend interface |
| `README.md` | Project documentation |

---

## ▶️ How to Run Locally

### 1. Clone the Repository

```bash
git clone <your-github-repository-link>
```

### 2. Navigate to the Project Directory

```bash
cd Credit-Risk-Prediction
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Virtual Environment

For Windows:

```bash
venv\Scripts\activate
```

### 5. Install Required Libraries

```bash
pip install -r requirements.txt
```

### 6. Run the Flask Application

```bash
python app.py
```

### 7. Open the Application

Open the address shown in the terminal, usually:

```text
http://127.0.0.1:5000/
```

---

## 🎯 Project Objective

The main objective of this project is to build a machine learning application that classifies loan applicants as Good or Bad customers, so lenders can assess credit risk quickly and consistently.

The project covers the full machine learning lifecycle:

**Data → Cleaning → Encoding → Feature Selection → Balancing → Scaling → Training → Evaluation → Deployment**

---

## 🔮 Future Improvements

* Experiment with additional classification algorithms
* Compare different data balancing techniques
* Add probability-based prediction output (confidence score)
* Add model explainability techniques
* Build a complete preprocessing pipeline for deployment
* Improve the frontend user experience

---

## ⚠️ Disclaimer

This project is developed for **educational and machine learning practice purposes only**. The prediction should **not be used as a real lending decision** without proper validation and review by qualified professionals.

---

## 👨‍💻 Author

**Macha G R P Himavantha Reddy**

CSE Student | Machine Learning Enthusiast

Developed as part of Machine Learning training at **Vihara Tech**.

---

## 📄 License

This project is created for **educational and learning purposes**.
