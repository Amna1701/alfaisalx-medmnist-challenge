# AlfaisalX Postdoctoral Technical Challenge  
MedX Research Unit – Cognitive Robotics & Autonomous Agents  

This repository contains my submission for the 7-Day Postdoctoral Technical Challenge based on the PneumoniaMNIST dataset (MedMNIST v2).

---

## Repository Structure

- `notebooks/` – Colab/Jupyter implementation
- `reports/` – Task reports and generated figures
- `requirements.txt` – Python dependencies

---

# Task 1 – CNN Classification on PneumoniaMNIST

## Objective
Binary classification of chest X-ray images (Normal vs Pneumonia).

## Model Architecture
Lightweight CNN:
- 3 convolutional blocks
- ReLU activations
- MaxPooling layers
- Adaptive average pooling
- Final linear layer (1 logit)

## Training Setup
- Loss: BCEWithLogitsLoss
- Optimizer: Adam
- Learning rate: 1e-3
- Epochs: 15
- Runs on CPU

---

## Performance (Test Set)

| Metric     | Value |
|------------|--------|
| Accuracy   | 0.886 |
| Precision  | 0.857 |
| Recall     | 0.982 |
| F1-score   | 0.915 |
| AUC        | 0.942 |

High recall (0.982) indicates strong sensitivity for pneumonia detection, which is desirable in medical screening contexts.

---

## Saved Outputs

Figures are stored in:

`reports/task1/`

- training_curves.png  
- confusion_matrix.png  
- roc_curve.png  
- failure_cases.png  

Full written analysis:
`reports/task1_classification_report.md`

---

## Reproducibility

Install dependencies:

```bash
pip install -r requirements.txt
