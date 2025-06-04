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
