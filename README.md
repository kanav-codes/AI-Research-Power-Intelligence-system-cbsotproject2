# Research Insight: AI-Powered Paper Retrieval & Analysis Engine

Research Insight is an advanced retrieval engine designed to find research papers and extract technical entities (such as models, frameworks, datasets, and methodologies) using FAISS (Facebook AI Similarity Search) and GLiNER (Generalist and Lightweight NER).

## Key Features

* Semantic Search: Leverages FAISS for deep semantic understanding to retrieve highly relevant research papers.
* Technical Entity Extraction: Utilizes the GLiNER model to automatically extract crucial technical entities (Programming languages, Metrics, Methodologies, etc.) directly from paper abstracts.
* Intelligent Filtering: Supports keyword-based filtering combined with dynamic confidence scoring to ensure precision.
* Structured Analysis: Presents retrieved papers, match confidence, and extracted technical entities in a clean, interactive tabular format.

## The Extra Mile (Advanced Engine Intelligence)

What sets this project apart is its multi-layered analytical approach:

* Named Entity Recognition (NER) via GLiNER: Unlike standard keyword search, our engine understands context. Using the GLiNER model, it identifies and categorizes complex technical entities like "methodologies," "metrics," and "frameworks" from unstructured text.
* Precision Filtering: We implemented a custom keyword filtering layer that weeds out irrelevant results, ensuring that the user only interacts with high-utility content.
* Confidence Scoring: Every search result comes with a normalized Confidence Score (0–100%), which combines FAISS vector similarity and semantic relevance. This gives researchers an immediate assessment of how well a paper aligns with their query.

## Tech Stack

* Core Logic: Python
* Vector Search: FAISS (by Meta AI)
* Embeddings: Sentence-Transformers (all-MiniLM-L6-v2)
* Named Entity Recognition: GLiNER (Generalist NER)
* Data Handling: Pandas (for efficient data organization and table visualization)

## How It Works

1. Retrieval: The query is converted into a vector embedding and compared against the FAISS index to fetch the most relevant papers.
2. Filtering: User-defined keywords are used to filter the search results, ensuring only papers containing specific terms are processed.
3. Confidence Scoring: FAISS distance scores are normalized into a 0–100% similarity percentage for easy interpretation.
4. Analysis: The GLiNER model scans the paper title and abstract to identify key technical components, which are then categorized and presented in a table.

## Example Usage

```python
# Search for papers on a specific topic with a keyword filter
search_and_analyze_papers(
    query="Transformers in computer vision", 
     filter_keyword="Attention", 
    k=3
)

(This returns the top 3 matches with their Confidence Scores and a categorized table of extracted entities.)

Why This Project?
While traditional search engines rely heavily on keyword matching, Research Insight understands context and technical depth. With GLiNER integration, the system can instantly identify the specific tools, models, or datasets used in a paper—saving researchers hours of manual literature review.

Setup Guide
Clone the repository.

Install the necessary dependencies:
pip install faiss-cpu sentence-transformers gliner pandas

Ensure your dataframe.pkl and faiss_index.faiss files are in the working directory.

Run the notebook to start searching through your research database.

Developed By
[Kanav Bansal]
    
