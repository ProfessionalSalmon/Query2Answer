# Query Answering and Summarization with Semantic Search
This project is designed to answer queries based on a `MS MARCO` dataset using semantic search, relevant sentence extraction, and text summarization. The system is capable of answering both user input queries and dataset queries by.

## 🧸How It Works
1. **Semantic Search**: `sentence-transformers`

    When a query is entered (either from the user or pre-defined in the dataset), the system generates embeddings for the query and passages and searches the dataset to find the most relevant passage.

2. **Sentence Extraction**: 
    - The selected passage is split into individual sentences using `nltk.tokenize.sent_tokenize`.
    - To extract the most relevant sentence, the system uses a `Cross-Encoder` model to rank the sentences based on their relevance to the query. The Cross-Encoder evaluates the query and sentence pairs, and the top-ranked sentences are selected for further processing.

3. **Summarization**: `pipeline("summarization", model="facebook/bart-large-cnn")`

    The extracted relevant sentences are then summarized using a `facebook/bart-large-cnn` summarization model to provide a concise answer.

4. **Result Display**: 
    
    The query, best sentences, summarized text, and similarity score between the query and the passage are displayed in a user-friendly format (i.e., pandas DataFrame).
