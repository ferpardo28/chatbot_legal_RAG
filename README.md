# Chatbot Legal con LangChain y RAG

Este proyecto implementa un chatbot legal utilizando modelos de lenguaje (LLM) con la arquitectura RAG (Retrieval-Augmented Generation) usando LangChain, FAISS y Gradio.

## Objetivo

Proveer respuestas a preguntas frecuentes relacionadas con la Ley Federal del Trabajo en México, consultando directamente el texto oficial en PDF.

## Tecnologías usadas

- Python
- LangChain
- OpenAI
- FAISS (vector store)
- pdfplumber
- Gradio (interfaz)
- Google Colab

## Instalación de dependencias

Ejecuta estas celdas al inicio del notebook para instalar las dependencias necesarias:

```python
!pip install langchain langchain-community langchain-openai faiss-cpu pdfplumber > /dev/null 2>&1
!pip install pypdf > /dev/null 2>&1
!pip install gradio > /dev/null 2>&1
!wget --no-check-certificate -O LFT.pdf https://www.diputados.gob.mx/LeyesBiblio/pdf/LFT.pdf > /dev/null 2>&1
```

## Funcionamiento

1. El PDF de la Ley es dividido en fragmentos (chunks).
2. Se generan embeddings de esos fragmentos usando OpenAI.
3. Se crea una base vectorial FAISS para recuperar los fragmentos más relevantes.
4. Gradio permite interactuar con el chatbot usando un input en lenguaje natural.

## Instrucciones

1. Sube tu API key como variable de entorno en Google Colab:
   ```python
   import os
   os.environ["OPENAI_API_KEY"] = "tu_clave_aquí"
   ```
2. Corre el notebook por bloques.
3. Interactúa con el chatbot desde el link generado por Gradio (`.gradio.live`).

## Ejemplo de uso

- *"¿Qué prestaciones me da la ley si soy empleado formal?"*
- *"¿En qué casos me pueden despedir sin responsabilidad para el patrón?"*

## Notas

- El modelo no garantiza precisión legal. Solo resume el contenido oficial de la ley.
- Proyecto académico con fines demostrativos de NLP + RAG.
