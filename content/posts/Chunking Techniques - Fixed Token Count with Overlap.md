
+++
title = 'Chunking Techniques - Fixed Token Count with Overlap'
date = '2024-01-30'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques: Fixed Token Count with Overlap

Choosing a good chunking strategy for unstructured text documents is critical to the success of your Retrieval Augmented Generation (RAG) use case. In this blog post, we will focus on one of the most basic yet effective techniques: fixed token count with overlap. This method is widely used in RAG libraries like LangChain and LLAMAindex.

## Background

Chunks of text are sent to the text embedding model, which produces dense vectors that can be searched for similarity using vector search. Chunks returned are then sent to the Large Language Model (LLM) to answer questions. There is no one-size-fits-all approach to text chunking; however, we have observed many different strategies in the field. It's essential to experiment with various techniques and benchmark them against recall and precision using your chosen embedding model.

## Fixed Token Count with Overlap

The fixed token count with overlap method is a default chunking technique in most RAG libraries. In this approach, you define a fixed number of tokens (words) that will be used per chunk, typically 256 or 512, and specify the desired amount of overlap between adjacent chunks. This method works well when you don't know the structure of the document source upfront and rely on the LLM to reason through broken sentences and potentially irrelevant data.

This technique is particularly effective with larger, more complex LLM models as it heavily relies on their reasoning capabilities. To implement fixed token count with overlap, follow these steps:

1. Define the maximum number of tokens per chunk (e.g., 256 or 512).
2. Specify the desired overlap between adjacent chunks (e.g., 32 tokens).
3. Break down your unstructured text documents into chunks based on the defined token count and overlap.
4. Feed these chunks to the embedding model for vectorization.
5. Use the resulting dense vectors in a vector search to find similar chunks.
6. Send the retrieved chunks to the LLM for answering questions or generating responses.

## Experimentation and Benchmarking

To optimize your RAG use case, it's crucial to experiment with various chunking techniques and benchmark their performance against recall and precision metrics using your chosen embedding model. This will help you identify the best possible approach for your specific use case.

## Conclusion

The fixed token count with overlap method is a versatile and effective text chunking technique used in RAG libraries like LangChain and LLAMAindex. By defining the maximum number of tokens per chunk and the desired overlap between adjacent chunks, you can leverage the reasoning capabilities of larger, more complex LLM models to process unstructured text documents effectively. Experiment with different techniques and benchmark their performance against recall and precision metrics to optimize your RAG use case.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* The most basic text chunking strategy is fixed token count with overlap.  This is the default chunking method in most RAG libraries like “langchain” or “llamaindex”.  In this method, you define a fixed number of tokens (words) that will be used per chunk, usually 256 or 512 and how much overlap you want from the previous and next chunk.  This method works well for time when you don’t know the structure of the document source up front and want to rely on the LLM (large language model) to reason through broken sentences and possibly irrelevant data.  This relies heavily on the LLMs reasoning capability and works best with larger, more complex LLM models.
