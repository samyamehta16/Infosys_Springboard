# Infosys CodeGenie — Milestone 1: Code Explainer

## Overview

This milestone focuses on building a **Code Explainer pipeline** using advanced NLP models. The pipeline parses Python code snippets, extracts their structure using AST (Abstract Syntax Tree), tokenizes them, generates embeddings using pretrained models, and visualizes similarities.


- **code/**: Contains the Python notebook or script with the full pipeline.
- **README.md**: Documentation of approach and observations.


## Approach

1. **Code Snippets**  
   - Prepared at least 10 Python snippets covering functions, classes, recursion, decorators, async functions, list comprehensions, imports, etc.

2. **AST Parsing**  
   - Extracted functions, classes, imports, and common code patterns using Python's `ast` module.
    <img width="2332" height="410" alt="image" src="https://github.com/user-attachments/assets/e6da84fb-49e7-48ee-b16d-ceaa2c89486d" />

3. **Textual Summaries**  
   - Created summarized textual representations of snippets, combining imports, class names, function names, patterns, and code content.
     <img width="2227" height="201" alt="image" src="https://github.com/user-attachments/assets/14e87d70-0eda-41bc-b499-f175cb06ddea" />


4. **Embedding Models**  
   - Used the following pretrained NLP models to generate embeddings for code summaries:
     - **MiniLM** (`all-MiniLM-L6-v2`)
     - **DistilRoBERTa** (`stsb-distilroberta-base-v2`)
     - **MPNet** (`all-mpnet-base-v2`)

5. **Embedding Comparison**  
   - Computed **pairwise cosine similarity** matrices for each model.
   - Visualized similarities using **heatmaps**, **PCA**, **t-SNE**, and a **bar chart of mean similarities**.
     <img width="622" height="912" alt="image" src="https://github.com/user-attachments/assets/5f4f7c8f-315f-41f2-a65f-73c99660bd99" />
     <img width="702" height="918" alt="image" src="https://github.com/user-attachments/assets/c649f8e4-6d51-41ed-9f02-6a49c8f38c58" />
     <img width="641" height="386" alt="image" src="https://github.com/user-attachments/assets/42ab9b33-eaaa-4e64-8738-dbb4dda3b5e1" />

6. **Saving Results**  
   - Stored embeddings, summaries, and similarity matrices in `milestone1_results.json` for reproducibility.

---

## How to Run

1. Open the notebook or Python script in **Google Colab**.
2. Install dependencies:
   ```bash
   !pip install -q sentence-transformers scikit-learn matplotlib seaborn transformers nltk
   !python -m nltk.downloader punkt

