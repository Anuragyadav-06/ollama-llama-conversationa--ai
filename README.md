
# 🤖 LLaMA Conversational AI — Local Chatbot with Ollama

A fully **local**, **privacy-first** conversational AI assistant powered by Meta's LLaMA model via Ollama. No cloud APIs. No data leaves your machine. Just fast, intelligent conversation — running entirely on your hardware.

---

## 🚀 Demo

<img width="1372" height="1046" alt="image" src="https://github.com/user-attachments/assets/1f38383a-e893-4fbf-9eb0-834d5a1b4868" />


![Demo](assets/demo.gif)

---

## 🧠 How It Works

```
User Input
    ↓
Python App
    ↓
Ollama REST API  (/api/chat)
    ↓
LLaMA Model (running locally)
    ↓
Streamed Response (JSON chunks)
    ↓
Assembled Reply → User
```

The app maintains full conversation history in memory (as a list of `role: user / role: assistant` message objects), sending the entire context window to Ollama on every turn — this is what gives the chatbot memory across a conversation.

---

## ✨ Features

- 🏠 **100% Local** — No internet required after setup. Your conversations never leave your machine
- 💬 **Multi-turn Memory** — Maintains full conversation context across the entire session
- ⚡ **Streaming Responses** — Real-time token-by-token output, parsed from Ollama's JSON stream
- 🔧 **Configurable** — Easily swap LLaMA model versions (llama3, llama2, mistral, etc.)
- 🐍 **Pure Python** — No heavy frameworks, minimal dependencies

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3.10+ |
| LLM Backend | [Ollama](https://ollama.ai) |
| Model | Meta LLaMA (llama3 / llama2) |
| API | Ollama REST API (`/api/chat`) |
| Response Handling | JSON streaming |

---

## 📦 Setup & Installation

### Prerequisites
- Python 3.10+
- [Ollama](https://ollama.ai) installed and running

### Step 1 — Install Ollama
```bash
# macOS / Linux
curl -fsSL https://ollama.ai/install.sh | sh

# Pull the LLaMA model
ollama pull llama3
```

### Step 2 — Clone the repo
```bash
git clone https://github.com/Anuragyadav-06/ollama-llama-conversationa--ai.git
cd ollama-llama-conversationa--ai
```

### Step 3 — Install Python dependencies
```bash
pip install -r requirements.txt
```

### Step 4 — Run the chatbot
```bash
python chatbot/app.py
```

---

## 💬 Example Conversation

```
You: What is machine learning?
Assistant: Machine learning is a branch of AI where systems learn patterns
from data to make predictions or decisions without being explicitly
programmed for each task...

You: Give me a real-world example.
Assistant: Sure! A great example is email spam detection. The model
is trained on thousands of emails labelled "spam" or "not spam"...
```

---

## 🔧 Configuration

You can configure the model and parameters inside `chatbot/app.py`:

```python
MODEL = "llama3"        # Change to llama2, mistral, codellama etc.
TEMPERATURE = 0.7       # Higher = more creative, Lower = more focused
MAX_CONTEXT = 10        # Number of previous messages to keep in memory
```

---

## 📂 Project Structure

```
ollama-llama-conversationa--ai/
│
├── chatbot/
│   └── app.py          # Main chatbot application
├── requirements.txt    # Python dependencies
├── README.md
└── LICENSE
```

---

## 🔮 Future Improvements

- [ ] Web UI using Streamlit or Gradio
- [ ] Persistent conversation history (save/load sessions)
- [ ] RAG (Retrieval-Augmented Generation) — chat with your own documents
- [ ] Voice input / output support
- [ ] Multi-model switching from the UI

---

## 👨‍💻 Author

**Anurag Yadav**  
B.Sc Data Science | AI & ML Enthusiast  
📍 Mumbai, Maharashtra

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/anurag-yadav-93216b314/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/Anuragyadav-06)

---

## ⭐ If you found this useful, give it a star!

> **Disclaimer:** This project is for educational and research purposes. LLaMA models are subject to Meta's usage policies.
