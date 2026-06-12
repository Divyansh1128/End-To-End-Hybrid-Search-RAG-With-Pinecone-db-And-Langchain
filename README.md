# 🔍 Hybrid Search RAG System (Vector + Keyword Search)

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![LangChain](https://img.shields.io/badge/LangChain-Integration-green)
![Pinecone](https://img.shields.io/badge/Pinecone-VectorDB-lightgrey)
![LLM](https://img.shields.io/badge/GenAI-LLM-orange)

## 📌 Project Overview
This project implements an advanced **Retrieval-Augmented Generation (RAG)** pipeline using **Hybrid Search**. By combining traditional keyword-based search (sparse vectors) with semantic vector search (dense embeddings), this system drastically improves document retrieval accuracy and significantly reduces LLM hallucinations.

The pipeline utilizes **Reciprocal Rank Fusion (RRF)** to seamlessly merge the results of both search methodologies before passing the optimized context to the generative model.

## 🚀 Key Features
*   **Hybrid Retrieval System:** Combines the exact keyword matching of BM25 (sparse) with the contextual understanding of semantic embeddings (dense).
*   **Reciprocal Rank Fusion (RRF):** An algorithmic approach to rerank and fuse results from multiple search queries, ensuring the highest quality context is retrieved.
*   **Pinecone DB Integration:** Utilizes Pinecone as a highly scalable cloud vector database for fast, low-latency dense and sparse vector storage.
*   **LangChain Orchestration:** Streamlined data ingestion, chunking, and LLM chain execution using the LangChain framework.

## 🛠️ Tech Stack
*   **Framework:** LangChain
*   **Vector Database:** Pinecone DB (Serverless)
*   **Language Models:** OpenAI API / Hugging Face (Embeddings & Generation)
*   **Language:** Python
*   **UI/Frontend:** Streamlit (Optional for interacting with the agent)

## 🏗️ Architecture Workflow
1.  **Data Ingestion:** Documents are loaded and split into manageable chunks using LangChain's `RecursiveCharacterTextSplitter`.
2.  **Embedding Generation:** Text chunks are converted into dense embeddings (e.g., HuggingFace/OpenAI) and sparse vectors (e.g., Splade/BM25).
3.  **Vector Storage:** Both sparse and dense vectors are upserted into a Pinecone Hybrid index.
4.  **Querying:** User queries are vectorized and searched against the Pinecone DB using both semantic meaning and keyword relevance.
5.  **RRF Fusion:** The retrieved documents from both search types are ranked and fused using the RRF algorithm.
6.  **Generation:** The optimized, highly relevant context is passed to the LLM to generate an accurate, hallucination-free response.

## ⚙️ Installation and Setup

1. **Clone the repository:**
```bash
   git clone [https://github.com/Divyansh1128/Hybrid-Search-RAG.git](https://github.com/Divyansh1128/Hybrid-Search-RAG.git)
   cd Hybrid-Search-RAG
