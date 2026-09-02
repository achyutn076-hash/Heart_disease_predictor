# Heart Disease Prediction App

A Streamlit-based machine learning application that predicts whether a person is likely to have heart disease using health indicators such as age, blood pressure, cholesterol, chest pain, ECG results, and heart rate.

## Overview

This project uses a trained logistic regression model to assess heart disease risk from patient medical data. The app provides a simple, interactive interface where users enter clinical values and receive a prediction in real time.

The project is intended for:
- educational purposes
- demonstration of machine learning in healthcare
- quick risk screening awareness and discussion

## Problem Statement

Heart disease remains one of the leading causes of death worldwide. Early detection of risk factors can encourage timely medical evaluation and preventive action. This application demonstrates how machine learning can support that process through a user-friendly interface.

## Features

- Interactive patient form for entering medical values
- Real-time heart disease prediction using a saved ML model
- Support for categorical features such as sex, chest pain type, resting ECG, and ST slope
- Numeric health inputs including age, blood pressure, cholesterol, max heart rate, and oldpeak
- Clear result messages for positive or negative risk prediction
- Simple web interface built with Streamlit

## Tech Stack

- Python
- Streamlit
- Pandas
- scikit-learn
- Joblib
- Jupyter Notebook

## Model and Data

This project loads the following model artifacts:
- `LR_heart.pkl` — trained logistic regression classifier
- `scaler.pkl` — preprocessing scaler used to standardize input features
- `columns.pkl` — expected feature order used during prediction

The training dataset is stored in:
- `heart.csv`

The dataset includes the following attributes:
- Age
- Sex
- ChestPainType
- RestingBP
- Cholesterol
- FastingBS
- RestingECG
- MaxHR
- ExerciseAngina
- Oldpeak
- ST_Slope
- HeartDisease

## How the App Works

1. The user enters clinical values in the Streamlit interface.
2. The app builds a dictionary of input features.
3. Missing categorical columns are filled to match the model’s expected structure.
4. The feature order is aligned with the training data format.
5. The scaler transforms the input values.
6. The logistic regression model predicts whether the patient is likely to have heart disease.
7. The result is shown directly in the app.

## Project Structure

```text
Heart_disease/
├── app.py
├── heart.csv
├── LR_heart.pkl
├── scaler.pkl
├── columns.pkl
├── Project_Heart.ipynb
├── README.md
└── .gitignore
```

## Prerequisites

Before running this project, ensure you have:
- Python 3.8 or newer
- pip
- a virtual environment (recommended)

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd Heart_disease
```

2. Create and activate a virtual environment:

On Windows:
```bash
python -m venv venv
venv\Scripts\activate
```

On macOS/Linux:
```bash
python -m venv venv
source venv/bin/activate
```

3. Install the required dependencies:

```bash
pip install streamlit pandas scikit-learn joblib
```

## Run the Application

Start the app with:

```bash
streamlit run app.py
```

Then open the local URL shown in the terminal, typically:
```text
http://localhost:8501
```

## Usage

1. Open the Streamlit application in your browser.
2. Enter the patient’s detail values.
3. Click the Predict button.
4. Read the output message:
   - The person is likely to have heart disease.
   - The person is unlikely to have heart disease.

## Input Features Used by the Model

The prediction logic includes the following patient attributes:

- Age
- Sex
- Chest pain type
- Resting blood pressure
- Cholesterol
- Fasting blood sugar
- Resting ECG result
- Maximum heart rate achieved
- Exercise-induced angina
- Oldpeak
- ST slope

## Example Prediction Logic

The app creates one-hot-style fields such as:
- Sex_M
- Sex_F
- ChestPainType_ATA
- ChestPainType_ASY
- RestingECG_Normal
- ST_Slope_Flat

This ensures the data matches the feature structure expected by the trained model.

## Notes

- This project is intended for learning and demonstration.
- It is not a substitute for professional medical diagnosis.
- Prediction reliability depends on the quality of the training dataset and the clinical context of the patient.

## Future Improvements

Possible enhancements include:
- adding model evaluation metrics
- comparing multiple algorithms such as Random Forest and XGBoost
- adding patient history tracking
- visualizing prediction factors
- deploying the application to Streamlit Cloud or another hosting platform

## License

This project is available for educational and research use. Add a license file if you intend to distribute it publicly.

## Author

This project was developed as a machine learning exercise focused on heart disease prediction with Python and Streamlit.

## Contributing

Contributions are welcome. If you would like to improve the model, UI, or documentation, feel free to fork the repository and submit a pull request.

## Acknowledgements

This project is inspired by healthcare analytics and machine learning workflows used for clinical risk prediction.
