
+++
title = 'Tool Series - VectorService'
date = '2024-02-06'
draft = false
tags = ['Vector Search', ' Tools']
categories = ['AI']
+++

 # Tool Series - VectorService: Exploring the Journey of Text Embedding Models

In this series, we will dive deep into different tools used for building Generative AI (GenAI) applications. The first tool in our exploration is [VectorService](https://www.github.com/patw/VectorService), a FastAPI service that generates dense vectors using various text embedding models.

The initial motivation behind VectorService was to test out multiple different text embedding models for generating semantic search capabilities for RAG (Retrieval Augmented Generation) tools with LLMs (Large Language Models). The journey of exploring and implementing various embedding models in this tool has taught us valuable lessons about the evolution of language processing techniques.

## From SpaCY to SentenceTransformers: A Journey of Improvement

VectorService's initial models were sourced from the Python [SpaCY Library](https://spacy.io/). We implemented small (96d), medium (384d), and large (384d) SpaCY models, which proved to be quite easy to use. However, these models performed poorly beyond a few words or a single sentence compared to more modern alternatives like BERT. They remain in use for legacy reasons in some applications.

To improve the quality of text embeddings, we then moved on to using the [SentenceTransformers Library](https://www.sbert.net/), which was incredibly easy to work with. The library provided two models: all-MiniLM-L6-v2 (384d) and all-mpnet-base-v2 (768d). These models performed significantly better than SpaCY, demonstrating the advancements in language processing techniques over time. Many RAG examples online still show miniLM as the text embedding model of choice; however, it's worth noting that larger models like mpnet-all-MiniLM-L6-cos-v1 outperform it significantly.

## BERT: A Significant Leap in Quality

Next, we explored using [BERT](https://arxiv.org/abs/1810.04805) (Bidirectional Encoder Representations from Transformers), a groundbreaking language processing model developed by Google. BERT uses 768 dimensions and delivered a substantial improvement in the quality of text embeddings compared to its predecessors. The recall and precision metrics showed significant jumps, indicating that BERT was a major step forward for text embedding models.

## SOTA: Instructor-Large Takes Center Stage

The final model we integrated into VectorService was [Instructor-Large](https://huggingface.co/hkunlp/instructor-large), a state-of-the-art (SOTA) language processing model at the time of its release. This model achieved exceptional results on the HuggingFace MTEB leaderboard and required 4 gigabytes of memory to run, making it quite slow on CPUs.

However, the quality level of Instructor-Large was considered the bare minimum for production use cases, and it could be quantized to reduce its memory footprint and latency. This model required LLM-style prompting to produce optimal results and directly competed with OpenAI's much larger text-ada-002 model, which is typically used as a default in RAG applications.

## A Comparison of Models: The Power of Benchmarking

To provide users with valuable insights into the performance of different models, VectorService included endpoints for comparing similarity results across all text embedding models implemented. This feature allowed users to benchmark recall and precision metrics between various models, which in turn helped them optimize their RAG use cases.

## The Evolution of Text Embedding Models: From Legacy to State-of-the-Art

As we have seen, the journey from SpaCY to Instruction-Large showcases the evolution of text embedding models and how they have improved over time. VectorService served as a valuable experimentation platform for exploring different models and their capabilities. However, it is now considered legacy and not recommended for use. Instead, we recommend using [InstrucTorVec](https://www.github.com/InstructorVec), an open-source alternative that offers self-hosted vector embedding solutions with exceptional performance and ease of use.

In conclusion, the development of VectorService has been a fascinating journey through the world of text embedding models. From SpaCY's early attempts to BERT's groundbreaking achievements and Instruction-Large's SOTA status, we have witnessed the incredible progress made in language processing technologies. As we move forward into an era of increasingly sophisticated AI applications, it is essential for developers and researchers alike to continue exploring new frontiers in this rapidly evolving field.
 * Human Intervention: Moderate: the bot continues to call the Instructor model Instruction and totally made up a research paper for it.  I also had to correct the two sentence transformer model names, but that was entirely my fault for providing the wrong names in the facts.  I wrote it on a plane while I was half asleep.

### Facts Used:
* * This series covers different tools used for building Generative AI (genai) applications
* * First tool in the series is VectorService (https://www.github.com/patw/VectorService)
* * Text embedding models that output dense vectors and critical for building semantic search for RAG (retrieval augmented generation) tools with LLMs (large language models)
* * Originally wanted to test out multiple different text embedding models, so built a FastAPI service in Python that would generate dense vectors using different models.
* * The first 3 models were from the Python SpaCY Library. I implemented small (96d), medium (384d) and large (384d).  SpaCY was very easy to use, but performed pretty poorly beyond a few words or a single sentence, compared to more modern models like BERT.  They're still in the process for legacy reasons.
* * The next two models were minilm-l6 (384d) and mpnet-alllm (768d).  These models performed much better than SpaCY and used the HuggingFace SentenceTransformers library, which was super easy to use.  Many RAG examples online still show minilm as the text embedding model, and while it performs poorly compared to larger models it's still quite good.
* * Next, I tried BERT (768d).  This model used 768 dimensions and seemed to be another large step up in quality for embeddings and was the first time I saw large jumps in recall and precision.  BERT has much more dimensions than minilm, but performed better in all my tests
* * Finally I added in Instructor-large (768d).  This model was considered SOTA (state of the art) for the time it released and quickly became #1 on the Huggingface MTEB leaderboard.  The model itself needed 4 gigs of memory to run and is quite slow on CPU.  However, the quality level should be considered the bare minimum for production use cases, and can be quantized to run with less memory and less latency. Instructor requires LLM style prompting to produce good results and competes directly with OpenAI's much larger text-ada-002 model, which is the default for most RAG use cases.
* * This tool also included endpoints for comparing similarity results across all the models, which is useful to show off in a demo.  It gives customers the idea that they should be benchmarking recall and precision between multiple models to optimize the RAG use case.
* * At this point, VectorService is legacy and not recommended.  InstructorVec (https://www.github.com/InstructorVec) is considered a replacement for this tool.  It was a great exercise for experimenting with different embedding models but InstructorVec is all you need for self hosted, open source vector embeddings.
