# Automated Interview Transcript Classifier (DistilBERT)

This project uses NLP and transformer-based models to automate hiring decisions by analyzing interview transcripts. It helps recruiters make fair, consistent, and data-driven decisions based on both structured and unstructured candidate information.

---

## Problem Statement

Manual interview evaluation is slow, inconsistent, and biased. This tool automates transcript analysis using ML/NLP techniques to assist hiring teams in evaluating candidate fit.

---

## Features

- Uses **DistilBERT** for binary classification (Hired/Rejected)
- Handles large transcript data and maps skillsets/experience
- Preprocessing: Q&A tagging, skill normalization, experience conversion
- MongoDB for flexible transcript storage
- Generates classification reports, ROC/PR curves, and confusion matrix
- Saves all model artifacts for reuse

---

## 📊 Dataset Overview

| **Feature**  | **Description**                         |
| ------------ | --------------------------------------- |
| transcript   | Raw interview conversation              |
| skills       | Claimed skills (comma-separated)        |
| experience   | Textual experience converted to numeric |
| decision     | Final label (Hired/Rejected)            |


- 3,000 synthetic samples with balanced class distribution
- Data generated across 5 job roles

---

## Model Configuration

- `Model`: distilbert-base-uncased  
- `Max Tokens`: 256  
- `Epochs`: 3  
- `Batch Size`: 8  
- `Optimizer`: AdamW  
- `Loss`: CrossEntropyLoss  
- `Evaluation`: F1-score, ROC-AUC, PR-AUC

---

## Limitations

- May overfit synthetic data if labels leak into responses
- Limited generalization to domain-specific/multilingual interviews
- Long transcripts are truncated due to token limits

---

## Future Improvements

- Test with RoBERTa, DeBERTa, and LLaMA-based models
- Add RAG-based contextual reasoning
- Hyperparameter tuning (Optuna/Ray Tune)
- Deploy as a microservice with FastAPI

---



