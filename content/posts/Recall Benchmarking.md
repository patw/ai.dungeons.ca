
+++
title = 'Recall Benchmarking'
date = '2024-01-18'
draft = false
tags = ['RAG', ' Embedding', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Recall Benchmarking: Optimizing Vector Search for RAG Chatbots

In the realm of Retrieval Augmented Generation (RAG) chatbots, benchmarking the recall of your knowledge or text chunks is critical to building an efficient and accurate AI system. Vector search technology powers this retrieval process, making it essential to optimize for both recall and accuracy in order to create a reliable and useful chatbot. This blog post will delve into the importance of vector search recall accuracy, the role of text embedding models and chunking strategies, and how to benchmark your model effectively.

## The Impact of Text Embedding Models and Chunking Strategies

The effectiveness of a chatbot's vector search functionality hinges on the selection of an appropriate text embedding model and the chunking strategy for your documents (e.g., word, PDF, HTML, or TXT). If chunks are too large, you risk losing semantic context; if they are too small, you may fail to capture the entire concept you intend to represent.

Additionally, low-dimensional embedding models may struggle to adequately represent multiple concepts in a single vector. While high-dimensional models can offer more complexity, it's essential to benchmark their accuracy before implementing them. Some large dimension models might even include dimensions representing languages you never plan on embedding.

## Benchmarking the Embedding Model with Cosine Similarity Function

As part of your Proof of Concept (PoC), you should develop a series of questions and answers and identify where they can be found within your documentation. By using a simple cosine similarity function, you can evaluate how well each question correlates with its corresponding chunk. It's also important to "red team" some irrelevant promptsto rule out false positives and ensure the accuracy of your search results.

This benchmarking process should be conducted without involving the Large Language Model (LLM) at first, as it will help you understand the performance of your vector search before integrating the LLM into the equation.

## Managing False Positives and Setting Confidence Levels

False positives—high scoring chunks that are irrelevant to a user's query—are one of the most significant challenges in achieving accurate recall accuracy. To mitigate this issue, set a confidence level (a high cosine similarity score) as a threshold for returning relevant chunks. If no chunk meets this threshold, the chatbot should respond with a message like "Sorry, I can't answer this question." This serves as the first critical guardrail against leaking underlying training data or providing hallucinated answers.

## Experimenting with Different Embedding Models

When selecting an embedding model for your RAG chatbot, start with the text-ada-002 model from OpenAI and then explore other models that perform well on HuggingFace's MT5 Leaderboard, focusing on semantic text similarity metrics. The goal is to find a combination of an embedding model and chunking strategy that delivers optimal results.

In summary, the success of your RAG chatbot relies heavily on optimizing vector search recall accuracy through careful selection of text embedding models and effective chunking strategies. By benchmarking these components thoroughly and setting appropriate confidence levels, you can ensure that your chatbot provides accurate and helpful responses to users' inquiries while preventing false positives and hallucinated answers.
 * Human Intervention: None

### Facts Used:
* Benchmarking the recall of your knowledge/text chunks is critical to building your RAG (retrieval augmented generation) chatbots.  Vector search is the technology that powers the retrieval, so we must optimize for search recall and accuracy.
* Vector search recall accuracy comes down to the text embedding model selection and your chunking strategy of your documents (word, pdf, html, txt).  If the text chunks are too large, you can lose semantic context, if it’s too small you might not capture the entire concept you are trying to represent.  If the embedding model is low dimensional it might not have the ability to represent multiple concepts in a single vector.  But also, the number of dimensions is only a rough estimate of how sophisticated the embedding model is, so you need to benchmark for accuracy.  Some really large dimension models are using dimensions to represent languages you might never need to embed!
* As part of your PoC you need to come up with a series of questions and answers, and where they can be found within your documentation.  Using this you can benchmark the embedding model with a simple cosine similarity function to see how well the question and the chunk correlate.  You should also “red team” some prompts that should not match your data to rule out false positives.  This whole process can be done without the LLM (large language model) involved at all.  
* False positives (high scoring chunks that are not relevant to the search) are the #1 observed problem with recall accuracy in vector search use cases.  You need to make sure your questions are not returning irrelevant data at high cosine similarity scores
* Not every question can be answered.  There must be a confidence level (high cosine similarity score) in the returned chunks before you send them to the LLM.  Use the scores returned from the search engine and a defined score cut-off point to prevent irrelevant chunks from being sent for question answering.  If no chunk scores well, return a message like “Sorry, I can’t answer this question”.  This is your first major guardrail against your chatbot from leaking the underlying training data or providing hallucinated answers.
* Experimenting with different embedding models is encouraged at this stage.  Start with text-ada-002 model from OpenAI, and then try models that are high on the semantic text similarity metric on the HuggingFace MTEB Leaderboard (https://huggingface.co/spaces/mteb/leaderboard).  What you want for an outcome is an embedding model and chunking combination that produce the best results.  Use some data science here!
