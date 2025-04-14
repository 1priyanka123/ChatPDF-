# ChatPDF

A web application that allows users to chat with their PDF documents using AI. Upload any PDF and ask questions to get instant answers based on the content of your document.

## Overview

ChatPDF is built using FastAPI and integrates with LangChain and Ollama to provide a conversational interface for PDF documents. The application extracts text from uploaded PDFs, processes it into embeddings, and enables users to ask questions about the document content through a simple chat interface.

## Features

- PDF document upload and processing
- Text extraction from PDF files
- Conversational interface to query document content
- Based on LangChain for document processing
- Uses Ollama for local LLM inference
- ChromaDB for vector storage and similarity search
- FastAPI backend with simple HTML/JavaScript frontend

## Tech Stack

- **Backend**: FastAPI
- **Frontend**: HTML, CSS, JavaScript
- **AI/ML**: LangChain, Ollama LLM
- **PDF Processing**: PyPDF library
- **Vector Store**: ChromaDB for efficient similarity search

## Project Structure

```
ChatPDF-/
├── app.py              # FastAPI application
├── templates/          # HTML templates
│   └── index.html      # Main application interface
├── static/             # Static assets
│   ├── css/            # CSS stylesheets
│   │   └── style.css
│   └── js/             # JavaScript files
│       └── main.js
├── requirements.txt    # Python dependencies
└── README.md
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/1priyanka123/ChatPDF-.git
cd ChatPDF-
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Install and set up Ollama:
   - Follow the installation instructions at [Ollama's official website](https://ollama.ai/)
   - Pull the required model (e.g., `ollama pull llama2`)

## Usage

1. Make sure Ollama is running with your chosen model.

2. Start the FastAPI server:
```bash
uvicorn app:app --reload
```

3. Open your browser and navigate to:
```
http://localhost:8000
```

4. Upload a PDF document using the interface.

5. Once processed, you can start asking questions about the content of your PDF.

## How It Works

1. **PDF Upload**: The user uploads a PDF document through the web interface.

2. **Text Extraction**: The application extracts text content from the PDF using PyPDF.

3. **Document Processing**: The extracted text is processed into chunks and converted into embeddings using LangChain.

4. **Vector Storage**: The embeddings are stored in ChromaDB for efficient retrieval.

5. **Question Answering**: When a user asks a question, the application:
   - Converts the question into an embedding
   - Finds the most relevant chunks of the document using ChromaDB's similarity search
   - Uses Ollama's LLM to generate a response based on the relevant chunks

6. **Response**: The answer is displayed in the chat interface.

## Requirements

- Python 3.8+
- Ollama (local LLM service)
- Sufficient RAM to run the language model (requirements depend on the specific Ollama model used)

## Limitations

- The application has a file size limit for PDF uploads
- Complex PDFs with heavy formatting or images may not be processed correctly
- Response quality depends on the Ollama model used
- Requires local resources to run the LLM

## Future Enhancements

- Support for multiple document types (DOCX, TXT, etc.)
- Improved document chunking for better context understanding
- User authentication and document management
- Session persistence for chat history
- PDF preview and navigation interface
- Options for different language models

## License

This project is licensed under the MIT License.

## Acknowledgements

- [LangChain](https://github.com/hwchase17/langchain) for document processing
- [Ollama](https://ollama.ai/) for local LLM capabilities
- [FastAPI](https://fastapi.tiangolo.com/) for the web framework
- [ChromaDB](https://www.trychroma.com/) for vector database functionality
