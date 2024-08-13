# LLaMA-2 Retrieval-Augmented Generation (RAG) System

This project showcases the implementation of a Retrieval-Augmented Generation (RAG) system using the Llama 2 language model from Meta. It focuses on loading, indexing, and querying documents to generate responses utilizing different response modes. The HuggingFace library and the Llama 2 model are pivotal components in achieving these functionalities.

## Setup

To set up the environment, ensure the following Python packages are installed:

- llama-index
- transformers
- accelerate
- bitsandbytes
- llama-index-llms-huggingface
- llama-index-embeddings-huggingface
- llama-index-program-openai
- llama-index-agent-openai
- rouge

## Loading Stage

Documents are loaded from a directory named `data` using SimpleDirectoryReader. 

## Indexing Stage

The Llama 2 model from HuggingFace is configured with quantization settings to optimize loading efficiency. Authentication is handled via an API token from HuggingFace.

## Embedding Model

Vector representations of documents are generated using the embedding model `BAAI/bge-small-en-v1.5`.

## Storing Stage

Documents are stored in a VectorStoreIndex for efficient retrieval during queries.

## Query Stage

The system supports querying of indexed documents using various response modes:

- **Default Mode**: Generates standard responses.
- **Similarity Top K**: Returns the top K most similar documents.
- **Refine Mode**: Iteratively refines responses based on additional context.
- **Compact Mode**: Provides concise and to-the-point answers.
- **Tree Summarize Mode**: Organizes information hierarchically, summarizing main points and their relationships.

Only Default and Refine modes were taken for comparison of model performance.

## Usage

To query the system, use the `query_engine` with specific queries and response modes. Results can be displayed using the `display_response` function.

## Queries
A set of QA pairs were created manually based on the information given in the collection of our dataset/PDF files.

## Evaluation Metrics
- Accuracy
- Precision
- F1 Score
- BLEU Score
- ROUGE Scores

This system demonstrates the flexibility and capability of the RAG approach using the Llama 2 model, facilitating detailed and contextual responses to diverse queries.
