---
title: "Event 2"
date: 2026-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Event Report: "Fireside chat with Dr. Werner: Navigating the future of cloud & AI in Vietnam"

**Event Name:** Fireside chat with Dr. Werner: Navigating the future of cloud & AI in Vietnam

**Date & Time:** 02/10/2026

**Location:** Bitexco Finance Tower, 2 Đ. Hải Triều, Sài Gòn, Hồ Chí Minh, Việt Nam

**Role:** Attendee

### Event objectives
* Answer the question that opened the conversation: how is the AI era changing the work of technical people, and what should product builders do?
* Hear Dr. Werner Vogels tell three stories from Amazon's early years: the 12/12 database outage that led to Dynamo and then DynamoDB, three years spent building an engineering culture (measurement, removing single points of failure, cost efficiency), and why AWS was created with a pay-as-you-go model.
* Understand the five qualities he named for the engineer of the future: lifelong learning, systems thinking, ownership, broad knowledge and, most important of all, communication.
* Understand how AI shortens the path from idea to prototype, and why Amazon still uses the Working Backwards process to decide what to build.

### Speakers
* **Dr. Werner Vogels**: Chief Technology Officer and Vice President of Amazon
* **My Nguyen**: Sr Prototyping Architect, AWS Vietnam, host of the conversation
* **Nguyen Gia Hung**: Solutions Architect Manager, AWS Vietnam

### Highlights

#### From "bookstore" to distributed systems problems at real scale
* Before joining Amazon, Dr. Werner researched large distributed systems at a university. The first time he was invited to give a talk there, he thought Amazon was just a bookstore that needed one web server and one database. When he arrived, he saw that Amazon had to build almost everything itself, from databases to messaging systems, because commercial software could not run at their scale. At the time, Amazon was growing tenfold every year.
* He described the 12/12 outage, which fell on the shipping deadline for Christmas delivery and was also the busiest day of the year. The relational database cluster that stored customer information ran with multiple machines sharing disks, and it hit a software bug that only appeared under very high load. The system was down all day and Amazon lost millions of dollars. The vendor came in, and the first thing they said was "you should have tested more thoroughly". He admitted they were right: Amazon had used the software far beyond the limits it was designed for.
* After the outage, he asked Swami, then an intern and now head of AI at AWS, to find out how Amazon actually used relational databases. The result: about 70% was key-value access, about 20% was single structured tables unrelated to any other table, and only about 10% actually needed relations. He used the shopping cart as an example: nobody queries "every cart that contains Harry Potter"; people just fetch a cart by customer ID. If that kind of query is needed, it is fine to let a back-end management system run it slowly. That analysis led to Dynamo, and later DynamoDB.

#### Three years of building an engineering culture: measurement, fault tolerance and efficiency
* The year of metrics: if you do not know how your system is running, you are flying blind, and in 2000 the tools we have today did not exist yet. He gave the example of a 1.5-second median latency: that number says almost nothing, because at least 50% of customers are having a worse experience. Amazon's approach:
  1. Measure latency at the 99.9th percentile instead of the median.
  2. Build an engineering culture to gradually pull that tail in.
  3. Stop when extra effort no longer improves latency by much.
* The year of removing single points of failure: the rule was to run in at least three data centers. If one data center is lost, customers must still be able to use the service on the remaining two, perhaps more slowly or with fewer features. To verify this, Amazon held "game days":
  1. Notify every team in advance that there will be a drill.
  2. Cut the network to one data center so that it looks like it has disappeared.
  3. Watch how the systems and the people react, and record what breaks.
  4. Fix the issues and repeat the game day until there are no problems left.
  The first time they did it, every team said it was ready, but reality was different: many operations still needed manual work, such as database failover. People had to come into the office and log in, so they could not respond quickly. In other words, people themselves had become a single point of failure.
* Amazon learned one more thing: they knew how to switch to the remaining two data centers, but they had no process for synchronizing the updates written to those two data centers once the old one came back. They only discovered this by actually testing it. He repeated the phrase "everything fails": you need to plan for failure, including when the failed component comes back.
* The year focused on cost efficiency: he admitted this effort failed. Amazon engineers were hired to care about customers, so they preferred working on new ideas for customers rather than optimizing costs, which is a concern of the company and its shareholders.

