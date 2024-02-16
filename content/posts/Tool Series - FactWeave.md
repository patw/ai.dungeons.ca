
+++
title = 'Tool Series - FactWeave'
date = '2024-02-09'
draft = false
tags = ['AI Tools', ' Vector Search', ' Python']
categories = ['AI']
+++

 # Tool Series - FactWeave: Writing More by Writing Less

In the ongoing series of covering different tools for building Generative AI applications, we introduce FactWeave (https://github.com/patw/FactWeave), a unique tool that can generate blog posts with minimal input. Designed with Fact Expansion in mind, it's the perfect solution if you want to share your thoughts and ideas without spending hours crafting each post.

## How FactWeave Works

FactWeave is an incredible example of Fact Expansion. This tool allows you to input individual facts, which are then fed into a Large Language Model (LLM) along with some prompt engineering to generate specific types of blog posts. You can choose from technical, personal, or humor-based content, and the output will be Markdown files ready for consumption by static site generators like HUGO.

## A Website Built with FactWeave

The website you're currently reading is a testament to the power of FactWeave. This tool has helped me share my ideas in a well-formatted and professional manner, which has been incredibly valuable for my customers at Mongodb who are interested in building Retrieval Augmented Generation (RAG) use cases.

## Managing Your Blog Posts with FactWeave

FactWeave also acts as a Content Management System (CMS). It enables you to manage your blog posts, change their tags, titles, or content. If the "post" field is blank, FactWeave will generate the blog post using the LLM. Afterward, you can edit the post as needed.

## Tailoring the Content

The default tone for FactWeave's generated posts is technical, detailed, and professional. However, you have the option to change this tone to personal if you prefer a more casual writing style. The term "detailed" might sometimes produce overly wordy content, so you can also switch it to "succinct" for shorter blog posts.

## Automating Tags

Currently, FactWeave uses default tags such as "RAG", "Grounding", and "LLM". However, I plan on updating the system to generate these tags automatically based on the content of each post. This way, the AI can help you categorize your blog posts more effectively!

##  FactWeave Built With Python

FactWeave is built using Flask, FlaskBootstrap, and FlaskForms, which are popular tools in this series. The tool also incorporates vector search functionality to help you find relevant articles for editing later.

## Conclusion

In conclusion, FactWeave is a powerful tool that can help you create engaging blog posts with minimal effort. By inputting individual facts, the AI generates well-formatted, personalized content that can be edited and managed as needed. With its versatility and ease of use, FactWeave is an excellent choice for anyone looking to streamline their blogging process.

So why not give it a try? Write more by writing less with FactWeave!
 * Human Intervention: Minor.  It called Fact Expansion "Facet Expansion".  Also renamed one of the headings.

### Facts Used:
* This series covers different tools used for building Generative AI (genai) applications
* Seventh Tool in the series is FactWeave (https://www.github.com/patw/FactWeave)
* FactWeave is a tool for generating blog posts by just providing individual facts.
* This tool is an example of Fact Expansion (see previous blog post about this subject), it's the opposite of Fact Synthesis
* You can provide an arbitrary number of facts, which get fed to the LLM (large language model), with some prompt engineering to produce a specific type of blog post (technical, personal, humor) and output Markdown files.
* The Markdown files can be consumed by static site generators like HUGO, to deploy a complete website with minimal inputs.
* The website you're reading right now is produced by FactWeave
* FactWeave helped me get my ideas into a nicely formatted blog site which has been valuable for my customers at MongoDB who are interested in building RAG (retrieval augmented generation) use cases
* FactWeave itself is a CMS.  It provides the ability to manage the blog posts, change their tags, title or content.  It only generates the blog post using the LLM if the “post” field is blank.  After the post is generated it can be edited.
* Sometimes I do need to edit the blog posts and I indicate that with the “Human Intervention” part at the bottom of the post.  If it says “None”, it means I haven’t edited the post.  If I do have to edit I explain what and why.  Usually it’s due to the LLM hallucinating URLs or referencing open source projects with the wrong name.
* The default tone for posts is “technical, detailed and professional”.  This directs the LLM to produce technical sounding blogs.  I sometimes change "professional to “personal” when I want that tone instead.  The term “detailed” can also be a problem, sometimes.  It’ll get very wordy, so I’ll change it to “succinct” instead.
* The system also has default tags “RAG, Grounding, LLM” but I’ll modify the system later to have to produce tags automatically from the outputted content.  When you have an AI problem, more AI fixes it!
* The tool is built using Flask, FlaskBootstrap and FlaskForms as are many of the tools in this series.
* It also incorporates vector search, to find relevant articles.  This is so I can edit them later.
* Call to action:  This same technique could be used for building technical documentation, or even your own blogging solution.  Clever tagline: Write more by writing less!
