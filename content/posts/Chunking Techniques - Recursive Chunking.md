
+++
title = 'Chunking Techniques - Recursive Chunking'
date = '2024-02-02'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques - Recursive Chunking

In the realm of text processing, selecting an appropriate chunking strategy is paramount for a successful Retrieval Augmented Generation (RAG) use case. The primary purpose behind this technique is to segment unstructured text documents (such as PDFs, Word files, or HTML pages) into manageable pieces that can be fed to the Text Embedding model. This model then produces dense vectors for each chunk, which are subsequently searched based on similarity using vector search algorithms. The retrieved chunks are sent to a Large Language Model (LLM), typically for question-answering purposes.

When it comes to text chunking strategies, there is no one-size-fits-all solution. Different methods might yield varying levels of recall and precision depending on the specifics of your project. It's crucial to experiment with different strategies, benchmark them against each other, and determine which combination offers the best performance with your chosen text embedding model.

In this blog post, we will delve into one such chunking technique: **Recursive Chunking**. This method has been observed to produce stronger recall results in vector search compared to other popular strategies such as token limit with overlap. The recursive approach involves dividing a single page of text into smaller chunks at multiple levels, resulting in a total of seven embedding vectors per page.

The process begins by creating an embedding at the page level. This initial step may produce a vague semantic representation in the vector space, depending on the question being asked. To refine this representation and improve recall, the next stage involves splitting each full page into two halves, with separate embeddings generated for the top and bottom parts of the page.

The recursion continues as we further subdivide these halved sections into quarters, generating more precise embeddings for each quarter. This process generates seven total dense vector embeddings per page, each potentially performing better or worse than others depending on the specifics of the query. The underlying principle behind this technique is that by representing the same data multiple times in different ways, we can achieve better recall rates overall.

Recursive Chunking has become one of the default chunking methods in popular libraries such as "langchain" and "llamaindex". Its adoption has been driven by its proven effectiveness compared to alternative strategies like token limit with overlap. This technique offers a promising solution for those seeking improved performance in their RAG applications, particularly when working with large amounts of unstructured data.

In summary, recursive chunking is an innovative and effective approach for segmenting text documents into smaller chunks suitable for embedding and vector search operations. Its ability to produce multiple embeddings per page can significantly improve recall rates, making it a valuable asset in any developer's toolkit. As with any technique, however, it's essential to experiment with different strategies and find the one that works best for your specific use case.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* The sixth in our series of posts about Chunking techniques we will discuss splitting a single page of text in half, then in half again to produce 7 embeddings per page.  This method is similar to our first method, token limit with overlap but has proven to produce stronger recall in vector search
* Recursive chunking takes advantage of the idea that different text chunk sizes can produce better or worse recall, depending on the text embedding model.
* In this method you will split your documents up page by page, and produce an embedding at the page level.  This will probably produce a vague semantic representation in the vector space, depending on the question.
* We then split the page in half, embedding the top and bottom halves at the middle part of the page.  This should produce slightly stronger embeddings.
* We take those 2 halves and split them again in half, embedding on the quarter of the page of text.  Producing even stronger embeddings, but potentially missing some of the context the longer page could contain.
* This technique produces 7 total dense vector embeddings for vector search, and each embedding may perform well or poorly depending on the question.  The idea is that the same data is represented multiple ways, in the hope that you will get better recall
* This method is one of the new default chunking methods in the “langchain” and “llamaindex” libraries and has proven to be better than the token limit with overlap chunking method.
