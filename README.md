# RAG based Q&A, ABSA, Summrization
# Project code - 5.1

## Features
- Perform Q & A on uploaded PDF maintaining conversation history
- Perform Aspect Based Sentimental Analysis on uploaded PDF
- Perform Summarization on uploaded PDF

## Libraries Used
- Langchain: 0.2.0
- Langchain_openai: 0.1.7
- Langchain_core: 0.2.0
- Langchain_community: 0.2.0

## Dataset
- Tata Safari Reviews

## Input
- PDF (can be optimized for .docx, CSV, Excel, URL)
- Queries (String)

## Output
- Answers generated (String)
- Summary (String)
- Aspect-Feedback pair (String)

## Procedure

### Q & A
1. Install and import all required packages.
2. Set up the Python environment with OpenAI API.
3. Load and extract the PDF using `PyPDFLoader`.
4. Split the extracted document with `RecursiveCharacterTextSplitter` with chunk size 1000, chunk overlap 100.
5. Convert the text to vector using `OpenAIEmbeddings`.
6. Store the vectors in Vector database (Chroma).
7. Create a history-aware retriever using LLM (ChatGPT 3.5 Turbo) and a clear Prompt Template.
8. Pass the query through the final conversational RAG chain and get the output.

### Aspect Based Sentiment Analysis and Summarization
1. Prepare a pipeline which takes the extracted text of the PDF as input.
2. Perform ABSA and Summarization using 2 different potential prompt templates and LLM (ChatGPT 3.5 Turbo).
3. Obtain a precise summary and Aspect-Feedback pairs as output.

### Final Pipeline
- Gather all the tasks into a final Pipeline.
