
+++
title = 'Chunking Techniques - Static Text Generation from Structured Data'
date = '2024-02-04'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques: Static Text Generation from Structured Data

Choosing a good chunking strategy for your unstructured text documents is critical to the success of your Retrieval Augmented Generation (RAG) use case. Chunks of text, in this context, are the segments that are sent to the text embedding model, which produces dense vectors that are searched for similarity using vector search. The chunks returned are then sent to the Large Language Model (LLM), typically to answer questions.

There is no one-size-fits-all strategy to text chunking; however, we have observed many different strategies in the field. You should try each approach and benchmark it for recall and precision with your chosen embedding model or experiment with multiple embedding models against each chunking method until you achieve the best possible recall.

As we delve deeper into this series, the level of sophistication of the techniques will increase. In previous chunking methods in this series, the text chunk was always sent to the LLM without modification after retrieval. In this method, we will use a script to summarize structured data, such as a JSON document from a Mongo collection, into a paragraph of English text. We embed the summarized text but send the original JSON structured document to the LLM prompt to answer the user's question.

In this eighth post in our series about Chunking techniques, we will discuss pre-summarizing structured data using a script and running the summary text through a text embedding model for vector search retrieval later. Creating dense vector embeddings with structured data like XML and JSON often produces weak embeddings that suffer from poor recall and even worse precision due to the abundance of repeating keys and control characters, which are not semantically rich in plain English text. This same problem can occur with tabular data, point-form data, tables of contents, and appendixes on regular documents as well.

Converting a JSON document into a paragraph of English text requires a writing script that consumes all the fields and tries to tell a story about the data. Typically, this is done using a story template where the values of the fields get filled in. This process is similar to creating a MadLib, where the nouns and verbs are the values in the source document. The story output will then be run through your text embedding model to store the dense vectors that represent it. Additionally, you will store the original Mongo document ID for the source record along with it, so when you perform a vector search match afterward, you can retrieve the original document and send it to the LLM as part of the prompt augmentation.

This technique should provide a better match between structured data and text embedding models, allowing you to perform semantic search against structured data. This approach is also significantly cheaper to implement than LLM Structured Data Summarization, which we will discuss in a future blog post.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* As we get further into this series, the level of sophistication of the techniques will increase.  
* In previous chunking methods in this series, the text chunk was always sent to the LLM, unmodified after retrieval.  In this method we will use a script to summarize structured data, like a JSON document from a Mongo collection, into a paragraph of english text.  We embed the summarized text, but we will send the original JSON structured document to the LLM prompt to answer the user's question. 
* The eighth in our series of posts about Chunking techniques we will discuss pre-summarizing structured data, using a script, and running the summary text through a text embedding model for vector search retrieval later.
* Creating dense vector embeddings with structured data like XML and JSON tends to produce really weak embeddings that suffer from poor recall and even worse precision.  This happens because structured data has lots of repeating keys and control characters.  Text embedding models tend to perform best against semantically rich paragraphs of plain english text.
* This same problem can happen with tabular data, point form data, tables of content and appendixes on regular documents as well.  In this blog post we will address JSON documents specifically.
* Converting a JSON document into a paragraph of english text requires a writing script that consumes all the fields and tries to tell a story about the data.  Typically this is done with a story template, where the values of the fields get filled in.  This is similar to creating a MadLib, where the nouns and verbs are the values in the source document.
* The story output will then be run through your text embedding model to store the dense vectors that represent it.  You will also store the original mongo document ID for the source record along with it, so when you perform a vector search match afterwards you can retrieve the original document and send it to the LLM, as part of the prompt augmentation.
* This technique should provide a better match between structured data and text embedding models, allowing you to perform semantic search against structured data.
* This technique is also significantly cheaper to implement than LLM Structured Data Summarization, which we will talk about in a future blog post.
