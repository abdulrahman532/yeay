````markdown
# 🩺 Medical Assistant Chatbot

This is a simple AI-powered medical chatbot that uses retrieval-augmented generation (RAG) to answer user queries based on a medical reference document.

## 🚀 Features

- Chat interface with session-based chat history
- Context-aware responses using FAISS vector store
- Automatic chat title generation
- Built with **Streamlit** and **FastAPI**
- Embedding powered by `sentence-transformers/all-MiniLM-L6-v2`
- RAG from the book *"Where There Is No Doctor"*

## 🧠 Tech Stack

- Python
- Streamlit (frontend)
- FastAPI (backend)
- LangChain
- HuggingFace Sentence Transformers
- FAISS for vector storage
- Together AI for LLM API access

## 📂 Project Structure

- `main.py` — Streamlit app for user interaction
- `api.py` — FastAPI backend that handles retrieval and LLM responses
- `rag.py` — Preprocessing script to load PDF and build FAISS index

## ⚙️ Setup & Run

1. **Install dependencies:**

```bash
pip install streamlit fastapi uvicorn langchain[all] sentence-transformers python-dotenv together
````

2. **Download the reference book (PDF):**

Place `14.DavidWerner-WhereThereIsNoDoctor.pdf` in the project directory.

3. **Run `rag.py` to build the FAISS index:**

```bash
python rag.py
```

4. **Start the FastAPI backend:**

```bash
uvicorn api:app --reload
```

5. **Run the Streamlit frontend:**

```bash
streamlit run main.py
```

## ⚠️ Disclaimer

This application is intended for **educational and reference purposes only**. It does **not** provide medical advice, diagnosis, or treatment.

## 👥 Authors

* \[Your Team Name or Members]



```
```
