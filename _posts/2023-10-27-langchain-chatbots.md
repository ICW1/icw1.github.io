---
layout: post
published: True
title: PLACEHOLDER - langhchain chatbots memory
---

# LLM - Agent Memory - LangChain / Chatbots

## Intro 

During my time at MindGym I was very fortunate to work on a prototype virtual coach chatbot. This chatbot was the outcome of a design sprint earlier on in 2023. We started with a simple Slack-based ReAct agent (using the [LangChain](https://python.langchain.com/docs/get_started/introduction) python module). The use case for the chatbot product changed multiple times in the development cycle, we had many iterations. It very quickly snowballed with extra features and requirements as we spoke to prospective internal and external clients to assess their needs. You can read more about this process [here](/link-to-linkedin-articles/).  

It has been incredibly interesting to work in a rapidly evolving arm of data science / research. Working with LLMs like the GPT models has been enlightening, these models have opened up a whole new world of possibility. Whilst I worked on all components of our chatbot product, my main remit was memory. This proved a difficult topic, with many challenges and barriers to overcome. But solving these issues has been extremely rewarding. 

## Memory

So, you have an LLM agent chain designed for a specific task. You may or may not have added some document retrieval or some other tooling functionality. You've done your prompt engineering and it works relatively well in your tests. Now it's time to ask the question: _Outside of the input, what does my agent need to know in order to effectively perform its function?_ If the answer is information from previous interactions, then you need memory. LangChain defines [memory](https://python.langchain.com/docs/modules/memory/) as _the ability to store information about past interactions_. A memory system can do multiple things, but it needs to support two basic actions: reading and writing from the llm chain. See the following diagram from LangChain.

<div class="img-div-any-width" markdown="0">
  <img src="/images/langchain_memory_diagram.png" />
</div>

It may be that your agent simply summarises documents and needs no memory whatsoever. However, most cases require some kind of memory. If your agent needs, for example, access to the chat history of the conversation or extracted entities, then these things need to be configured such that they are effective and scalable for all consumers. The following article will talk about the different options for memory and challenges contained within.  

#### note on LangChain
For this article most examples will be provided in Python using LangChain's abstractions. The team at LangChain have done most of the heavy lifting already in terms of setting up these components. Check out their [GitHub]() and [documentation](https://python.langchain.com/docs/get_started/introduction).

#### note on Chatbots
I will also explain these components using a chatbot example, as they typically have more memory needs than other LLM agent use cases. In our case, we would like our chatbot to, ideally, be able to remember facts about the human and any previous interactions in order to have a flowing and logical conversation.

### Types of memory

There are multiple types of memory for chatbots. Langchain has [good documentation](https://python.langchain.com/docs/modules/memory/types/) on their available options but I will explain a few here:  
* [Conversation Buffer](https://python.langchain.com/docs/modules/memory/types/buffer): This simply inserts all message history as a buffer into the prompt that is passed to the LLM. The buffer will be of the form: `history: human_message: "Hello, how...", ai_message:"Hi, great question, I ..."` The buffer has no limit. It contains all previous messages within the conversation this leads to large contexts and proves to be problematic.
* [Conversation Buffer Window](https://python.langchain.com/docs/modules/memory/types/buffer_window): This is the same as above but the buffer is limited to `k` message pairs. This helps limiting the tokens inputted tp say OpenAI's GPT APIs.
* [Conversation Summary](https://python.langchain.com/docs/modules/memory/types/summary): Instead of the buffer. The conversation is summarised using another LLM. The advantage is that the summary would be smaller than a buffer in terms of tokens. However, in this situation you may lose information. Furthermore, If there are multiple message histories the summaries are computed consecutively. So this can take some time. Here the following would be injected into the prompt: `history: "The human asked about ... and I responded ..."`
* [Conversation Summary Buffer](https://python.langchain.com/docs/modules/memory/types/summary_buffer): The same as the above, but combines the buffer and summary. It keeps a buffer of recent interactions in memory and compiles older interactions into a summary then uses both. Here the buffer is determined by tokens. The summary is computed every time. Here both a message buffer and a summary would be injected into the prompt.
* [Entity](https://python.langchain.com/docs/modules/memory/types/entity_summary_memory): Using another call to an LLM, the Entity memory module extracts facts about specific entities in a conversation. This creates a _Context_ field which is added to the prompt like so `Context: {'Deven': 'Deven is working on a hackathon project with Sam.', 'Sam': 'Sam is working on a hackathon project with Deven.'}`.
* [Conversation Knowledge Graph](https://python.langchain.com/docs/modules/memory/types/kg):