---
layout: post
published: False
title: My Running Data Platform - 0. The Reality of Data Science
---

### The Reality of Data Science

In my professional experience, I have frequently encountered datasets that are far from being neat and tidy, ready for analysis. Unlike the structured data used in Machine Learning and AI courses, real-world data often requires collection from various sources, extraction, and processing. The choice of how to utilize this data in various data products, such as reports, data marts, dashboards, APIs, or models, is left to us.

As someone who has worked with companies undergoing digital transformations, I've spent a substantial amount of my time establishing these foundational components. Typically, I would estimate that this type of work constitutes at least 90% of my daily tasks. Any modeling, even in areas considered "hot topics" in data science, falls within the remaining 10%. Moreover, in these scenarios, practical and straightforward solutions are often favored over cutting-edge and trendy methods. Additionally, the need for rapid delivery of data products often takes precedence over intricate, complex solutions. A former manager of mine lived by the mantras, "move fast and break things" and "keep it simple, stupid!"

### Data Platforms
As previously mentioned, data requirements can span various data products, such as reports, dashboards, and models, without necessarily involving machine learning. The integrated set of technologies that collectively meet end-to-end data needs is often referred to as a "Data Platform." Data platforms facilitate the acquisition, storage, preparation, delivery, and governance of data, alongside providing a security layer for users and applications.

### My Running
Outside of my full-time work commitments, I have a passion for running. I have been a runner since junior school, but I began training seriously during my university years and have continued this pursuit throughout my professional life. Balancing my athletic, academic, and working commitments has proven to be both challenging and rewarding. This balance has led me to achieve significant milestones in my running career, including breaking the 4-minute mile barrier and achieving a 5km time of 13:28, which ranks me 9th in the UK in 2023. I've had the privilege of representing England on multiple occasions and am currently a member of the England Athletics Development Hub program, based out of St. Mary's University in South West London.  

While I may not be at a level to become a full-time professional runner just yet, I'm fortunate to receive support from [SOAR running](https://www.soarrunning.com/). I even wrote an [article](https://www.soarrunning.com/blogs/news/the-way-back) for SOAR in 2022 about my journey of recovering from injury. Having my running pursuits alongside my work provides me with a valuable balance, preventing burnout. Now that I've achieved this equilibrium, I find that each aspect of my life complements the other quite harmoniously.

### Data Platform for My Running
Despite the existence of numerous established products, I had a strong desire to leverage the extensive training data available from my running watch (where I record every training run) and other sources. My goal was to create a fully automated data platform, allowing people to track and analyze my training progress. Be on the lookout for upcoming blog posts in which I will detail the key steps in creating this platform, including: 

1. Source-to-datalake workflows: Using technologies like EKS (Kubernetes), Dagster/Argo, and S3.
2. Data marts: Reporting and anonymization of my data.
3. Data dashboards: Hosting on Streamlit through AWS.
* Stretch: Expanding into data APIs: Providing information on my daily training.
* Stretch: Preparing the above as a standalone product for others to use with their data. Authentication?

This platform will not only enable individuals to monitor my athletic journey but will also shed light on my day-to-day work. Moreover, it serves as an intriguing side project at the intersection of my two primary life endeavors, whilst enhancing my data engineering skills. I look forward to sharing it with you!