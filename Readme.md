# 🔧 Log Classification using a Hybrid System

This is a basic log classification project that combines three methods to handle different types of log messages — from simple and predictable ones to complex or unlabeled ones.

We upload a log file (in CSV format) through a FastAPI backend, and it returns a classified version of the file.

---

## 🧠 How It Works

This system uses three different techniques:
- **Regex** — for basic, predictable log formats using predefined patterns.
- **Sentence Transformer + Logistic Regression** — for classifying logs when you have enough labeled training data.
- **LLM (Large Language Models)** — for complex logs when there's very little or no labeled data available.

Each method handles logs depending on how structured or ambiguous the text is.

---

## 📁 Project Structure

- `training/` → Code for regex and model training (Sentence Transformer + Logistic Regression)
- `models/` → Stores saved model files and embeddings
- `resources/` → Includes images, sample CSVs, and output files
- `server.py` → FastAPI app for receiving and processing uploaded log files

---

## 🛠️ Setup Instructions

### 1. Install dependencies
Make sure you have Python installed, then run:

```bash
pip install -r requirements.txt

