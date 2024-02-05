
+++
title = 'Updating RAG Data Sources'
date = '2024-01-18'
draft = false
tags = ['RAG', ' Chatbot', ' Data Sources']
categories = ['AI']
+++

 # Updating RAG Data Sources: A Comprehensive Guide to Ensuring Your Chatbot Remains Informed

Retrieval-Augmented Generation (RAG) chatbots are valuable tools for providing users with relevant and up-to-date information. However, as the world evolves and data in your document sources (PDF, HTML, Word, Text) changes over time, it's crucial to have a robust strategy in place for updating these vectors so that your RAG chatbot can continue delivering accurate responses. In this blog post, we will discuss various strategies for updating RAG data sources, including using transactional data stores, batch update processes, and implementing a Change Data Capture (CDC) approach.

## Utilizing Transactional Data Stores

One of the most effective ways to manage updates in your RAG chatbot's data sources is by chunking documents into a transactional data store, such as LangChain or LLamaIndex. This allows you to replace chunks when they are updated while also tracking important metrics about their performance, including how often they are queried and the number of positive/negative responses they receive from users.

### Chunking Application

When implementing a chunking application, it's essential to consider real-time edits in your Content Management System (CMS) system. This will enable you to make corrections to poor or incorrect responses promptly and ensure that your chatbot provides accurate information at all times.

### Batch Update Strategy

An efficient way to keep your RAG data sources up-to-date is by employing a batch update strategy, either through a timer-based system or by detecting changes in the documents themselves. This method may not be the most immediate, but it ensures that your chatbot always has access to current information.

### Change Data Capture (CDC) and Triggers

To stay informed about updates in your data sources, you can also leverage Change Data Capture (CDC), which involves monitoring changes within your database and triggering actions based on those modifications. One example of how this works is VectorStreaM, an open-source tool developed by Patrick Walton that enables real-time vector updates in MongoDB Atlas.

## Conclusion: Plan for Updates to Ensure Solid Responses

In summary, developing a plan for updating RAG data sources is essential for maintaining the accuracy and reliability of your chatbot's responses. By utilizing transactional data stores, employing batch update strategies, and leveraging CDC techniques, you can ensure that your chatbot remains well-informed and ready to assist users with up-to-date information.
 * Human Intervention: None

### Facts Used:
* Data in your document sources (PDF, HTML, Word, Text) will change over time.  You should have a strategy for updating your vector embeddings so your RAG (retrieval augmented generation) chatbot can talk about up to date information
* Consider a process of chunking your documents into a transactional data store (using langchain or llamaindex), so you can replace chunks if they are updated.  This also lets you store metrics about the chunks performance, such as how often it’s queried.  You can also track how many times the chunk had  a positive or negative response if you implement user provided thumbs up/down on your chatbot responses.
* A batch update strategy is recommended, either on a timer or when you detect changes to the documents.  This is not super efficient, but it’ll ensure you have up to date knowledge in your chatbot
* If you build a CMS system on top of your text/knowledge chunks you can edit them in real time to correct poor or incorrect responses from the chatbot.
* Also consider that you need to run updated chunks through your text embedding models, so you have updated dense vectors in your vector search engine.  This can be done using CDC (change data detection) and triggers or as part of your chunking application.  VectorStream (https://github.com/patw/VectorStream) is an example of how to do this in MongoDB Atlas
* Call to action:  Make sure you have a plan in place for updating the knowledge your chatbot has, so it’s always giving solid responses.
