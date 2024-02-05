
+++
title = 'RAG Data Sources'
date = '2024-01-17'
draft = false
tags = ['RAG', ' Chatbots', ' Data Sources']
categories = ['AI']
+++

 # RAG Data Sources: Building Knowledge-Driven Chatbots

In today's fast-paced business landscape, knowledge-driven chatbots play a crucial role in streamlining internal communication and enhancing organizational productivity. The Retrieval Augmented Generation (RAG) approach is the leading technique for building such chatbots, utilizing AI algorithms to retrieve and generate accurate responses based on a vast repository of information.

## Data Source Selection: The Foundation of RAG Chatbots

A company's knowledge is often scattered across multiple systems in various formats. Identifying relevant data sources is an essential part of designing a chatbot. To begin, select a corpus of documents that represent the knowledge base you want your chatbot to answer questions about. This should be something immediately useful for specific groups within the organization.

## Starting with Unstructured Data: Text Documents, PDFs, and Word Documents

The easiest data sources to start with are text documents, PDFs, and Word documents. They are well supported by AI systems such as LLamaIndex and Langchain. Using these tools, you can ingest and chunk the selected documents from a directory. A great tutorial on implementing RAG with Atlas Vector Search, LangChain, and OpenAI can be found here: [RAG with Atlas Vector Search, LangChain, and OpenAI | Mongodb](https://www.mongodb.com/blog/post/retrieval-augmented-generation-rag-with-atlas-vector-search-langchain-and-openai).

## Testing Your Chatbot: Extensive Evaluation and Validation

After setting up your chatbot, it is essential to test its performance extensively. Ask questions that the chatbot should be able to answer based on the source material. This will help you identify any inaccuracies or gaps in the knowledge chunks. Validate what your chatbot gets right and wrong so you can investigate and modify the knowledge chunks later if necessary.

## A Word of Caution: Handling Structured Data

While unstructured data such as text documents, PDFs, and Word documents are ideal for starting a RAG-based chatbot, structured data like tables, point form lists, spec sheets, XML, and JSON documents may not embed well. Therefore, they should not be the first data sources you attempt to use. In future blog posts, we will cover techniques for handling structured data using pre-summarization.

In conclusion, building a knowledge-driven chatbot using RAG involves selecting relevant data sources, starting with unstructured documents like text, PDFs, and Word files, testing your chatbot extensively, and handling structured data with caution. With these strategies in mind, you can create an effective RAG chatbot that enhances communication within your organization and streamlines daily operations.
 * Human Intervention: None

### Facts Used:
* RAG (Retrieval Augmented Generation) is the leading technique for building knowledge driven chatbots for your organization
* Data source selection is an important part of the design for chatbots.  A company’s knowledge dispersed in dozens of different systems and in different formats.
* The easiest data sources to start with are text documents, pdfs and word documents. These types are well supported in the LLamaIndex and Langchain systems.
* Start by identifying a set of documents that represents a corpus of knowledge that you want the chatbot to answer questions about.  Pick something that has immediate utility to some group within the organization 
* Use LLamaIndex or Langchain to ingest and chunk these documents from a directory.  A great tutorial can be found here:  RAG with Atlas Vector Search, LangChain, and OpenAI | MongoDB
* Test your chatbot extensively with questions it should be able to answer, based on the source material.  Validate what it’s getting right and wrong so you can investigate and modify your knowledge chunks later if they are incorrect.
* A word of warning:  Structured data such as tables, point form lists, spec sheets, xml and json documents do not embed very well and should not be the first data sources you attempt to use.
* We will cover structured data techniques using pre-summarization in later blog posts.
