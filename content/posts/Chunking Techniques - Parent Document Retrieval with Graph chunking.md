
+++
title = 'Chunking Techniques - Parent Document Retrieval with Graph chunking'
date = '2024-02-03'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques: Parent Document Retrieval with Graph Chunking

In the realm of retrieval augmented generation (RAG) use cases, selecting an appropriate chunking strategy is paramount to the success of your text documents processing. In this blog post, we will delve into a more sophisticated technique called "Parent Document Retrieval with Graph Chunking." This method allows for the retrieval of additional context and related chunks from the same collection when answering questions.

## Background on Text Chunking

Chunks of text serve as the input to text embedding models, which generate dense vectors that are then used for vector search, comparing similarity among the chunks. These chunks are subsequently sent to large language models (LLMs) to answer questions or provide relevant information. There is no one-size-fits-all strategy for text chunking; however, it is essential to benchmark various methods against your chosen embedding model to achieve optimal recall and precision.

## Parent Document Retrieval with Graph Chunking

In previous techniques, the text chunks were directly sent to the LLM after being retrieved from the vector search. In this method, we store both the text chunk and an embedding for the chunk. However, when sending data to the LLM, we opt to utilize the entire page or even the parent document rather than individual chunks. This approach enables us to incorporate more context into our responses, thereby enhancing the accuracy of the generated answers.

## Paragraph Level Chunking with Graph Traversal

To implement this advanced technique, we will break down the source documents into paragraph-level chunks and store pointers to the preceding and subsequent paragraphs in a database like MongoDB. This allows us to leverage MongoDB's $graphLookup function after performing vector search, retrieving all related paragraphs surrounding the selected paragraph. Consequently, we can send all relevant chunks to the LLM for more contextualized responses.

### Maximum Depth Control

Setting a maximum depth parameter enables you to specify how many chunks before or after you would like to retrieve for additional context in your answers. This provides flexibility in controlling the scope of information included when providing responses, ensuring that the generated content remains relevant and concise.

In conclusion, Parent Document Retrieval with Graph Chunking is a highly effective technique for enhancing RAG use cases by incorporating more contextual information into your text chunking strategy. By leveraging paragraph-level chunks, graph traversal, and MongoDB's $graphLookup function, you can achieve improved recall and precision in your text embedding models while providing more accurate responses to user queries. As we continue to explore advanced techniques in this series, the level of sophistication will only increase, offering even greater opportunities for optimizing your RAG use cases.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* As we get further into this series, the level of sophistication of the techniques will increase.  
* In previous chunking methods in this series, the text chunk was always sent to the LLM, unmodified after retrieval.  In this method we will store the text chunk and an embedding for the chunk but we may be sending the page or even the whole parent document to the LLM instead of the individual text chunk.
* The seventh in our series of posts about Chunking techniques we will discuss paragraph level chunking while using graph traversal to retrieve the page or even whole document.
* In this method we will continue to break the source documents down into paragraph level chunks, but we will also store pointers to the previous and next paragraph giving us the ability to use MongoDB’s $graphLookup function (after $vectorSearch) to grab all the related paragraphs around the retrieved paragraph, and send all the related chunks to the LLM as well.
* This method lets us retrieve extra chunks from the same collection to provide more context for answering the question.  Setting maxDepth allows you to specify how many chunks before or after you need.
