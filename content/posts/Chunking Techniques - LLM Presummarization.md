
+++
title = 'Chunking Techniques - LLM Presummarization'
date = '2024-02-05'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques - LLM Presummarization

Choosing a good chunking strategy for unstructured text documents is crucial to the success of your Retrieval Augmented Generation (RAG) use case. In this post, we will discuss the use of Large Language Models (LLMs) for pre-summarizing structured data, with the aim of producing semantically rich paragraphs that are ideal inputs for text embedding models and semantic search recall.

## The Challenges of Structured Data

Creating dense vector embeddings with structured data like XML and JSON often results in weak embeddings due to repetitive keys and control characters, which can cause poor recall and precision when performing semantic searches. Similar issues can be encountered with tabular data, point form data, tables of contents, and appendixes found in regular documents. In this post, we will focus on JSON documents specifically.

## LLM Pre-Summarization Method

To address these challenges, we propose using the LLM pre-summarization method, where your original JSON document is fed to the LLM, asking for a one-paragraph summary of the record itself. The output of this summarized record is then sent to the text embedding model for vectorization. This approach can provide significantly improved recall and precision compared to other chunking methods we have discussed in previous posts.

## Cost Considerations

The downside of the LLM pre-summarization method is its cost, as running an entire set of structured or unstructured data through the LLM for summarization can be expensive, especially when using commercial models like OpenAI's GPT-4. To mitigate costs, we recommend testing less expensive alternatives such as GPUs or services like Mistral.ai and the "mistral-tiny" model.

## Future Trends in Chunking Strategies

For projects with larger budgets, LLM pre-summarization will likely be the best choice for chunking strategies. In the future, almost all use cases will require some level of data summarization like "Fact Synthesis" mentioned earlier in this series. By employing techniques such as LLM pre-summarization, you can better align structured data with text embedding models, enabling more effective semantic search capabilities against structured data.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* As we get further into this series, the level of sophistication of the techniques will increase.  
* In previous chunking methods in this series, the text chunk was always sent to the LLM, unmodified after retrieval.  In this method we will use the LLM itself to pre-summarize the source text.  This ensures that if the data is structured, poorly worded or overly verbose you can output a semantically rich paragraph of english text, which is the ideal input for a text embedding model and semantic search recall.
* The ninth in our series of posts about Chunking techniques we will discuss pre-summarizing structured data, using an LLM for the purpose of producing very strong text embeddings.
* Creating dense vector embeddings with structured data like XML and JSON tends to produce really weak embeddings that suffer from poor recall and even worse precision.  This happens because structured data has lots of repeating keys and control characters.  Text embedding models tend to perform best against semantically rich paragraphs of plain english text.
* This same problem can happen with tabular data, point form data, tables of content and appendixes on regular documents as well.  In this blog post we will address JSON documents specifically.
* Using the LLM pre-sum method, you will feed your original JSON document to the LLM asking for a one paragraph summary of the record itself.  The output of this record should be sent to the text embedding model for vectorization.  This summarized version of the record will have dramatically better recall and precision against natural language queries/prompts than any other chunking method we’ve discussed in this series.
* The downside of LLM pre-sum is the cost.  You need to run your entire set of structured or unstructured data through the LLM to summarize it first.  This can be quite expensive if you’re using commercial LLMs like GPT4 from OpenAI.  Test with the less expensive GPT3-turbo models first to see if the summaries it produces are good enough for your use case.  Even better, try services like Mistral.ai and the “mistral-tiny” model, which are 10x cheaper than even the GPT3-turbo model.
* If money and budget is not a concern for your project, this will be the best possible choice for chunking strategies.  In the future, almost all use cases will require some level of data summarization like the “Fact Synthesis” blog post from earlier in this series.
* This technique should provide a better match between structured data and text embedding models, allowing you to perform semantic search against structured data.
