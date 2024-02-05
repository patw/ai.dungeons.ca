
+++
title = 'Chunking Techniques - Whole Page Chunks'
date = '2024-02-01'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques - Whole Page Chunks

In the realm of text processing, choosing an effective chunking strategy is crucial for the success of your RAG (Retrieval Augmented Generation) use case. Chunks of text serve as input to text embedding models that generate dense vectors, which are then used in vector search algorithms for finding similarity. These chunks are subsequently sent to LLMs (Large Language Models), often to answer specific questions.

There is no one-size-fits-all approach to text chunking; however, various strategies have emerged in the field. To optimize your RAG use case, you should test different chunking methods and benchmark their performance using recall and precision measures with your chosen embedding model or experiment with multiple embedding models against each method until achieving optimal recall.

In our series of posts about Chunking techniques, we will discuss the whole page chunking approach – its advantages and disadvantages. In this strategy, the entire page of the document is treated as a single unit, assuming that the content on each page revolves around a single subject. This method works well for certain PDF documents where each page represents a distinct topic.

It is essential to note that vector embedding models have token limits, similar to LLMs, which may prevent you from feeding an entire page into the model for vectorization. To overcome this limitation, consider using text-ada-002 from OpenAI, which offers a higher token limit (8192 tokens) for such tasks. However, keep in mind that employing whole page chunking can lead to weak semantic representation when multiple different topics are discussed on a single page.

To summarize, while the whole page chunking technique has its advantages and may work well for specific document formats, it is crucial to consider potential limitations and optimize your approach accordingly. Experiment with different strategies to find the best solution that aligns with your RAG use case's requirements, and always benchmark your results using relevant metrics such as recall and precision.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* The third in our series of posts about Chunking techniques we will discuss embedding the entire page of text, and the advantages and disadvantages of that.
* Whole page chunking.  In this method we chunk the entire page of the document at once, assuming the page itself is talking about a single subject.  This works well for some PDF documents where each page represents a different subject.  Keep in mind that vector embedding models have token limits (just like LLMs) that may prevent you from feeding an entire page into the model for vectorization.  Choose a text embedding model like text-ada-002 from OpenAI, which has a larger token limit (8192 tokens) for a task like this.  Also keep in mind that you will get a weak semantic representation if there’s lots of different topics discussed in the single page
