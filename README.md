# ML-Powered Stress Recognition and Wellness Recommendation System

A machine learning-based system that predicts an individual's stress level using health and lifestyle data, then provides personalized wellness recommendations.

## Project Overview

This project builds and compares four classification models to predict stress levels (on a scale of 1-10) from features such as sleep duration, physical activity, BMI, blood pressure, heart rate, and daily steps. The best-performing models are combined via majority voting and a stacking ensemble meta-model. A rule-based recommendation engine then suggests wellness actions based on the predicted stress level and health metrics.

**Dataset:** [Sleep Health and Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset) (Kaggle) — 374 records, 13 columns.

## Models Used

| Model | Type | Role |
|---|---|---|
| **Support Vector Machine (SVM)** | RBF Kernel Classifier | Base classifier |
| **XGBoost** | Gradient Boosted Trees | Base classifier |
| **Logistic Regression** | Linear Classifier | Base classifier |
| **Meta-Model (Stacking Ensemble)** | Logistic Regression trained on SVM + XGBoost probability outputs | Ensemble meta-classifier |

Final prediction uses **majority voting** across the three base models.

## Features

**Input features used for prediction:**
- Gender, Age, Sleep Duration, Quality of Sleep, Physical Activity Level, BMI Category, Blood Pressure, Heart Rate, Daily Steps

**Target:** Stress Level (integer, range 3-8 in dataset)

## Recommendation System

A rule-based function provides personalized advice based on predicted stress level and health metrics:

| Condition | Recommendation |
|---|---|
| Stress Level > 7 | Meditation, Yoga, Reduce screen time, Regular Sleep |
| Physical Activity < 5 | Increase Physical Activity, Morning Walk, Breathing Exercises |
| Sleep Quality < 5 | Improve Sleep Hygiene, Avoid Caffeine, Create Sleep Schedule |
| BMI > 30 | Consult a nutritionist, Begin a weight loss program |
| Blood Pressure > 140 | Consult with a healthcare provider for blood pressure management |
| None of the above | Maintain Current Lifestyle, Stay Positive |

## Project Structure

```
ML_Powered_Stress_Recognition/
├── Stress_Recognition_and_Wellness_Recommendation.ipynb   # Jupyter Notebook (Google Colab)
├── stress_recognition_and_wellness_recommendation.py       # Python script (exported from Colab)
├── Sleep_health_and_lifestyle_dataset.csv                  # Dataset
├── Colab_Link.txt                                          # Link to Colab notebook
├── requirements.txt                                        # Python dependencies
├── README.md                                               # This file
├── ML-FinalTerm-Reort-SEC-D-group-8.docx                   # Project report (Word)
└── ML-Powered Stress Recognition and Wellness Recommendation System.pdf  # Project report (PDF)
```

## Installation & Usage

### Option 1: Google Colab (Recommended)

1. Open the notebook via the link in `Colab_Link.txt`:
   ```
   https://colab.research.google.com/drive/1tsDBkCnbTZdIvrXWSh8XfTjwg6H0kCwm?usp=sharing
   ```
2. Upload the dataset to Google Drive at `/content/drive/My Drive/ML_Project/Sleep_health_and_lifestyle_dataset.csv`
3. Run all cells.

### Option 2: Local Environment

1. Clone the repository and navigate to the project directory:
   ```bash
   git clone https://github.com/yourusername/ML_Powered_Stress_Recognition.git
   cd ML_Powered_Stress_Recognition
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Before running locally, edit `stress_recognition_and_wellness_recommendation.py`:
   - Comment out lines 36-37 (`from google.colab import drive` / `drive.mount`)
   - Update the `path` variable on line 40 to point to the local CSV file
4. Run the script:
   ```bash
   python stress_recognition_and_wellness_recommendation.py
   ```

## Dependencies

- Python 3.x
- numpy, pandas
- scikit-learn, xgboost
- matplotlib, seaborn
- scipy

## Evaluation Metrics

The script evaluates all models using:
- Accuracy
- Weighted F1 Score
- Weighted Precision & Recall
- Classification Report (per-class)
- Confusion Matrix

## Results

| Model | Accuracy | F1 Score | Precision | Recall |
|---|---|---|---|---|
| SVM | — | — | — | — |
| XGBoost | — | — | — | — |
| Logistic Regression | — | — | — | — |
| Meta-Model | — | — | — | — |

*(Run the notebook/script to populate results.)*

## Team

SEC-D, Group 8 — Final Term Project

## License

This project is for educational purposes.
