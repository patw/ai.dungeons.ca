
+++
title = 'Fact Synthesis - A Powerful Technique for Augmentation'
date = '2024-01-25'
draft = false
tags = ['Facts', ' RAG', ' Grounding', ' LLM']
categories = ['AI']
+++

 # Fact Synthesis: A Powerful Technique for Augmentation

The use of large language models (LLMs) has become increasingly prevalent in the industry, with retrieval augmented generation (RAG) emerging as a reliable method to achieve strong results from these models. Current techniques involve "chunking" documents into individual paragraphs or fixed numbers of words and running them through text embedding models for vector search later. While effective, this approach relies heavily on the ability of the embedding model to accurately represent semantic concepts within the chunks of text and requires constant experimentation and benchmarking for optimal results.

To address these limitations and improve the process of augmenting LLMs, we propose a new method: fact synthesis. This technique involves extracting individual facts from raw source texts and summarizing them with the assistance of LLMs. The first step in this process is to reduce the source data into individual facts, which can then be stored in a transactional data store like MongoDB.

Facts can be grouped together into "chunks" for vectorization using text embedders such as text-ada-002. When a user poses a question, it too can be vectorized and a simple similarity search performed to retrieve the relevant facts. The LLM can then generate an answer based on these retrieved facts.

Fact grouping into chunks can be achieved through several methods:

1. **Fixed number of facts per chunk:** Generate chunks containing a fixed number of facts, with no semantic boundaries between them. This approach is straightforward but may result in less coherent information.
2. **Topic-grouped facts:** If metadata such as document names or chapters is available, it can be used to group related facts together based on context. This method allows for larger chunks as the embedding models represent semantically similar facts within a single knowledge domain.
3. **Semantically similar facts:** Grouping facts by their similarity enables the generation of large text chunks with fewer embedding vectors. However, this method is computationally expensive and may not be feasible for all use cases.

By adopting fact synthesis in your own application, you can leverage the power of LLMs while minimizing their reliance on irrelevant information within text chunks. The blog system FactWeave, for example, employs a different technique called "fact expansion" to generate its content. However, by exploring and implementing fact synthesis, developers can create more efficient and effective augmentation systems tailored to their specific needs.

To get started with fact synthesis, refer to the following GitHub examples:

* [Fact Synthesis Example](https://github.com/patw/ExternalBrain)
* [Fact Expansion Example (FactWeave)](https://github.com/patw/FactWeave)
 * Human Intervention: None

### Facts Used:
* RAG (retrieval augmented generation) has emerged as the most reliable technique for getting strong results from LLMs (large language models)
* The current state of the industry is “chunking” documents. Word, PDF, HTML and other unstructured data sources are chunked into individual paragraphs or fixed numbers of words.  These chunks are then run through a text embedding model which produces vectors and those vectors are stored in a vector search engine for retrieval later.  The chunks we retrieve will be sent to the LLM prompt as part of the augmentation process.  This lets the LLM provide grounded answers to users' questions with retrieved data (chunks).
* This technique relies heavily on the embedding model’s ability to represent the semantic concepts in the chunk of text, which can be hit or miss.  You need to experiment and benchmark to get good results.
* It also relies on the LLMs ability to reason through the irrelevant text in the chunk, because you will not always have a perfect chunk of text with only the concepts required to answer the question using RAG
* We propose a new method of chunking with only point form, individual facts extracted from the raw source text and summarized by the LLM itself.  This is fact synthesis
* The first step in the process is to reduce the source data (usually blobs of text) into individual facts.  These facts can then be stored individually in a transactional data store like MongoDB
* Facts can be grouped together into a “chunk” and the chunk can be run through a text embedder model like text-ada-002 to generate vectors.  When a user provides a question, this question can be vectorized as well and then a simple vector similarity search can be done to retrieve the facts relevant to the question, for the LLM to provide an answer.
* Grouping facts into chunks can be done though a few methods:  1) Fixed number of facts per chunk.  Generate the chunks with a fixed number of facts, with no real semantic boundary between the facts.  2) Topic grouped facts.  If you have topic metadata (document name, document chapter) you can group the facts together by the context they were found in.  This should allow you to group more facts together per chunk because the embeddings are representing facts that should be covering a single topic or knowledge domain  3) Semantically similar facts.  You can group facts by how similar they are to other facts allowing you to generate very large text chunks with very few embeddings.  This method will be the most compute expensive to generate but provides a large reduction in vector storage.
* Call to action:  Try Fact Synthesis in your own use case!  This blog system (FactWeave) actually uses the opposite technique (Fact Expansion) to generate these blog posts.
* See the following github example for Fact Synthesis:  https://github.com/patw/ExternalBrain
* See the following github example for Fact Expansion:  https://github.com/patw/FactWeave
