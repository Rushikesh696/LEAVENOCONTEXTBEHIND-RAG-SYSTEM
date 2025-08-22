# 💡 Leave No Context Behind: A RAG System Powered by Infini-Attention Paper

> 🧠 A Retrieval-Augmented Generation (RAG) system built using LangChain and Hugging Face models to answer questions based on Google’s **"Leave No Context Behind"** paper (April 2024).

---

---

## ⚙️ Tech Stack

| Component       | Description                                      |
|----------------|--------------------------------------------------|
| LangChain   | Framework to build LLM-powered chains            |
| Hugging Face | Models for embedding + generation                |
| Chroma       | Vector store to persist and query embeddings     |
| Flan-T5      | Instruction-tuned text generation model          |
| Sentence Transformers | Embedding model for semantic search     |
| PDFLoader    | Extracts content from research paper (PDF)       |

---

## 🧰 Features

- 🔍 **Semantic Search** over the full paper using ChromaDB
- 🧠 **Custom Prompt Templates** to improve generation quality
- 📝 **Synthesized Answers**, not just copy-paste
- 📊 Handles both technical and architectural queries
- 🔄 Modular: Easily swap in other documents, LLMs, or embeddings

---

##  Overview

Large Language Models (LLMs) like Gemini or GPT often lack access to private or domain-specific information. However, critical insights are often hidden in PDFs, documents, and research papers. This project solves that problem by building a **RAG pipeline** that:

Ingests and processes the paper “Leave No Context Behind”  
Stores semantic chunks in a vector database  
Retrieves relevant context for a given query  
Synthesizes accurate, context-aware answers using an LLM

---

## 🧪 Based On:  
📄 [Leave No Context Behind — Google Research Paper (April 2024)](https://arxiv.org/pdf/2404.07143.pdf)  
📚 Focus: **Infini-attention**, a plug-and-play long-context Transformer architecture  



