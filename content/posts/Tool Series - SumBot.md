
+++
title = 'Tool Series - SumBot'
date = '2024-02-06'
draft = false
tags = ['LLM', ' Chunking', ' Presum', ' llama.cpp']
categories = ['AI']
+++

 # Tool Series - SumBot: A Powerful AI Summarization Tool for Structured Data

https://www.github.com/patw/sumbot

In our ongoing series covering various tools used for building Generative AI (genai) applications, we are excited to introduce you to SumBot, a Python FastAPI service designed specifically for summarizing structured data into semantically rich English text. As the second tool in this series, SumBot has proven its worth as an essential addition to any genai developer's toolbox, particularly when working with JSON or XML data.

## What is SumBot?

SumBot is a powerful AI summarization tool that takes structured data (usually JSON) and converts it into coherent paragraphs of English text. With just a single endpoint (`summarize`) and two parameters - `entity` and `data`, this Python FastAPI service can quickly process and summarize your data, making it ideal for running through text embedding models like BERT or Instruct-large.

## Why Use SumBot?

Embedding models often struggle to perform well on JSON, XML, point form data, or tabular data. By using an LLM (Large Language Model) for pre-summarization before text embedding, you can significantly improve recall and precision for semantic search. SumBot was the first tool I hosted on a GPU with LLaMA.cpp running in server mode, utilizing the OpenHermes-2.5-Mistral-7b model to provide accurate summarizations.

## How Does SumBot Work?

The actual LLM prompt uses the `entity` parameter to guide the LLM into summarizing the JSON or XML data. This guidance can be necessary if the keys in your JSON document aren't clear enough for the LLM to figure out what it's summarizing. Thankfully, SumBot doesn't require validation of whether the input data is actually JSON or XML; it can summarize almost anything as long as you provide it an `entity` and `data`.

## Deploying SumBot

SumBot can be deployed against any LLaMA.cpp server running locally or could be easily updated to point to a hosted service like Mistral.ai or OpenAI. This flexibility makes SumBot an excellent choice for developers who need to quickly process and summarize large amounts of structured data while taking advantage of the latest advancements in AI technology.

In conclusion, SumBot is a valuable addition to any genai developer's toolbox. Its ability to transform JSON or XML data into coherent English text using LLM pre-summarization makes it an essential tool for improving recall and precision in semantic search. As the second installment in our series on tools for building Generative AI applications, SumBot demonstrates the power of leveraging cutting-edge technology to optimize workflows and enhance productivity.
 * Human Intervention: Minor.  I had to add the Github URL to sumbot to the article.

### Facts Used:
* This series covers different tools used for building Generative AI (genai) applications
* * Second tool in the series is SumBot (https://www.github.com/patw/sumbot)
* * SumBot is used for summarizing structured data (usually JSON) into paragraphs of sementically rich english text.
* * The tool is a Python FastAPI service with a single endpoint (summarize) and two parameters: entity and data
* * The output of SumBot is ideal for running through text embedding models like BERT or Instructor-large
* * Embedding models tend to perform poorly on JSON, XML, point form data and tabular data.  Using an LLM (large language model) for pre-summarization before text embedding can provide a drastic increase in recall and precision for semantic search
* * SumBot was the first tool I hosted on GPU with llama.cpp running in server mode with the OpenHermes-2.5-Mistral-7b model.
* * The actual LLM prompt uses the entity parameter to guide the LLM into summarizing the JSON or XML data.  This can be necessary if the keys in the JSON document aren't clear enough for the LLM to figure out what it's summarizing.
* * SumBot doesn't validate if it's actually JSON or XML data! It can be used to summarize almost anything, as long as you provide it an entity and data.
* * This tool can be deployed against any llama.cpp server running locally or could be easily updated to point to a hosted service like Mistral.ai or OpenAI
