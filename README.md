**Step 1**:
#  HackRx AI Insurance Query System

### 📄 Overview
HackRx AI is an intelligent insurance document analysis and query system that uses **semantic search** and **large language models (LLMs)** to understand and respond to complex insurance-related queries.  

It enables users to ask natural-language questions (e.g., _"Does this policy cover maternity expenses?"_) and instantly receive contextual, policy-based answers with justifications extracted from real policy PDFs.

---

## ⚙️ Features

✅ **Multi-policy support** – Works with multiple insurance documents (health, travel, maternity, etc.)  
✅ **Semantic Search** – Uses FAISS and Sentence Transformers for vector-based retrieval  
✅ **AI Decision Engine** – Uses an LLM to generate natural, accurate responses  
✅ **FastAPI Backend** – Lightweight REST API for real-time querying  
✅ **Containerized Deployment** – Runs seamlessly in Docker  
✅ **Pre-trained Embeddings** – Speeds up startup using precomputed vector files  

---

## 🗂️ Project Structure

📦 HackRx/
├── app/
│ ├── data/
│ │ ├── hackrx-1.pdf # Bajaj Allianz Global Health Care
│ │ ├── hackrx-2.pdf # Cholamandalam Travel Insurance
│ │ ├── hackrx-3.pdf # Edelweiss Well Baby Well Mother
│ │ ├── hackrx-4.pdf # HDFC ERGO Easy Health
│ │ ├── hackrx-5.pdf # ICICI Lombard Golden Shield
│ │ ├── chunks.csv # Generated text chunks
│ │ ├── embeddings.npy # Precomputed embeddings
│ │ ├── faiss_index.idx # FAISS semantic index
│ │ ├── metadata.pkl # Chunk metadata
│ │ └── texts.pkl # Raw chunk texts
│ ├── utils/ # Helper modules
│ │ ├── pdf_parser.py # Extracts text from PDFs
│ │ ├── embedder.py # Embedding model wrapper
│ │ ├── search.py # Semantic search logic
│ │ └── llm_decider.py # AI response generator
│ └── models/schema.py # Request/response models
│
├── main.py # FastAPI backend
├── generate_chunks.py # Step 1: Extract chunks from PDFs
├── precompute_embeddings.py # Step 2: Generate embeddings + FAISS
├── requirements.txt # Python dependencies
├── Dockerfile # Docker build instructions
├── .dockerignore # Ignored files for Docker builds
└── README.md # Project documentation


---

## 🧠 Workflow

| Step | Script | Purpose |
|------|--------|----------|
| 1️⃣ | `generate_chunks.py` | Extracts text from all policy PDFs into chunks |
| 2️⃣ | `precompute_embeddings.py` | Generates embeddings, builds FAISS index |
| 3️⃣ | `main.py` | Runs FastAPI server to handle user queries |
| 4️⃣ | `Dockerfile` | Containerizes the app for deployment |
| 5️⃣ | `.dockerignore` | Excludes unnecessary files in Docker builds |

---

## 🧩 Installation

### 🪶 Prerequisites
- Python 3.9+
- pip
- (Optional) Docker

### 🧱 Step 1: Clone the Repo
```bash
git clone https://github.com/<your-username>/HackRx.git
cd HackRx


**Step 2**: Install Dependencies
pip install -r requirements.txt

**Step 3**: Add Environment Variables

Create a .env file in your root directory:

API_KEY=your_secret_api_key

**Step 4**: Generate Data (Optional if already included)

If you haven’t precomputed the embeddings yet:

python generate_chunks.py
python precompute_embeddings.p