#### The birth of AWS and a new economic model
* Around 2000, many companies opened APIs for their core functions to see what outsiders could build with them. Amazon opened APIs for four things: the product catalog, search, the shopping cart and payments. Outsiders used them to build price-comparison sites and entirely new interfaces. Having already built shared infrastructure for small internal teams, Amazon wanted other companies that needed internet scale to benefit as well. When S3 launched, the slogan was "storage for the internet": they had businesses like Amazon in mind, not traditional enterprise computing.
* With the large database vendors, the only way to get a discount was to sign a 5- to 10-year contract and pay up front, even though nobody knew how many databases they would need in 5 years. Vendors would also come to audit usage and impose penalties for overuse. Once they had been paid, they had little incentive to provide support; if you wanted help, you had to pay more. In his view, power at that time sat with the vendor, not with the customer.
* AWS did the opposite: pay for what you use, no contractual lock-in, leave whenever you want. He compared it to a restaurant: nobody would agree to put a large sum of money on the table just to get in, with the restaurant keeping the rest if they ate little. This model forces AWS to deliver the best value every day, or customers will leave. It changed the economic model of the entire industry; large companies used to living on huge contracts all had to change as well.

#### The "Renaissance" engineer: lifelong learning, systems thinking, ownership
* To the question "will my job disappear?", he said probably not, but those who do not change will be left behind. Tools are always changing: in school he learned Cobol and assembly, which nobody writes anymore; programming environments have gone from the first generation, through Visual Studio, to Cursor today. Engineers have to accept lifelong learning.
* He quoted Grace Hopper, regarded as one of the first programmers: the most dangerous phrase in the English language is "we've always done it like this". A team that calls itself "a Java shop" and thinks it will run Java forever is likely to be wrong.
* Systems thinking: seeing the big picture, both the good and the bad, and seeing how components relate to each other instead of looking only at one module or one small service.
* Ownership: if you use AI to generate code and the code has bugs, the person who did the work is responsible, not the tool. In heavily regulated industries such as finance or healthcare, when the regulator comes asking, you cannot blame the tool. He mentioned recent news about AI agents going beyond their limits and tens of thousands of websites being compromised: the fault does not lie with the agent; whoever owns the agent is responsible.
* Broad knowledge: companies used to reward engineers who dug very deep into one specialty, the "I-shaped" engineer. He wants "T-shaped" engineers: still deeply skilled, for example still a database expert, but using that knowledge to help colleagues working on the interface or business logic, and conversely understanding how their data is used so they can do their own part better. Companies also have to change what they reward.
* Amazon believes in small teams of about 10 to 12 people, small enough to be fed by two pizzas. If you want to be fast and agile, keep teams small so everyone knows what the others are doing.
* He mentioned formal reasoning and formal verification, especially in security: you must be able to prove that software does what you say it does, for example proving that an AI agent cannot escape its isolated environment. For customers, ideally this should be just a button press. Some techniques that seem unrelated to a database engineer's work turn out to be useful in the long run.

#### Communication: the most underrated skill
* He believes communication is the most underrated skill, because historically few people have invested effort in it. Writing is a very good skill; AI can help, but do not let AI write for you.
* Customers, whether external or inside the company, often come with "we need to use AI to build this". The engineer's job is to find out what really matters to them and see whether the technology they have in mind fits the problem. He pointed out that AI has been around for about 70 years, the term appeared in the 1950s, and many applications such as forecasting, translation and medical document scanning have worked well for a long time.
* You should ask "what is the problem you haven't been able to solve?". For example, upgrading a Java version is not just swapping the virtual machine but also fixing code. With about 4,500 Java applications, that is a mountain of repetitive work, and automating it is good because the risk is relatively low.
* On the availability of Amazon's website and mobile app, he walked through each step of the conversation with the business side:
  1. Ask them how available the system needs to be. The answer is always "four nines".
  2. Explain how much four nines costs, since it requires replication across multiple data centers, and compare it with three nines and two nines.
  3. Work with them to determine which functions must always run. At Amazon there are five: search, product browsing, payments, the shopping cart and reviews, because if reviews stop, people do not buy.
  4. Set a lower availability level for parts that matter to customers but are not core, such as product recommendations, to save cost.
* He gave a few more examples of digging deep into the problem: a law firm needed AI to gather documents before writing a case brief; Amazon used billions of past orders to build a model that scores new orders, with suspicious orders sent to a human reviewer rather than rejected; security engineers had to look up the customer database, open additional files and do a dozen other things before handling each ticket.
* He mentioned a former Amazon employee who later became a CEO and wrote a book advising CEOs: if you want to know the future, just go down to the engineers' room and ask, because engineers usually already know which tools are the right ones. That only happens when engineers communicate well.
* The host added that engineering interviews consist almost entirely of live coding, with no round on communication. Dr. Werner added: junior engineers only become senior once they carry the "scars" from their junior years.

