# AI Phishing Detector 🛡️

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

A machine learning app that detects phishing in two places: **suspicious URLs** and **scam emails**.
Paste a link or an email and it labels it as **Safe** or **Phishing** instantly.

## Features

- **URL analyzer:** extracts structural features from a link (length, symbols, subdomains and so on), scales them and classifies it
- **Email classifier:** turns email text into TF-IDF vectors and classifies it with an NLP model
- **Two trained models** saved as `.pkl` files for instant predictions, with no retraining needed
- **Simple web UI** built with Streamlit
- **Full training notebook** (`code/system.ipynb`) covering data cleaning, exploration, training and evaluation

## How it works

```
URL   ──► feature extraction ──► scaler ──► URL model   ──┐
                                                          ├──► Safe / Phishing
Email ──► text cleaning ──► TF-IDF vectorizer ──► email model ──┘
```

## Getting started

```bash
git clone https://github.com/Zotriq/ai-phishing-detector.git
cd ai-phishing-detector
pip install streamlit scikit-learn joblib numpy pandas

cd code
streamlit run app.py
```

Run the app from inside `code/`, because that's where the trained model files are.

## Project structure

```
code/
  app.py                  Streamlit app
  system.ipynb            Data analysis and model training
  url_model.pkl           URL classifier
  url_scaler.pkl          URL feature scaler
  email_model.pkl         Email classifier
  email_vectorizer.pkl    TF-IDF vectorizer
datasets/
  dataseturl.csv          Labeled URL dataset
  emailscam.csv           Labeled email dataset
```

## Tech stack

Python · scikit-learn · pandas · NumPy · Streamlit · joblib
