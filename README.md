# Agentic-Chatbot-with-LangGraph-Chromadb-FastAPI

An open-source **agentic AI chatbot** built with **Python, FastAPI, LangGraph, LangChain, Google Gemini, Tavily, ChromaDB, and SQLite**.

It supports real-time streaming chat, document uploads, retrieval-augmented generation (RAG), web search, conversation memory, and a simple web UI.

![Project architecture diagram](diagram.png)

---

## Features

* Chat with an AI agent powered by Google Gemini
* Stream responses in real time
* Upload documents such as PDF, DOCX, TXT, MD, PY, and CSV
* Use uploaded files as context through RAG
* Search the web with Tavily for current information
* Store and recall conversation history
* Simple FastAPI-based web interface
* Docker-ready deployment
* AWS CI/CD support using GitHub Actions, ECR, and EC2

---

## Project Overview

This project combines:

* **FastAPI** for the backend server and API endpoints
* **Jinja2** for rendering the frontend UI
* **LangGraph** for agent orchestration
* **LangChain** for tools, messages, and RAG workflow
* **Google Gemini** as the LLM provider
* **Tavily** for web search
* **ChromaDB** for vector search over uploaded documents
* **SQLite** for conversation and persistence
* **Docker** for containerized deployment

---

## Prerequisites

Make sure you have the following installed:

* Python 3.11
* pip or conda
* Git
* Google API key for Gemini
* Tavily API key for web search

---


## Run Locally

Start the FastAPI app:

```bash
python app.py
```

The app will be available at:

```text
http://127.0.0.1:8080
```

---

## Project Structure

```text
BappyGPT/
│
├── app.py                  # FastAPI app and streaming chat endpoints
├── agent.py                # LangGraph agent setup and tool orchestration
├── database.py             # Conversation and persistence logic
├── rag.py                  # Document ingestion and RAG logic
├── tools.py                # Agent tools such as web search, memory, and RAG
├── requirements.txt        # Python dependencies
├── Dockerfile              # Docker image configuration
├── .dockerignore           # Docker ignore rules
│
├── templates/
│   └── index.html          # Frontend UI
│
├── uploads/                # Uploaded documents
├── data/                   # SQLite database and app data
└── chroma_db/              # ChromaDB vector database storage
```

---

## Docker Deployment

### 1. Build the Docker image

```bash
docker build -t bappygpt .
```

### 2. Run the Docker container

```bash
docker run -d \
  --name bappygpt \
  --restart always \
  -p 8080:8080 \
  --env-file .env \
  bappygpt
```

The app will be available at:

```text
http://localhost:8080
```

---