#### AI, prototypes and deciding what to build next
* The host asked: AI has cut the time from idea to working prototype from several weeks to very little, so how does the way teams decide what to build next change?
* Dr. Werner introduced Amazon's Working Backwards process, used for everything to make sure you correctly understand the customer's problem. The process has four documents; he went into detail on the first two:
  1. Write a press release that clearly and simply describes what the new product or feature does for customers.
  2. Write a document of about 10 to 15 frequently asked questions, answering the open questions very clearly.
  3. Revise through many rounds until you know exactly what you want to build, all before writing the first line of code.
  He also said engineers often think about version 2 while still working on version 1 and then cram in all sorts of things; this process keeps version 1 true to what was written.
* For something truly new, where you do not know whether it will work, you should build a prototype and use it yourself for a while. He told of a group of scientists who put together a tool for their research; the more people learned about it, the more it resembled a product, and at that point they still went back and wrote the documents according to the process. Another example is Amazon Fresh, the grocery delivery service: at first nobody knew what customers wanted, what the website should look like or what delivery times to offer; later it turned out that the most popular delivery slot was 6 a.m. Once you know clearly what you need, you have to move to a scalable environment.
* He compared AI to a compiler: a compiler takes code and generates machine code that nobody reads, while AI takes natural language and generates code. This makes managing code even more effort. Financial or healthcare businesses subject to legal regulation spend a lot of time reviewing machine-generated code, because the people doing the work are still responsible.

#### Professional pride
* Much of the best work engineers produce will never be seen by anyone. A customer clicks buy and receives the goods, without thinking about the forecasting or fraud prevention behind it. What keeps an engineer going is professional pride: in how things are executed, how systems are operated, and in operational excellence.
* The host concluded: be proud of your work and bring out the best in people, because in the end we build products for people.

### What I learned
* Failures will definitely happen, so you must design for fault tolerance: run in at least three data centers, automate failover, and verify with game days. I realized a plan on paper is not enough: only by actually cutting off a data center did Amazon see which steps still had to be done manually, and that they had no process for resynchronizing data when the old data center came back.
* Performance measurement must look at the tail, such as the 99.9th percentile, not just the median, because the median hides the experience of half of the customers.
* Technology choices should start from how the data is actually used. The analysis of 70% key-value, 20% single tables and 10% needing relations led to Dynamo and then DynamoDB, showing that using the relational database "big hammer" for everything is both costly and fragile at large scale.
* AWS's pay-per-use model puts customers in control and forces the provider to keep creating value, in contrast to 5- to 10-year prepaid contracts.
* Engineers in the AI era need lifelong learning, systems thinking, ownership of their product including AI-generated code, and to be "T-shaped" engineers broad enough to support teammates in a two-pizza team.
* Communication is a core skill: understand the customer's real problem before talking about AI, and be able to explain the trade-off between availability and cost, like splitting out five functions that must always run from product recommendations, which are allowed a lower level.
* AI helps build prototypes faster, but I still have to understand the customer through the press release and FAQ of Working Backwards, and carefully review what AI produces, because final responsibility still lies with the engineer.

### Applying to my work
- I will read and test every piece of AI-suggested code myself before putting it into the workshop, because I am the one responsible.
- I will write a Working Backwards-style description (what the workshop helps learners do) before starting work.
- Before choosing RDS or DynamoDB for the workshop, I will list the real query patterns to see whether relations are needed or only key-value access.

### Event experience
- I was quite nervous to hear Dr. Werner Vogels speak in person for the first time.
- What I remember most is the 12/12 outage story and the figure of 70% key-value access, because it explains why DynamoDB exists.
- I was surprised when he said communication is the most underrated skill, because until now I had focused only on technical skills.
- The phrase "everything fails" and the game day story made me rethink how I design labs.

#### Event photos
![Check-in](/images/4-eventparticipated/4.2-event2/checkin.jpg)

*Figure 1: Event check-in.*

![222222222](/images/4-eventparticipated/4.2-event2/222222222.jpeg)
*Figure 2: Dr. Werner Vogels speaking on stage next to Ms. My Nguyễn, the host.*

<!-- Check: sources.md has no "Your draft / notes" section, and Key learning and Reflection in the record are still empty, so this page has no point that comes only from your notes. To review: the titles of My Nguyen and Nguyen Gia Hung were read from small text on a slide in the photo, compare them with the original photo; Dr. Werner Vogels's title is not in any source yet; the two-pizza team size follows the transcript at 10 to 12 people, while the MED-001 summary says 10 to 13 people. This revision: removed "Amazon CTO" from the Experience section because no source states that title; the transcript says Cobol while MED-001 says Pascal, so re-listen to the segment at [19:54]; MED-001 notes that the Working Backwards and Amazon Fresh segment [43:33-47:30] is very hard to hear, so re-listen before submitting; the source has no commands or configuration, so the page does not add that section. -->
