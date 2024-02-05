
+++
title = 'Chunking Techniques - Single or Multiple Paragraph'
date = '2024-01-31'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques: Single or Multiple Paragraphs

Choosing an effective chunking strategy for your unstructured text documents (PDF, Word, HTML) is critical to the success of your Retrieval Augmented Generation (RAG) use case. In RAG applications, chunks of text serve as inputs to the text embedding model, which generates dense vectors that are searched for similarity using vector search techniques. The returned chunks then get sent to a Large Language Model (LLM), usually for question-answering tasks.

Unfortunately, there is no one-size-fits-all approach to text chunking; however, various strategies have been observed in the field. It's crucial to try each strategy and benchmark it against your chosen embedding model or experiment with multiple embedding models against different chunking methods until you achieve the best possible recall.

In this post, we will discuss paragraph boundary chunking, where chunks typically consist of 1-2 paragraphs of text. This method works best for documents written in proper English and assumes that a full semantic thought or concept can be encapsulated within a single paragraph (as good writing should have). Consequently, these tend to produce better vector embeddings due to their strong, semantically defined concepts.

When using the 1-2 paragraph boundary chunking method, keep in mind that it may not be as effective on documents with less structured or poor English writing. Additionally, you'll need to consider how well your chosen LLM handles larger chunks of text.

To implement this technique, start by breaking your unstructured document into individual paragraphs using a parsing library or regular expressions. Then, apply the paragraph boundary chunking method, either by grouping consecutive paragraphs together (up to 2) or selecting single paragraphs as chunks. Finally, evaluate the quality of your vector embeddings and adjust your chunking strategy accordingly.

Remember that experimenting with various chunking methods is essential for achieving optimal results in RAG applications. By benchmarking each method against your chosen embedding model, you can determine which approach yields the best recall and precision. As you continue to refine your chunking strategy, consider exploring other simpler techniques like fixed token with overlap for your RAG use case.
 * Human Intervention: Minor.  It recommended sentence level and n-gram embedding which is a terrible idea.

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* The second in our series of posts about Chunking techniques we will discuss paragraph boundary chunking, with usually 1 to 2 paragraphs of text.
* 1-2 paragraph boundary.  This method works best on documents of proper English writing.  It assumes a full semantic thought or concept will be encapsulated in a single paragraph (as good writing should have) and you chunk on a single paragraph or 2 paragraphs.  These tend to produce better vector embeddings as they have a single, strongly semantically defined concept.
