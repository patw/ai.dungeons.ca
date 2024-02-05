
+++
title = 'Atlas Vector Search Collection Modelling'
date = '2024-01-18'
draft = false
tags = ['RAG', ' Embedding', ' MongoDB', ' Vector Search', ' Atlas']
categories = ['AI', ' Database Design', ' Search']
+++

 # Atlas Vector Search Collection Modeling: Designing for Optimal RAG Chatbot Performance

In the world of retrieval augmented generation (RAG) chatbots, designing Mongodb collections to support vector search plays a crucial role in achieving optimal performance. This blog post will guide you through the essential factors to consider when modeling your MongoDB collections for efficient vector search, including text chunking strategy and query filters. We'll also discuss the importance of identifying different vector field names to facilitate benchmarking and storage of multiple vectors within a document.

## Text/Knowledge Chunking Strategy

To support vector search in your RAG chatbots, you must first determine an effective text or knowledge chunking strategy. This involves breaking down the source documents into smaller, manageable chunks of text that can be indexed and queried efficiently. The choice of chunk size will depend on factors such as the complexity of the information and the specific use case for your chatbot.

## Query Filters

A well-designed query filter is essential to ensure that only relevant results are returned by the vector search algorithm. Each field you need to filter on should be included in the vector search index, along with the chunk text and the resulting vector output of the text embedding process. This will enable your chatbot to retrieve accurate and precise information from the MongoDB collection during RAG interactions.

## Storing Different Text for LLMs

In some cases, you may want to store different text for sending to the large language model (LLM) in the RAG process than the text used for vector embedding. For instance, pre-summarization techniques can be employed to improve recall and precision of semantic search while still providing the original source document text to the LLM. This dual approach ensures that your chatbot can provide accurate responses based on both summarized and full-text information.

## Identifying Vector Field Names

To facilitate benchmarking different chunking and embedding strategies, it is crucial to assign unique vector field names that identify which embedding model was used to generate the vector. For example, "content_embedding_text_ada_002" represents the OpenAI text-ada-002 model. This naming convention will help you track the performance of different models and make informed decisions about optimizing your RAG chatbot's search capabilities.

## Scaling MongoDB Atlas Cluster for Vector Storage

As vector search collections can quickly grow in size, particularly with high-dimensional models like text-ada-002 (1536 dimensions or nearly 12kb of floating point numbers per vector), it is essential to plan ahead and configure your MongoDB Atlas cluster accordingly. By sizing up the cluster to accommodate the total number of vectors you intend to store multiplied by the total number of documents, you can ensure that your RAG chatbot maintains optimal performance and responsiveness even as the data volume grows over time.

In conclusion, designing an efficient MongoDB collection for vector search in RAG chatbots requires careful consideration of text chunking strategy, query filters, differentiation between LLM input text, and unique vector field names to track model performance. By following these best practices and planning for scalability, you can create a powerful, reliable, and responsive RAG chatbot that delivers accurate information to users in real-time.
 * Human Intervention: None

### Facts Used:
* Designing MongoDB collections to support vector search, for your RAG (retrieval augmented generation) chatbots requires thinking about your text/knowledge chunking strategy and your query filters.
* Every field you need to filter on will need to be included in the vector search index, along with your chunk text and the vector output of the text embedding.
* It’s also possible you’ll want to store different text for sending to the LLM (large language model) in the RAG process than the text you are embedding on.  You might be using pre-summarization techniques to get better recall and precision on your semantic search, but still want to send the original text from the source document to the LLM
* Come up with a vector field name that identifies which embedding model you used to generate the vector, for example:  content_embedding_text_ada_002 to represent the OpenAI text-ada-002 model.  This will become important later when you are benchmarking different chunking and embedding strategies and are storing multiple vectors in your mongo document.
* Warning:  These collections can get quite large!  With models like text-ada-002 being 1536 dimensions, this is nearly 12kb of floating point numbers!  Plan ahead and size up your Mongo Atlas cluster large enough to handle the total number of vectors you want to store multiplied by the total number of documents.
