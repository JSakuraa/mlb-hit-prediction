# 🧠 CS5100 Final Project – Predicting MLB Hits Using Machine Learning

## 🔍 Project Overview
This project was created as the final assignment for **CS5100: Foundations of Artificial Intelligence** at Northeastern University. The goal was to apply machine learning techniques learned in class to investigate a real-world question.

**Research Question:**  
*Can we predict if a batter will get a hit in a given at-bat?*

Using data from MLB pitch-by-pitch records, we attempted to classify whether a batter would get a hit based on pre-at-bat and pitcher/batter matchup information.

---

## 📁 Dataset
The dataset used contains **pitch-level** data including:

- Batter and pitcher IDs
- Batter's stance and pitcher's throwing hand
- Description of the pitch (e.g., swing, foul, ball)
- Game outcomes (hit, out, walk, etc.)
- Batter's statistics (AVG, OBP, SLG, PA)
- Pitcher’s statistics (ERA, WHIP, SO9, etc.)

### ⚠️ Preprocessing Steps:
- Dropped rows where the event outcome (`events`) was missing to focus on final pitches of each at-bat.
- Categorical columns (`stand`, `p_throws`, `description`) were encoded using one-hot encoding and label encoding.
- Applied feature scaling to continuous variables.
- Addressed **class imbalance** using **SMOTE** to synthetically balance the dataset.

---

## 🤖 Models Trained
Three types of models were trained and evaluated:

### 1. Logistic Regression
- Baseline model to evaluate linear separability.
- Performance suffered due to class imbalance.
- After SMOTE: Accuracy ~71%, with improved recall for the minority class.

### 2. Random Forest Classifier
- Best-performing model after resampling.
- After SMOTE:  
  **Accuracy:** 81%  
  **Precision/Recall (Hit):** 0.79 / 0.83  
  **F1-score:** 0.81  
- Captured complex patterns and balanced prediction between classes.

### 3. Neural Network (Keras)
- Basic feedforward network with two hidden layers.
- Accuracy plateaued similar to other models, showing diminishing returns from complexity.

---

## 📈 Model Evaluation
Models were evaluated using:

- **Accuracy**: Overall correctness.
- **Precision**: Out of all predicted hits, how many were actual hits.
- **Recall**: Out of all actual hits, how many the model correctly identified.
- **F1-score**: Harmonic mean of precision and recall.

> Initial high accuracy was misleading due to class imbalance. After applying SMOTE, both precision and recall improved significantly, especially for predicting actual hits.

---

## 🧠 Key Takeaways
- **Class imbalance** heavily affected model performance — accuracy alone was not a good indicator.
- **SMOTE** helped models learn meaningful distinctions between hit and no-hit at-bats.
- **Random Forest** provided the best balance of performance and interpretability.

---

## 🏫 Course Info
**Course:** CS5100 Foundations of Artificial Intelligence  
**Instructor:** Prof. Richard Hoshino
**Institution:** Northeastern University 
**Semester:** Spring 2025  
**Student:** Justin Nappi

---

## 📌 Future Work
- Incorporate pitch location and speed data.
- Explore time-series models for full at-bat prediction sequences.
- Test additional balancing strategies like ensemble methods with stratified sampling.

---
