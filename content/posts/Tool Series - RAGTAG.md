
+++
title = 'Tool Series - RAGTAG'
date = '2024-02-07'
draft = false
tags = ['RAG', ' Chunking', ' Vector Search', ' Tools']
categories = ['AI']
+++

 # Tool Series - RAGTAG: An In-depth Look at Retrieval Augmented Generation

https://www.github.com/patw/RAGTAG

In our ongoing series covering various tools for building Generative AI applications, we dive into the third tool: **RAGTAG**. This end-to-end example of RAG (Retrieval Augmented Generation) allows you to experiment with question/answer pairs, test lexicographic and semantic search capabilities, and generate an LLM (Large Language Model) response using semantically augmented data.

As a simple CRUD application, RAGTAG enables users to create and modify question/answer pairs that are combined into a single chunk of text. This text is then run through the "instruct-large" text embedding model for retrieval later on. All semantic search in RAGTAG is performed using vector search with the same "instruct-large" model.

The key to RAGTAG's effectiveness lies in its tunable features. The chunk testing tool allows users to adjust the score cut-off for cosine similarity in vector search as well as control the K value, which determines the overrequest value on the vector search query. Meanwhile, the LLM tester provides an interface to set the above semantic search parameters along with system messages, prompts, and user questions.

RAGTAG is a product of Mongodb's specialist search group and has been in production since its inception. It serves as a valuable tool for question answering, demonstrating the power of RAG and its practical applications. However, there is room for improvement. The current LLM (implemented with the Llama.cpp Python module) runs on CPU instead of GPU, which can cause response generation to be slow.

Looking towards the future, we envision a more efficient version of RAGTAG that incorporates InstructorVec for text embedding and runs Llama.cpp in server mode. By leveraging these advancements, RAGTAG will be better equipped to share infrastructure with other tools and enjoy the benefits of GPU-accelerated token generation for faster response times.

In conclusion, RAGTAG is an essential tool for those looking to experiment with Retrieval Augmented Generation. With its robust capabilities and potential for improvement, it continues to be a valuable resource within our Generative AI toolkit. Stay tuned as we explore further advancements in this exciting field!
 * Human Intervention: Added URL for github project and fixed InstructionVec to InstructorVec

### Facts Used:
* This series covers different tools used for building Generative AI (genai) applications
* * Third Tool in the series is RAGTAG (https://www.github.com/patw/RAGTAG)
* * RAGTAG is an end-to-end example of RAG (retrieval augmented generation) allowing you to manually create question/answer pairs, testing lexical and semantic search and allow you to generate an LLM (large language model) response with semantic search augmented data and manipulate the system message and the prompt to see how it changes the ouput.
* * This is a pretty simple CRUD application that lets you create and modify question/answer pairs which get appended together as a single chunk of text and run through the "instructor-large" text embedding model for retrieval later.
* * All semantic search is performed using vector search using the same instructor-large model
* * The chunk testing tool allows you to tune the score cut-off for the cosine similarity in the vector search as well as the K value, which controls the overrequest value on the vector search query
* * The LLM tester allows you to set the above semantic search values as well as the system message and the LLM prompt format along with the users question.
* * RAGTAG was a great experiment and is still used in production for question answering for our own specialist search group at MongoDB
* * This tool also integrated the text embedding model and the LLM into a single installable package, which was very convenient.  However, the LLM (running on llama.cpp python module) will run on CPU instead of GPU making the output responses quite slow
* * The future for this tool is to migrate it to the InstructorVec for text embedding and on llama.cpp running in server mode, so it can share infra with other tools and run on GPU for much faster token generation.
