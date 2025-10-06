# RAG-Web-Data-Embedding-Demo
Technologies: LangChain · Chroma · OpenAI · Python · RAG

# 🌐 LangChain Web Data RAG Pipeline

A simple pipeline built with **LangChain** that:
1. Loads data from a web page  
2. Splits the text into smaller chunks  
3. Converts them into **vector embeddings** using OpenAI  
4. Stores and retrieves them from a **Chroma** vector database

---

## 🚀 Overview

This project demonstrates a basic **Retrieval-Augmented Generation (RAG)** workflow using the `langchain` ecosystem.  
It scrapes text content from a given website, processes it, embeds it, and stores it for semantic search or retrieval tasks.

---

## 🧩 Tech Stack

- 🧠 **LangChain** — LLM orchestration framework  
- 🧱 **Chroma** — Local vector database  
- 💬 **OpenAI** — For text embeddings & chat models  
- 🕸 **BeautifulSoup (via bs4)** — HTML parsing  
- 🧰 **Python-dotenv** — Environment variable management  

---

## 📦 Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/<your-username>/LangChain-Web-Data-RAG-Pipeline.git
cd LangChain-Web-Data-RAG-Pipeline
pip install -r requirements.txt
```

**Example `requirements.txt`:**
```
python-dotenv==1.0.1
openai==1.109.1
langchain-core==0.3.76
langchain==0.3.68
langchain-community==0.3.30
langchain-openai==0.3.33
langchain-text-splitters==0.3.11
langchain-chroma==0.2.6
bs4
```

---

## ⚙️ Environment Setup

Create a `.env` file in the project root:

```
OPENAI_API_KEY=your_openai_api_key_here
```

---

## 🧠 How It Works

```python
# 1. Load web data
loader = WebBaseLoader(web_paths=("https://lilianweng.github.io/posts/2023-06-23-agent/",))

# 2. Split into chunks
text_splitter = RecursiveCharacterTextSplitter(chunk_size=1000, chunk_overlap=200)
splits = text_splitter.split_documents(docs)

# 3. Embed and store in Chroma
vectorstore = Chroma.from_documents(documents=splits, embeddings=OpenAIEmbeddings())
```

You can later query or retrieve these vectors for context-aware AI responses.

---

## 🧪 Example Output

When you run the script:
```bash
python main.py
```

You’ll see the parsed web content printed in chunks (clean text from the site).

---

## 📁 Project Structure

```
LangChain-Web-Data-RAG-Pipeline/
│
├── main.py                 # Main pipeline script
├── .env                    # API key (ignored by Git)
├── requirements.txt        # Dependencies
└── README.md               # Documentation
```

---

## 🧱 Future Improvements

- Add a **query interface** to ask questions from the stored vector database  
- Integrate with **LangChain Agents**  
- Store vectors persistently using `persist_directory`  

---

## 👨‍💻 Author

**Düzgün Barış Polat**  
Software Test Engineer | AI & Data Enthusiast  
🌍 [GitHub](https://github.com/<your-username>) | [LinkedIn](https://linkedin.com/in/<your-profile>)

---

⭐ *If you like this project, consider giving it a star!*

