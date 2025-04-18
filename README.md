# Neural Media Bias Detection - Classification Notebook 🧠📰

This notebook trains and evaluates transformer-based deep learning models (e.g., BERT) to detect **media bias** using expert-labeled datasets. It is part of the project titled:

**"Neural Media Bias Detection Using Distant Supervision With BABE (Bias Annotations By Experts)"**

---

## 📁 Notebook: `classification.ipynb`

### 🎯 Purpose
The main goal of this notebook is to train a **neural language model** (like BERT) for **bias classification** using datasets labeled by experts and crowdsourcers. It optionally uses pre-trained weights from distant supervision.

---

## 🔍 What Happens in This Notebook?

### 1. **Library Imports**
Essential libraries such as `transformers`, `sklearn`, `pandas`, `torch`, etc., are imported.

---

### 2. **Data Loading**
One of the following datasets is loaded:
- `final_labels_MBIC.xlsx` (crowdsourced)
- `final_labels_SG1.xlsx` (8 expert annotators)
- `final_labels_SG2.xlsx` (5 expert annotators)

Each sentence is labeled as **Biased** or **Non-biased**.

---

### 3. **Preprocessing**
- Tokenization using BERT tokenizer.
- Conversion of labels to binary form.
- Splitting into training, validation, and test sets.

---

### 4. **Model Setup**
- Loads `bert-base-uncased` from HuggingFace.
- Sets up binary classification head on top of BERT.
- Defines training parameters (batch size, learning rate, epochs).

---

### 5. **Training**
- Fine-tunes the model on the selected labeled dataset.
- Uses training loop with validation after each epoch.

---

### 6. **Evaluation**
- Reports performance metrics:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
- Visualizes confusion matrix.

---

### 7. **Prediction Examples**
- Predicts bias on new, unseen sentences.
- Shows probability scores and model confidence.

---

## ✅ Requirements

Install the following libraries if not already available:

```bash
pip install transformers datasets sklearn pandas openpyxl

##📦 Data Requirements
Ensure the following data files are available in a data/ directory:

final_labels_SG1.xlsx or final_labels_MBIC.xlsx or final_labels_SG2.xlsx
---
```

These contain the sentences and corresponding bias labels.

⚠️ Notes
The model can train from scratch, so distant_supervision.ipynb is optional.

To use GPU, ensure your Colab environment is set to GPU Runtime (Runtime > Change Runtime Type > GPU).

👤 Authors

Ritul Kulkarni 16010422063

Anish Ketkar 16010422055

Nidhi Korpe 16010422060
