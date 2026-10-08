---
title: "Day 3 - 07/10/2026"
date: 2026-01-01
weight: 3
chapter: false
pre: " <b> 1.2.3. </b> "
---

### Objectives

- Finish 3 CloudJourney labs within the day: Creating Your First AWS Account, Managing Costs with AWS Budgets and Getting Help with AWS Support
- Record all 5 credit-earning tasks and the list of credit-draining things to avoid
- Create all 4 budget types in AWS Budgets (Cost Budget, Usage Budget, RI Budget, Savings Plans Budget), then delete all 4 when done
- Submit 1 support request via AWS Support, choosing an appropriate severity level

### Tasks carried out

- CloudJourney lab 000001 - Creating Your First AWS Account
- CloudJourney lab 000007 - Managing Costs with AWS Budgets
- CloudJourney lab 000009 - Getting Help with AWS Support
- Credit-earning tasks and credit-draining things to avoid
- Sample architectures using 200$ credit, how to monitor and optimize costs, 6-month AWS learning path
- Budget types in AWS Budgets and how to clean up after finishing the lab
- AWS Support plans, support request types and severity levels

### Results

- Lab Creating Your First AWS Account: learn about the 5 credit-earning tasks, note down the credit-draining things to avoid, review 2 sample architectures with 200$ credit and how to monitor costs
- Lab Managing Costs with AWS Budgets: create in turn the 4 budget types in AWS Budgets, namely Cost Budget, Usage Budget, RI Budget and Savings Plans Budget, then delete them all to clean up resources
- Lab Getting Help with AWS Support: learn about the AWS Support plans, how to access the Support page and how to change the support plan
- Lab Getting Help with AWS Support: create 1 support request and choose an appropriate severity level

### Problems & how they were solved

- At first I couldn't distinguish the Actual alert threshold (based on actual cost) from the Forecasted threshold (based on forecasted cost), so I didn't know which one to choose → I reread the Budgets section in the AWS Cost Management documentation to understand Actual and Forecasted, then reselected the appropriate thresholds
- I also didn't understand how Utilization differs from Coverage when creating the RI Budget and the Savings Plans Budget → I reviewed the explanation of Utilization and Coverage in the AWS documentation, then redid the RI Budget and Savings Plans Budget following the lab instructions

### Lessons learned

- Costs need to be monitored regularly, and you need to know in advance which services easily drain credit
- AWS Budgets has 4 budget types: Cost Budget tracks cost, Usage Budget tracks usage, RI Budget tracks Reserved Instances, Savings Plans Budget tracks Savings Plans
- A budget only monitors and sends alerts; it does not block or stop resources on its own, and deleting a budget has no effect on running resources
- Every lab should end with a resource clean-up step to avoid being charged
- In AWS Support, support requests are categorized by type and by severity level, and how far you are supported depends on the plan you are on
- Lab Creating Your First AWS Account - earning credit and avoiding credit drain:

| Content | What I learned |
|---|---|
| 5 credit-earning tasks | Done in the Explore AWS widget on AWS Console Home, each task earns 20$ credit:<br>1. Launch EC2 Instance, create an instance then Terminate it when done<br>2. Use Amazon Bedrock Playground, choose the Claude 3 Haiku model and run 1 test prompt; if you get a permission error, create an Account and billing case to request access<br>3. Set up AWS Budgets, create 1 cost budget with a notification email<br>4. Create Lambda Web App, use the Getting started with Lambda HTTP blueprint then delete the function<br>5. Create RDS Database, use Easy create with Aurora PostgreSQL Compatible then delete the instance and cluster, remembering to untick Create final snapshot.<br>• Each task is credited only once; if done wrong, it can be redone<br>• the easiest is Set up AWS Budgets, taking about 10-15 minutes, the hardest is Create RDS Database, about 30-40 minutes plus waiting time |
| Credit-draining things | The most dangerous group, which can burn through the whole 200$ in a few hours:<br>• Amazon SageMaker with Training Jobs, Notebook Instances and Endpoints, because they are easy to forget to stop and they auto-scale<br>• GPU EC2 such as p3.2xlarge, p4d.24xlarge, g4dn.xlarge, because they are very expensive and have no Free Tier<br>• Amazon Redshift, because it has a minimum cluster size and is hard to optimize.<br>• Services that are usable but need care: EC2 only t2.micro or t3.micro, RDS only db.t3.micro, ElastiCache only cache.t3.micro, API Gateway requires monitoring the number of requests.<br>• Defence: create a 200$ monthly Cost budget with 4 alert thresholds 12.5, 25, 50, 75, check Cost Explorer daily and enable Cost Anomaly Detection |
| What credit does not cover | • Reserved Instances, Savings Plans, some products on AWS Marketplace, Support Plans and domain name registration.<br>• Even with credit remaining, you can still be charged if you use services that are not covered, exceed Free Tier limits, use an ineligible region or incur data transfer fees |
| When a Free Plan account closes automatically | • When 6 months have passed since creation or when credit reaches 0, whichever comes first.<br>• Credit cannot be transferred to another account<br>• the remaining credit is shown in the Credits section of the Billing Console |
| General principle | Monitor costs regularly, know in advance which services easily drain credit |

