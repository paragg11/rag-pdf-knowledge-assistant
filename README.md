# AI PDF Knowledge Assistant — RAG Project

A Retrieval-Augmented Generation (RAG) project built with Python that extracts information from PDF documents, retrieves relevant passages using semantic search, and displays source-page references through an interactive Gradio interface.

## Project Overview

The goal of this project is to demonstrate how users can search information in PDF documents using natural-language questions.

The application converts document text into embeddings, stores them in a FAISS vector index, and retrieves relevant passages based on semantic similarity.

**Current status:** The PDF retrieval and Gradio interface are implemented. The current version displays retrieved evidence; LLM-based answer generation is a planned improvement.

## Features

- Extract text from PDF documents
- Split text into overlapping chunks
- Generate embeddings using Sentence Transformers
- Perform semantic similarity search using FAISS
- Retrieve relevant passages for user questions
- Display source PDF pages and similarity scores
- Provide an interactive Gradio interface
- Evaluate retrieval using predefined test questions

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Google Colab | Development environment |
| PyPDF | PDF text extraction |
| Sentence Transformers | Text embeddings |
| all-MiniLM-L6-v2 | Embedding model |
| FAISS | Vector indexing and similarity search |
| NumPy | Numerical operations |
| Gradio | Interactive user interface |

## System Architecture

PDF Document → Text Extraction → Text Chunking → Embeddings → FAISS Vector Index → Semantic Retrieval → Retrieved Passages with Source Pages

### How It Works

1. **Document ingestion:** Extract text from the uploaded PDF using PyPDF.
2. **Chunking:** Divide extracted text into smaller, overlapping chunks.
3. **Embedding generation:** Convert each chunk into a numerical vector using `all-MiniLM-L6-v2`.
4. **Vector indexing:** Store normalized embeddings in a FAISS index for similarity search.
5. **Query retrieval:** Convert the user's question into an embedding and retrieve the most relevant passages.
6. **Source display:** Show the retrieved text, PDF page numbers, and similarity scores through Gradio.

## Example Questions

Using the sample employee handbook, users can ask:

- How many annual leave days do employees receive?
- What are the standard working hours?
- What security practices are required?
- How should critical customer issues be escalated?

## Evaluation

The notebook includes predefined test cases to evaluate whether the retrieved passages contain expected information.

The evaluation covers topics such as annual leave, working hours, security practices, and critical-issue escalation.

Retrieval quality depends on chunk size, embedding quality, similarity ranking, and the document's structure. Similarity scores alone do not guarantee factual correctness.

## Getting Started

### Prerequisites

- A Google account
- Google Colab
- A PDF document you are authorized to process

### Run the Project

1. Open `RAG_PDF_Knowledge_Assistant.ipynb` in Google Colab.
2. Execute the notebook cells in order.
3. Upload the sample PDF when prompted.
4. Allow the notebook to extract text, create chunks, generate embeddings, and build the FAISS index.
5. Launch the Gradio interface.
6. Enter a question and review the retrieved passages and source-page references.

## Current Limitations

- The application currently retrieves relevant passages rather than generating final answers with an LLM.
- Unsupported questions may still retrieve loosely related passages.
- Similarity thresholds require further calibration.
- Performance should be tested across different PDF formats and larger documents.

## Future Improvements

- Integrate a working LLM for answer generation grounded in retrieved context.
- Add a fallback when relevant evidence cannot be found.
- Improve retrieval evaluation and tune similarity thresholds.
- Support searching across multiple PDF documents.
- Add a more robust interface and deployment workflow.

## Skills Demonstrated

Python, PDF processing, text chunking, embeddings, vector search, FAISS, semantic retrieval, RAG architecture, retrieval evaluation, and Gradio.



