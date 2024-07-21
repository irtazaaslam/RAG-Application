# RAG Application
This RAG application consistis of 2 parts.

Simple RAG Application (Part 1): For Part 1 we will import different types of documents such as .txt, web, and pdf. Then create a simple RAG Application using Langchain, PyPDFLoader, RecursiveCharacterTextSplitter, OllamaEmbeddings, Chroma DB, and similarity_search.

Advance RAG Application (Part 2) : For the second part we will use the same pdf document attention.pdf to create an advanced RAG pipeline with Chain and Retriver. To create this application we will be using Langchain, PyPDFLoader, RecursiveCharacterTextSplitter, OllamaEmbeddings, FAISS db, LLAMA3, as_retriver, create_stuff_documents_chain, create_retrieval_chain.

## Simple RAG Application
- Firstly we have explored different Data ingestion techniques. 
- Then worked on the pdf file to create the application, we will convert our doc into smaller chunks using RecursiveCharacterTextSplitter it takes a large text and splits it based on a specified chunk size.
- After chunking we will convert these chunks into vectors using OllamaEmbeddings and store these embeddings in a vector store. For this part we are using Chroma db as a vector store.
- We can ask questions from our RAG application using a query. It will perform a similary search and give us the related answers from our own pdf.

## Advance RAG Application using Retriever And Chain
- In part 1 we have used OllamaEmbeddings to convert the chunks into vectors. We will store those vector in a vector DB called FAISS.
- We will combine Prompts along with chain and retriver to get our desired results. We will use an open source Ollama model LLAMA3, our application will use assigned LLM and prompt template to act accoringly.

### Chain Introduction: Chains refer to sequences of calls - whether to an LLM, a tool, or a data preprocessing step.

- We will use create_stuff_documents_chain: This chain takes a list of documents and formats them all into a prompt, then passes that prompt to an LLM. It passes ALL documents, so you should make sure it fits within the context window of the LLM you are using.
- In the part 1 of this RAG application we used a technique called similarity search to query results.

For this part we will use Retriever.

### Retrievers: A retriever is an interface that returns documents given an unstructured query. It is more general than a vector store. A retriever does not need to be able to store documents, only to return (or retrieve) them. Vector stores can be used as the backbone of a retriever, but there are other types of retrievers as well.

Retrievers accept a string query as input and return a list of Document's as output.

- Now we are going to use retriever chain by combining retriver and the document chain.

### Retriever chain: This chain takes in a user inquiry, which is then passed to the retriever to fetch relevant documents. Those documents (and original inputs) are then passed to an LLM to generate a response.
