MULTILINGUAL PDF RAG SYSTEM ![ref1]

GitHub link: https://github.com/Geeteshkamble/Data\_scientist

Technical Documentation 

Multilingual PDF Retrieval-Augmented Generation (RAG) System 

1. Overview:  

   This system implements a RAG pipeline capable of processing multilingual PDFs (both digital and scanned) in languages such as English, Hindi, Bengali, and Chinese. It utilizes a combination of text extraction, chunking, embedding generation, and retrieval techniques to summarize content and answer questions based on the input PDFs.  

2. System Architecture: - 
- Input Layer: Handles both scanned and digital PDFs using OCR for scanned documents and PyPDF2 for digital PDFs. 
- Text Extraction: Digital PDFs are extracted using PyPDF2 and scanned PDFs are processed using Tesseract OCR. 
- Chunking: The extracted text is chunked into smaller pieces to fit the token limit of transformer models.  
- Embedding  and  Search:  A  lightweight  model  (MiniLM)  generates embeddings, and FAISS is used for efficient retrieval. 
- Summarization: Summaries and answers are  generated  based on  retrieved chunks using LLM.  
3. Key Features: -  
- Multilingual support for OCR and text extraction. 
- Hybrid Search combining keyword and semantic search. 
- Efficient Chunking for handling large documents. 

User Guide ![ref1]

User Guide for Multilingual PDF RAG System  

1. Installation: 
- Install the following dependencies:  
- pip install PyPDF2 pdf2image pytesseract transformers sentence-transformers faiss-cpu torch 
- apt-get install poppler-utils tesseract-ocr tesseract-ocr-hin tesseract-ocr-chi-sim tesseract-ocr-ben 
2. Running the System: -  
- Place your PDFs in the pdfs/ directory. 
- Run the extraction script: text = extract\_text("path\_to\_pdf.pdf", scanned=True) 

  # Set scanned=False for digital PDFs 

- Generate Embeddings:  
- chunks = chunk\_text(text)  
- embeddings = [model.encode(chunk) for chunk in chunks] 
- Search  and  Summarize:  Input  a  user  query,  retrieve  relevant  chunks,  and summarize them. 
3. Troubleshooting: -  
- Ensure correct OCR language support is installed. 
- For large files, adjust chunking parameters to avoid memory overload 

[ref1]: Aspose.Words.b7f2e86e-bf57-4c1b-8457-c12725be7d29.001.png
