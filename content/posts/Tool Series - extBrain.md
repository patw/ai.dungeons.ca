
+++
title = 'Tool Series - extBrain'
date = '2024-02-12'
draft = false
tags = ['AI Tools', ' Vector Search', ' Python']
categories = ['AI']
+++

 # Tool Series - extBrain: Your External Brain for Building Another You

https://github.com/patw/ExternalBrain

In our ongoing series exploring various tools to build Generative AI applications, we present the eighth tool in the lineup: *extBrain*. This innovative platform allows you to tap into a powerful knowledge management system designed specifically for question answering. By leveraging advanced techniques such as Fact Synthesis and Retrieval Augmented Generation (RAG), extBrain enables efficient storage, vector storage, and precise semantic search capabilities. In this blog post, we'll delve into the technical aspects of *extBrain* and how it can transform your AI application development process.

## A Brief Overview of Fact Synthesis

At the core of extBrain lies its ability to break down large text articles into individual facts using Fact Synthesis. This process involves reducing textual data into a structured format (facts), making it easier for machines to understand and process information. By storing these facts in Mongo collections alongside metadata such as the source, context, and timestamp, extBrain can provide authoritative answers based on up-to-date knowledge sources.

## Grouping Facts into Semantically Relevant Chunks

One of the key advantages of using extBrain is its ability to group facts into chunks of text. This can be achieved through various methods, including fixed numbers of grouped facts or more advanced techniques like context-based grouping and semantic similarity matching. By organizing facts into relevant groups, extBrain ensures that users receive accurate responses tailored to their specific inquiries.

## Leveraging RAG for Enhanced Question Answering

RAG (Retrieval Augmented Generation) systems  are common in the AI industry. These systems break down source documents such as PDF, Word, or HTML files into smaller text blobs and perform text embedding to generate dense vectors. ExtBrain takes this concept one step further by focusing exclusively on grouping facts together, resulting in a more efficient use of resources and improved vector search accuracy.

## Using Semantically Similar Facts for Larger Text Chunks

By grouping semantically similar facts into larger text chunks, extBrain enables users to ask broader questions while still maintaining high recall rates. This approach ensures that relevant information is readily available without compromising the overall efficiency of the system.

## A Second You: The Power of Your External Brain

ExtBrain's primary goal is to act as an extension of your own knowledge and cognitive abilities. By ingesting all your relevant data, extBrain can provide authoritative answers on demand, allowing you to work smarter instead of harder. This innovative approach to AI application development has the potential to revolutionize how we approach problem-solving and information retrieval.

## Multiple Front End Options for Easy Access

To make it even more convenient for users, extBrain offers multiple front end options for asking questions, including a website, a Discord bot, and a Slack bot. These intuitive interfaces allow you to access your external brain from virtually anywhere, making it simple to retrieve accurate information whenever you need it.

## Managing Facts and Summarizing Text with the extBrain Back End

The extBrain back end serves as an administrative interface for managing facts and summarizing large chunks of text into digestible pieces of information. This powerful tool enables users to input, organize, and refine their knowledge base, ensuring that they always have access to up-to-date, accurate data when needed.

## Conclusion: Why Everyone Should Have an External Brain

In conclusion, extBrain offers a comprehensive solution for building scalable AI applications focused on question answering. With its innovative approach to Fact Synthesis and RAG systems, combined with the ability to group semantically similar facts into larger text chunks, extBrain delivers efficient storage solutions and accurate vector search capabilities. By leveraging these features, you can work smarter, not harder, and revolutionize your AI application development process. So why wait? It's time to unlock the power of your external brain!

*Note: The views expressed in this blog post are based on publicly available information and represent our understanding of extBrain as a tool for building Generative AI applications.*
 * Human Intervention: None

### Facts Used:
* This series covers different tools used for building Generative AI (genai) applications
* Eighth Tool in the series is External Brain (https://github.com/patw/ExternalBrain)
* External Brain uses Fact Synthesis (reducing text into facts - see previous posts about the subject) which allows the user to paste in large text articles and reduce them down to individual facts.
* Facts are stored in Mongo collections along with some metadata about who stated the facts, what was the context and when it was stated.
* The facts can then be grouped together into chunks of text, by either a fixed number of grouped facts or with more clever methods like only grouping together facts from the same context or even facts based on their semantic similarity.
* Users can then ask questions to the LLM (large language model) and we will perform semantic search to find the fact chunks that are most relevant to the question, which will be injected into the prompt to the LLM.  This is an example of RAG (retrieval augmented generation).
* Most RAG systems will chunk up source documents like PDF, Word, HTML files into blobs of text, and run text embedding models against that to produce dense vectors.
* extBrain only chunks on groups of facts, which reduces the overall size of the data set and produces more accurate results in vector search and stronger results from the LLM.
* Semantically similar facts can produce larger text chunks without causing recall issues later on.
* External Brain can act as a second you.  It’s designed to ingest all your knowledge and be able to answer authoritatively on it.  This technique could allow knowledge workers to scale.
* extBrain has multiple front ends for asking questions:  A website, a Discord bot and a Slack bot.
* The extBrain back end, or admin UI allows you to enter and manage facts and summarize large chunks of text into facts.
* This is a pretty ideal system for question answering.  It’s efficient on storage and vectors (which are expensive to store).
* Call to action:  Everyone should have an external brain!  Work smarter not harder.
