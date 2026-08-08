# Fraud Detection App

A machine learning project that predicts whether a financial transaction is fraudulent, with results served through an interactive Streamlit interface.

## Overview

This project applies a supervised classification model to detect fraudulent transactions in financial data. The full pipeline — exploratory data analysis, preprocessing, and model training — was developed in a Jupyter notebook, and the trained model was then integrated into a Streamlit application for interactive predictions.

## Dataset

The model was trained on the [Fraud Detection Dataset](https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset) from Kaggle, a tabular dataset with over 6.3 million transaction records for binary fraud classification.

## Model

- **Algorithm:** Logistic Regression
- **Recall:** 0.94

Given the highly imbalanced nature of fraud detection datasets (fraudulent transactions are a small minority), **recall** was prioritized as the key evaluation metric, since minimizing false negatives (missed fraud cases) is typically more critical than minimizing false positives in this context.

> **Note:** No resampling or class-weighting technique (e.g., SMOTE, class_weight='balanced') was applied during training. This is a known limitation — see [Future Improvements](#future-improvements).

## Tech Stack

- **Language:** Python
- **Data manipulation:** pandas, numpy
- **Visualization:** matplotlib, seaborn
- **Machine learning:** scikit-learn
- **Model persistence:** joblib
- **Interface:** Streamlit

## Project Structure

```
fraud-detection-app/
├── data/                  # Dataset files
├── models/                # Trained/serialized model artifacts
├── dea.ipynb              # Data exploration, preprocessing, and modeling
├── fraud_detection.py     # Streamlit application
└── README.md
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/MthLeal/fraud-detection-app.git
cd fraud-detection-app
```

2. Create and activate a virtual environment (optional but recommended):
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

Run the Streamlit app locally:

```bash
streamlit run fraud_detection.py
```

The application will open in your browser, where you can input transaction data and receive a real-time fraud prediction from the trained model.

> Currently, the app runs locally only and is not deployed to a hosting service.

## Future Improvements

- Apply resampling techniques (SMOTE, undersampling) or class-weighting to address class imbalance
- Evaluate and report additional metrics (precision, F1-score, AUC-ROC, confusion matrix)
- Experiment with alternative models (Random Forest, XGBoost) for comparison
- Deploy the app to Streamlit Community Cloud for public access

## License

This project is open for educational and portfolio purposes.