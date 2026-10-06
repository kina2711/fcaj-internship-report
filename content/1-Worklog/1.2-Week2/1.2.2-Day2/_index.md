---
title: "Day 2 - 06/10/2026"
date: 2026-01-01
weight: 2
chapter: false
pre: " <b> 1.2.2. </b> "
---
### Objectives
- Watched all 6 Module 01 lectures and the FCAJ Community Day video, with separate notes for each one.
- Able to restate AWS's definition of cloud computing, its 4 main benefits and the 3 things that make AWS different.
- Able to redraw the 4 layers of AWS global infrastructure (data center, Availability Zone, Region, Edge Location) and state 3 criteria for choosing a Region.
- Able to distinguish the 3 ways of working with AWS (Management Console, AWS CLI, AWS SDK): what each one authenticates with and who the caller is.
- Able to list 8 cost optimization measures, 3 payment methods, 4 AWS Support plans and the minimum plan that should be used for production environments.
### Tasks carried out
- Watch lecture: Module 01-01 - What Is Cloud Computing?
- Watch lecture: Module 01-02 - What Makes AWS Different?
- Watch lecture: Module 01-03 - How to Start Your Journey to the Cloud
- Watch lecture: Module 01-04 - AWS Global Infrastructure
- Rewatch the event recording: 23-05-2026 | FCAJ Community Day
- Watch lecture: Module 01-05 - Tools for Managing AWS Services
- Watch lecture: Module 01-06 - Cost Optimization on AWS and Working with AWS Support
- **Module 01-01, what cloud computing is:** AWS defines cloud computing as the on-demand delivery of IT resources over the Internet, where you pay for what you use. I no longer need to buy and install servers, storage devices or network equipment myself; I just send a request with the configuration I want. The provider checks whether the sender is authenticated and authorized, creates a virtual server and then returns the connection details. The lecture names four benefits:
    - Pay for what you use: a server that only needs to run in the morning can be turned off in the evening.
    - Faster development thanks to built-in automation and management features.
    - Flexible scaling of resources up or down: use 4 CPUs today, and if users grow tomorrow, upgrade to 8 CPUs. With on-premises infrastructure, the configuration has to be planned 3 to 5 years ahead.
    - Global expansion through the provider's infrastructure network.
- **Module 01-02, what makes AWS different:**
    - AWS has led the Gartner Magic Quadrant for 13 consecutive years, as of the end of 2023.
    - On pricing, AWS wants customers to pay less and less for the same service, and has cut prices more than 120 times. The economies-of-scale flywheel has 6 steps: value-based pricing, more customers, increased usage, more infrastructure, economies of scale, lower infrastructure costs, and then back to price cuts.
    - AWS culture is embodied in Amazon's Leadership Principles. The instructor analyzed three principles in depth: Customer Obsession, Ownership and Deliver Results.
- **Module 01-03, starting the journey to the cloud:** AWS has the most and the deepest courses, both from AWS and from third parties, so self-study is entirely possible. The instructor advises having a study partner, because AWS services are closely interrelated and the number of services grows very quickly. You should sign up for an AWS account as early as possible and try services yourself with the Free Tier, instead of only learning in pre-built lab environments. The slides list Udemy, Cloud Guru and the AWS learning paths page. The First Cloud Journey programme focuses on learners building their own workshops and personal projects to prove their skills to employers.
- **Module 01-04, global infrastructure:**
    - A single data center can hold up to tens of thousands of servers, using hardware optimized specifically for AWS. Therefore, when comparing providers you must look at actual measured performance; nominal specs like 1 CPU, 4 GB RAM say nothing.
    - Choose a Region based on three criteria. First, proximity to users to reduce latency; for users in Vietnam, choose Singapore. Second, whether that Region already offers the services you need. Third, cost: Regions in the US are cheaper than Singapore, so development and test environments can be placed in the US to save money.
- **Module 01-05, management tools:**
    - The root user is used for the first sign-in; after that, create an IAM user for daily use.
    - After signing in to the Console, find services with the search box; each service has its own management page. To get help from AWS, open the Support menu, go to Support Center and create a support case.
    - AWS CLI is an open-source tool that can do the equivalent of what is done on the Console.
    - AWS SDK is a set of libraries for many languages. When calling an API, the SDK handles 5 things for the developer: credential management, retries, data marshalling, serialization and deserialization.
