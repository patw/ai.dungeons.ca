
+++
title = 'Chunking Strategy'
date = '2024-01-18'
draft = false
tags = ['RAG', ' Chunking', ' LLM']
categories = ['AI']
+++

 # Chunking Strategy: A Comprehensive Approach to Text Vectorization

Text vectorization is an essential step in various Natural Language Processing (NLP) tasks, such as information retrieval, question answering, and sentiment analysis. One critical aspect of text vectorization is chunking, or breaking down the source documents into smaller, manageable pieces for processing. This blog post will delve into the intricacies of chunking strategies, highlighting various approaches and their implications on model performance.

## The Importance of Chunking in Text Vectorization

Chunking is an iterative process involving experimentation to find the optimal way to break down source documents like Word, PDF, Text, or HTML files. These documents can be chunked into single sentences, fixed-length bytes, multiple sentences, paragraphs, pages, chapters, or even entire documents. A suitable starting point for this endeavor is utilizing the chunking functionality provided by libraries such as LlamaIndex or LangChain. However, it may be necessary to evolve and adopt more sophisticated methods based on specific project requirements.

## Token Limits in Text Embedding Models

Most text embedding models have a maximum token limit of 512 tokens, with exceptions like OpenAI's text-ada-002 model offering an extended limit of 8192 tokens. These constraints significantly impact the chunking strategy as they directly affect the semantic representation and recall accuracy. While it might be tempting to fill up the entire token limit for models with higher thresholds, it is essential to consider that smaller amounts of text tend to capture more precise semantic details.

## Improving Recall Accuracy through Recursive Chunking

Recursive chunking is an emerging technique aimed at enhancing recall accuracy by breaking down larger chunks of text into smaller pieces progressively. This method involves vectorizing a more extensive segment of text, splitting it in half, and then vectorizing those parts again. Real-world results demonstrate that this approach can improve recall accuracy by up to 10-20%, although it comes with the cost of generating additional vectors (seven, in particular). To implement this technique, duplicate the original larger chunk of text in each Mongo document before sending it to a Large Language Model (LLM) for evaluation. Afterward, use an MQL $group stage operation to remove duplicates.

## Chunking and Sending Text to LLMs

It is crucial to consider that the chunked data might not be identical to the text submitted to the LLM for evaluation. In many cases, it may be beneficial to send a larger amount of text, such as an entire paragraph surrounding a specific sentence, particularly when employing sentence-level chunking. This approach ensures that the LLM has sufficient context to evaluate the question accurately and effectively. Be mindful of the token limits imposed by different LLMs (generally between 4,000 and 8,000 tokens) and use as much text as necessary without exceeding these constraints.

## Pre-Summarizing Non-Textual Data

Not all text yields useful vectors for embedding models, particularly when dealing with tabular or point form data structures. A viable solution to this issue is pre-summarization. By sending such non-textual content to the LLM for summarization into a paragraph of semantically rich text, you can improve the likelihood of generating meaningful vectors. Text embedding models perform best when processing well-structured English texts.

## Tailoring Chunking Strategies for Different Document Types

The chunking strategy required for vectorizing source documents will vary depending on their structure. For instance, spreadsheets, CSV files, or structured data (JSON or XML) will necessitate different approaches compared to unstructured Word and PDF documents or HTML files. In the former case, it may be challenging to employ the same workflow as for the latter, requiring adjustments and customizations according to each document type's specific characteristics.

In conclusion, the chunking strategy plays a critical role in determining the effectiveness of text vectorization and subsequent NLP tasks. By carefully considering token limits, recursive chunking, sending the appropriate amount of text to LLMs, pre-summarizing non-textual data, and tailoring strategies for different document types, one can optimize their text processing workflows and achieve better model performance and accuracy.
 * Human Intervention: None

### Facts Used:
* There is no right answer for chunking your source documents (Word, PDF, Text, HTML).  This is an iterative process of experimentation where the end result could be chunked by a single sentence, fixed byte length, multiple fixed sentences, whole paragraph, multiple paragraph, whole page, whole chapter, or even whole document.  A good place to start is the chunking functionality in llamaindex or langchain, but you may need to evolve to more sophisticated methods.
* Most text embedding models are limited to 512 tokens (words or word parts).  The text-ada-002 model from OpenAI is the exception at 8192 tokens.  These limits will greatly influence the chunking strategy.  
* Recall accuracy does not seem reliable at the edge of the token limit of the embedding model.  The naive strategy is to just stuff the text up to 8192 tokens (e.g. text-ada-002) and hope for the best, but smaller amounts of text seem to capture the semantic details better. 
* However, you can also use a large token limit to get a vague semantic representation of a large chunk of text for multi-level vector search, so it depends on the requirement. See Recall Benchmarking post for more details.
* Another emerging technique to improve recall accuracy is recursive chunking:  Vectorize a larger chunk of text, split that text in half then vectorize those pieces, then split in half again and vectorize again.  Real world results show up to 10-20% better accuracy, at the (higher) cost of 7 vectors.  Each mongo document would duplicate the larger chunk of text, to send to the LLM (large language model) and you would perform an MQL $group stage to remove duplicates.
* Your chunked data might not be what you stuff into the prompt for the LLM to evaluate. In many cases you might want to send a larger amount of text.  This is especially true if you decide to chunk on a sentence level.  It’s much better to send the entire paragraph surrounding the sentence, as it could contain more details for the LLM to evaluate against the original question.  If you chunk on a paragraph, it might be useful to send the surrounding paragraphs.  The LLM needs enough text to answer the question, what you vectorize might not be enough.  Be aware of the token limit on the LLM model you are using (usually 4-8k) and use as much as you need for accuracy.
* Not all text will produce useful vectors.  Tables and point forms can produce unexpected results in the text embedding model.  One solution to this is pre-summarization:  You can send these tables or point form lists to the LLM to pre-summarize into a paragraph of semantically rich text, and then vectorize on that text.  Embedding models tend to perform best with semantically rich english text.
* Depending on the structure of the documents, different chunking strategies may be needed.  If you are attempting to vectorize spreadsheets, csv files or structured data (json or xml), you will probably not be able to use the same workflow as your unstructured Word and PDF and HTML docs. 
