---
layout: post
published: True
title: PLACEHOLDER - langhchain chatbots memory
---

### LangChain Chatbots - Memory

#### Intro 

During my time at MindGym I was very fortunate to work on a prototype virtual coach chatbot. This chatbot was the outcome of a design sprint earlier on in 2023. We started with a simple Slack-based ReAct agent (using the LangChain python module). The use case for the chatbot product changed multiple times in the development cycle, we had many iterations. It very quickly snowballed with extra features and requirements as we spoke to prospective internal and external clients to assess their needs. You can read more about this process [here](/)  

It has been incredibly interesting to work in a rapidly evolving arm of data science / research. Working with LLMs like the GPT models has been enlightening, these models have opened up a whole new world of possibility. Whilst I worked on all components of our chatbot product, my main remit was memory. This proved a difficult topic, with many challenges and barriers to overcome. But solving these issues has been extremely rewarding. 

#### Memory

So, you have an LLM agent designed for a specific task. You may or may not have added some document retrieval or some other tooling functionality. You've done your prompt engineering and it works relatively well in your tests. Now it's time to ask the question: _Outside of the input, what does my agent need to know in order to effectively perform its function?_   

It may be that your agent simply summarises documents and does not need memory whatsoever. However most cases require some kind of memory. If your agent needs, for example, access to the chat history of the conversation or extracted entities, then these things need to be configured such that they are effective and scalable for all consumers. The following article will talk about the different options memory and challenges contained within.