- Lab Creating Your First AWS Account - 2 sample architectures with 200$ credit:

| Architecture           | Used for                                           | Components                                                                                       | Estimated cost over 6 months                                                                            |
| ---------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| Simple Web Application | Personal blog, portfolio, MVP | CloudFront, S3, ALB, EC2 t3.micro, RDS db.t3.micro Single-AZ | • About 232$, exceeding 200$<br>• if too high, the lab suggests dropping the ALB and running Single AZ.<br>• The ALB is the most expensive part, about 99$ |
| Serverless Application | API backend, microservices, event-driven applications | CloudFront, Amplify with S3, Lambda, Bedrock Haiku 3, DynamoDB, Cognito, CloudWatch, optional SNS | • About 60$, assuming about 1000 prompts per month<br>• the advantages are that it is cheap, scales automatically and has no servers to manage |

- Lab Creating Your First AWS Account - cost monitoring and optimization process:
1. Basic level, first week: create several budgets, for example 50$/month alerting at 80%, 25$/month alerting at 50%, 10$/day alerting at 100%; create CloudWatch Alarms for billing at the 25$, 50$, 75$ marks; enable daily cost reports in Cost Explorer and track the 5 most expensive services
2. Advanced level, weeks 2-4: use boto3 to fetch daily costs from Cost Explorer and push them to CloudWatch as a custom metric; attach mandatory tags to resources such as Project, Environment, Owner, CostCenter, AutoShutdown, CreatedDate
3. Once more than 150$ has been spent: see which service costs the most with the command `aws ce get-cost-and-usage --granularity MONTHLY --metrics BlendedCost --group-by Type=DIMENSION,Key=SERVICE`, then stop non-critical instances with `aws ec2 stop-instances` combined with `aws ec2 describe-instances` filtered by the tag `Critical=false`
- Lab Creating Your First AWS Account - 6-month learning path: months 1-2 learn the fundamentals EC2, S3, IAM, VPC, with a budget of about 50-70$; months 3-4 learn Lambda, API Gateway, ECS, CloudWatch, about 60-80$; months 5-6 learn advanced architecture, CI/CD, security and cost optimization, about 70-90$. The suggested certifications, in order, are Cloud Practitioner, Solutions Architect Associate, then Solutions Architect Professional.
- Lab Managing Costs with AWS Budgets - comparison of the 4 budget types in AWS Budgets:

| Budget type          | Tracks            | Metric to choose when creating                                                                                                      | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cost Budget | Cost | Actual or Forecasted alert threshold | • Choose Customize then Cost budget<br>• Budget name `Monthly`<br>• For Period, choose Daily, Monthly, Quarterly or Annually<br>• Recurring Budget to repeat periodically, Expiring Budget to apply once<br>• Fixed if every period is the same, Monthly Budget Planning if each month has a different amount<br>• For Budget scope choose All AWS services, for Aggregate costs by choose Unblended costs.<br>• The time zone in AWS Budgets is always UTC.<br>• To create one quickly, use Use a template with the Monthly cost budget template.<br>• Amount I set: 1$ |
| Usage Budget | Usage | For Budget against choose Usage type groups, then choose EC2: ELB - Running Hours to track running hours, then enter the maximum usage hours |  |
| RI Budget | Reserved Instance | Coverage threshold | • Choose Customize then Reservation budget, set a name, configure Coverage threshold and Budget scope, enter an email in Alert setting, then Create budget.<br>• This part is only for illustration because Reserved Instances require prepayment |
| Savings Plans Budget | Savings Plans | Utilization threshold | • Choose Customize then Savings Plans budget, set a name, configure Utilization threshold, leave Budget scope as default, enter an email in Alert setting, then Create budget.<br>• This part is also only for illustration because Savings Plans require an upfront commitment<br>• Savings Plans are up to 72% cheaper than On-Demand, in exchange for committing to a USD/hour amount for 1 or 3 years |

- Process for creating and cleaning up the 4 budget types in the lab Managing Costs with AWS Budgets:
1. Create the Cost Budget
2. Create the Usage Budget
3. Create the RI Budget
4. Create the Savings Plans Budget
5. Clean up: go to Billing and Cost Management, choose Budgets, select each budget, choose Action then Delete, confirm Delete, and repeat for all 4 budgets
- Comparison of the two alert threshold types:

