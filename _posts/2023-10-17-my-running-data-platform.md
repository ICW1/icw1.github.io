---
layout: post
published: True
title: PLACEHOLDER - My Running Data Platform + the Reality of Data Science
---

### The Reality of Data Science
As I've often found in my professional experience, one rarely comes across _nice and tidy_ datasets ready for analysis. Unlike Machine Learning and AI courses, in the real world we have to collect data, connect to different sources of data, extract it, and process the data. How we then choose to use this data through different data products is up to us. This could be reports, data-marts, dashboards, APIs or models.  

As I have worked with companies undergoing a digital transformation, I have spent a lot of time establishing these introductory components. Typically I would say that this kind of work amounts to at least 90% of what I do day to day. Any modelling, which includes most "hot topics" in data science, is found in that remaining 10%. Even then, pragmatic simple solutions are preferred to cutting edge "trendy" methods. Furthermore, the pace at which data products are required often takes precedence over fully fleshed out complex solutions. A great manager of mine lived by the mantras; _move fast and break things_ and  _keep it simple stupid_!

### Data Platforms
As previously mentioned data needs could be from a variety of different data products; reports, dashboards, models etc. Note this may not necessarily include any actual machine learning. The integrated set of technologies that collectively meets the end-to-end data needs can be called a _Data Platform_. Data platforms enable the acquisition, storage, preparation, delivery, and governance of your data, as well as a security layer for users and applications.

### My Running
Outside of my full time work commitments I like to run. I have ran since junior school but I started training seriously throughout university and have continued this throughout my working life. I have found it challenging but rewarding to balance my athletic, academic and working commitments. This has led to me breaking 4-minutes for the mile and running 13:28 for the 5km, a time which ranks me 9th in the UK in 2023. I have represented England multiple times and I'm currently a member of the England Athletics Development Hub programme based out of St. Mary's University in South West London.  

Whilst I'm not yet good enough to be a full time professional. I'm lucky enough to have help from [SOAR running](https://www.soarrunning.com/). Here's an [article](https://www.soarrunning.com/blogs/news/the-way-back) I wrote for SOAR back in 2022 about recovering from injury. I do enjoy having my running outside of work to focus on, and vice-versa, it stops me from going all in on any one thing. Preventing burnout. Now I have balance, I find that each complements the other quite nicely.

### Data Platform for My Running
Whilst there are many established products out there. I wanted to use the vast amounts of training data available from my running watch (I record every training run on here) and other sources. To create a complete automated data platform where people can follow and analyse my training. Keep an eye out for the following blogs in which I will detail the important steps in the creation of such a platform and any components contained within:  

1. Source-to-datalake workflows: eks (kubernetes), dagster/argo, s3 
2. data marts: reporting and anonymising my data
3. data dashboards: hosting on streamlit through AWS
4. stretch ~ data APIs: what's my daily training today? -app?
5. stretch ~ packaging the above as it's own product for others to use on their data?

This will not only enable people to follow my athletic progress it also highlights my day to day work. Furthermore, this creates an interesting side project at the intersection of my two main life endeavors, whilst improving my data engineering skills. I look forward to sharing it with you!