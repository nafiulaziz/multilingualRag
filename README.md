# Multilingual Retrieval-Augmented Generation (RAG) System
#NoteBook link: https://colab.research.google.com/drive/1XmViKkQpTcFfnooaVZUGC7FGoz5--nud?usp=sharing
Overview
This project implements a simple multilingual Retrieval-Augmented Generation (RAG) pipeline capable of understanding and answering queries in English and Bangla. It uses a local PDF corpus as the knowledge base, extracts and processes text, and leverages free/open-source models for embeddings and language generation — without requiring any API keys.

Features
Extracts text from PDF documents using pdfplumber

Cleans and preprocesses Bengali and English text

Splits large documents into manageable chunks

Embeds chunks with multilingual Sentence-Transformers

Uses FAISS for efficient similarity search over document chunks

Generates answers with a local causal language model (e.g., facebook/opt-1.3b)

Supports both Bangla and English queries

Interactive user interface via:

Inline Jupyter notebook UI using ipywidgets, or

Web-based UI using gradio

Requirements
Python 3.7+

GPU recommended for LLM inference, but CPU can work with smaller models

Google Colab or local Jupyter notebook environment

Installation
Run the following commands to install dependencies:

bash
Copy
Edit
pip install pdfplumber sentence-transformers faiss-cpu transformers ipywidgets gradio
Usage
Mount your Google Drive (if using Colab) and upload your PDF knowledge base:

python
Copy
Edit
from google.colab import drive
drive.mount('/content/drive')
pdf_path = "/content/drive/My Drive/HSC26_Bangla_1st_Paper.pdf"
Extract, clean, and chunk text from the PDF.

Create embeddings and build a FAISS index.

Load the local LLM model for answer generation.

Run queries in English or Bangla.

Use the interactive UI (choose one):

ipywidgets inline UI:

python
Copy
Edit
# (See notebook for code)
Gradio web app UI:

python
Copy
Edit
# (See notebook for code)
Example
python
Copy
Edit
query = "ভাষার গুরুত্ব কি?"
answer = generate_answer(query)
print(answer)
Notes
The model facebook/opt-1.3b is used by default but can be replaced with smaller or larger open-source LLMs.

For large documents or datasets, consider more advanced chunking and indexing strategies.

GPU is highly recommended for faster embedding and generation.

License
This project uses open-source libraries and models under their respective licenses.

