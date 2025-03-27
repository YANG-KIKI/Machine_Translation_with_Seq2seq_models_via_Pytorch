# Machine_Translation_with_Seq2seq_models_via_Pytorch

This repository contains the final submission for our **Machine Translation** lab project. It implements a **sequence-to-sequence (Seq2Seq) model with attention** using PyTorch to perform **English-to-French translation**.

## 📌 Project Objectives
The goal of this lab is to:
- Familiarize ourselves with **Machine Translation (MT)**.
- Implement a **basic recurrent sequence-to-sequence model** in PyTorch.
- Train the model on a simple **English → French dataset** from the **Tatoeba corpus**.
- Add an **attention mechanism** to improve translation quality and visualize attention weights.

---

## 📂 File Structure
- **`Lab_Seq2seq_MT_Hanqi_Yang_Ming_Gao_Final Submission.ipynb`** → Jupyter Notebook containing full implementation.
- **`fra.txt`** → Preprocessed English-French sentence pairs.
- **`README.md`** → Project documentation (this file).

---

## 📖 Dataset and Preprocessing
### 🔹 **Dataset**
We use a preprocessed version of the **Tatoeba corpus** from [this source](https://www.manythings.org/anki/), which contains human-made translations for short sentences.

### 🔹 **Preprocessing Steps**
- **Cleaning:** Remove unnecessary characters while keeping French accents.
- **Tokenization:** Split sentences into words.
- **Vocabulary Building:** Construct word-index mappings for both languages.
- **Filtering:** Remove sentence pairs exceeding a set length.

#### ⚡ Required Data:
Ensure that `fra.txt` is placed in the working directory before running the notebook.

---

## 🏗️ Model Architecture
We implement a **Seq2Seq model with attention**, consisting of:

1. **Encoder:** A bidirectional GRU (Gated Recurrent Unit) that encodes input sentences into context vectors.
2. **Decoder:** Another GRU that generates translated sentences from the context vector.
3. **Attention Mechanism:** Allows the decoder to focus on specific parts of the input sentence while translating.

### 🔹 **Key Components**
- **`Vocab` class** → Builds word-to-index mappings.
- **`Encoder` class** → Encodes input sequences using GRU.
- **`Decoder` class** → Decodes the encoded vectors.
- **`Attention` module** → Computes alignment scores between encoder and decoder states.

---

## 🏋️‍♂️ Training & Evaluation
### 🔹 **Training Procedure**
- Use **cross-entropy loss** for optimization.
- Employ **teacher forcing** to speed up training.
- Monitor **loss trends** and adjust hyperparameters accordingly.

### 🔹 **Evaluation Metrics**
- BLEU Score (Bilingual Evaluation Understudy)
- Translation quality analysis through sample outputs.

---

## 🚀 How to Run the Notebook
### 📦  **Dependencies**
Before running the notebook, install the required Python libraries:
```bash
pip install torch torchvision torchaudio numpy pandas matplotlib nltk