- **Module 01-06, cost and AWS Support:** The lecture lists 8 cost optimization measures:
    - Choose the right configuration and storage location; do not lift the on-premises configuration to the cloud as-is.
    - Use the On-demand, Reserved Instance, Savings Plan and Spot payment methods.
    - Delete unused resources, and automatically start and stop resources that do not need to run 24/7.
    - Use serverless services.
    - Design an optimized architecture.
    - Use AWS Budgets.
    - Manage costs by department with cost allocation tags.
    - Monitor and optimize continuously.
    The lecture also introduces AWS Pricing Calculator: add services, enter usage, then view the estimated total cost, and the estimate can be shared with others. Costs vary by Region, service and configuration.
- **FCAJ Community Day:**
    - Session on context when working with AI: good context has 4 parts: goal, situation, constraints and relevant documents. Two common mistakes are stuffing everything you find into the same conversation, and repeating what the AI already knows.
    - Amazon Quick Suite connects company data with AI agents for reporting, analysis and automation.
    - Amazon CloudFront flat-rate pricing plan: each distribution pays a fixed monthly rate that already includes WAF, DDoS protection, Route 53 and CloudWatch, so the bill does not spike. Currently this plan must be enabled manually on the Console.
    - LLM non-determinism: setting temperature = 0 still does not guarantee the same output, due to floating-point computation on GPUs and because providers batch multiple requests together. To reduce it, you can run multiple times and take the majority result, self-host the model, enforce structured output, and design the system to tolerate variation from the start.
    - Multi-agent system for startup credit scoring: a manager agent orchestrates 5 specialist agents (finance, market, team, risk, compliance).
