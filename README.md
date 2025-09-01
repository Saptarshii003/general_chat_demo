# general_chat_demo

This project processes NetSuite PDF guides and prepares them for use in a vector database.
It includes parsing, chunking, cleaning, merging short chunks, and deduplication.

## Features
- Parse multiple PDF documents into text.
- Chunk text using LangChain's `RecursiveCharacterTextSplitter`.
- Merge short chunks (<50 characters) into adjacent chunks from the same PDF.
- Deduplicate chunks using SHA256 hashing.
- Store clean chunks into a vector database (e.g., Milvus, FAISS, Qdrant, Chroma).
- Retrieve chunks using Maximal Marginal Relevance (MMR) search

## Workflow
1. Load PDFs using `PyPDFLoader`.
2. Deduplicate based on hash.
3. Split into overlapping text chunks.
4. Merge short chunks into neighbors.
5. Insert into vector DB.
6. Retrieve chunks using Maximal Marginal Relevance (MMR) search