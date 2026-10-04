---
title: "Event 1"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Learning Report: "Kickoff FCAJ Buildrathon 2026 (Season 01) - The Thinking Behind Building The Bot"

**Event name:** Buildrathon Kickoff: Code the Future with CMC Global

**Time:** Saturday, 26/09/2026, 09:00 - 12:00

**Venue:** AWS Vietnam office, 26th floor, Bitexco Financial Tower, Ho Chi Minh City

**Role:** Attendee, member of the Xóm Data team competing in FCAJ Buildrathon 2026

### Event objectives

* Kick off FCAJ Buildrathon 2026 (Season 01), a 6-month hands-on competition for the AI and Cloud community in Vietnam. Teams will build real products on AWS instead of only studying theory, in line with the programme's message: *"Don't just learn Cloud & AI for knowledge - build real products, gain lifelong teammates, and make your mark in the tech world."*
* Equip participants with architectural thinking and approaches to deploying AI Agents in an enterprise environment, through the talkshow *"The Thinking Behind Building The Bot"*.
* Analyse real-world testing problems and the technical challenges commonly met when taking a bot from a prototype into real operation.
* Expand connections and career direction together with CMC Global's technology and HR team, via the Mock-interview session at the end of the programme.

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
* Teams are assessed at each milestone. The criteria emphasise practical applicability, system stability and scalability when running in a Production environment, rather than stopping at a demo that merely works.
* The Xóm Data team has 6 representative groups taking part. Over the next 6 months, the groups aim to build solutions on AWS across three areas:
  * **Infrastructure and compute:** AWS Lambda for serverless processing flows, combined with Auto Scaling and Elastic Load Balancing so the system is always available.
  * **Data:** managing large data flows with Amazon S3, Amazon Redshift and Amazon DynamoDB.
  * **Intelligent systems:** integrating Generative AI, Machine Learning and AI Agents to solve business problems.

#### The Thinking Behind Building The Bot: real-world AI Agent architecture

* **Foundational mindset:** moving from writing individual, disconnected prompts to building an autonomous AI Agent system. Such an agent needs to be able to do three things:
  * Decompose a large request into small, executable steps.
  * Manage memory: short-term memory holds the context within one working session, long-term memory stores information needed across many sessions.
  * Orchestrate tools: know when to call an API, query data or run a function instead of only answering with text.
* **Integration architecture in the enterprise:** the data flow must be secure end to end; the agent draws knowledge from the enterprise knowledge base and connects to internal APIs, so that answers are based on the organisation's real data.
* **Operational optimisation:** a real deployment always has to balance three factors: the cost of each model call, response latency and accuracy. Increasing one factor usually reduces another, so you need to pick the balance point that suits the problem.

#### Technical challenges when going to Production

* **Controlling hallucination:** use guardrails and automated testing frameworks to check outputs, ensuring the information the agent returns is trustworthy.
* **Handling edge cases:** prepare fallback plans for the cases where the large language model cannot call a tool, or returns results in a wrong format that downstream systems cannot read.

#### Career networking with CMC Global

* The Mock-interview session at the end of the programme was an opportunity to meet and talk directly with CMC Global's HR team and Technical Lead about workforce needs in the Cloud, AI Engineering and Data Analytics areas.

### What I learned

#### Design thinking

* **Architecture first, prompts second:** a bot or agent that runs stably in an enterprise depends on system design, not only on prompt tuning. A good prompt with weak architecture still breaks when it meets real data and real user volume.
* **Security and data safety:** an AI Agent has the right to call tools and read data, so it must strictly follow access control and protect sensitive data right from the design stage.

#### Technical architecture

* Optimising agent orchestration architecture on AWS infrastructure.
* Monitoring is mandatory: log the agent's activity and measure the performance of each reasoning step, so that when the agent answers incorrectly you can trace back to see which step the error is in.

#### Community

* AWS Study Group's "Pay It Forward" spirit creates motivation for members to connect, learn from real practice and continuously share knowledge with each other.

### Applying this to my work

* **Standardising AI Agent architecture:** split the agent into clear components: planning, memory and tools, then apply this way of organising to the automation and data processing projects I am currently working on.
* **Preparing for Buildrathon:** together with the group, plan the product design and prepare the testing environment on AWS for the next stages.
* **Testing before operating:** set criteria for measuring accuracy and controlling security risk before putting any AI solution into real operation.

### Event experience

The FCAJ Buildrathon 2026 Season 01 Kickoff at the AWS Vietnam office was an opening session with a lot of professional value.

#### Learning from experts

* CMC Global's sharing gave me a direct view of the difficulties in moving an AI Agent from the experimental stage onto an enterprise Production system, something tutorials usually do not mention.

#### Event atmosphere

* The event gathered a very large number of builders and engineers. Being able to talk directly at the AWS office helped me connect the pieces of knowledge from Cloud infrastructure and Data Engineering through to AI.

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

> The Kickoff gave me up-to-date knowledge about AI Agents and is the starting step to confidently enter the 6-month journey of Buildrathon Season 01.
