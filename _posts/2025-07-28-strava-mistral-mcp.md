---
layout: post
published: True
title: Strava + Mistral + MCP 
---
### Mashing Up Running Data with LLMs: My Strava MCP Project
As a data scientist and an avid runner, I’ve always been fascinated by the patterns in my workouts—especially the ones hiding in plain sight on Strava. Recently, I built a small project to combine both of these passions.

#### What is it?
This tool connects your Strava activity data with a Large Language Model (LLM) via<!--more--> a custom Model Context Protocol (MCP) server, letting you ask questions about your runs, rides, and other activities in plain English.

For example, you can ask:

“How many miles did I run last month?”

“Show me my fastest 10k this year.”

“Which route has the most elevation gain?”

It uses Mistral LLMs, a custom MCP server, and a Gradio web interface to make it easy to query your personal fitness history like you would a chatbot.

#### Why I built it
I wanted to explore MCP in a real-world, data-rich setting—and what better dataset than my own running history? Strava's API provides great structured data, and combining that with LLMs opens up some fun and surprisingly powerful possibilities for natural language exploration.

This project is also a testbed for experimenting with LLM interaction design on private data, and it’s been a great way to learn more about deploying conversational interfaces.

#### See it in action
🎥 Watch the demo video here (link coming soon—stay tuned!)

#### Try it yourself
Check out the code and setup instructions on GitHub at https://github.com/ICW1/strava_mcp_test if you want to run it with your own Strava (developper) account.
