# Retrieval-Augmented-Generation-RAG-with-FAISS-and-GPT-4
This project implements a Retrieval-Augmented Generation (RAG) pipeline that enhances the performance of GPT-4 by retrieving document-based context using Sentence-BERT embeddings and FAISS similarity search. The system allows PDF uploads, chunk indexing, and top-k retrieval to generate fact-grounded, domain-specific answers.

🔍 Overview
Large Language Models (LLMs) like GPT-4 are powerful but limited by training cutoffs. RAG solves this by injecting real-time, retrieved knowledge into the generation process, reducing hallucinations and improving contextual accuracy.

📌 Features
🔗 Document-aware QA using dense embeddings + vector search

🧾 PDF upload + automatic chunking for corpus creation

🎯 Top-k retrieval with FAISS based on cosine similarity

🤖 Contextual answer generation using OpenAI’s GPT-4

🧠 Offline-compatible with Hugging Face Transformers & FAISS

🛠 Tech Stack
Python (core implementation)

FAISS (Facebook AI Similarity Search)

Sentence-BERT (all-MiniLM-L6-v2) via HuggingFace

OpenAI GPT-4 API for final response generation

PyPDF2 for PDF parsing

Jupyter / Google Colab for development and demo

🧪 How It Works
User Uploads File
→ Extracts text using PyPDF2

Text Chunking
→ Divides long text into manageable semantic chunks

Embedding
→ Sentence-BERT converts chunks and query into dense vectors

Similarity Search
→ FAISS returns top-k similar chunks based on cosine similarity

Contextual Generation
→ Retrieved chunks + user query fed into GPT-4 for grounded response

📈 Evaluation
ROUGE / BLEU metrics for textual overlap (if references exist)

Human evaluation for factual grounding and fluency

Chunk relevance, coherence, and hallucination checks

📚 Applications
🧑‍⚖️ Legal/Healthcare document QA

🧑‍🎓 Academic research assistants

💬 Internal chatbot assistants for customer support

🚧 Challenges & Future Work
FAISS index must be rebuilt for new documents

Latency depends on chunk size & embedding performance

GPT-4 API usage incurs costs — future work includes adding cost-efficient open-source generators
