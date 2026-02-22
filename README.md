# AlfaisalX Postdoctoral Technical Challenge – PneumoniaMNIST

This repository presents a complete experimental pipeline addressing classification, multimodal report generation, and representation-based retrieval on the PneumoniaMNIST dataset.

---

## Task 1 – Supervised Pneumonia Classification

A deep convolutional neural network was trained for binary chest X-ray classification (normal vs pneumonia). The study includes:

- Training and validation loss curves  
- ROC curve and AUC analysis  
- Confusion matrix evaluation  
- Structured performance reporting  

These analyses assess diagnostic reliability and model generalization.

---

## Task 2 – Vision-Language Report Generation

A pretrained BLIP vision-language model was used to generate structured radiology-style findings and impressions directly from chest X-ray images.

The pipeline demonstrates multimodal reasoning by linking visual features to coherent clinical text outputs. Generated reports are stored alongside corresponding images for qualitative inspection.

---

## Task 3 – Embedding-Based Image Retrieval

High-level visual embeddings were extracted from chest X-ray images and indexed using FAISS for efficient similarity search.

Evaluation includes:

- Embedding extraction and storage  
- FAISS index construction  
- Recall@K metrics  
- Qualitative nearest-neighbor visualization  

This task evaluates semantic consistency and representation quality in a retrieval setting.

---

## Summary

Together, these tasks demonstrate supervised learning, multimodal modeling, and representation learning within a unified medical imaging framework.
