
+++
title = 'Retrieval Augmented Generation'
date = '2024-01-16'
draft = false
tags = ['RAG', ' Grounding', ' LLM']
categories = ['AI']
+++

 # Retrieval Augmented Generation: Enhancing LLM Performance with Contextualized Information

Large Language Models (LLMs) have revolutionized the field of natural language processing, providing us with powerful tools for text generation, understanding, and reasoning. However, as with any technology, there are limitations to what LLMs can achieve on their own. One such limitation is the issue of "hallucinations", where an LLM may provide incorrect or fabricated information in response to a question that it has generalized and not retained specific details for. This blog post will explore Retrieval Augmented Generation (RAG), a technique that utilizes semantic search and augmented prompt engineering to enhance the performance of LLMs by providing them with contextually relevant information to answer questions more accurately.

## Understanding Large Language Models

LLMs are trained on massive corpora of text from various data sources, often reaching multiple trillions of tokens (words) of internet content. They combine memorization and generalization to provide information compression, which can be inherently lossy, resulting in the aforementioned hallucination phenomenon. Despite these limitations, LLMs are excellent summarization and reasoning machines that have the potential to revolutionize fields like AI-powered chatbots, virtual assistants, and content generation.

## Introducing Retrieval Augmented Generation (RAG)

RAG is a technique that leverages an LLM's strong summarization capabilities by allowing users to provide all the data required to answer a question, along with the question itself. This can be achieved through a combination of information retrieval and prompt engineering techniques. At its core, RAG aims to address the issue of hallucinations by providing contextually relevant knowledge to LLMs to help them ground their answers in reality.

## The Role of Prompt Engineering in RAG

A key aspect of RAG is prompt engineering, which involves crafting an effective prompt that includes both the user's question and any relevant data required for the LLM to provide a reliable answer. This can involve techniques such as prompt augmentation, where additional information is added to the initial question. For example, if you asked an LLM "What is my name?", providing the prompt "Hello, my name is Patrick. What is my name?" would help ground the response and prevent hallucinations.

## Semantic Search for RAG

A major challenge in implementing RAG is retrieving relevant information from vast databases or knowledge repositories to include in the LLM's prompt. Traditional database techniques and simple lexicographical searches may not be effective, as users do not typically ask questions that match database query formats. Instead, semantic search is a more suitable approach for RAG implementations, as it allows the retrieval of information based on dense vector similarity. This enables the retrieval of chunks of knowledge that are semantically similar to the user's question, providing contextually relevant information to the LLM without relying solely on lexical matching.

## Workflow for RAG

The workflow for implementing RAG involves several steps:

1. Intercepting the user's prompt and sending it to a vector search engine.
2. Retrieving a fixed number of results (typically 3-10) from the search engine.
3. "Prompt stuff" these retrieved results into the LLM prompt, along with the original question.
4. Running the augmented prompt through the LLM to receive a grounded answer based on the contextually relevant information provided in the prompt.

## Conclusion

Retrieval Augmented Generation (RAG) is an innovative technique that harnesses the power of semantic search and prompt engineering to enhance the performance of large language models by providing them with contextually relevant information to answer questions more accurately. By addressing the issue of hallucinations and improving the grounding of LLM responses, RAG has the potential to revolutionize the way we interact with AI-powered chatbots, virtual assistants, and content generation tools. As we continue to explore the possibilities of RAG, it is essential to focus on refining data ingestion, prompt engineering, and text embedding models for optimal performance and accuracy in our LLM implementations.
 * Human Intervention: None

### Facts Used:
* Large Language Models (LLMs) are trained on massive corpus of text from various data sources
* This can be up to multiple trillions of tokens (words) of text from the internet
* LLMs are a combination of memorization and generalization and are a type of information compression
* The information compression is inherently lossy and not all details are retained.  If you ask an LLM a question that it has generalized and not retained details for it can either tell you it doesn’t know (ideal answer) or worse make up an answer.  This is called a hallucination.
* LLMs are excellent summarization and reasoning machines
* Augmented Generation takes advantage of an LLMs strong summarization capability by allowing you to provide all the data required to answer the question, along with the question itself.  If you combine that with an information retrieval mechanism you have Retrieval Augmented Generation or RAG.
* A simple example is putting something in a prompt like “Hello my name is Patrick.  What is my name?”  This is the most basic example of a prompt augmentation technique.
* In a perfect world you could put all your knowledge and data in a single document and provide that whole document in the LLM prompt to answer questions. This is slow and expensive with our current LLM technology.
* Retrieving chunks of data from your own data sources solves this issue.  It allows you to provide these chunks of knowledge to the LLM, in the prompt to get it to answer questions.
* Retrieving information is difficult.  Users don’t ask questions that look like SQL or MQL style queries.  You can’t rely on traditional database techniques.
* Lexical search is better, but you need to rely on the user's question having tokens (words) that match something in the lexical search index.  This is also not optimal.
* Semantic search is a good match for the problem space because it allows you to search, semantically, using dense vector similarity, for chunks of knowledge that are similar to the question.
* So the workflow for RAG is to intercept the users prompt, send it to a vector search engine, get a fixed number of results (usually 3-10) and “prompt stuff” these results into the LLM prompt, along with the question.  The LLM then has all the information it needs to reason about the question and provide a “grounded” answer instead of a hallucination.
* The real complexity in RAG solutions is in how to ingest your data, how to chunk it, what text embedding model works best for your use case, the prompt engineering that nets you the most reliable and accurate answers and finally the guard rails that go around the inputs and outputs to prevent the LLM from providing undesirable answers.  We will cover all these topics in future posts.
