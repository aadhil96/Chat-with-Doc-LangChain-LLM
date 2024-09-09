# 🦙 Chat with Doc - LLAMA 3.1

This project is a **Conversational Document Q&A** application using **Streamlit** and **LLAMA 3.1**. Users can upload a PDF, and the system will allow them to ask questions based on the content of the document. It uses **Groq’s LLAMA 3.1 model** for natural language understanding and **FAISS** for document search via vector embeddings. The application also maintains a chat history for a conversational experience.

## Features

- **PDF Upload**: Users can upload PDF documents for processing.
- **Conversational Q&A**: The app allows users to interact with the content of the document through natural language queries.
- **Chat History**: A conversational interface is maintained throughout the session, preserving the chat history for more context-aware responses.
- **LLAMA 3.1**: Integration of the **LLAMA 3.1-70b-versatile** model to generate responses based on document context.
- **Vector Embeddings**: PDF content is split into chunks and embedded using **HuggingFaceEmbeddings**, with efficient search powered by **FAISS**.
  
## Requirements

- Python 3.8 or higher
- Required libraries:
  - `streamlit`
  - `langchain`
  - `langchain_community`
  - `FAISS`
  - `HuggingFaceEmbeddings`
  - `ChatGroq`
  - `dotenv`
 
## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/your-repo.git
    cd your-repo
    ```

2. Install the required Python packages:

    ```bash
    pip install streamlit langchain langchain-groq langchain-community dotenv
    ```

3. Create a `.env` file in the root directory of your project and add your Groq API key:

    ```
    GROQ_API_KEY=your_groq_api_key
    ```

## Usage

1. Run the Streamlit application:

    ```bash
    streamlit run your_script_name.py
    ```

2. Open the provided URL in your web browser.

3. Upload a PDF document using the file uploader.

4. Start chatting with the bot by entering your queries in the chat input field.

5. The chatbot will respond with information based on the content of the uploaded PDF document.

## Code Overview

The main components of the code are as follows:

- **Streamlit Configuration**: Sets up the Streamlit page configuration and title.
- **Environment Variables**: Loads the Groq API key from the `.env` file.
- **Document Loading**: Loads the PDF document using `UnstructuredPDFLoader`.
- **Vector Store Setup**: Sets up the vector store using HuggingFace embeddings and `FAISS`.
- **Chain Creation**: Creates a conversational retrieval chain using the Groq API and the vector store.
- **Chat Interface**: Manages the chat session state and displays messages.
- **User Input Handling**: Processes user input and generates responses using the conversational retrieval chain.
