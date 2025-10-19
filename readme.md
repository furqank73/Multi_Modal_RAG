# Multi Modal RAG for PDFs (Text & Images)

This repository implements a **Multimodal Retrieval-Augmented Generation (RAG)** pipeline capable of extracting and retrieving **both text and images** from PDF documents. It uses the Unstructured library for PDF parsing and LangChain to build a hybrid retrieval workflow that enhances large-language-model responses with grounded context from your documents.

---

## 🚀 Features

* Extracts **text content** from PDFs (headings, paragraphs, tables, etc.).
* Extracts **embedded images** (charts, figures, diagrams) and treats them as retrievable content.
* Builds separate embeddings (or unified embeddings) for **text + image** modalities.
* Supports **multimodal retrieval**: when a query relates to text or image, you get relevant context from either.
* Uses LangChain’s loaders, vector stores and retrieval chains for rapid prototyping.
* Configurable and modular — you can swap out embedding models, vector-stores, or retrieval strategies.

---

## 🧰 Tech Stack

* **Python** – core implementation language
* Unstructured – for parsing PDFs (text + images)
* LangChain – for document loaders, vector stores, retrieval chains
* Vector store (e.g., FAISS, Chroma) – for embedding storage & retrieval
* Embedding models (e.g., from OpenAI, Hugging Face) – for text & image embedding
* Base64 or other encoding – for image conversion and embedding storage
* Jupyter Notebook – demonstration and interactive exploration

---

## 📁 Repository Structure

```
/Multi_Modal_RAG
│   README.md
│   requirements.txt
│   .env         ← secret keys, config
│
└── content/
    └── langchain_multimodal.ipynb   ← interactive notebook
```

---

## 🧭 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/furqank73/Multi_Modal_RAG.git
cd Multi_Modal_RAG
```

### 2. Setup environment

* Create a Python virtual environment:

  ```bash
  python3 -m venv venv
  source venv/bin/activate   # (on Windows: venv\Scripts\activate)
  ```
* Install dependencies:

  ```bash
  pip install -r requirements.txt
  ```

### 3. Configure environment variables

Create a `.env` file in the project root with your secrets and config, for example:

```dotenv
OPENAI_API_KEY=your_openai_key
EMBEDDING_MODEL=text-embedding-xyz
IMAGE_EMBEDDING_MODEL=vision-embedding-xyz
VECTOR_STORE_PATH=./vector_store
```

### 4. Run the interactive notebook

Open `content/langchain_multimodal.ipynb` in Jupyter Notebook or JupyterLab and run through the steps:

* Load a PDF (or multiple PDFs)
* Extract text + images using Unstructured
* Embed text and images
* make summaries of text and images and emmbed it
* Build a vector store
* Perform queries (text-only, image-only, or mixed)
* Retrieve relevant chunks and generate answers via an LLM

---

## 🎯 Use Cases

* Research papers that include both text and figures — ask questions like *“What does Figure 2 show?”*
* Corporate reports with charts and textual analysis — retrieve context for both modality types.
* Manuals, product catalogs, or scanned documents with mixed content — make them searchable.

---