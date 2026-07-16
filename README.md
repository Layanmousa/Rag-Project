# RAG-Based Question Answering System using FLAN-T5

> A Retrieval-Augmented Generation (RAG) system that retrieves relevant information from the ISO/IEC 27001:2022 document and generates document-grounded answers using Google's FLAN-T5 model.

---

# Table of Contents

- Project Overview
- Problem Statement
- Project Objectives
- Knowledge Source
- Technologies Used
- System Architecture
- Project Workflow
- RAG Pipeline
- Embedding Model
- Vector Database
- Retrieval Process
- Language Model
- Prompt Construction
- Question Categories
- Project Structure
- Installation
- How to Run
- Results
- Strengths
- Limitations
- Future Improvements
- Conclusion
- Author

---

# Project Overview

This project implements a complete Retrieval-Augmented Generation (RAG) pipeline for document-based question answering.

Instead of relying only on the language model's internal knowledge, the system retrieves the most relevant information from a PDF document before generating an answer.

The knowledge source used in this project is:

**ISO/IEC 27001:2022 – Information Security Management Systems Requirements**

The pipeline performs the following tasks:

- Load a PDF document
- Extract document text
- Clean the extracted text
- Split the text into overlapping chunks
- Generate sentence embeddings
- Store embeddings inside ChromaDB
- Retrieve the most relevant chunks
- Generate the final answer using FLAN-T5

---

# Problem Statement

Large Language Models may produce unsupported answers when they do not have access to external knowledge.

Retrieval-Augmented Generation solves this issue by retrieving relevant information from a document before answer generation, reducing hallucination and improving answer quality.

---

# Project Objectives

- Build a complete RAG pipeline.
- Retrieve document-based information.
- Reduce hallucination.
- Generate accurate answers using retrieved context.
- Demonstrate semantic retrieval using embeddings.

---

# Knowledge Source

- ISO/IEC 27001:2022 PDF

---

# Technologies Used

- Python
- Jupyter Notebook
- PyPDF
- Sentence Transformers
- ChromaDB
- Hugging Face Transformers
- FLAN-T5
- NumPy

---

# System Architecture

```text
PDF
 ↓
Text Extraction
 ↓
Chunking
 ↓
Embeddings
 ↓
ChromaDB
 ↓
Similarity Search
 ↓
Retrieved Context
 ↓
FLAN-T5
 ↓
Generated Answer
```

---

# RAG Pipeline

1. Load PDF
2. Extract Text
3. Clean Text
4. Chunk Text
5. Generate Embeddings
6. Store in ChromaDB
7. Retrieve Top-3 Chunks
8. Generate Answer

---

# Embedding Model

```
all-MiniLM-L6-v2
```

Embedding Dimension:

```
384
```

---

# Vector Database

The project stores document embeddings using **ChromaDB**.

For each question:

- Convert question to embedding.
- Perform similarity search.
- Retrieve the three most relevant chunks.
- Send retrieved context to FLAN-T5.

---

# Retrieval Process

```python
results = collection.query(
    query_texts=[question],
    n_results=3
)
```

---

# Language Model

```
google/flan-t5-base
```

The retrieved context and the user question are combined into a prompt before generation.

---

# Prompt Construction

```text
Context:
...

Question:
...

Answer:
```

---

# Question Categories

The project evaluates three types of questions:

- Available Questions
- Detailed Questions
- Unavailable Questions

---

# Project Structure

```text
RagProject/
│
├── RagProject1_.ipynb
├── ISO_IEC_27001_2022.pdf
├── README.md
└── requirements.txt
```

---

# Installation

```bash
git clone https://github.com/Layanmousa/Rag-Project.git

cd Rag-Project

pip install pypdf sentence-transformers chromadb transformers torch sentencepiece
```

---

# How to Run

1. Open the notebook.
2. Run all cells in order.
3. Enter a question.
4. Retrieve the most relevant chunks.
5. Generate the final answer.

---

# Results

The project successfully:

- Extracted PDF text.
- Created semantic embeddings.
- Stored vectors in ChromaDB.
- Retrieved relevant document sections.
- Generated document-based answers using FLAN-T5.

---

# Strengths

- End-to-end RAG pipeline.
- Semantic retrieval.
- Modular implementation.
- Easy to extend.
- Suitable for document question answering.

---

# Limitations

- Fixed-size chunking.
- CPU inference can be slow.
- Performance depends on retrieval quality.

---

# Future Improvements

- Semantic Chunking
- Late Chunking
- Hybrid Search
- Better Prompt Engineering
- Streamlit Interface
- FastAPI Deployment
- Source Citation
- Retrieval Evaluation Metrics

---

# Conclusion

This project demonstrates how Retrieval-Augmented Generation improves document-based question answering by combining semantic retrieval with a pretrained language model.

The retrieved document context helps the model generate more reliable and grounded answers than relying solely on pretrained knowledge.

---

# Author

**Layan Mousa**
