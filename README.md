# Advanced RAG Q&A System

This project is an Advanced Retrieval-Augmented Generation (RAG) Question & Answer (Q&A) System built with Streamlit, FAISS, and Hugging Face. It allows users to process various input types (e.g., links, PDFs, DOCX, plain text) and interact with an AI model to retrieve accurate answers to their queries.

## Features

- Supports multiple input types: Links, PDFs, DOCX, TXT, and plain text.
- Processes documents using a character-based text splitter.
- Uses FAISS for fast similarity search and vector storage.
- Integrates Hugging Face embeddings for creating vector representations.
- Employs a Hugging Face model for answering user queries.
- Streamlit-based interface for easy interaction.

## Requirements

Make sure you have the following dependencies installed:

- Python 3.7+
- Streamlit
- FAISS (CPU version)
- PyTorch
- Hugging Face Hub
- LangChain Community libraries
- PyPDF2
- python-docx

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Add your Hugging Face API token to the Streamlit secrets file:

   - Create a `.streamlit/secrets.toml` file in the project directory.
   - Add the following content:

     ```toml
     [secrets]
     HUGGINGFACE_TOKEN = "your_huggingface_api_token"
     ```

## Usage

1. Run the Streamlit app:

   ```bash
   streamlit run app.py
   ```

2. Open the app in your browser at `http://localhost:8501`.

3. Select an input type and provide the corresponding data:
   - **Link:** Enter the number of links and provide the URLs in the sidebar.
   - **Text:** Input plain text in the text box.
   - **PDF, DOCX, or TXT:** Upload the corresponding file.

4. Click **Proceed** to process the input and create the vector store.

5. Ask your question in the query input box and click **Submit** to get an AI-generated answer.

## Project Structure

```
├── app.py               # Main Streamlit app file
├── requirements.txt     # Python dependencies
├── .streamlit/          # Streamlit configuration folder
│   └── secrets.toml     # Hugging Face API token (not included in the repo)
└── README.md            # Project documentation
```

## Key Components

- **FAISS:** Used for storing and retrieving document embeddings efficiently.
- **Hugging Face:** Provides embeddings and the LLM for answering queries.
- **Streamlit:** Simplifies the development of the user interface.
- **LangChain Community:** Manages document loaders, retrievers, and chains.

## Troubleshooting

- **FAISS Errors:** Ensure `faiss-cpu` is installed if you're running on a CPU-only environment.
- **CUDA Issues:** The app defaults to `cuda` if available. If running on Streamlit Cloud, ensure the device is set to `cpu`.
- **Hugging Face Model Errors:** Verify that your API token has access to the required model.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for improvements.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments

- [FAISS](https://github.com/facebookresearch/faiss)
- [Hugging Face](https://huggingface.co/)
- [Streamlit](https://streamlit.io/)
- [LangChain](https://github.com/hwchase17/langchain)
