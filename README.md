**🧠 Local Retrieval-Augmented Generation (RAG) System with LLaMA 3.2**
Built by Sagar Naduvinkeri

**📌 **Overview****
This project demonstrates how to build a local Retrieval-Augmented Generation (RAG) system that allows natural language querying over custom documents without writing SQL. Using LLaMA 3.2, HuggingFace embeddings, and ChromaDB, we create a lightweight yet powerful system that enhances language model responses with domain-specific document context.

**🔍 Problem Statement**
Traditional LLMs lack access to real-time, proprietary, or niche knowledge unless fine-tuned or augmented. This project solves that by enabling contextual question answering via local document embedding and retrieval.

**⚙️ Technologies Used**
LLaMA 3.2 via Ollama

HuggingFace Sentence Transformers

ChromaDB for vector storage and retrieval

Python (venv environment)

transformers, accelerate, sentence-transformers

(Optional) Phi model for benchmarking

Prompt engineering using PromptTemplate

**📂 Project Structure**
bash
Copy
Edit
.
├── ragrun.py                  # Main script to run RAG queries
├── chroma_db/                 # Folder storing persisted vector database
├── knowledge_docs/            # Input PDFs or documents for embedding
├── persistent_client.py       # Persistent client for querying system
├── snapshots/                 # Screenshots and outputs for documentation
├── README.md                  # This file
└── requirements.txt           # Python dependencies
**🛠️ Setup Instructions**
Create a virtual environment:

bash
Copy
Edit
python -m venv rag_env
source rag_env/bin/activate  # On Windows use rag_env\Scripts\activate
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Start Ollama & LLaMA model:

bash
Copy
Edit
ollama run llama3
Run the script:

bash
Copy
Edit
python ragrun.py
**📚 How It Works**
Documents are embedded using HuggingFace transformers.

ChromaDB stores the vectors.

When a user types a query, the top-k similar document chunks are retrieved.

These chunks are appended as context for the LLaMA model to generate an informed response.

**💡 Key Learnings**
Importance of managing dependencies in virtual environments.

Debugging LLM setup issues (e.g., init_empty_weights error).

Fine-tuning context memory vs. performance trade-offs.

Using prompt engineering to refine LLM responses.

**🧪 Sample Queries & Outputs**
“What topics does this class cover?” → Initially blank, later populated after adding the syllabus PDF to knowledge base.

“Where is University at Buffalo?” → Quick response.

“Who is the mascot of University at Buffalo?” → Answer with source reference from uploaded content.

Added a custom PromptTemplate for better response structuring.

**⚠️ Known Issues**
Some models (e.g., Phi) time out on large context prompts.

High latency observed with larger knowledge bases.

**🚀 Future Improvements**
Add GUI with Streamlit or Gradio

Enable multi-file indexing and file upload via WebUI

Integrate document chunking and ranking strategies for better precision
