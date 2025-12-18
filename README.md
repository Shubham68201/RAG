📚 RAG System with FAISS + Sentence Transformers + Groq LLM

A Retrieval-Augmented Generation (RAG) system that loads documents from multiple formats, creates vector embeddings using Sentence Transformers, stores them in FAISS, and generates answers using Groq LLM.

🚀 Features

📂 Load documents from PDF, TXT, CSV, Excel, Word, JSON

✂️ Smart text chunking using LangChain splitters

🔢 Embeddings via all-MiniLM-L6-v2

⚡ Fast vector search with FAISS

🧠 Answer generation using Groq LLM

🔁 Persistent vector store (build once, reuse later)

🛡️ Safe FAISS loading (no crashes on first run)

🏗️ Project Structure
RAG/
│
├── app.py                     # Entry point
├── README.md
├── data/                       # Input documents
│
├── faiss_store/                # Saved FAISS index
│   ├── faiss.index
│   └── metadata.pkl
│
└── src/
    ├── __init__.py
    ├── data_loader.py          # Load documents
    ├── embedding.py            # Chunking & embeddings
    ├── vectorstore.py          # FAISS vector store
    └── search.py               # RAG logic (retrieve + LLM)

🧰 Tech Stack

Python 3.9+

LangChain

Sentence Transformers

FAISS

Groq LLM

dotenv

🔑 Environment Setup
1️⃣ Create Virtual Environment
python -m venv .venv
source .venv/bin/activate   # Linux / Mac
.venv\Scripts\activate      # Windows

2️⃣ Install Dependencies
pip install -r requirements.txt


Example requirements.txt:

langchain
langchain-community
langchain-groq
sentence-transformers
faiss-cpu
python-dotenv
unstructured
pypdf
docx2txt
openpyxl

3️⃣ Set Groq API Key

Create a .env file:

GROQ_API_KEY=your_groq_api_key_here

📥 Add Your Documents

Place your files inside the data/ directory.

Supported formats:

.pdf

.txt

.csv

.xlsx

.docx

.json

▶️ Run the Application
python app.py

🔁 How It Works
First Run

Loads documents from data/

Splits text into chunks

Generates embeddings

Saves FAISS index to disk

Next Runs

Loads FAISS index directly

Skips re-embedding

Faster startup 🚀

💬 Example Query
query = "What is attention mechanism?"

Output:
Summary: Attention mechanism allows a model to focus on relevant parts of input...

🛡️ Safe FAISS Loading

The system checks if FAISS files exist before loading:

if not store.load():
    store.build_from_documents(docs)


No crashes on first run ✅

🧠 Future Improvements

🔍 MMR (Max Marginal Relevance) search

📚 Source citations

🔄 Hybrid BM25 + FAISS retrieval

🌐 FastAPI backend

🧵 Streaming LLM responses

🖥️ Web UI (Streamlit)

📄 License

This project is for learning and experimentation purposes.
You may extend and adapt it freely.

🙌 Acknowledgements

FAISS by Meta

Sentence Transformers

LangChain

Groq LLM
