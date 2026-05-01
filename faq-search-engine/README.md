# 🔍 Semantic FAQ Search Engine

A local-first Information Retrieval system demonstrating the **Vector Space Model (VSM)** and **TF-IDF ranking**.

## 🧬 IR Core Concepts

### 1. Tokenization & Normalization
The engine processes raw text by:
- Converting to lowercase.
- Removing non-alphanumeric characters.
- Filtering out **Stop Words** (non-informative terms like 'the', 'is', 'at').

### 2. The Inverted Index
Instead of scanning every document for every query, the engine uses an inverted index ($Term \rightarrow DocID$). This reduces search complexity from $O(N \cdot M)$ to $O(Term\_Count)$.

### 3. TF-IDF Weighting
- **Term Frequency (TF):** Measures how often a word occurs in a document.
- **Inverse Document Frequency (IDF):** Penalizes common words and boosts rare, high-information words (e.g., "calculus" vs "computer").

### 4. Cosine Similarity
Search results are ranked by calculating the cosine of the angle between the Query Vector and the Document Vector in N-dimensional space.
