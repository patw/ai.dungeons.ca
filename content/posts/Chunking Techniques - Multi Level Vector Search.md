
+++
title = 'Chunking Techniques - Multi Level Vector Search'
date = '2024-02-02'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search']
categories = ['AI']
+++

 # Chunking Techniques - Multi Level Vector Search

In the realm of Retrieval Augmented Generation (RAG) use cases, selecting an appropriate chunking strategy for unstructured text documents is vital to achieving success. This blog post delves into the topic of multi-level vector search, a technique that helps combat semantic overlap or false positive issues in RAG chatbot implementations.

## Understanding Chunking and Text Embeddings

Chunks of text, sent to a text embedding model, are responsible for producing dense vectors that are then searched for similarity. The chunks returned from this search are subsequently processed by the Large Language Model (LLM) to generate answers or responses. There is no one-size-fits-all approach to text chunking; therefore, it is essential to benchmark various techniques and evaluate their recall and precision against your chosen embedding model.

## Embedding Larger Chunks of Text

The fifth installment in our series on chunking techniques focuses on the idea of embedding larger chunks of text, such as entire chapters from a document. This approach enables more precise vector searches to determine which chapter a specific chunk of text resides within. By incorporating both paragraph-level and chapter-level embeddings, we can improve recall in instances where multiple chapters contain similar topics or lexical elements.

## The Multi Level Vector Search Approach

Multi level vector search requires a two-step embedding approach to effectively handle semantic overlap. Firstly, each paragraph of the source document is embedded using a technique similar to single paragraph chunking that we have covered in previous posts. Secondly, an embedding model with a large token limit, such as OpenAI's "text-ada-002", is utilized to generate vector embeddings for entire chapters within the document.

The chapter-level embeddings provide a general semantic representation of the topics covered within each section but may not be suitable for precise fact recall or answering specific questions. In contrast, paragraph-level embeddings excel in these tasks and can accurately retrieve relevant information.

## Integrating Chapter and Paragraph Embeddings

The power of multi level vector search lies in its ability to combine both chapter-level and paragraph-level embeddings to narrow down the scope of a user's query. This process begins by querying the chapter-level embedding to identify the specific chapter that contains the topic of interest. Next, the paragraph-level embeddings are queried with a filter that only returns paragraphs from the previously identified chapter.

By employing this multi-level vector search technique, we can significantly enhance recall in situations where multiple chapters within a document may have considerable semantic overlap. This approach ensures that users receive accurate and relevant responses to their queries while minimizing the risk of false positives or off-topic suggestions.
 * Human Intervention: None

### Facts Used:
* Choosing a good chunking strategy for your unstructured text documents (pdf, word, html) is critical to the success of your RAG (retrieval augmented generation) use case.
* Chunks of text, in this case are what is sent to the text embedding model, which produces dense vectors which are searched for similarity using vector search.  Chunks returned are sent to the LLM (large language model), usually to answer questions.
* There is no one size fits all strategy to text chunking, however we have observed many different strategies in the field.  You should try each one and benchmark it for recall and precision with your embedding model of choice, or experiment with multiple embedding models against each chunking method until you get the best possible recall.
* The fifth in our series of posts about Chunking techniques we will discuss embedding larger chunks of text, such as whole chapters of a document, to allow us to vector search what chapter our chunk of text will reside in
* Multi Level Vector Search helps us with a common issue in RAG chatbot use cases, called “semantic overlap” or the false positive problem.  Multiple chunks of text might have vector embeddings that are extremely similar but in different, unrelated, parts of your original documentation.  Imagine an insurance booklet where you have paragraphs of text that cover “what to do in an accident” and another chapter that discusses your accident coverage.  These are very different concepts but share a lot of lexical similarity.
* Solving this problem requires a 2 step embedding approach:  First we embed each paragraph of our source document, similar to the Single Paragraph Chunking Technique we covered in earlier posts.  We also produce a vector embedding for the entire chapter the paragraph is contained in.
* The whole-chapter embedding will require an embedding model with a very large token limit, such as OpenAI’s “text-ada-002” model.  This will produce a vague semantic representation of what topics are contained in the chapter, but provide very poor similarity search for individual facts.
* The paragraph level embeddings do have good fact recall, and be able to answer our questions
* Multi Level Vector Search is the technique of querying the chapter level embedding to narrow down which chapter of your document contains the topic of interest. We then query the paragraph level embeddings with a filter on the vector search to say we only want to query paragraphs in the specific chapter we narrowed it down to.
* This technique allows us to get much better recall in situations where multiple chapters of a document might have a lot of semantic overlap.
