
+++
title = 'Embedding Model Selection'
date = '2024-01-18'
draft = false
tags = ['RAG', ' Embedding Models']
categories = ['AI']
+++

 # Embedding Model Selection: A Comprehensive Guide

Embedding models play a crucial role in natural language processing (NLP) applications, enabling accurate analysis and understanding of human language. Selecting the right embedding model can significantly impact the performance and effectiveness of your NLP solution. This blog post aims to provide you with an extensive overview of various embedding model options, along with their strengths and weaknesses, and offer guidance on how to choose the best model for your specific use case.

## Getting Started: Text-Embedding Models in OpenAI

The easiest way to begin is by directly calling OpenAI's text-embedding-ada-002 model, a 1536-dimensional model with high recall accuracy on non-industry-specific language. However, most RAG use cases will involve GPT-3.5-turbo or GPT-4-turbo models as the large language model (LLM). If you already have an API key and client library for these models, you can use them without any additional effort.

## Alternatives: Azure OpenAI, AWS Bedrock, and Google Cloud Platform (GCP) Vertex

In some cases, organizations may lack access or authorization to utilize OpenAI services. In such situations, alternative platforms like Azure OpenAI, AWS Bedrock, and GCP Vertex can be recommended as fallback options.

### Azure OpenAI

For Azure OpenAI, the advice remains the same - use text-embedding-ada-002 as the embedding model. You will still find high recall accuracy with this model in non-industry-specific languages.

### Google Cloud Platform (GCP) Vertex

When working with GCP Vertices, the recommended embedding model is gecko-001, and for LLMs, Palm2 is suggested. The model selection process should be based on your specific requirements and use case scenarios.

## Open Source Models: HuggingFace's MTEB Leaderboard

If you don't have access to the aforementioned platforms or their models, there are various open-source models available on Huggingface's MTEB Leaderboard. Instruction is one such model family that has demonstrated excellent accuracy in text-embedding tasks. However, new model families with better accuracy continue to emerge, so it's essential to stay updated with the latest advancements.

Accessing HuggingFace models can be done directly through their API or by downloading and running them locally using the sentence-transformer Python library. Self-hosting these models as a service is also possible, making it easier for organizations to integrate NLP solutions into their systems.

## Understanding Model Cards: A Crucial Step in Selection

Before selecting any embedding model, thoroughly review its model card available on HuggingFace. This document contains valuable information about the model's capabilities and limitations, such as context window length (ranging from 512 tokens to 8192 tokens), multi-lingual text embedding support, and more. By understanding these aspects, you can ensure that you choose a model best suited for your specific use case.

In conclusion, selecting the right embedding model is critical to achieving optimal performance in NLP applications. While this blog post has provided an overview of various options available, it's essential to conduct thorough research and testing before finalizing a model. Remember, each model comes with unique strengths and weaknesses that may or may not align with your requirements.
 * Human Intervention: Minor Corrections, the LLM tried to correct GCP Vertex (a product name) to GCP Vertices.  It also renamed the METB leaderboard to M5EB for some reason.  This is probably one of the worst generated blog posts from the system so far.

### Facts Used:
* The easiest way to start is calling OpenAI directly with text-ada-002 as the text embedding model.  It’s 1536 dimensions and has very high recall accuracy on non-industry specific language.  Most use cases will be using gpt-3.5-turbo or gpt4-turbo models as the LLM (large language model), so they will already have an API key and a client library to use this.
* Some larger customers don’t have access or authorization to use OpenAI, so the fallback here is to recommend Azure OpenAI, AWS Bedrock or GCP Vertex.  With Azure OpenAI, the advice above stays the same. With Google GCP and Vertex the embedding model is gecko-001 and the LLM recommended is Palm2.  With Bedrock try Cohere embedding models and Anthropic Claude as the LLM.
* If none of these are available, there’s a wide selection of open source models on Huggingface on the MTEB Leaderboard.  I’ve seen good accuracy with the Instructor family of models but new model families are showing up all the time, with claims of better accuracy:  https://huggingface.co/spaces/mteb/leaderboard
* Huggingface models can be accessed through the Huggingface API directly, as a simple replacement for the OpenAI text-ada-002 API.  However, these models can also be downloaded and run locally with the sentence-transformer python library and even self hosted as a service.  See this code for an example: https://github.com/patw/InstructorVec
* Embedding models all have different strengths and weaknesses, they can vary in the length of the context window (512 tokens to 8192 tokens) and some can handle multilingual text embedding.  Make sure to check out the model card on Huggingface before selecting a model to know what it’s capable of.
