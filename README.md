# 🎓 Student Performance Predictor

A production-ready end-to-end Machine Learning web application that predicts a student's **math score** based on socio-demographic and academic factors — built with a modular ML pipeline, Flask backend, and deployed on **AWS Elastic Beanstalk**.

---

## 🔍 Problem Statement

Can we predict how well a student will perform in mathematics based on factors like gender, parental education level, lunch type, test preparation, and scores in other subjects?

This project answers that — and deploys it as a live web application.

---

## 🚀 Live Demo

> Deployed on AWS Elastic Beanstalk  
> *(Add your live URL here once deployed)*

---

## 🧠 Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.8+ |
| ML Models | CatBoost, XGBoost, Random Forest, Ridge, Lasso |
| Web Framework | Flask |
| Deployment | AWS Elastic Beanstalk |
| Data Processing | Pandas, NumPy, Scikit-learn |
| Serialization | Dill |
| Packaging | setuptools |

---

## 📁 Project Structure

```
student-performance-predictor/
│
├── src/
│   ├── components/
│   │   ├── data_ingestion.py       # Load and split dataset
│   │   ├── data_transformation.py  # Feature engineering & preprocessing
│   │   └── model_trainer.py        # Train & evaluate multiple models
│   │
│   ├── pipeline/
│   │   ├── predict_pipeline.py     # Inference pipeline
│   │   └── train_pipeline.py       # Training pipeline
│   │
│   ├── exception.py                # Custom exception handling
│   ├── logger.py                   # Logging setup
│   └── utils.py                    # Helper functions
│
├── artifacts/                      # Saved models & preprocessor
├── notebook/                       # EDA & model experimentation
├── templates/                      # HTML templates (Flask)
├── logs/                           # Application logs
├── .ebextensions/                  # AWS EB config
├── app.py                          # Flask app entry point
├── application.py                  # AWS EB entry point
├── setup.py
├── requirements.txt
└── README.md
```

---

## 📊 Features Used

| Feature | Type |
|---|---|
| Gender | Categorical |
| Race/Ethnicity | Categorical |
| Parental Level of Education | Categorical |
| Lunch Type | Categorical |
| Test Preparation Course | Categorical |
| Reading Score | Numerical |
| Writing Score | Numerical |

**Target Variable:** Math Score

---

## ⚙️ ML Pipeline

```
Raw Data → Data Ingestion → Train/Test Split
       → Data Transformation (OneHotEncoding + StandardScaler)
       → Model Training (6 models evaluated)
       → Best Model Selection (R² threshold)
       → Artifact Serialization (model.pkl + preprocessor.pkl)
       → Flask Prediction API
```

**Models evaluated:** Linear Regression, Ridge, Lasso, K-Neighbors, Decision Tree, Random Forest, XGBoost, CatBoost, AdaBoost

---

## 🏁 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/your-username/student-performance-predictor.git
cd student-performance-predictor
```

### 2. Create virtual environment

```bash
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the app

```bash
python app.py
```

Visit `http://localhost:5000` in your browser.

---

## ☁️ AWS Deployment

This project is configured for **AWS Elastic Beanstalk** deployment.

```bash
# Initialize EB
eb init -p python-3.8 student-performance-app

# Create environment
eb create student-performance-env

# Deploy
eb deploy
```

The `.ebextensions/` folder handles environment configuration automatically.

---

## 📈 Model Performance

> *(Add your best model's R² score here after training)*

| Model | R² Score |
|---|---|
| CatBoost | ~0.88 |
| XGBoost | ~0.87 |
| Random Forest | ~0.85 |
| Ridge Regression | ~0.88 |

*Best model is automatically selected and saved during training.*

---

## 🐛 Known Issues

- Reading and writing score fields in the form are currently swapped — fix in progress.

---

## 👤 Author

**Abhinav Sinha**  
📧 abhinavsinha0093@gmail.com  
🔗 [GitHub](https://github.com/your-username) | [LinkedIn](https://linkedin.com/in/your-profile)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
