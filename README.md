# Medical Transcription Classification using Text Mining and Machine Learning

## Overview

This project focuses on classifying **medical transcription reports into medical specialties** using **text mining and machine learning techniques**.

Medical transcription is the process of converting spoken medical reports into written text. Managing and categorizing large volumes of these transcriptions manually can be time-consuming and error-prone. This project automates the classification process using Natural Language Processing (NLP) and machine learning models.

The system processes unstructured medical text, extracts relevant medical terms, and predicts the correct medical specialty associated with each transcription.

---

## Dataset

The dataset used in this project is the **Medical Transcriptions dataset from Kaggle**, which contains medical reports categorized by specialty.

Dataset characteristics:

* **4998 records**
* **5 columns**

  * description
  * medical_specialty
  * sample_name
  * transcription
  * keywords

The project primarily uses the following columns:

* **transcription** – the medical text
* **medical_specialty** – the target label for classification

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* spaCy / SciSpaCy
* NLTK
* Matplotlib
* Seaborn
* imbalanced-learn (SMOTE)

---

## Project Workflow

### 1. Data Loading

The dataset is loaded into a Pandas DataFrame and inspected to understand its structure, number of classes, and distribution of medical specialties.

---

### 2. Data Cleaning

The transcription text contains noise such as special characters and formatting issues. Cleaning steps include:

* Converting text to lowercase
* Removing special characters
* Removing null values
* Normalizing text

---

### 3. Lemmatization

Lemmatization is applied to convert words to their base form.

Example:

* "walking" → "walk"
* "dogs" → "dog"

This helps reduce variations of words and improves model performance.

---

### 4. Entity Extraction

Medical entities are extracted using **SciSpaCy biomedical NLP models**.
These models identify important medical terms such as:

* diseases
* drugs
* symptoms
* procedures

This step helps isolate meaningful medical terminology from the transcription text.

---

### 5. Exploratory Data Analysis

EDA is performed to understand patterns within the dataset, including:

* distribution of medical specialties
* similarity between specialties
* common medical terms

Cosine similarity is used to analyze relationships between different specialties.

---

### 6. Tokenization

Tokenization splits text into smaller components (tokens), typically words.

Example:

Sentence:

```
Left ventricular wall abnormality detected
```

Tokens:

```
["left", "ventricular", "wall", "abnormality", "detected"]
```

NLTK is used for tokenization.

---

### 7. Part-of-Speech Tagging

POS tagging identifies grammatical roles of words.

Important POS tags retained:

* **NN** – Nouns
* **JJ** – Adjectives
* **NNS** – Plural nouns

These tags help capture important medical terms and descriptions.

---

### 8. Feature Engineering

#### TF-IDF Vectorization

Text data is converted into numerical form using **TF-IDF (Term Frequency-Inverse Document Frequency)**.

This allows machine learning models to analyze textual information.

After vectorization:

* Dataset transformed into a **1000-feature numerical matrix**

---

### 9. Dimensionality Reduction

**Principal Component Analysis (PCA)** is applied to reduce dimensionality while retaining important information.

Benefits:

* reduces noise
* improves model performance
* improves visualization of clusters

---

### 10. Handling Class Imbalance

Medical datasets often suffer from **class imbalance**, where some specialties have fewer samples.

To address this issue:

* **SMOTE (Synthetic Minority Over-sampling Technique)** is applied to generate synthetic samples for minority classes.

---

## Machine Learning Models

Two classification algorithms are implemented and compared:

### Logistic Regression

A statistical classification model used to estimate the probability of category membership.

### Random Forest

An ensemble learning method that combines multiple decision trees to improve prediction accuracy.

---

## Model Evaluation

The models are evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Classification Report

Results from both models are compared to determine the best performing algorithm.

---

## Results

The machine learning models successfully classify medical transcriptions into their respective specialties using textual patterns and extracted medical terms.

Feature engineering techniques such as **TF-IDF vectorization, PCA, and SMOTE** significantly improve classification performance.

---

## Future Improvements

Possible improvements for this project include:

* Implementing **Deep Learning models (LSTM, BERT, BioBERT)**
* Using **advanced biomedical NLP models**
* Improving dataset balance
* Deploying the model as a **web application or API**

---

## How to Run the Project

### Clone the repository

```
git clone https://github.com/yourusername/medical-transcription-classification.git
```

### Install dependencies

```
pip install pandas numpy scikit-learn matplotlib seaborn nltk spacy scispacy imbalanced-learn
```

### Run the notebook

```
Medical_transcription_classification.ipynb
```

---

## Author

Sidharth Vengathattil
MSc Data Analytics
De Montfort University
