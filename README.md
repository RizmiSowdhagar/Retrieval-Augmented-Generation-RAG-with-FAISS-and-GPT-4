# Retrieval-Augmented-Generation-RAG-with-FAISS-and-GPT-4
This project implements a Retrieval-Augmented Generation (RAG) pipeline that enhances the performance of GPT-4 by retrieving document-based context using Sentence-BERT embeddings and FAISS similarity search. The system allows PDF uploads, chunk indexing, and top-k retrieval to generate fact-grounded, domain-specific answers.

Overview
Large Language Models (LLMs) like GPT-4 are powerful but limited by training cutoffs. RAG solves this by injecting real-time, retrieved knowledge into the generation process, reducing hallucinations and improving contextual accuracy.

📌 Features
1.Document-aware QA using dense embeddings + vector search
2.PDF upload + automatic chunking for corpus creation
3.Top-k retrieval with FAISS based on cosine similarity
4.Contextual answer generation using OpenAI’s GPT-4
5.Offline-compatible with Hugging Face Transformers & FAISS

Tech Stack
1.Python (core implementation)
2.FAISS (Facebook AI Similarity Search)
3.Sentence-BERT (all-MiniLM-L6-v2) via HuggingFace
4.OpenAI GPT-4 API for final response generation
5.PyPDF2 for PDF parsing
6.Jupyter / Google Colab for development and demo

How It Works
1.User Uploads File → Extracts text using PyPDF2
2.Text Chunking → Divides long text into manageable semantic chunks
3.Embedding → Sentence-BERT converts chunks and query into dense vectors
4.Similarity Search → FAISS returns top-k similar chunks based on cosine similarity
5.Contextual Generation → Retrieved chunks + user query fed into GPT-4 for grounded response

Evaluation
1.ROUGE / BLEU metrics for textual overlap (if references exist)
2.Human evaluation for factual grounding and fluency
3.Chunk relevance, coherence, and hallucination checks

Challenges & Future Work
1.FAISS index must be rebuilt for new documents
2.Latency depends on chunk size & embedding performance
3.GPT-4 API usage incurs costs — future work includes adding cost-efficient open-source generators
