# IndustryLevel Credit Risk Modelling App

## Overview

This repository contains a Streamlit web application for credit risk modelling. The app predicts the probability of loan default and provides a credit score and rating based on user-provided borrower information.

The project includes:
- `app/main.py`: Streamlit application interface
- `app/prediction_helper.py`: Model loading, input preparation, and prediction logic
- `app/artifacts/model_data.joblib`: Saved ML model and preprocessing components
- `requirements.txt`: Python dependencies for deployment

## Features

- Interactive Streamlit UI to collect borrower data
- Uses a pretrained machine learning model to compute default probability
- Generates a credit score and rating category
- Supports categorical inputs such as residence type, loan purpose, and loan type

## Tools and Technologies

- Python 3.x
- Streamlit for the user interface
- scikit-learn for model serialization and classifier behavior
- joblib for saving and loading the model artifact
- pandas and numpy for data handling and numeric computation

## Repository Structure

```
app/
  main.py
  prediction_helper.py
  artifacts/
    model_data.joblib
artifacts/
  model_data.joblib
requirements.txt
README.md
```

## How It Works

1. `app/main.py` renders the Streamlit application and input form.
2. When the user clicks "Calculate Risk", it calls `predict()` from `app/prediction_helper.py`.
3. `prediction_helper.py` loads the saved model and scaler from `app/artifacts/model_data.joblib`.
4. The helper prepares the input data, scales numeric features, and computes a default probability.
5. It converts the probability into a credit score and rating.

## Running Locally

1. Create a virtual environment and activate it.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Streamlit app:
   ```bash
   streamlit run app/main.py
   ```

## Deployment

This app is ready for deployment on Streamlit Cloud. Ensure the app entrypoint is set to `app/main.py` and the repository root contains `requirements.txt`.

## Notes

- The current model artifact is stored in `app/artifacts/model_data.joblib`.
- If you want to retrain or update the model, first generate a new model artifact and replace the existing joblib file.
- Optional improvement: add data validation, more detailed feature engineering, and a clearer explanation of model output.
