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
