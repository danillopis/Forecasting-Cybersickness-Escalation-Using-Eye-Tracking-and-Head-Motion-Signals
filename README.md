Forecasting Cybersickness Escalation Using Eye-Tracking and Head-Motion Signals

<p align="center">
  <img src="general pipeline.png" width="900">
</p>
<p align="center">
  <strong>Master's Thesis | Master in Science in Neurotechnology</strong><br>
  Universidad Politécnica de Madrid (UPM)
</p>

# Overview

This project investigates whether cybersickness escalation events can be anticipated using eye-tracking and head-motion signals acquired directly from Virtual Reality (VR) head-mounted displays (HMDs).

The proposed framework combines:

* Time-series preprocessing
* Sliding-window forecasting
* Feature engineering
* Classical Machine Learning
* Deep Learning (1D-CNN and LSTM)
* Explainable Artificial Intelligence (SHAP)

The objective is to generate early warnings before cybersickness symptoms become severe enough to be explicitly reported by users.

# Research Motivation

Cybersickness remains one of the main barriers to the widespread adoption of immersive Virtual Reality systems.

Most existing approaches focus on detecting current discomfort levels. This project investigates a more challenging problem:

Can cybersickness escalation be predicted before users report an increase in symptoms?

Such forecasting capabilities could enable adaptive VR systems capable of proactively mitigating discomfort through dynamic interventions.

# Dataset

The experiments are based on the MazeSick dataset introduced within the RelaxVR framework.

Dataset Characteristics

* 60 participants
* HTC Vive Pro Eye headset
* Eye-tracking signals
* Head-motion signals
* 60 Hz sampling frequency
* Fast Motion Sickness Scale (FMS) labels every 30 seconds

Note: The original dataset is not redistributed in this repository. Please refer to the original RelaxVR publication for access conditions.

# Methodology

The complete pipeline consists of:

1. Dataset loading and exploratory analysis
2. Signal preprocessing
3. Forecasting window construction
4. Temporal feature extraction
5. Class imbalance handling
6. Machine Learning model development
7. Deep Learning model development
8. Explainability analysis with SHAP
9. Early-warning evaluation

Pipeline Overview

Raw VR Signals
       ↓
Preprocessing
       ↓
Forecasting Windows
       ↓
Feature Engineering
       ↓
ML / DL Models
       ↓
Model Comparison
       ↓
SHAP Explainability
       ↓
Cybersickness Escalation Forecasting

# Evaluated Models

Classical Machine Learning

* Logistic Regression
* Random Forest
* HistGradientBoosting
* XGBoost
* CatBoost
* Support Vector Machine (SVM)
* Multilayer Perceptron (MLP)

Deep Learning

* 1D Convolutional Neural Network (1D-CNN)
* Long Short-Term Memory Network (LSTM)

# Main Results

Key findings include:

* Classical ML models achieved competitive performance.
* XGBoost provided the strongest tree-based baseline.
* MLP achieved the highest ROC-AUC.
* 1D-CNN achieved the highest Recall and Balanced Accuracy.
* LSTM achieved the highest F1-score, PR-AUC, and MCC.
* Eye-tracking signals contained predictive information prior to cybersickness escalation.

The results support the hypothesis that temporal patterns in gaze behaviour and head-motion dynamics can be used for early cybersickness forecasting.

# Explainability

SHAP (SHapley Additive exPlanations) was used to identify the most influential predictors.

The most relevant variables were associated with:

* Gaze direction
* Eye position
* Pupil dynamics
* Eye openness
* Head movement behaviour

These findings are consistent with the neurophysiological mechanisms proposed by Sensory Conflict Theory.

# Repository Structure

```

├── MazeSick_final.csv: Final processed MazeSick dataset used throughout the study.

│

├── RelaxVR_Cybersickness_Reduction_in_Immersive_VR.pdf: Original publication introducing the RelaxVR framework and MazeSick dataset.

│

├── tfm_mazestick copy.ipynb: Main Jupyter notebook containing the complete experimental pipeline, including preprocessing, feature engineering, model training, evaluation, and explainability analyses.

│

├── all_model_results.csv: Consolidated performance metrics for all evaluated models.

│

├── logistic_regression_results.csv: Detailed results obtained from Logistic Regression experiments.

│

├── xgboost_results.csv: Detailed results obtained from XGBoost experiments.

│

├── lstm_hyperparameter_search_results.csv: Hyperparameter optimization results for the LSTM architecture.

│

├── lstm_test_metrics.csv: Final evaluation metrics obtained by the selected LSTM model.

│

├── general pipeline.png: Visual summary of the complete forecasting methodology.

│

├── README.md: Project documentation and usage instructions.

│

├── LICENSE: Repository license information.

│

└── .gitignore: Files and folders excluded from version control.

```

# Technologies

* Python
* NumPy
* Pandas
* Scikit-Learn
* XGBoost
* CatBoost
* TensorFlow / Keras
* SHAP
* Matplotlib
* Seaborn
* Jupyter Notebook

# Author

Daniel Llopis

Master in Science in Neurotechnology

Universidad Politécnica de Madrid (UPM)

GitHub: @danillopis

# Citation

If you use this work, please cite:

Llopis, D; Melgar, Laura; Bajo, Javier
Forecasting Cybersickness Escalation Using Eye-Tracking and Head-Motion Signals.
Master's Thesis, Universidad Politécnica de Madrid (UPM), 2026.


License

This project is released under the MIT License.
