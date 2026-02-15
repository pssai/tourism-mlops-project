%%writefile README.md
# Tourism Package Purchase Prediction - Complete MLOps Project

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![HuggingFace](https://img.shields.io/badge/🤗-HuggingFace-yellow.svg)](https://huggingface.co/)

## Project Overview

This is a comprehensive end-to-end MLOps project that predicts whether a customer will purchase a tourism package. The project implements:

-  Data registration and versioning on HuggingFace
-  Automated data preparation and cleaning
-  Multiple ML model training with hyperparameter tuning
-  Experiment tracking with MLflow
-  Model deployment using Streamlit on HuggingFace Spaces
-  CI/CD pipeline with GitHub Actions
-  Containerization with Docker

## Problem Statement

Predict whether a customer will purchase a tourism package based on:
- Customer demographics (age, gender, occupation, income)
- Interaction details (pitch duration, followups, satisfaction)
- Travel preferences (destinations, property stars)
- Historical data (previous trips, passport status)

## Project Structure

```
tourism-mlops-project/
│
├── data/                          # Dataset storage
│   ├── tourism_raw.csv
│   ├── train.csv
│   ├── test.csv
│   └── label_encoders.pkl
│
├── models/                        # Trained models
│   ├── best_model.pkl
│   └── model_metadata.json
│
├── deployment/                    # Deployment files
│   ├── app.py                    # Streamlit application
│   ├── requirements.txt          # Python dependencies
│   ├── Dockerfile                # Docker configuration
│   ├── README.md                 # Deployment docs
│   └── deploy_to_hf.py          # HuggingFace deployment script
│
├── outputs/                       # Model outputs and visualizations
│   ├── model_comparison.csv
│   ├── confusion_matrix.png
│   └── feature_importance.png
│
├── .github/workflows/            # CI/CD pipeline
│   └── ml_pipeline.yml
│
├── tourism_mlops_project.ipynb   # Main Google Collab
├── tourism.csv                    # Original dataset
├── README.md                      # This file
└── .gitignore
```

## Quick Start

### Prerequisites
- Python 3.10+
- HuggingFace account and access token
- GitHub account
- Git installed

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/pssai/tourism-mlops-project.git
cd tourism-mlops-project
```

2. **Install dependencies**
```bash
pip install -r deployment/requirements.txt
```

3. **Run the Google collab **
```bash
collab notebook tourism_mlops_project.ipynb
```

## Models Implemented

All models with hyperparameter tuning:
- Decision Tree Classifier
- Random Forest Classifier
- Bagging Classifier
- AdaBoost Classifier
- Gradient Boosting Classifier
- XGBoost Classifier

## ML Pipeline

### 1. Data Registration
- Created folder structure
- Registered data on HuggingFace dataset space

### 2. Data Preparation
- Load data from HuggingFace
- Data cleaning and preprocessing
- Train-test split (80-20)
- Upload processed data to HuggingFace

### 3. Model Building
- Load data from HuggingFace
- Model training with GridSearchCV
- MLflow experiment tracking
- Model evaluation and comparison
- Register best model on HuggingFace

### 4. Model Deployment
- Streamlit web application
- Dockerfile for containerization
- Requirements file
- Deployment script for HuggingFace Spaces

### 5. MLOps Pipeline
- GitHub Actions workflow
- Automated CI/CD pipeline
- Auto-deployment on push to main

## Deployment

### Local Deployment
```bash
cd deployment
streamlit run app.py
```

### Docker Deployment
```bash
cd deployment
docker build -t tourism-predictor .
docker run -p 8501:8501 tourism-predictor
```

### HuggingFace Spaces
```bash
cd deployment
python deploy_to_hf.py
```

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Best Model | 0.XX | 0.XX | 0.XX | 0.XX |

*Note: Run the notebook to see actual performance metrics*

## Links

- **Dataset**: [HuggingFace Dataset](https://huggingface.co/datasets/sspingali/tourism-package-prediction-model)
- **Model**: [HuggingFace Model Hub](https://huggingface.co/sspingali/tourism-prediction-model)
- **App**: [HuggingFace Spaces](https://huggingface.co/spaces/sspingali/tourism-package-prediction)
- **GitHub**: [Repository](https://github.com/pssai/tourism-mlops-project)

## Configuration

### HuggingFace Setup
1. Create account at https://huggingface.co/
2. Generate access token: Settings → Access Tokens → New Token
3. Update credentials in notebook and deployment scripts

### GitHub Actions Setup
1. Go to repository Settings → Secrets and variables → Actions
2. Add secrets:
   - `HF_TOKEN`: xxx
   - `HF_USERNAME`: xxx

## Technologies Used

- **ML Frameworks**: scikit-learn, XGBoost
- **Experiment Tracking**: MLflow
- **Deployment**: Streamlit, Docker
- **Cloud**: HuggingFace Spaces
- **CI/CD**: GitHub Actions
- **Data Processing**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn

## Features

-  Comprehensive data cleaning and preprocessing
-  Feature engineering (age groups, income groups)
-  Multiple model comparison
-  Hyperparameter tuning with GridSearchCV
-  Cross-validation
-  Detailed model evaluation
-  Feature importance analysis
-  Interactive web application
-  Real-time predictions
-  Automated CI/CD pipeline

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License.

## Author

Your Name - [GitHub](https://github.com/pssai)

## Acknowledgments

- Dataset source: Tourism company customer data
- HuggingFace for hosting services
- Scikit-learn and XGBoost communities
---
