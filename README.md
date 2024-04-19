# Semantic Search Engine

This project is a semantic search engine that uses BERT-based SentenceTransformers to generate embeddings from subtitle documents. The search engine ingests, preprocesses, and stores data in ChromaDB to enable efficient and accurate semantic search, providing users with relevant results based on their search queries.

## Features

- **Semantic Embeddings**: Utilizes BERT-based SentenceTransformers to generate embeddings for documents and queries.
- **Data Preprocessing**: Cleans and preprocesses subtitle documents by converting text to lowercase, removing unnecessary text, and formatting data for storage.
- **ChromaDB Storage**: Stores embeddings in a ChromaDB database for efficient retrieval and querying.
- **Cosine Similarity**: Calculates cosine similarity between document embeddings and query embeddings to find the most relevant results.
- **User-Friendly Query Interface**: Accepts user queries and returns the top 10 most relevant documents based on similarity scores.

## Installation

To run this project, you will need the following prerequisites installed:

- **Python 3.x**
- **Required Python packages**: `pandas`, `tqdm`, `chromadb`, and `SentenceTransformers`

To install the required packages, use the following command:

```bash
pip install pandas tqdm chromadb sentence-transformers
```


## Usage

### Data Loading and Preprocessing

- Load the data from a CSV file using pandas.
- Perform necessary preprocessing, such as converting text to lowercase and removing unnecessary text.

### Embedding Creation and Storage

- Use the `SentenceTransformerEmbeddingFunction` from SentenceTransformers to create embeddings for the documents and queries.
- Store the embeddings in a ChromaDB database.

### Search Function

- The search function takes a user query as input, creates a query embedding, and calculates similarity scores between the query embedding and document embeddings.
- It returns the top 10 most relevant documents based on similarity scores.

### Running the Search

- Enter the user's search query when prompted.
- The search engine will display the most relevant documents along with their similarity scores and document names.

## Database Information

The database contains a sample of 82,498 subtitle files from opensubtitles.org. Most of the subtitles are from movies and TV series released after 1990 and before 2024.

- **Database File Name**: `eng_subtitles_database.db`
- **Database Table**: The database contains a table called 'zipfiles' with three columns:
    - `num`: Unique Subtitle ID reference for www.opensubtitles.org
    - `name`: Subtitle File Name
    - `content`: Subtitle files compressed and stored as a binary using 'latin-1' encoding.

You can use the `num` column to get more details about each subtitle by going to the following link:
[https://www.opensubtitles.org/en/subtitles/{num}](https://www.opensubtitles.org/en/subtitles/{num})
Replace `{num}` with the Unique Subtitle ID.

**Note**: Only 30% of the data from the database was used for this project.

## Examples

The provided code demonstrates how to perform a semantic search using the search engine. The user is prompted to enter a search query, and the engine returns the top 10 most relevant documents.

## Contributing

Contributions to the project are welcome. Please follow the standard GitHub process for contributing.

## License

This project is open-source and available under the GPL License.
