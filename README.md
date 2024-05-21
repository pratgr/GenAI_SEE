# GenAI SEE

This project allows you to interact with PDF documents using a conversational AI powered by Google's Gemini model. You can upload PDF files, ask questions, and receive detailed answers based on the content of the PDFs.

## Features

- Upload multiple PDF files
- Extract text from PDFs
- Generate text embeddings using Google Generative AI
- Store and retrieve embeddings using FAISS
- Ask questions and get detailed answers from the PDF content

## Requirements

- Python 3.8 or higher
- Streamlit
- PyPDF2
- langchain
- langchain_google_genai
- google-generativeai
- FAISS
- python-dotenv

## Setup

1. Clone the repository:

    ```sh
    git clone https://github.com/pratgr/genai.git
    cd genai_see
    ```

2. Create a virtual environment and activate it:

    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```sh
    pip install streamlit PyPDF2 langchain langchain_google_genai google-generativeai faiss-cpu python-dotenv
    ```

4. Set up your Google API key:
    - Create a `.env` file in the project directory.
    - Add your Google API key to the `.env` file:

    ```env
    GOOGLE_API_KEY=your-google-api-key
    ```

## Usage

1. Run the Streamlit app:

    ```sh
    streamlit run app.py
    ```

2. Open your web browser and go to `http://localhost:8501`.

3. In the sidebar, upload your PDF files and click on "Submit & Process".

4. Once processing is complete, you can ask questions about the content of the PDFs in the text input box and receive detailed answers.

## Code Overview

### Main Functions

- `get_pdf_text(pdf_docs)`: Reads and extracts text from the uploaded PDF files.
- `get_text_chunks(text)`: Splits the extracted text into manageable chunks.
- `get_vector_store(text_chunks)`: Creates text embeddings using Google Generative AI and stores them in a FAISS vector store.
- `get_conversational_chain()`: Sets up the question-answering chain using Google's Gemini model and a custom prompt template.
- `user_input(user_question)`: Handles user questions, retrieves relevant documents, and generates a response.

### Streamlit UI

- The main user interface is created using Streamlit.
- Users can upload PDF files and submit questions through the web interface.
- Responses are displayed directly on the web page.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## License

This project is licensed under the MIT License.

## Acknowledgements

- [Streamlit](https://streamlit.io/)
- [PyPDF2](https://pythonhosted.org/PyPDF2/)
- [Langchain](https://langchain.com/)
- [FAISS](https://github.com/facebookresearch/faiss)
- [Google Generative AI](https://cloud.google.com/generative-ai)
