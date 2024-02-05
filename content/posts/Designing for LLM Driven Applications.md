
+++
title = 'Designing for LLM Driven Applications'
date = '2024-01-25'
draft = false
tags = ['LLM', ' Prompt Engineering', ' Design', ' RAG']
categories = ['AI']
+++

 # Designing for LLM-Driven Applications: A Comprehensive Guide

Large Language Models (LLMs) have revolutionized the way we interact with technology, enabling natural language processing and generation to new heights. To harness the full potential of these powerful models in application development, it's crucial to focus on designing effective prompts that optimize their performance. This blog post will delve into the four essential elements of prompt design for LLM-driven applications: system message, augmentation, pre-question prompt, and user question.

## System Message
The system message plays a pivotal role in shaping the tone and personality of the LLM's responses. If you want professional, technical replies, incorporate that into the system message. Similarly, if you desire more conversational or irreverent outputs, reflect those qualities in your system message as well. This will help guide the model towards delivering the desired output style and format.

## Augmentation
In RAG (Retrieval Augmented Generation) use cases, augmentation is critical for providing authoritative responses to user questions. By adding text chunks or distilled facts with context, you empower the LLM to answer queries accurately and efficiently.

When working with smaller parameter count models (e.g., Mistral-7b), it becomes even more important to have the right data or facts in the prompt, as well as minimizing irrelevant information. Optimize your chunking and recall strategy to achieve optimal performance from the LLM.

## Pre-Question Prompt
The pre-question prompt serves as a crucial guiding element for LLMs. A typical prompt starts with "Answer the following question using the facts above:", but you will need to customize this message to steer the model away from irrelevant topics, such as discussing the facts or revealing its system message. Additionally, use this section of the prompt to specify the desired output format (e.g., JSON or XML), ensuring that the LLM adheres to your requested format.

Development cycles may involve iterating on the pre-question prompt to refine and improve the model's responses. This "steerability" is a critical aspect of designing prompts for LLM-driven applications.

## User Question
The user question, provided at the end of the prompt, directly impacts the LLM's response generation process. While there are differing opinions on where to place the question within the prompt, our observations have shown stronger performance when placing the data/facts at the top and the pre-question and question at the bottom.

By meticulously crafting each element of the prompt, developers can maximize the potential of LLMs in their applications, ultimately delivering more accurate, engaging, and user-friendly experiences for end-users.
 * Human Intervention: None

### Facts Used:
* Designing for LLM (large language model) driven applications should focus on the various elements of the prompt to the LLM
* The prompt should be broken down into the following 4 elements:  system message (bot identity and personality), the augmentation (data and facts) which is used to answer the question, the pre-question prompt used for steering the response output style and format, and finally the user provided question itself.
* The system message should be designed to give the LLM responses a personality or tone for responses.  If you want a professional tone with technical expertise, build that into the system message.  Same if you want a more conversational, irreverent tone to the outputs.
* The augmentation piece is critical for RAG (retrieval augmented generation) use cases. This is where you add your text chunks or distilled facts with context, so that the LLM can answer the question authoritatively.  The smaller the parameter count of the model (ie mistral-7b) the more important it is to have the correct data or facts in the prompt and as little irrelevant data as possible.  Optimize your chunking and recall strategy to get the biggest wins here.
* The pre-question prompt is usually something like “Answer the following question using the facts above:”, which is a great starting point.  You will need to modify this prompt to steer the model away from things like talking about the facts, or revealing it’s system message or sticking to JUST the facts provided and nothing else.  This is also the place you specify the output format, if you want JSON or XML you ask for it here.  You will spend some development cycles iterating on this part of the prompt to get the best possible outputs.  This is your steerability.
* The question itself is provided by the user and gets quoted into the prompt as the final step.  There’s some arguments in the industry to put the question up at the top of the prompt, but I’ve observed stronger responses by laying out the prompt with the data/facts at the top of the prompt and the pre-question and question at the bottom.
