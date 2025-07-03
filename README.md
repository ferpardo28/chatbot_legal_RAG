
# Legal Chatbot with LangChain and RAG

This project implements a legal chatbot that answers questions about the **Federal Labor Law (LFT)** of Mexico. It uses the **RAG (Retrieval-Augmented Generation)** technique to retrieve relevant fragments from the official document and generate answers using OpenAI language models.

## 🚀 Technologies used

- `LangChain`
- `FAISS` for vector storage
- `OpenAI` (embeddings y modelo generativo)
- `Gradio` for the interface
- `pdfplumber` for processing the legal PDF

## 📄 Data source

The chatbot is based on the official file of the Federal Labor Law available at:
https://www.diputados.gob.mx/LeyesBiblio/pdf/LFT.pdf

## ⚙️ Installation (if running in Colab)

```python
!pip install langchain langchain-community langchain-openai faiss-cpu pdfplumber > /dev/null 2>&1
!pip install pypdf > /dev/null 2>&1
!pip install gradio > /dev/null 2>&1
!wget --no-check-certificate -O LFT.pdf https://www.diputados.gob.mx/LeyesBiblio/pdf/LFT.pdf > /dev/null 2>&1
```

## 💬 Overview

The system splits the PDF into chunks, generates embeddings with OpenAI, and stores the vectors using FAISS. Then, using LangChain and the RAG technique, it generates responses based on the most relevant fragments.

## ✅ Testing

The system was tested with various questions related to labor rights in Mexico.

## 👨‍💻 Author

This project was developed as part of a master's degree assignment in NLP.
