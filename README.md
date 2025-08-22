# Leave No Context Behind: A RAG System Powered by Infini-Attention Paper

>  A Retrieval-Augmented Generation (RAG) system built using LangChain and Hugging Face models to answer questions based on Google’s **"Leave No Context Behind"** paper (April 2024).

---

---

### Tech Stack

| Component       | Description                                      |
|----------------|--------------------------------------------------|
| LangChain   | Framework to build LLM-powered chains            |
| Hugging Face | Models for embedding + generation                |
| Chroma       | Vector store to persist and query embeddings     |
| Flan-T5      | Instruction-tuned text generation model          |
| Sentence Transformers | Embedding model for semantic search     |
| PDFLoader    | Extracts content from research paper (PDF)       |

---

## Features

- **Semantic Search** over the full paper using ChromaDB
- **Custom Prompt Templates** to improve generation quality
- **Synthesized Answers**, not just copy-paste
- Handles both technical and architectural queries
- Modular: Easily swap in other documents, LLMs, or embeddings

---

##  Overview

Large Language Models (LLMs) like Gemini or GPT often lack access to private or domain-specific information. However, critical insights are often hidden in PDFs, documents, and research papers. This project solves that problem by building a **RAG pipeline** that:

Ingests and processes the paper “Leave No Context Behind”  
Stores semantic chunks in a vector database  
Retrieves relevant context for a given query  
Synthesizes accurate, context-aware answers using an LLM

---

##  Based On:  
📄 [Leave No Context Behind — Google Research Paper (April 2024)](https://arxiv.org/pdf/2404.07143.pdf)  
📚 Focus: **Infini-attention**, a plug-and-play long-context Transformer architecture  



###  Pipeline Architecture

mermaid
graph TD
A[PDF Paper] --> B[LangChain PDF Loader]
    
B --> C[Recursive Text Splitter]    

C --> D[Hugging Face Embeddings]

D --> E[Chroma Vector Store]

F[User Query] --> G[Retriever (Top-k Chunks)]

G --> H[Custom Prompt + Flan-T5]

H --> I[Answer Synthesized]

Key Implementation Highlights

Advanced Prompt Engineering:

Encourages synthesis, avoids raw copying

Summarizes experimental results meaningfully

### LLM Hyperparameter Tuning:

temperature, max_new_tokens, and prompt structure are optimized for clarity and depth

Flexible Retrieval:

Easily tune k value (top-k chunks)

Metadata filtering to exclude irrelevant content (e.g., references)

Multiple Integration Styles:

Manual LLM chain (StuffDocumentsChain)

Auto-generated via RetrievalQA.from_chain_type

### Performance Tips

Increase chunk_size to 1500+ and chunk_overlap to 200–300

Use top_k=5 in retriever for better evidence retrieval

Prefer text2text-generation over question-answering pipeline

Use larger LLMs like flan-t5-xl if GPU resources allow

### Final Thoughts

This project showcases the real-world power of RAG systems: combining LLMs with external knowledge sources like research papers. By leveraging Infini-attention’s core ideas, we built a system that — like the paper — ensures no context is left behind.

Plug-and-play RAG pipelines are the future of personalized, domain-specific AI — and this is just the beginning.
