# RAG QnA Chatbot

A Retrieval-Augmented Generation (RAG) chatbot built with Streamlit that allows you to upload documents, ingest them into a ChromaDB vector database, and ask questions about the content. The chatbot uses OpenAI for answering queries based on retrieved context.

## Features

- Upload and ingest documents (`txt`, `pdf`, `md`, `html`, `docx`)
- Automatic text extraction and summarization
- Stores document chunks in ChromaDB for semantic search
- Ask questions about your uploaded document
- Answers are generated using OpenAI and relevant context from your document

## Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/yourusername/rag-chatbot.git
   cd rag-chatbot
   ```

2. **Create and activate a virtual environment:**
   ```sh
   python -m venv .venv
   .venv\Scripts\activate   # On Windows
   ```

3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

4. **Set up environment variables:**
   - Create a `.env` file in the root directory.
   - Add your OpenAI API key and ChromaDB collection name:
     ```
     OPENAI_API_KEY=your_openai_api_key
     CHROMA_COLLECTION_NAME=rag_docs
     ```

## Usage

1. **Start the Streamlit app:**
   ```sh
   streamlit run main.py
   ```

2. **Document Ingestion:**
   - Go to the "Document Ingestion & Summarization" page.
   - Upload your document.
   - Preview the extracted text and summary.
   - Click "Upload & Ingest to Chroma DB" to store the document chunks.

3. **Chatbot QnA:**
   - Go to the "RAG QnA Chatbot" page.
   - Ask questions about your ingested document.
   - The chatbot retrieves relevant context and generates an answer.

## Project Structure

```
RAG-Chatbot/
├── main.py
├── chroma_services.py
├── genai_services.py
├── pages/
│   ├── ingest_page.py
│   └── chatbot_page.py
├── requirements.txt
├── .env
└── README.md
```

## Dependencies

- [streamlit](https://streamlit.io/)
- [openai](https://pypi.org/project/openai/)
- [tiktoken](https://github.com/openai/tiktoken)
- [chromadb](https://docs.trychroma.com/)
- [markitdown](https://github.com/markitdown/markitdown)

## Notes

- Each new document upload clears previous data in ChromaDB to ensure only the latest document is used for QnA.
- Make sure your OpenAI API key is valid and has sufficient quota.

## License

MIT License

## Acknowledgements

- [Streamlit](https://streamlit.io/)
- [ChromaDB](https://docs.trychroma.com/)
- [OpenAI](https://openai.com/)
