
+++
title = 'Tool Series - InstructorVec'
date = '2024-02-07'
draft = false
tags = ['Vector Search', ' Tools']
categories = ['AI']
+++

 # Tool Series - InstructorVec: A Single Endpoint for Text Embedding

https://www.github.com/patw/InstructorVec

In this series, we dive into different tools and techniques used to build Generative AI applications. As we progress through the series, we'll explore a variety of methods that aid in creating efficient and powerful models. Today, we delve into InstructorVec, the latest evolution in the VectorService tool family.

InstructorVec is not just another text embedding model; it's an innovative approach to generating dense vectors for production use cases. It's designed as a single endpoint that calls the instructor-large model from HuggingFace, marking a departure from the previous VectorService tool that hosted eight different embedding endpoints. This change allows us to focus entirely on a singular solution for text embedding and outputting 768 dimension dense vectors, making it ideal for real-world applications.

To achieve this, InstructorVec loads the full instructor-large model but quantizes it from its original FP32 precision down to FP8. This slight reduction in precision offers significant performance improvements without compromising the quality of the outputs. In fact, executing InstructorVec takes no more than 100 milliseconds on a CPU, compared to the 1000 millisecond execution time at full FP32 precision. As a result, many RAG (Retrieval Augmented Generation) tools that consume this service have become much more responsive and efficient.

As we continue to build new production applications, InstructorVec will serve as the baseline vectorizer for all our tools moving forward. This is because its performance and precision make it a reliable solution for various use cases. Moreover, we currently maintain multiple copies of this service to cater to different production requirements.

In the future, we may expand InstructorVec's capabilities by adding a similarity checking endpoint. Similarity checking was one of the most useful features in the legacy VectorService tool, and its integration into InstructorVec will further enhance its versatility and utility.

To sum it up, InstructorVec is an innovative single-endpoint solution for text embedding that delivers high performance and precision while being ideal for production applications. As we continue to refine this tool, we're excited about the possibilities it holds for enhancing our Generative AI applications and unlocking new levels of efficiency in RAG tools. Stay tuned as we explore more exciting developments in the world of text embedding and Generative AI!
 * Human Intervention: Minor.  I added the URL for the github repo.  Sometimes it adds it as a link in the text, other times it forgets it entirely.

### Facts Used:
* * This series covers different tools used for building Generative AI (genai) applications
* * Fourth Tool in the series is InstructVec (https://www.github.com/patw/InstructorVec)
* * InstructorVec is the next generation of VectorService tool, however instead of hosting 8 different embedding endpoints, it hosts a single endpoint that calls the instructor-large model from HuggingFace.
* * The other text embedding models in VectorService are nice to show off differences in vector outputs and can demonstrate how different models measure similarity between two strings of text.
* * InstructorVec is focused entirely on being a single endpoint for text embedding and outputting 768 dimension dense vectors for production use cases.
* * This tool loads the full instructor-large model, but quantizes it from full FP32 precision down to FP8.  For a small loss in precision in the model weights, it executes in 100 ms or less on CPU compared to 1000 ms at full precision.  This has made some RAG (retrieval augmented generation) tools that consume this service, much more responsive.
* * This will be the baseline vectorizer I'll be using in all tools moving forward, and currently operate multiple copies of this for servicing different production applications
* * Future state for this tool might include a similarity checking endpoint, as this has been very useful in the legacy VectorService tool.
