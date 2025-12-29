# DNA-seq-promoter-vs-non-promoter-classification
# Promoter vs Non-Promoter DNA Sequence Classification

This project implements **binary classification of bacterial DNA sequences** to identify **promoter vs non-promoter regions** using **Recurrent Neural Networks (LSTM and GRU)**.  
The notebook was developed and executed in **Google Colab** using TensorFlow/Keras.

---

## 📌 Project Overview

Promoters are specific DNA regions that initiate transcription. Correct identification of promoter sequences is a key task in **computational genomics** and **regulatory sequence analysis**.

In this project:
- DNA sequences are **one-hot encoded**
- Sequence classification is performed using **LSTM** and **GRU** models
- Model performance is evaluated using **accuracy on a validation split**

---

## 📂 Dataset

- **Source**: HuggingFace Datasets  
- **Dataset name**: `neuralbioinfo/bacterial_promoters`
- **Task**: Binary classification  
  - `1` → Promoter  
  - `0` → Non-promoter
- **Sequence length**: Variable (max length = 81 bp)

```python
from datasets import load_dataset
dataset = load_dataset("neuralbioinfo/bacterial_promoters")
```

---

## 🔬 Data Preprocessing

### One-Hot Encoding

| Nucleotide | Encoding |
|-----------|----------|
| A | [1, 0, 0, 0] |
| C | [0, 1, 0, 0] |
| G | [0, 0, 1, 0] |
| T | [0, 0, 0, 1] |

- All sequences are padded/truncated to **81 bp**
- Final input shape: **(N, 81, 4)**

---

---

## 📊 Results

| Model | Validation Accuracy |
|------|---------------------|
| LSTM | ~70–71% |
| GRU  | ~71–72% |

---

---

## 👤 Author

**Ayush Nandi**  
Bioinformatics | Machine Learning | Genomics

