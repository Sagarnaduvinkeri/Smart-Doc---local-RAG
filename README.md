**🧠 Local Retrieval-Augmented Generation (RAG) System using LLaMA 3.2, HuggingFace, and ChromaDB**

Developed by Sagar Naduvinkeri

**📌 Overview**

This project implements a local Retrieval-Augmented Generation (RAG) architecture that enables natural language querying over custom documents—no SQL needed. It uses the LLaMA 3.2 model from Ollama, HuggingFace sentence embeddings, and ChromaDB for vector storage and retrieval.

This setup allows you to ask context-aware questions that are answered using your own knowledge base (e.g., PDFs or text files).

**🔍 Problem Statement**

Traditional LLMs lack access to real-time, proprietary, or niche knowledge unless fine-tuned or augmented. This project solves that by enabling contextual question answering via local document embedding and retrieval.

📂 **Project Structure**

├── `ragcreate.py` – Script to create and persist vector DB from documents  
├── `ragrun.py` – Script to query the knowledge base with LLaMA + Chroma  
├── `chroma_db/` – Auto-generated ChromaDB directory storing embeddings  
├── `knowledge_docs/` – Folder containing PDFs or text files used as knowledge base  
├── `README.md` – Project documentation (this file)  
└── `requirements.txt` – Python dependencies  


**⚙️ Tech Stack**

🧠 **LLM**: LLaMA 3.2 via Ollama

📚 **Embedding**: HuggingFace (sentence-transformers)

🗃️ **Vector DB:** ChromaDB

🐍 **Environment**: Python 3.10+ with virtualenv

**🚀 Setup Instructions**

1. Clone the Repository

**2. Set Up Python Virtual Environment**

python
Copy
Edit
# Create a virtual environment
python -m venv venv

# Activate the environment
source venv/bin/activate       # Windows: venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt

**3. Start the LLaMA Model with Ollama**

# Make sure Ollama is installed
ollama run llama3

**4. Prepare the Knowledge Base**

# Place your documents (PDF or TXT) into the 'knowledge_docs/' folder
# Then run the following script to embed and store vectors in ChromaDB
python ragcreate.py

🔹 This will:

Load and embed your documents

Persist the vectors into the chroma_db/ folder

**5. Ask Questions via the RAG System**

# Run this to start querying the knowledge base
python ragrun.py

💬 **Sample Queries**

Examples of questions you can ask after loading your documents:

“What are the topics covered in the syllabus?”

“Summarize key points from document X.”

“What is the University at Buffalo known for?”

The system uses ChromaDB to find contextually relevant chunks and feeds them into LLaMA to generate precise, natural-language responses.

✅**Features**

🔍 **Natural language querying over local files**

🧠 **Context-aware responses powered by LLaMA**

📦 **Local vector storage with ChromaDB (no cloud dependency)**

🧪 **Prompt engineering using PromptTemplate for enhanced precision**

💾 **Modular code split into creation (ragcreate.py) and querying (ragrun.py)**

**🛠️ Troubleshooting**

Model errors? Make sure transformers, accelerate, and sentence-transformers are updated.

Slow response? Large knowledge bases increase retrieval latency.

Vector index issues? Delete and regenerate chroma_db/ using ragcreate.py.

**🧠 Key Learnings**

The importance of managing dependencies with a virtual environment.

How to build scalable, modular architectures for RAG-based LLMs.

Understanding trade-offs between precision, speed, and memory usage.

**📌 Future Improvements**

Add Web UI using Streamlit or Gradio

Support for real-time file uploads

Use of chunking and ranking strategies for large corpora

Add logging and response traceability




