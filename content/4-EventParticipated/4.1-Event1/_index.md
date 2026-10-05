---
title: "Event 1"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---
# Learning Report: "Kickoff FCAJ Buildrathon 2026 (Season 01) - The Thinking Behind Building The Bot"
**Event Name:** Buildrathon Kickoff: Code the Future with CMC Global
**Date & Time:** Saturday, 26/09/2026, 09:00 - 12:00
**Location:** AWS Vietnam office, 26th floor, Bitexco Financial Tower, Ho Chi Minh City
**Role:** Attendee, member of the Xóm Data team competing in FCAJ Buildrathon 2026
### Event objectives
* Kick off FCAJ Buildrathon 2026 (Season 01), a 6-month hands-on competition for the AI and Cloud community in Vietnam. Teams will build real products on AWS, in line with the programme's message: *"Don't just learn Cloud & AI for knowledge - build real products, gain lifelong teammates, and make your mark in the tech world."*
* Equip participants with architectural thinking and approaches to deploying AI Agents in an enterprise environment, through the talkshow *"The Thinking Behind Building The Bot"*.
* Analyse real-world testing problems and the technical challenges commonly met when taking a bot from a prototype into real operation.
* Meet CMC Global's technology and HR team to ask about hiring and career paths, in the Mock-interview session at the end of the programme.
### Speakers and organisers
* **Thien Lu** - Program Manager, First Cloud AI Journey (FCAJ)
* **Phong Pham** - Program Manager, First Cloud AI Journey (FCAJ)
* **Bui Nhat Truong** - Technical Leader, CMC Global, speaker of the talkshow *"The Thinking Behind Building The Bot"*
* **Organisers and partners:** AWS Study Group / First Cloud Journey in charge of organising and coordinating the community; CMC Global as co-organiser, in charge of the technical track and the career networking segment.
### Agenda
| Time | Content |
| --- | --- |
| 09:00 - 09:30 | Buildrathon Kickoff |
| 09:30 - 11:15 | Talkshow "The Thinking Behind Building The Bot" |
| 11:15 - 12:00 | Mock-interview |
### Highlights
#### The FCAJ Buildrathon 2026 (Season 01) challenge roadmap
* Buildrathon is a long-term competition (6 months), focused on real-world problems that combine AWS cloud computing with generative artificial intelligence and AI Agents.
* Teams are assessed at each milestone. The criteria are practical applicability, system stability and scalability in a Production environment.
* The Xóm Data team has 6 representative groups taking part. Over the next 6 months, the groups aim to build solutions on AWS across three areas:
  * Infrastructure and compute: AWS Lambda for serverless processing flows, combined with Auto Scaling and Elastic Load Balancing to keep the system available under load.
  * Data: managing large data flows with Amazon S3, Amazon Redshift and Amazon DynamoDB.
  * Intelligent systems: integrating Generative AI, Machine Learning and AI Agents into the product each group builds.
#### The Thinking Behind Building The Bot: real-world AI Agent architecture
* The talk started from moving beyond individual, disconnected prompts to an autonomous AI Agent system. Such an agent has to be able to:
  * Decompose a large request into small, executable steps.
  * Manage memory: short-term memory holds the context within one working session, long-term memory stores information needed across many sessions.
  * Orchestrate tools: know when to call an API, query data or run a function rather than answer in text.
* In an enterprise integration architecture the data flow must be secure end to end: the agent draws knowledge from the enterprise knowledge base and connects to internal APIs, so answers are based on the organisation's real data.
* Operational optimisation: a real deployment has to balance the cost of each model call, response latency and accuracy, and improving one usually costs another.
#### Technical challenges when going to Production
* To control hallucination, use guardrails and automated testing frameworks to check outputs before they reach the user.
* Handling edge cases: prepare fallback plans for the cases where the large language model cannot call a tool, or returns results in a wrong format that downstream systems cannot read.
#### Career networking with CMC Global
* In the Mock-interview session at the end of the programme I talked directly with CMC Global's HR team and Technical Lead about workforce needs in the Cloud, AI Engineering and Data Analytics areas.
### What I learned
#### Design thinking
* Whether an agent runs stably in an enterprise depends mostly on system design. A well-written prompt on weak architecture still breaks once it meets real data and real user volume.
* An AI Agent has the right to call tools and read data, so it must strictly follow access control and protect sensitive data right from the design stage.
#### Technical architecture
* How to organise the agent's orchestration layer on AWS.
* Log the agent's activity and measure the performance of each reasoning step, so that when the agent answers incorrectly you can trace back to which step the error is in.
#### Community
* AWS Study Group's "Pay It Forward" spirit encourages members to share what they learn from practice.
### Applying this to my work
* Split the agent into clear components: planning, memory and tools, then apply this way of organising to the automation and data processing projects I am currently working on.
* For Buildrathon, plan the product design with the group and prepare the testing environment on AWS for the next stages.
* Set criteria for measuring accuracy and controlling security risk before putting any AI solution into real operation.
### Event experience
#### Learning from experts
* CMC Global's talk showed me the difficulties of moving an AI Agent from the experimental stage onto an enterprise Production system.
#### Event atmosphere
* The event gathered builders and engineers from the community. Talking with them at the AWS office, I saw how their Cloud infrastructure and Data Engineering work connects to the AI Agent layer.
#### Proof of attendance
* Xóm Data's LinkedIn post about the Kickoff, with my name in the list of participating teams: <https://lnkd.in/p/ea265it3>
#### Event photos
![Buildrathon Kickoff event poster](/images/4-eventparticipated/4.1-event1/poster.png)
*Figure 1: Poster of the Buildrathon Kickoff: Code the Future with CMC Global event.*
![Check-in at the AWS office lobby](/images/4-eventparticipated/4.1-event1/anh-tuong-its-still-day-1.png)
*Figure 2: Check-in at the "It's Still Day 1" lobby of the AWS office, next to the topic standee of CMC Global and AWS.*
![Group photo in the conference room](/images/4-eventparticipated/4.1-event1/anh-nhom-hanoi-team.png)
*Figure 3: Group photo with the speaker in the conference room.*
![Conference room during the talkshow](/images/4-eventparticipated/4.1-event1/anh-phong-hoi-thao.png)
*Figure 4: The conference room during the talkshow "The Thinking Behind Building The Bot".*
