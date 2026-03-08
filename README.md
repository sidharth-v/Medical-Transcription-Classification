# Medical Transcription Classification

## Overview
This project builds a Natural Language Processing (NLP) system that automatically classifies medical transcription documents into medical specialties.

The system processes raw medical text, extracts biomedical entities using SciSpaCy, and trains machine learning models to predict the correct specialty.

Example specialties include:
- Cardiology
- Neurology
- Radiology
- Orthopedics
- Gastroenterology

---

## Project Pipeline

1. Data Cleaning
2. Text Preprocessing
3. Stopword Removal
4. Lemmatization
5. Biomedical Named Entity Recognition (SciSpaCy)
6. Feature Extraction using TF-IDF
7. Machine Learning Model Training
8. Model Evaluation
9. Cross Validation
10. Prediction Interface

---

## Technologies Used

- Python
- spaCy
- SciSpaCy
- scikit-learn
- NLTK
- Pandas
- Matplotlib
- Joblib

---

## Dataset

The dataset used is the **Medical Transcriptions (mtsamples)** dataset.

Each record contains:
- medical transcription text
- medical specialty label

---

## Machine Learning Models

The following models were trained and compared:

- Linear SVM
- Logistic Regression
- SGD Classifier
- Complement Naive Bayes

The best model is selected based on accuracy.

---

## Feature Engineering

Text features are created using:

- Text preprocessing
- Biomedical entity extraction
- TF-IDF vectorization
- n-gram features (1–3)

---

## Example Prediction

Input:
Patient complains of chest pain and shortness of breath.

Output:
Cardiology

---

## Model Output

The trained model and vectorizer are saved as:

best_model.pkl  
tfidf_vectorizer.pkl

---

## How to Run

1. Install dependencies
2. Run the notebook
3. Train the model
4. Enter a new medical transcription to get a prediction

---

## Future Improvements

- Deep learning models (BioBERT / ClinicalBERT)
- Larger clinical datasets
- Web interface for real-time prediction
- Clinical entity linking
