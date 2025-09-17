This project implements a Retrieval-Augmented Generation (RAG) pipeline using LangChain
, FAISS
, HuggingFace Embeddings
, and Groq LLMs
.

It allows you to upload a PDF, index its contents, and query it in natural language.

🚀 Features

📄 Load documents from PDF files.

✂️ Split text into manageable chunks.

🔎 Store embeddings in a FAISS vector database.

🤖 Use Groq LLMs (via langchain_groq) for question answering.

❓ Ask natural language questions and get context-aware answers.

📂 Project Structure
.
├── main.py          # Main script (pipeline)
├── requirements.txt # Dependencies
├── README.md        # Project documentation
└── your_file.pdf    # Example PDF (replace with your docs)

⚙️ Installation

Clone the repository:

git clone https://github.com/your-username/your-repo.git
cd your-repo


Create and activate a virtual environment:

python -m venv venv
source venv/bin/activate   # On Linux/Mac
venv\Scripts\activate      # On Windows


Install dependencies:

pip install -r requirements.txt

🔑 Environment Variables

Set your Groq API key before running the script:

export GROQ_API_KEY="your_api_key"    # Linux/Mac
setx GROQ_API_KEY "your_api_key"      # Windows

▶️ Usage

Place your PDF file in the project directory.

Update the filename in main.py:

loader = PyPDFLoader("your_file.pdf")


Run the script:

python main.py


Example test query:

query = "What does the Constitution say about the right to life?"
answer = qa.run(query)
print("Q:", query)
print("A:", answer)

🗄️ (Optional) Persisting the Vector Store

To avoid re-embedding each time:

# Save FAISS index
vectorstore.save_local("faiss_index")

# Load it later
vectorstore = FAISS.load_local("faiss_index", embeddings, allow_dangerous_deserialization=True)

📌 Roadmap

 Add persistence by default

 Add Gradio/Streamlit UI

 Support multiple documents

 Deploy as a web app

🤝 Contributing

Pull requests are welcome! If you’d like to add new features, feel free to fork the repo and submit a PR.
