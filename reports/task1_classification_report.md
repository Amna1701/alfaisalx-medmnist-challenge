# Task 1 – CNN Classification on PneumoniaMNIST

## 1. Objective
Train a convolutional neural network (CNN) to classify chest X-ray images as Normal (0) or Pneumonia (1) using the PneumoniaMNIST dataset.

---

## 2. Dataset
- Dataset: MedMNIST v2 – PneumoniaMNIST
- Image size: 28 × 28 (grayscale)
- Train: 4708
- Validation: 524
- Test: 624

---

## 3. Model Architecture

A lightweight convolutional neural network (CNN) was implemented to balance performance and computational efficiency.

Architecture components:

- 3 convolutional blocks (Conv → ReLU → MaxPooling)
- Adaptive average pooling
- Fully connected layer producing a single logit output

The model was intentionally designed to remain compact, as PneumoniaMNIST images are low-resolution (28×28) and do not require deep high-capacity architectures.

**Loss Function:** BCEWithLogitsLoss  
**Optimizer:** Adam  
**Learning Rate:** 1e-3  
**Epochs:** 15   

---

## 4. Evaluation Metrics (Test Set)

| Metric     | Value |
|------------|--------|
| Accuracy   | 0.886 |
| Precision  | 0.857 |
| Recall     | 0.982 |
| F1-score   | 0.915 |
| AUC        | 0.942 |

The model demonstrates strong discriminative performance with an AUC of 0.942. 
High recall (0.982) indicates that most pneumonia cases are correctly identified, 
which is desirable in medical screening scenarios. 
The lower precision (0.857) suggests some false positives, 
which is clinically safer than false negatives but may require further calibration.

---

## 5. Training Behavior

Training and validation losses decreased consistently across epochs, demonstrating stable convergence. The validation loss closely followed the training loss, indicating minimal overfitting and good generalization performance.

See:  
- `training_curves.png`

---

## 6. Confusion Matrix

See:  
- `confusion_matrix.png`

The model shows stronger sensitivity toward detecting pneumonia but produces a moderate number of false positives.

---

## 7. ROC Curve

AUC ≈ 0.94, indicating strong discriminative ability.

See:  
- `roc_curve.png`

---

## 8. Failure Case Analysis

Most misclassifications correspond to false positives (normal images predicted as pneumonia), suggesting sensitivity to high-contrast lung patterns.

False negatives are fewer but clinically more significant.

Limitations include:
- Extremely low spatial resolution (28×28)
- Potential ambiguity in borderline cases
- Limited anatomical detail
The observed misclassifications are likely influenced by resolution constraints and subtle radiographic patterns that are difficult to capture at 28×28 scale.
---

## 9. Limitations & Future Work

- Use higher-resolution datasets
- Incorporate explainability methods (Grad-CAM)
- Apply calibration for medical deployment
- Explore deeper pretrained architectures
