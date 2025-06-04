# 🔍 Hybrid Log Classification System

![Python](https://img.shields.io/badge/python-3.7%2B-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-0.68.0-green)
![License](https://img.shields.io/badge/license-MIT-orange)

An intelligent log classification tool that automatically categorizes computer logs using three complementary AI approaches.

## Table of Contents
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Quick Start](#-quick-start)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Example](#-example)
- [API Documentation](#-api-documentation)
- [Contributing](#-contributing)
- [License](#-license)

## 🌟 Features

- **Multi-method classification** (Regex, Sentence Transformer, LLM)
- **Simple CSV input/output** format
- **Built-in API documentation** (Swagger UI)
- **Local processing** - Your data never leaves your machine
- **Customizable** classification rules

## 🧠 How It Works

The system intelligently routes each log message through the most appropriate classification method:

```mermaid
graph TD
    A[Incoming Log] --> B{Simple Pattern?}
    B -->|Yes| C[Regex Classification]
    B -->|No| D{Enough Training Data?}
    D -->|Yes| E[Sentence Transformer + Logistic Regression]
    D -->|No| F[LLM Classification]
    C --> G[Output Label]
    E --> G
    F --> G


Installation
bash
git clone https://github.com/yourusername/classification-logs1.git
cd classification-logs1
pip install -r requirements.txt
Launch the Server
bash
uvicorn server:app --reload
📊 Usage
Prepare your log file as CSV with columns:

csv
source,log_message
server1,Error 404: File not found
server2,Connection timeout after 30s
Access the interactive docs:
http://localhost:8000/docs

Upload your file using the /classify endpoint

Download results with new target_label column

📁 Project Structure
.
├── training/           # Model training scripts
│   ├── regex_rules.py  # Predefined patterns
│   └── train_model.py  # Sentence Transformer training
├── models/             # Saved models
├── resources/          # Example files
├── server.py           # FastAPI server
├── classify.py         # Classification orchestrator
├── processor_bert.py   # Sentence Transformer processor
├── processor_llm.py    # LLM processor
├── processor_regex.py  # Regex processor
└── requirements.txt    # Dependencies
💡 Example
Input:

csv
source,log_message
auth_server,Login failed for user admin
db_server,Query timeout (3000ms)
Output:

csv
source,log_message,target_label
auth_server,Login failed for user admin,auth_failure
db_server,Query timeout (3000ms),db_timeout
📚 API Documentation
When the server is running, access:

Interactive docs: http://localhost:8000/docs

Alternative docs: http://localhost:8000/redoc

🤝 Contributing
Fork the repository

Create your feature branch (git checkout -b feature/your-feature)

Commit your changes (git commit -m 'Add some feature')

Push to the branch (git push origin feature/your-feature)

Open a Pull Request
