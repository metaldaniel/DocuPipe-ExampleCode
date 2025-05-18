# DocuPipeOCR

A Python-based OCR (Optical Character Recognition) solution that leverages the DocuPipe.ai API to extract text from PDF documents, with special support for right-to-left (RTL) languages like Hebrew.

## Overview

DocuPipeOCR provides a simple interface to extract text from PDF documents using the DocuPipe.ai service. The project includes a main Jupyter notebook:

**DocuPipeOCR.ipynb** - OCR text extraction with support for both standard and RTL languages

## Features

- Extract text from PDF documents
- Process multi-page documents
- Handle right-to-left (RTL) languages with proper text direction
- Format extracted Hebrew text with appropriate styling
- Support for document sections and page structure
- Fix number formatting in RTL text

## Prerequisites

- Python 3.x
- DocuPipe.ai API key

## Setup

1. Clone the repository:
   ```
   git clone <repository-url>
   cd DocuPipeOCR
   ```

2. Create a virtual environment:
   ```
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. Install required packages:
   ```
   pip install -r requirements.txt
   ```

4. Create a `.env` file with your DocuPipe.ai API key:
   ```
   MY_API_KEY=your_api_key_here
   ```

## Usage

Open `DocuPipeOCR.ipynb` in Jupyter and run the cells to process PDF documents:

```python
# Process a PDF document and extract text
do_ocr("your_document.pdf")
```

## How It Works

1. The PDF document is encoded in base64 and sent to the DocuPipe.ai API
2. The API processes the document and returns a document ID
3. The system polls the API until processing is complete
4. The extracted text is retrieved and processed
5. For RTL documents, special formatting is applied to ensure proper text display

## API Functions

### `process_document(file_name)`
Sends the document to DocuPipe.ai and returns a document ID.

### `check_result(document_id)`
Checks the processing status and retrieves results when complete.

### `extract_text_from_json(json_response)`
Extracts and formats text from the API response.

### `do_ocr(file_name)`
Main function that orchestrates the OCR process.

## Security Note

- The API key is stored in a `.env` file which is excluded from version control via `.gitignore`
- Always keep your API keys secure and never commit them to public repositories

## Acknowledgments

- [DocuPipe.ai](https://docupipe.ai) for providing the OCR API service