| Threshold type | Based on | When to use |
|---|---|---|
| Actual | Actual cost | • Alerts when the amount actually incurred exceeds the threshold.<br>• Use it to know for certain how much you have spent, but it only alerts after the money has already been charged |
| Forecasted | Forecasted cost | • Alerts when AWS forecasts that the cost for the whole period will exceed the threshold, before the money is incurred.<br>• Use it to have time to shut down some resources.<br>• One budget can have both types |

- Comparison of Utilization and Coverage when creating the RI Budget and the Savings Plans Budget:

| Metric | Meaning | How they differ |
|---|---|---|
| Utilization | • How much of the purchased RI or Savings Plans has been used up<br>• alerts when this ratio drops below the threshold, meaning you have over-purchased and part of the commitment is going to waste | • In the lab, the Savings Plans Budget is configured with a Utilization threshold<br>• the lab suggests setting the alert at 80-90% to leave time to adjust |
| Coverage | • The proportion of usage covered by RI or Savings Plans<br>• alerts when this ratio drops below the threshold, meaning you are paying On-Demand prices for more usage than intended | In the lab, the RI Budget is configured with a Coverage threshold |

- Lab Getting Help with AWS Support:

| Content                           | What I learned                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AWS Support plans | • How far you are supported depends on the plan you are on.<br>There are 4 plans from lowest to highest, and higher plans include all features of the lower ones:<br>• Basic is free, with chat for account and billing, AWS Support Forums, AWS Health Dashboard and documentation<br>• Business Support+ is for production workloads, with 24/7 technical support via phone, chat and email, unlimited cases, the full set of Trusted Advisor checks and the AWS Support API<br>• Enterprise Support adds a Technical Account Manager, Concierge Support Team, Well-Architected Reviews and a response within 15 minutes when a business-critical system is down<br>• Unified Operations adds AWS Managed Services so that AWS operates the infrastructure for you |
| How to access the Support page and change plans | According to the lab:<br>• open the AWS Management Console, search for AWS Support, in AWS Support Center choose Manage Support Plan, choose a new plan (for example Business Support+) then Get started, choose My account, tick the box agreeing to the terms, click Confirm, and about 15 minutes later the plan is changed.<br>• Accounts use the Basic plan by default<br>• upgrading the plan increases the monthly cost, and Support Plans fees are not covered by credit |
| Support request types | There are 3 types:<br>• Account and Billing Support for invoices, payments, account verification and taxes, available on every plan<br>• Service limit increase to request raising a service's default quota, available on every plan, and should be submitted 2-3 business days in advance<br>• Technical support for technical issues, which cannot be created on the Basic plan and requires Business Support+ or higher |
| Severity levels | There are 5 levels, based on initial response time:<br>• General guidance 24 hours<br>• System impaired 12 hours<br>• Production system impaired 4 hours<br>• Production system down 1 hour<br>• Business-critical system down 15 minutes, a level only available in Enterprise Support and Unified Operations.<br>• The lab's example uses General question for a billing case.<br>• When creating the request, I chose the General guidance 24 hours level |
| Support request creation process | Choose the request type (Account and Billing Support, Service limit increase or Technical support), choose an appropriate severity level, then submit |

### References

* <https://000001.awsstudygroup.com/>
* <https://000007.awsstudygroup.com/>
* <https://000009.awsstudygroup.com/>
* <https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html>
* <https://000001.awsstudygroup.com/vi/6-ki%E1%BA%BFn-tr%C3%BAc-m%E1%BA%ABu-v%E1%BB%9Bi-200-credit/>
* <https://000001.awsstudygroup.com/vi/7-monitoring-v%C3%A0-t%E1%BB%91i-%C6%B0u-chi-ph%C3%AD/>
* <https://000001.awsstudygroup.com/vi/8-faq---gi%E1%BA%A3i-%C4%91%C3%A1p-m%E1%BB%8Di-th%E1%BA%AFc-m%E1%BA%AFc/>
* <https://000001.awsstudygroup.com/vi/9-roadmap-h%E1%BB%8Dc-aws-v%E1%BB%9Bi-free-tier/>
* <https://000007.awsstudygroup.com/vi/3-usage-budget/>
* <https://000007.awsstudygroup.com/vi/4-reservation-budget/>
* <https://000007.awsstudygroup.com/vi/5-saving-plans-budget/>
* <https://000007.awsstudygroup.com/vi/6-clean-up/>

### Evidence:

![Getting Help with AWS Support](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0020.png)

*Getting Help with AWS Support*

![Managing Costs with AWS Budgets](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0021.png)

*Managing Costs with AWS Budgets*

![List of Credit "Killers" to Avoid](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0022.png)

*List of Credit "Killers" to Avoid*

![Detailed Guide for 5 "Money-Making" Tasks](/images/1-worklog/1.2-week2/1.2.3-day3/evd-0023.png)

*Detailed Guide for 5 "Money-Making" Tasks*
