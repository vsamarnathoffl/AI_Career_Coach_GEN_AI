# AI Career Coach - Gen AI

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project implements an AI-powered Career Coach designed to analyze your resume and provide personalized career insights and answer your career-related questions. Leveraging the power of Generative AI and Retrieval-Augmented Generation (RAG), this tool offers intelligent interaction with your resume.

## Overview

The AI Career Coach takes your resume in PDF format and performs the following key functions:

-   **Intelligent Resume Summarization:** Generates a structured and comprehensive summary of your resume, highlighting crucial aspects such as your career objective, skills, professional experience, educational background, and notable achievements.
-   **Interactive Q\&A:** Allows you to ask specific questions about your resume content or seek general career advice. The system intelligently retrieves relevant information from your resume to provide contextually accurate and actionable responses.

## Key Technologies

-   **LangChain:** A powerful framework for building applications with large language models.
-   **Google Gemini API (Gemini-2.0-Flash):** A cutting-edge generative AI model from Google, used for text generation and understanding.
-   **FAISS (Facebook AI Similarity Search):** An efficient library for similarity search of dense embeddings, enabling quick retrieval of relevant resume sections.
-   **RetrievalQA:** A LangChain chain specifically designed for question answering over retrieved documents.
-   **PyPDF2:** A Python library used for extracting text content from PDF files.
-   **sentence-transformers:** A Python framework for generating high-quality sentence and text embeddings.
-   **HuggingFace Embeddings:** Integration within LangChain for utilizing pre-trained sentence transformer models.

## Getting Started

This project is designed to be run in a Python environment, primarily intended for use within Google Colaboratory.

### Prerequisites

-   A Google account (required to use Google Colab).
-   A Google Gemini API key. You can obtain one by following the instructions on the [Google Cloud AI Platform](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/model-index).

### Running the Code

After downloading the Colab file (`.ipynb`), you can run it using the following steps:

1.  **Open in Google Colab:** Go to [Google Colab](https://colab.research.google.com/) and upload the downloaded `.ipynb` file.
2.  **Connect to Runtime:** Ensure that your Colab notebook is connected to a runtime (you'll see a "Connect" button if it's not already connected). It's recommended to use a GPU runtime if available for potentially faster processing, but it's not strictly required for this project. You can change the runtime type under "Runtime" -> "Change runtime type".
3.  **Install Dependencies:** The first code cell in the notebook installs the necessary Python libraries. Run this cell by clicking the play button next to it.
4.  **Enter API Key:** The next step will prompt you to enter your Google Gemini API key. Run that cell and securely input your key when asked.
5.  **Upload Your Resume:** You will need to upload your resume in PDF format to the Colab environment. The code expects the PDF file to be accessible within the Colab environment. You might need to modify the `pdf_path` variable in the code to point to the correct location of your uploaded file.
6.  **Run the Code Cells:** Execute the subsequent code cells step-by-step by clicking the play button next to each cell.
7.  **View Resume Summary:** After running the resume summary generation cell, a formatted summary of your resume will be displayed in the output.
8.  **Interactive Q\&A:** The final part of the code sets up an interactive loop. Run this cell, and you will be prompted to ask questions about your resume or career. Type your questions and press Enter. The AI Career Coach will provide answers based on your resume content. Type `exit` to end the interactive session.

## How It Works

1.  **PDF Extraction and Chunking:** The PDF resume is read, and its text content is segmented into smaller chunks.
2.  **Semantic Embedding:** Each text chunk is converted into a vector embedding using `sentence-transformers` and `HuggingFaceEmbeddings`.
3.  **Vector Store Indexing:** The embeddings are indexed using FAISS for efficient similarity searching.
4.  **Resume Summarization:** A prompt is used with the Gemini-2.0-Flash model to generate a comprehensive summary.
5.  **Question Answering:** User questions are used to retrieve relevant resume chunks from the vector store, which are then used by the Gemini-2.0-Flash model to generate contextually relevant answers.

## Contributing

Contributions to this project are welcome. Feel free to submit issues and pull requests to suggest improvements or report bugs.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

## Acknowledgements

-   The LangChain and Google Gen AI teams for their excellent libraries and APIs.
-   The creators of FAISS and sentence-transformers for their valuable tools.
-   The PyPDF2 library developers for PDF processing capabilities.
