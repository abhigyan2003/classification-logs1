# Log Classification using a Hybrid System

This is a basic log classification project that combines three methods to handle different types of log messages — from simple and predictable ones to complex or unlabeled ones.

We upload a log file (in CSV format) through a FastAPI backend, and it returns a classified version of the file.

---

##  How It Works

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

## 🛠️ Instructions

### 1. Install dependencies

```bash
pip install -r requirements.txt
   ```
### 2. **Run the FastAPI Server**:
   To start the server, use the following command:

   ```bash
   uvicorn server:app --reload
   ```

   Once the server is running, you can access the API at:
   - `http://127.0.0.1:8000/` (Main endpoint)
   - `http://127.0.0.1:8000/docs` (Interactive Swagger documentation)
     
### 3. **How to use?**
   Upload a CSV file containing logs to the FastAPI endpoint for classification. Ensure the file has the following columns:
- `source`
- `log_message`

The output will be a CSV file with an additional column `target_label`, which represents the classified label for each log entry.