### Results
- Able to restate AWS's definition of cloud computing: on-demand delivery of IT resources over the Internet with pay-as-you-go pricing. Able to list the 4 benefits, with examples compared to on-premises infrastructure such as turning servers off in the evening or upgrading from 4 to 8 CPUs.
- Able to distinguish the 4 infrastructure layers. An Availability Zone has one or more data centers; AZs are fault-isolated from each other and connected by private high-speed links. A Region has at least 3 AZs, and data by default stays in the Region where it was created. Edge Locations run Amazon CloudFront, AWS WAF and Amazon Route 53. Vietnam already has 2 locations, in Hanoi and Ho Chi Minh City.
- Understand the 3 ways of working with AWS: the Console authenticates with a password, AWS CLI authenticates with an access key and secret access key, and AWS SDK uses the same key pair but the caller is an application. All 3 ways send API requests to the AWS Services Endpoint.
- Able to list the 8 cost optimization measures, how to use AWS Pricing Calculator, and the 4 AWS Support plans: Basic for exploration, Developer for development and testing, Business for production environments, Enterprise for large corporations.
### Problems & how they were solved
- I could not yet distinguish Reserved Instance from Savings Plan, because the lecture only said both get discounts when you commit to 1 or 3 years of usage. → I read the AWS documentation page on Savings Plans. A Savings Plan commits to an amount of money per hour, so it is more flexible than a Reserved Instance, which is tied to a specific instance type.
### Lessons learned
- The root user should only be used to sign up for the account and set up security, for example enabling MFA; after that you should sign out and use an IAM user for daily work. Signing in as an IAM user requires also entering the 12-digit Account ID (or account alias).
- For high availability, you should deploy across at least 2 AZs. This is similar to the model of two data centers running in parallel in traditional infrastructure, except that you do not have to pay for the high-speed link yourself. For development or test environments, running in 1 AZ with backups is enough.
- On-demand is the default model and also the most expensive. Reserved Instance or Savings Plan gives a discount for a 1- or 3-year commitment; the longer the commitment, the bigger the discount. Spot gives up to 90% off but can be reclaimed at any time, so it can be combined with Savings Plan, for example with 10 servers, 4 run on Savings Plan and the rest run on Spot. 
- Architecture design affects cost the most. Poor queries or architecture make the system slow, forcing a configuration upgrade, and then discounts cannot make up for it. 
- AWS Budgets is used to set alert thresholds, for example alerting when 10 USD has been spent or when the forecast end-of-month cost reaches 100 USD. Budgets can also trigger actions, such as shutting down servers when a threshold is exceeded. With cost allocation tags, you must tag resources and enable the feature before costs can be separated by department or application.
- Only the Developer plan and above can submit technical questions to AWS Support. Production environments should use at least the Business plan. In an urgent incident you can upgrade the plan for a short period, but this should not be done regularly.
### References
* <https://www.youtube.com/watch?v=2PQYqH_HkXw>
* <https://www.youtube.com/watch?v=HSzrWGqo3ME>
* <https://www.youtube.com/watch?v=HxYZAK1coOI>
* <https://www.youtube.com/watch?v=IK59Zdd1poE>
* <https://www.youtube.com/watch?v=IY61YlmXQe8>
* <https://www.youtube.com/watch?v=XjMCrcDRACQ>
* <https://www.youtube.com/watch?v=pjr5a-HYAjI>
### Evidence:
![YouTube video "23-05-2026 | FCAJ Community Day" (AWS Study Group channel): speaker Tinh Truong (Platform Engineer, GoTymeX) presents the slide "Context Is Everything: Making AI Actually Work for You".](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0011.png)
*YouTube video "23-05-2026 | FCAJ Community Day" (AWS Study Group channel): speaker Tinh Truong (Platform Engineer, GoTymeX) presents the slide "Context Is Everything: Making AI Actually Work for You".*
![Video "Module 01-01 - Điện Toán Đám Mây Là Gì ?" (AWS Study Group), slide "What is cloud computing?" with the definition: on-demand delivery of IT resources over the Internet with a pay-as-you-go pricing policy.](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0012.png)
*Video "Module 01-01 - Điện Toán Đám Mây Là Gì ?" (AWS Study Group), slide "What is cloud computing?" with the definition: on-demand delivery of IT resources over the Internet with a pay-as-you-go pricing policy.*
![Video "Module 01-02 - Điều Gì Tạo Nên Sự Khác Biệt Của AWS ?" (AWS Study Group), slide titled "AWS, what makes the difference?".](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0013.png)
*Video "Module 01-02 - Điều Gì Tạo Nên Sự Khác Biệt Của AWS ?" (AWS Study Group), slide titled "AWS, what makes the difference?".*
![Video "Module 01-03 - Bắt Đầu Hành Trình Lên Mây Như Thế Nào" (AWS Study Group), slide listing third-party AWS course providers (udemy.com, cloudguru.com) and AWS learning paths (aws.amazon.com/vi/training/learning-paths).](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0014.png)
*Video "Module 01-03 - Bắt Đầu Hành Trình Lên Mây Như Thế Nào" (AWS Study Group), slide listing third-party AWS course providers (udemy.com, cloudguru.com) and AWS learning paths (aws.amazon.com/vi/training/learning-paths).*
![Video "Module 01-04 - Hạ Tầng Toàn Cầu Của AWS" (AWS Study Group), slide "Availability Zone": an AZ consists of one or more data centers, fault isolation, private high-speed connections between AZs, recommendation to deploy across at least 2 AZs.](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0015.png)
*Video "Module 01-04 - Hạ Tầng Toàn Cầu Của AWS" (AWS Study Group), slide "Availability Zone": an AZ consists of one or more data centers, fault isolation, private high-speed connections between AZs, recommendation to deploy across at least 2 AZs.*
![Video "Module 01-05 - Công Cụ Quản Lý AWS Services" (AWS Study Group), slide "AWS Command Line Interface (CLI)" with a diagram of a User accessing the AWS Services Endpoint via the Management Console (Passwords) and AWS CLI (Access key / Secret Access key).](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0016.png)
*Video "Module 01-05 - Công Cụ Quản Lý AWS Services" (AWS Study Group), slide "AWS Command Line Interface (CLI)" with a diagram of a User accessing the AWS Services Endpoint via the Management Console (Passwords) and AWS CLI (Access key / Secret Access key).*
![Video "Module 01-06 - Tối Ưu Hóa Chi Phí Trên AWS và Làm Việc Với AWS Support" (AWS Study Group), slide "Working with AWS Support" listing 4 support plans: Basic, Developer, Business, Enterprise, and that the support plan can be upgraded for a short period.](/images/1-worklog/1.2-week2/1.2.2-day2/evd-0017.png)
*Video "Module 01-06 - Tối Ưu Hóa Chi Phí Trên AWS và Làm Việc Với AWS Support" (AWS Study Group), slide "Working with AWS Support" listing 4 support plans: Basic, Developer, Business, Enterprise, and that the support plan can be upgraded for a short period.*
