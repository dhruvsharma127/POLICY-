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

**Step 2**: Install Dependencies
pip install -r requirements.txt

**Step 3**: Add Environment Variables

Create a .env file in your root directory:

API_KEY=your_secret_api_key

**Step 4**: Generate Data (Optional if already included)

If you haven’t precomputed the embeddings yet:

python generate_chunks.py
python precompute_embeddings.p
