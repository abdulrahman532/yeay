##🩺 AI Medical Assistant Chatbot

An AI-powered medical chatbot that provides general health information by combining document retrieval (RAG) with a powerful LLM. It uses LangChain, FAISS, and Together.ai's LLaMA 3.3 70B to answer questions based on real medical documents like Where There Is No Doctor.
🔧 Tech Stack
Component	Tool/Library
UI	Streamlit
Backend	FastAPI
Vector Search	LangChain + FAISS
Embedding	Hugging Face: all-MiniLM-L6-v2
LLM	Together AI: meta-llama/Llama-3.3-70B-Instruct
Document	Where There Is No Doctor (PDF)
✅ Features

    Ask health-related questions

    Retrieves info from real medical books (RAG)

    Auto-generates descriptive titles for each conversation

    Stores and manages chat history per session

    Basic name memory for a more personal experience

⚠️ Disclaimer

    This app is not a replacement for medical professionals. It is for informational and educational purposes only.

🚀 Setup Instructions
1. Clone the Repository

git clone https://github.com/yourusername/ai-medical-chatbot.git
cd ai-medical-chatbot

2. Create a Virtual Environment

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

3. Install Requirements

pip install -r requirements.txt

4. Prepare the FAISS Vector Index

Put the Where There Is No Doctor PDF in the project directory and run:

python rag.py

This will create and save the FAISS index in ./faiss_index/.
5. Set Environment Variables

Create a .env file in the root with your Together.ai key:

TOGETHER_API_KEY=your_together_api_key

6. Run the Backend API (FastAPI)

uvicorn backend:app --reload

Ensure your FastAPI backend is running on:
📍 http://127.0.0.1:8000/llm/
7. Run the Chat UI (Streamlit)

In another terminal:

streamlit run app.py

📂 File Structure

.
├── app.py                  # Streamlit frontend
├── backend.py              # FastAPI backend with LLM logic
├── rag.py                  # Script to load/process the medical PDF and build FAISS index
├── faiss_index/            # Saved FAISS index files
├── 14.DavidWerner-WhereThereIsNoDoctor.pdf  # Source document
├── requirements.txt
└── .env                    # API keys (not committed)

🧠 How It Works

    User Input → via Streamlit

    FastAPI backend receives query

    FAISS searches for top 3 relevant chunks from medical PDF

    Together AI LLaMA model receives prompt: retrieved context + user query

    Answer is returned and stored in session with optional title

🔒 Security Note

Never expose your .env or API keys in public repos. Use .gitignore to exclude them:

.env
faiss_index/

🙋‍♀️ Future Improvements

Multi-user persistent chat storage

Chat context memory

More medical books / multilingual PDFs

Live deployment (Render / HuggingFace Spaces / Docker)

Voice input/output support
