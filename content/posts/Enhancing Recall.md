
+++
title = 'Enhancing Recall'
date = '2024-01-18'
draft = false
tags = ['Vector Search', ' Recall']
categories = ['Vector Search', ' AI']
+++

 # Enhancing Recall: A Comprehensive Guide to Improving Vector Search Performance in RAG Chatbots

In the world of retrieval-augmented generation (RAG) chatbots, ensuring high recall and accuracy is crucial for providing users with relevant and accurate information. This blog post delves into various strategies and techniques that can help enhance recall in vector search applications, focusing specifically on improving the quality and efficiency of text chunk retrieval.

## NumCanDidates: Striking a Balance Between Accuracy and Time

The `numCandidates` parameter in the Atlas Vector Search operator determines the number of nearest neighbors to evaluate for similarity. While low values can result in poor quality chunks, higher values increase the chances that the approximate nearest neighbor (ANN) algorithm will find something useful. However, very high values (>800) may lead to slow query performance.

To improve recall accuracy, it is recommended to set a minimum of 100-200 candidates and apply a limit of 5-10 after that for chunks sent to the large language model (LLM). Applying re-ranking techniques in memory on the app tier using manual cosine re-rank with cross encoder can boost the text chunk scores, especially when re-ranking 100-500 vectors.

## Instructor Embeddings: Leveraging LLM-Style Prompting for Better Accuracy

The Instructor family of text embedding models requires an LLM-style prompt to generate vectors. By utilizing this additional prompting strategy, you can achieve better accuracy with fewer dimensions compared to OpenAI's text-ada-002 model. This technique allows the embedding model to capture more context and nuance in your data, resulting in improved recall performance.

## Multi-Level Vector Search: Achieving Better Precision Through Contextualization

Another effective approach for enhancing recall is through multi-level vector search. By first vectorizing a larger chunk of text, such as an entire chapter, and then also vectorizing individual paragraphs, you can narrow down the context to specific sections within your documents. This method helps mitigate false positives when multiple chapters contain semantically similar paragraphs.

## Hybrid Search: Combining Text and Vector Searches for Improved Confidence

Hybrid search involves sending both text and vector searches simultaneously, allowing you to re-rank vector results where they intersect with text search results or include high-scoring text results that are missing from the vector search result set. By combining these two powerful search methods, you can increase your confidence in the relevance of the recalled chunks.

## Pre-Summarizing and Chunking: Optimizing Token Limits for Improved Recall

Pre-summarizing entire sections of your documentation using an LLM can help you work within the token limits of embedding models, making it easier to represent complex content effectively. In addition, applying this technique to any section that isn't being represented well by the embedding model, such as point form, tables, or structured data (e.g., JSON and XML), may result in improved recall accuracy.

## Adjusting Chunk Sizes: The Impact on Recall Accuracy

Changing your chunk sizes (number of tokens) can significantly impact recall accuracy and should be explored before accepting poor results. Different strategies, such as breaking down content into smaller or larger chunks, may yield better outcomes depending on the nature of your data and the specific requirements of your chatbot application.

## Continuous Benchmarking: Staying Ahead of Emerging Trends in Embedding Models

As new embedding models continue to emerge, it's essential to continuously benchmark and assess their performance against your specific data. By building reproducible tests and staying up-to-date with the latest developments in this field, you can ensure that your chatbot remains optimized for accuracy and recall over time.

In conclusion, enhancing recall in vector search applications requires a combination of strategic techniques and careful consideration of various factors. By implementing these strategies effectively, you can improve the quality and efficiency of text chunk retrieval, ultimately resulting in a better user experience for your RAG chatbot.
 * Human Intervention: Minor.  It kept changing Instructor (name of an embedding model) to Instructors.

### Facts Used:
* The numCandidates in the Atlas Vector Search $vectorSearch operator determines the number of nearest neighbors to evaluate for similarity.  Our recommendation is a minimum of 100-200 and applying a limit of 5-10 after that for chunks to send to the LLM (large language model) for your RAG (retrieval augmented generation) chatbot.  Low  numCandidates values (sometimes called K in other vector search engines) can result in poor quality chunks being retrieved.  Higher numCandidates  values will result in a better chance than the ANN (approximate nearest neighbor) algorithm will find something useful but it’s a trade off between accuracy and time.  Very high numCandidates  values (> 800) can result in slow query performance.
* Re-ranking the results in-memory on the app tier, using a manual cosine re-rank with a cross encoder can result in better text chunk scores.  Re-ranking 100-500 vectors is relatively fast for a small boost in accuracy.
* The Instructor family of text embedding models requires an LLM style prompt to generate vectors.  You can use this additional prompting strategy to get better accuracy for less dimensions than OpenAI’s text-ada-002 text embedding model
* Multi-level vector search has worked well for some customers. The idea here is to use the large token limit (8192 tokens) of text-ada-002’s embedding model to summarize a large chunk of text, like an entire chapter of a book, then also vectorize the individual paragraphs.  You run the first vector search against the “wider” context to narrow down what chapter the text is relevant to, then query vector search again to get the specific paragraph.  This has been used to guard against false positives  when multiple chapters can contain semantically similar paragraphs.
* Hybrid Search can be used to increase the confidence you have in the recalled chunks.  If you send a text search, along with a vector search. You can re-rank vector results where they intersect with text search results, or include high scoring text results that are missing from the vector search result set.  The idea here is, if the vectors and tokens are both ranking highly, it’s probably a more relevant chunk.
* Using the LLM to pre-summarize entire sections of your documentation allows you to easier work within the token limits of the embedding models.  You can vectorize the smaller summarized text, and it may even have better recall than the original.  This same technique should be applied with any section of your documents that isn’t being represented well by the embedding model, like point form, tables or even JSON and XML structured data.  Yes, you can even summarize data in mongo collections!
* Changing your chunk sizes (numbers of tokens) can have a dramatic effect on recall accuracy.  Try different chunking strategies before accepting poor results.
* Always be benchmarking!  New embedding models are appearing all the time, and your specific data might be better represented by another model.  Build reproducible tests.
