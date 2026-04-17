# My Research Tool

> An end-to-end tool to accelerate AI research by automatically fetching papers,
> synthesizing their contents, and organizing them into interactive knowledge graphs.

**GitHub Repository:** [AI Research Tool](https://github.com/Abhinandan-KP/airesearchtool)

---
<img width="1024" height="420" alt="image" src="https://github.com/user-attachments/assets/d5ff1b07-c8c9-4f95-91fd-8bd8e1defafa" />


## Overview

This application uses Natural Language Processing (NLP) models to extract summaries
and core claims from arXiv papers and visualizes the connections between research
papers based on semantic similarity.

---

## Features

- **Automated Research Retrieval** — Fetch recent research papers directly from arXiv based on your search topic.
- **AI-Powered Synthesis** — Automatically summarizes paper abstracts and extracts core claims using Hugging Face Transformers.
- **Semantic Similarity Analysis** — Computes semantic similarity between papers using Sentence-Transformers to discover connections.
- **Interactive Knowledge Graphs** — Builds and renders an interactive knowledge graph using NetworkX and Pyvis.
- **Modern Dashboard** — An intuitive Streamlit frontend for seamless interaction, search configuration, and visualization.
- **Robust API Backend** — A FastAPI-based backend handling the full pipeline from data retrieval to graph generation.

---

## Tech Stack

| Layer           | Technology                                      |
| --------------- | ------------------------------------------------|
| Backend         | **FastAPI**                                     |
| Frontend        | **Streamlit**                                   |
| NLP & Embeddings| **Transformers, Sentence-Transformers, PyTorch**|
| Graph & Viz     | **NetworkX, Pyvis**                             |
| Data Processing | **Scikit-learn, NumPy, SciPy**                  |

## Project Structure

```
├── app.py                    # FastAPI backend application
├── requirements.txt          # Python dependencies
├── backend/
│   ├── fetch_papers.py       # arXiv data retrieval
│   ├── summarize.py          # Abstract summarization
│   ├── claim_extractor.py    # Core claim extraction
│   ├── embeddings.py         # Similarity matrix computation
│   ├── graph_builder.py      # Knowledge graph generation
│   └── graph_visualizer.py   # Graph HTML visualization
├── frontend/
│   └── streamlit_app.py      # Streamlit dashboard
├── lib/                      # Additional utilities
└── data/                     # Generated outputs (e.g., graph.html)
```

## Getting Started

### Prerequisites

Python 3.8+ is required. Using a virtual environment is recommended.

### Installation

Clone the repository and install dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Application

Both backend and frontend need to run at the same time in separate terminals.

### 1. Start the Backend (FastAPI)

```bash
uvicorn app:app --reload --host 0.0.0.0 --port 8000
```

Backend will be available at `http://localhost:8000`
API docs available at `http://localhost:8000/docs`

### 2. Start the Frontend (Streamlit)

Open a new terminal and run:

```bash
streamlit run frontend/streamlit_app.py
```

Frontend dashboard will open at `http://localhost:8501`

---

## Usage

1. Open the Streamlit frontend at `http://localhost:8501`
2. In the sidebar, enter a **Research Topic** (e.g., "Large Language Models", "Quantum Machine Learning", "Retrieval-Augmented Generation")
3. Adjust **Max Results** — how many papers to fetch
4. Adjust **Similarity Threshold** — minimum similarity score to form a connection in the graph
5. Click **Run Analysis**
6. View the **Extracted Papers**, their **Summaries**, extracted **Claims**, and the **Interactive Knowledge Graph**

---

_Developed by Abhinandan_
