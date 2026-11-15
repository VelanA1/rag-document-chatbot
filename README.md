# Retrieval-Augmented PDF Question Answering

An experimental document question-answering pipeline. The notebook extracts text from a PDF, splits it into overlapping passages, embeds passages with **all-MiniLM-L12-v2**, performs similarity-based retrieval in a lightweight in-memory vector store, and passes retrieved text to **google/flan-t5-base** for answer generation.

**Technologies:** Python, Sentence Transformers, Hugging Face Transformers, PyPDF, NumPy.

## Notebook
- [`RAG_Chatbot.ipynb`](RAG_Chatbot.ipynb) — PDF ingestion, embedding storage, retrieval, and an interactive question-answering loop.

## Reproduce
Install `requirements.txt` and place a PDF named `TechNova_IT_Handbook.pdf` next to the notebook, or change `pdf_path` in the notebook to a PDF you are permitted to use. The original handbook PDF is **not included** in this repository. Running the notebook downloads public model weights, which may be substantial.

## Notes & limitations
The code implements an in-memory array-based vector store and Euclidean-distance-derived similarity, **not FAISS**. A Hugging Face token is optional but the notebook includes a login attempt; configure `HF_API_KEY` in the environment if needed. The current notebook has not been validated end-to-end in this repository without its referenced PDF, and outputs are preserved from the submitted run. It is a prototype, not a production chatbot.
