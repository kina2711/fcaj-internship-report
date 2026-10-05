---
title: "Day 1 - 05/10/2026"
date: 2026-01-01
weight: 1
chapter: false
pre: " <b> 1.2.1. </b> "
---

### Objectives

- Understand the rules of First Cloud AI Journey: state all 6 principles, the graduation requirement of 5 projects, the 6-month milestone, and be able to check against the 7-item checklist to complete before Module 1.
- Foundation part of Module 1: distinguish Data Center, Availability Zone, Region, Edge Location, Local Zone; state the 3 ways to work with AWS (Management Console, AWS CLI, AWS SDK) and the credentials used by each.
- Get familiar with Kiro: state the difference between Vibe and Spec modes, the components of an Agent Hook, and the basic Kiro CLI commands.
- Understand cost optimization: list the 8 cost optimization principles and the 4 AWS Support plans, and know how to set AWS Budgets alerts at the forecasted level as well.
- Understand the draw.io architecture drawing conventions well enough to redraw the 2-Availability-Zone VPC diagram on my own and export it to an XML file without rewatching the video.
- Understand the 8-step process for writing a workshop and how to build the site with Hugo and the Learn theme, running at `https://kina2711.github.io/workshop-practice/`.

### Tasks carried out

- Watch the video Prologue: Know before you join First Cloud AI Journey.
- Watch the video Guide to drawing AWS architecture on draw.io.
- Watch the video Module 01-01 - Introduction to AWS.
- Watch the video Guide to building an AWS workshop.
- Watch the video Module 01-02 Management Console.
- Watch the video Module 01-03 Gen AI on AWS - Kiro.
- Watch the video Module 01-04 Cost optimization on AWS.
- Programme rules: 6 principles, graduation requirement of 5 projects, 6-month timeline, preparation checklist before Module 1.
- The concept of cloud computing, the pay-for-what-you-use model, and 4 groups of benefits compared with on-premises infrastructure.
- AWS global infrastructure: Data Center, Availability Zone, Region, Edge Location, Local Zone.
- Three ways to interact with AWS: Management Console, AWS CLI, AWS SDK and the corresponding authentication mechanisms.
- Spec-driven development and Kiro's feature set: Kiro IDE, Kiro CLI, Agent Hook, steering file, Kiro Powers.
- Cost optimization principles, AWS Pricing Calculator, the four AWS Support plans, AWS Well-Architected Framework.
- draw.io architecture drawing conventions and the workshop-building process with Hugo and the Learn theme.

### Results

- Able to distinguish Data Center, Availability Zone, Region, Edge Location and Local Zone; understand the recommendation to deploy across at least 2 Availability Zones and the significance of fault isolation between AZs.
- Understand the difference between the root user and an IAM user when signing in to the Management Console; signing in as an IAM user requires the 12-digit Account ID or the account alias.
- Understand the three entry points to AWS services: the Console uses a password, the CLI and SDK use an access key together with a secret access key, and all three send requests to the AWS Services Endpoint.
- Understand Kiro's feature set: Vibe and Spec modes, Agent Hooks triggered by file events, the 3 steering files `product.md`, `tech.md`, `structure.md`, Timeline Checkpointing, Property-Based Testing, Kiro CLI with custom agents and MCP.
- Understand the cost optimization directions: choosing configurations that closely match needs, Reserved, Savings Plans and Spot, automatically shutting down resources, serverless or fully managed, AWS Budgets combined with cost allocation tags, AWS Pricing Calculator.
- Understand the draw.io architecture drawing conventions: outer frame in the golden ratio 1.618, icons resized to size 60, labels with a white background, orange border `FF8000` for services and blue border `0000FF` for features, save formatted components to a Library, submit as an XML file.
- Understand the Hugo commands `hugo version`, `hugo`, `hugo server` and the `content`, `static/images`, `public` folder conventions of the sample workshop.

### Problems & how they were solved

- I opened draw.io but the left panel had no AWS icon set, and typing ALB or IAM into the shape search box returned nothing either. → It turns out that in the newer version of draw.io, this icon set is hidden in the shapes list. You have to click "More Shapes", then tick AWS2026 for the AWS icon set to appear.

### Lessons learned


**Module 1 foundational knowledge**

- Do not compare two cloud platforms 1-to-1 by CPU count and RAM capacity; performance must be tested at the application layer because AWS hardware has been customised.
- Regions are independent of each other by default, the exception being global-scale services such as DNS. Edge Locations in Vietnam are currently in Hanoi and Ho Chi Minh City.
    - Deploying across at least 2 Availability Zones is recommended. In certification exams, always design for 2 AZs.
    - If only 1 AZ is used for cost reasons, follow this order:
            1. Identify in advance the scenario in which that AZ fails.
            2. Choose one of two approaches: back up or synchronise data to another AZ; or back up to a storage service that replicates data across multiple AZs.
            3. Expected result: if one AZ fails, the system can still be recovered.
    - For customers that need a disaster recovery plan, such as the financial sector, the primary system is placed in one Region, for example Singapore, while the Disaster Recovery system is placed in another Region, for example Malaysia.
    - Static files, videos and images that are frequently downloaded should be pushed out to the Edge Locations in Hanoi and Ho Chi Minh City via CloudFront so that users do not have to download them from Singapore every time. WAF and Route 53 are also at the Edge.
    - A Local Zone is a smaller version of an AZ, located in Vietnam and connected directly to the Singapore Region; use it when a better experience is needed and when data must reside in Vietnam to meet compliance requirements.

**Management Console, AWS CLI, AWS SDK**

- The root user is only used for sign-up; after that, enable MFA and put it away; daily work uses an IAM user. A leaked access key is equivalent to leaking the password to your environment.
    - In an enterprise, root credentials should be split among several holders: one person holds the phone number, one holds the email and password, one holds the hardware MFA key. The finer the split the better; ideally, seal it and never use it again.
- Console sign-in flow:
    1. Go to `https://aws.amazon.com/console/`. If you do not have an account yet, click New to AWS? Sign up.
    2. On the Sign In form, under User type, choose Root user, enter the Email address and click Next; or choose IAM user, enter the 12-digit Account ID or the account alias and click Next.
    3. A successful sign-in lands on Console Home. Find services using the Search box with the shortcut Alt+S, or open All services to browse by group such as Compute, Containers, Management & Governance.
    4. Each service contains multiple features; for example, EC2 has a feature for creating virtual servers and one for creating virtual disks attached to the server.
- Recommended learning path, in order:
    1. Management Console first, to get an overview and become familiar with the components needed when creating a service; some operations can only be done in the Console.
    2. AWS CLI once familiar, configuring the access key and secret access key to write scripts that automate repetitive work.
    3. The language-specific AWS SDK when you need to write an application that calls AWS itself, for example a Python app that creates a virtual server by itself. The SDK handles credential management, request retries, and data conversion and serialisation.
- Do not push access keys to GitHub; protect access keys as you would protect a password.
- When running into problems with billing, account creation, identity verification, or forgetting to shut down a server and incurring charges:
    1. Click the ? icon on the top bar.
    2. Choose Support, then Support Center.
    3. Create a support case to send to the AWS team.
    4. In some cases, if you can prove that you forgot to shut down and have since shut down the practice resources, you may get a refund. The instructor only said "may", with no guarantee.

**Cost optimization and AWS Support**

- Cost optimization principles:
    1. Choose compute, storage and network configurations that closely match current needs and scale up only when needed; do not copy on-premises configurations, which are often over-provisioned for 3 to 5 years. You must review how each service is priced; for example, storage can be priced by capacity or by IOPS.
    2. Reserved and Savings Plans are prepaid, with a 1- or 3-year commitment in exchange for a discount; the longer the commitment, the larger the discount. Spot rents spare capacity at a low price, but AWS reclaims it immediately when needed; use it only when the application can tolerate that.
    3. Delete unused resources and enable automatic shutdown of resources that do not need to run 24/7, for example a server that is only on for 8 hours during working hours.
    4. Serverless or fully managed services charge by actual usage, suitable for sparse traffic; if the server's capacity is fully utilised, renting a whole server may be cheaper.
    5. Designing an optimised architecture is where the main intellectual effort lies; refer to reference architectures and weigh the trade-offs between options.
    6. You can only optimise what you can manage: use AWS Budgets to know current usage and the end-of-month forecast; apply cost allocation tags by department, application and resource to know who spends how much.
    7. Optimise continuously, reviewing whenever there is a new feature or AWS releases a new pricing option.
    8. Use Kiro CLI to generate a cost optimization checklist for each service, for example the prompt `Create a Cost Optimization check list for EC2`, so that no item is missed. Each prompt covers only one service, and the result is a markdown checklist file.
- AWS Budgets: alert thresholds should also be set at the forecasted level, so that you are alerted before actually spending the intended amount.
    - Example in the video: set a budget of 25 or 50 dollars; when practising, turning on service A and service B and then forgetting to turn them off, after just one day the system had already forecast that the month-end total would exceed 25 dollars and alerted in advance.
    - Why you must manage costs yourself on a personal account: if you cannot manage a personal account, an enterprise will not dare to hand you an enterprise account, and the consequences of cost mistakes on an enterprise account are much larger.
    - The hands-on lab Get started with AWS Budgets, code 000007, includes 4 tasks: create an expense budget, create a usage budget, create a preset budget, create a budget savings plan. Detailed step-by-step operations are not yet in the note; follow the lab 000007 page.
- Prices differ by region; large-scale regions are usually cheaper, but Singapore is an exception due to space and power constraints, being about 10 to 20% more expensive than Thailand and Malaysia.
    - Before proposing or estimating for a customer, once the design is done you must carefully calculate costs with AWS Pricing Calculator at `https://calculator.aws/#/`. The tool lets you create an estimate and share it with others, and the results change with both configuration and region.
    - How to open it: go to the page and click Create estimate to use it without signing in, or Sign in for personalized estimates. The subsequent configuration input steps are not yet in the note.
- Choose an AWS Support plan by environment: Basic is the default plan, with no fast-response commitment; Developer is for test and dev environments; Business is highly recommended when running production; Enterprise is for large enterprises with critical systems and comes with a dedicated engineer. You can temporarily upgrade the plan before an important event and then downgrade, but should not upgrade and downgrade constantly. The hands-on lab Support requests with AWS Support is code 000009.
- Additional research on AWS Well-Architected Framework at `https://docs.aws.amazon.com/wellarchitected/`: the framework consists of many yes-or-no questions for checking an architecture against best practices; the tool is available in the Management Console, following the steps generates a report, and each item needing improvement comes with further reading. The exact name and steps in the Console are not yet in the note.
- The checklist before moving on to the next module has 5 items:
    - [ ] Complete all hands-on labs, among which Create an AWS account, code 000001, includes a step to set up MFA for root.
    - [ ] Have set up a Budget on the AWS account.
    - [ ] Have installed Kiro IDE and Kiro CLI.
    - [ ] Understand all concepts, services and features of Module 1.
    - [ ] Have researched and read the AWS Well-Architected Framework documentation.

**Kiro**

- Choose a mode when starting:
    - Vibe: chat first, then build; suitable for exploring ideas.
    - Spec: plan first; Kiro guides you from the initial prompt to requirements, design and a task list before coding; suitable for features that need deep thinking and projects that need to be done in a structured way.
- An Agent Hook runs in 3 steps: an event occurs, a prompt is sent to a background agent, Kiro updates files automatically. How to create a hook:
    1. Open Create an agent hook, describe the hook in natural language, or choose a built-in suggestion such as Update my documentation, Optimize my code, Language localization.
    2. Check the fields Kiro generates: Title, Description, Event, File path(s) to watch, Instructions for Kiro agent.
    3. For Event, choose one of 4 types: File Created, File Saved, File Deleted, Manual Trigger.
    4. Example in the video: a Changelog Updater hook, Event is File Saved, watching `*.py`, `requirements.txt`, `conftest.py`, `migrate_categories.py`, `templates/*.html`; each time a file is saved, Kiro writes the time, the changed file name and a summary of the change to `CHANGELOG.md`.
    5. Expected result: the screen changes to Hook created, with the Hook enabled toggle switched on.
- For an existing project, you should ask Kiro to generate steering files before making changes. Kiro creates them in `.kiro/steering/`: `product.md` for the business side, `tech.md` for technologies and frequently used commands, `structure.md` for project organisation; you can add your own steering such as `coding-standards.md`.
- Use Timeline Checkpointing to try multiple approaches and return to a checkpoint with the Restore button when needed; a checkpoint can cover one file or multiple files.
- Property-Based Testing reads requirements written in the EARS format and generates hundreds of test cases; it runs in 3 ways: manually after code is generated, automatically via an Agent Hook, or during spec task execution.
- Kiro CLI commands seen in the video:
    - `kiro-cli` to start.
    - `/agent list` to view the list of custom agents, `/agent swap devops-agent` to switch to another agent.
    - `/mcp` to view the loaded MCP servers.
    - `/tools` to view servers still pending; `kiro-cli settings mcp.initTimeout {timeout in int}` to increase the MCP server loading timeout.
- Do not connect too many MCP servers at once because it consumes tokens, fills up the context window, is slow, gives poor results and is prone to fabricating information; use a custom agent that loads only what is needed, or Kiro Powers that activate only when needed.
- Learners must create a Kiro Free Tier account, 50 credits per month, applicable only when signing in with a social media account. The hands-on lab Kiro Spec Driven Development, code 000180, is mandatory and covers installing Kiro, signing in to Kiro IDE, building an application with Kiro SDD, practising Kiro SDD and an introduction to Kiro CLI.

**Guide to building an AWS workshop**

- The 8-step workshop process:
    1. Do the lab once first: you must understand the technique, solution and architecture yourself before you can write and share.
    2. Note down what needs to be prepared or added, for example granting an IAM Role, creating policies, prerequisites.
    3. Outline the structure: split into parts, each part with sub-sections; list the content, steps and images needed for each sub-section. The sample workshop has 6 parts; the guide has 4 parts.
    4. Delete the resources created in the first run.
    5. Do it a second time: if confident, take screenshots as you go; if unsure, record the screen so that if you make a mistake you still have material to capture from.
    6. Edit images: number the steps on the images, then insert them into the article.
    7. Write the complete content, then check formatting, fonts and logos; add important notes such as what needs to be prepared and which resources are costly and must be deleted immediately after finishing.
    8. Add attachments such as code files, Dockerfile, CloudFormation YAML template files.
- Install tools, in order:
    1. Visual Studio Code, then go to Extensions and install Markdown All in One by Yu Zhang.
    2. Snagit for capturing and editing images, with a FREE trial version; Active Presenter for screen recording.
    3. draw.io for drawing architecture: click Start to use it in the browser or Download to install it locally; also download the AWS architecture icon set.
    4. Hugo: on Windows use one of three commands `choco install hugo-extended`, `scoop install hugo-extended`, `winget install Hugo.Hugo.Extended`, then run `hugo version` to check.
    5. Theme hugo-theme-learn; in `config.toml` declare `theme = "hugo-theme-learn"` and an `[outputs]` block with `home = [ "HTML", "RSS", "JSON"]` to enable search.
- Hugo commands: `hugo version` checks the installation; `hugo` builds all Markdown into a static website in the `public` folder, which is what gets deployed; `hugo server` runs a local web server at `localhost:1313`, and when running multiple sites at once the port may differ. When running `hugo serve`, the page refreshes automatically whenever a file changes.
- File structure conventions: the `content` folder is divided into folders, each folder being one part with at most 2 levels, for example 2. and 2.1.; each folder has `_index.md` for English and `_index.vi.md` for Vietnamese, and if only Vietnamese has been written so far, copy `_index.vi.md` to `_index.md` to translate later; images go in `static/images`, which can be split into subfolders; `public` is created by Hugo at build time. The self-check exercise on page 3.1: delete the `public` folder, then run again and see whether the site still works.
- Content-writing conventions for a page:
    1. Front Matter includes `title`, `date`, `weight`, `chapter`, `pre`, where `weight` determines the order. Example from the sample workshop: `title : "Viết nội dung"`, `weight : 2`, `chapter : false`, `pre : " <b> 2. </b> "`.
    2. Section headings within a page consistently use h4 `####`.
    3. After writing the headings, generate the table of contents with Ctrl + Shift + P, type Create Table of Contents, select the Markdown All in One option and press Enter.
    4. The introduction icon is inserted with the `figure` shortcode, for example `{{</* figure src="../images/fcj.png" title="First Cloud Journey" width=150pc */>}}`.
    5. Notes use the Notice shortcode with 4 types: Note, Info, Tip, Warning. The exact Notice syntax is not yet in the note.
    6. Attachments are placed in a folder with the same name as the page, such as `_index.files` and `_index.vi.files`, then use the `attachments` shortcode with `title` and `pattern`, for example `{{%/*attachments title="Dockerfile" pattern="Dockerfile"/*/%}}`.
    7. Tables are created with Tables Generator: choose the Markdown tab, set the number of rows and columns in the Table menu, enter the data, click Generate, then Copy to clipboard and paste into the file.
- Image standards: capture in Chrome with the bookmark bar turned off, keep zoom at 100%, Full HD 1920 x 1080 screen, PNG format, text on images size 18; when inserting, use `?width=90pc` for full-screen images, `?width=40pc` or `?width=50pc` for cropped images; when writing multilingual content, `config.toml` must be updated.

**Guide to drawing AWS architecture with draw.io**


**1. Prepare the tools**

1. Open draw.io, create a new diagram, in the category tree choose Cloud then AWS, select any template and click Create. Doing so makes the whole AWS icon set available in the left panel. If you do not see the AWS icons, it is usually because this Cloud then AWS step was skipped.
2. Choose a Google Drive folder to save to; all diagrams will be stored in that folder.
3. Reduce the browser zoom to 80 to 90% for a wider workspace.
4. The icon set in draw.io is incomplete, so download the AWS Architecture Icons for PowerPoint at `https://aws.amazon.com/vi/architecture/icons/`, extract it and open the pptx file. PowerPoint opens in Protected View; click Enable Editing if you need to edit. Each slide has a Service Icon row for the service level and a Resource Icon row for the resource or feature level; use PowerPoint's Search box to find icons, then save the ones you need as image files.
5. Clear the template diagram completely before starting to draw: drag-select, then press Delete.

**2. Drawing principles**


**Level of detail**

- Principle: before drawing, define the scale of the architecture to choose a suitable outer frame. Draw at multiple levels: the 2-tier level first, then add the detailed level afterwards. Do not cram too much information into one diagram.
- Reason: cramming everything into one picture is "making things hard for yourself"; the picture becomes cluttered and hard to read.
- How: CIDR and route tables go in a separate network architecture diagram; have a separate overview diagram and a separate container diagram; the overview diagram should stop at, say, the ECS level. In draw.io, put each level on a separate page, for example Page-1, Page-2, Page-3.

**Outer frame in the golden ratio**

- Principle: draw the AWS Cloud frame as a horizontal rectangle following the golden ratio 1.618 as closely as possible.
- Reason: easy to put into slides or Word documents.
- How: width equals height multiplied by 1.618, for example a height of 500 gives a width of about 809, a height of 700 gives a width of about 1132. Click the frame and set the size in the Arrange tab, under Size.
- Common mistake: running out of space and stretching arbitrarily, which throws the frame out of proportion. When out of space, stretch the frame and then recalculate using the golden ratio. In the video, the final frame ended up at 1200 x 760 after several expansions.

**Layering the Region, VPC, AZ, subnet boundaries**

- Principle: groups are nested in the order AWS Cloud, Region, VPC, Availability Zone, subnet; each layer is smaller than the outer one and aligned to be balanced.
- How: drag the groups from the AWS / Groups category in the left panel onto the canvas, in the correct order from outside to inside.
- An Availability Zone is a physical concept, so it does not sit entirely inside the VPC but extends slightly beyond it: when drawn horizontally it extends on both sides, when drawn vertically it extends upward. After drawing one AZ, copy it to make the other AZ so they are identical.
- Each AZ has a pair of public subnet and private subnet, aligned as symmetrically as possible.

**Shared services area**

- Principle: leave an empty area below the VPC for shared services that are not inside the VPC.
- How: drag a Generic group into that area, name it Share Services, then in the Text tab change the label's Position to the left. The example in the video places IAM and Certificate Manager here.

**Component placement**

- Users and the Internet are placed outside the AWS Cloud frame.
- The public load balancer is placed level with the public subnet or slightly above, but must be attached to the public subnet because the ALB only works when there is a public subnet.
- In the video's example: two EC2 Web/App instances are in the two public subnets; the Primary DB is in the private subnet of one AZ, the Standby DB is in the private subnet of the other AZ. If a subnet is too small to fit the icon, enlarge the subnet.

**Data flow direction and connectors**

- Principle: use arrows to show the flow of requests.
- How: for example, draw arrows from the ALB distributing load to the two EC2 Web/App instances, and from Web/App to the Primary DB; after drawing, realign the arrows.
- Common mistake: arrows running over label text; for the fix, see the labels section below.


**Icon size**

- Principle: resize all icons to size 60.
- Reason: when there is a central drawing repository and everyone follows the same principle, it is easy to find, share and edit each other's diagrams. Default icons dragged out are usually too large for what is needed.
- How: click the icon, go to the Arrange tab, set Size to 60.

**Component labels**

- Principle: labels must have a white background and no extra whitespace.
- Reason: without a background, text is hidden by arrows or group boundaries; extra whitespace makes the text messy.
- How: select the label, go to the Text tab, set Background Color to white; trim leading and trailing whitespace from the name.

**Colors**

- Principle: label borders are distinguished by type.
    - Services such as EC2, RDS, IAM, Kinesis use an orange Border Color `FF8000`.
    - Sub-features use a blue Border Color `0000FF`, for example Application Load Balancer is a feature of Elastic Load Balancing.
- How: select the label and set Border Color in the Text tab.


**Correct icon generation and correct source**

- Principle: do not mix old-generation icons with new-generation icons in the same picture.
- How: searching "ec2" in draw.io returns the old-generation icon; EC2 must be taken from the AWS / Compute group. Missing icons are taken from the AWS PowerPoint file.
- Common mistake: copying architecture images from the internet and piecing them into a proposal. Each source has a different icon style, so the picture becomes patchy with no consistent style, and customers find it very unpleasant to look at.

**Alignment and spacing**

- Principle: group layers and AZs must be balanced and symmetrical.
- How: align by hand while dragging, and draw.io also suggests alignment when dragging components; draw one AZ and copy it so both sides are identical; use the Arrange tab to set exact sizes.


**Consistency when working in a team**

- Principle: when working in a team, agree on drawing style and formatting, and have a shared repository that everyone can access to view and edit.
- How: save formatted components to a Library, submit diagrams as XML to the shared repository.

**3. Step-by-step diagram building process**

1. Define requirements: what the diagram is for, overview or detailed level, and how large the scale is. The example in the video is a 2-tier web application: users on the Internet reach the ALB, which distributes load to 2 EC2 Web/App instances, which connect to the Primary and Standby databases, along with shared IAM and Certificate Manager. 
2. Choose components and find icons:
        - Group: AWS / Groups.
        - Application Load Balancer: AWS / Network & Content Delivery.
        - EC2: AWS / Compute.
        - RDS: search "rds" on the panel.
        - IAM: AWS / Security, Identity & Compliance.
        - Certificate Manager: found directly by search.
        - User: search "user"; for Internet, choose the cloud icon.
3. Build the layout: drag out the AWS Cloud frame and set its size by the golden ratio; nest Region, VPC, 2 AZs, each AZ with a pair of public and private subnets; leave a Share Services area below the VPC. At this point you should self-check: AWS Cloud, Region, VPC, 2 AZs, 2 public subnets, 2 private subnets are all present, and the frame has the correct ratio.
4. Place components: User and Internet outside the frame; ALB level with the public subnet; EC2 in the public subnet; DB in the private subnet; IAM and Certificate Manager in Share Services. Resize each icon to size 60.
5. Connect: draw arrows from the ALB to the two EC2 instances and from Web/App to the Primary DB, then realign the arrows.
6. Label: name each component, white background, orange or blue border by type, trim extra whitespace. For a detailed diagram, add CIDR and the VPC name.
7. Do a final check using the checklist in section 7.

**4. Working around the tool's limitations**

- The shape search box is very poor; typing ALB, ELB, IAM often returns nothing; you have to open each group manually as listed in step 2.
- When a large group overlaps and you cannot click the object underneath: select the overlapping object and press Cmd or Ctrl + Shift + B to Send to Back; each press moves it back one layer, so press several times to send it all the way back.
- Performing an action with no object selected shows the error "Nothing is selected".
- Icons added from image files are always very large because they are original icons to preserve quality; you must resize them to 60 and format them like the other icons.

**5. Library for reuse**

1. Create one via File > New Library > Google Drive, with a name such as My-AWS.
2. Open it via File > Open Library, choose My-AWS, then Select. The Library appears as a separate section in the left panel and the file `My-AWS.xml` is stored in Google Drive.
3. Only drag fully formatted components into the Library; you can drag-select a whole cluster such as VPC, subnet, Web/App, DB, selecting at whatever level you want to save.
4. For missing icons, click the plus sign or pencil on the Library, add an image, drag in the image file saved from PowerPoint; then drag the icon out, resize to 60, name it, apply the border convention, drag the formatted version into the Library, delete the unformatted version and save.
5. Once the Library has enough items, you no longer need to dig through hundreds of icons; for a new customer, just drag out the basic architecture and modify it, adding CIDR and the VPC name for a detailed diagram.

**6. Exporting and submitting**

1. Export an image via File > Export as > PNG; enabling Transparent Background keeps only the components, disabling it gives a white background. PDF export is possible; Visio export works but does not look good.
2. Submit and share via File > Export as > XML, choose All Pages, set a name, then Download as a `.xml` file.
3. Verify via File > Import from > Device, opening the `.xml` file; the diagram must reappear with all pages as in the original.
4. The video's exercise: choose any AWS architecture from the internet, redraw it following exactly this set of conventions, then submit the XML file to contribute to the shared architecture repository.

**7. Final diagram checklist**

- [ ] The diagram is at exactly one level of detail, with no CIDR or route tables crammed into the overview diagram.
- [ ] The AWS Cloud frame is horizontal, close to the 1.618 ratio.
- [ ] Groups are nested in the correct order AWS Cloud, Region, VPC, AZ, subnet; AZs extend beyond the VPC; the two AZs are identical.
- [ ] Each AZ has a symmetrical pair of public and private subnets.
- [ ] Users and the Internet are outside AWS Cloud; shared services are inside Share Services.
- [ ] The ALB is attached to the public subnet.
- [ ] Arrows show the complete flow and have been tidied up.
- [ ] All icons are size 60 and of the same icon generation.
- [ ] All labels have a white background, no extra whitespace, orange border `FF8000` for services, blue `0000FF` for features.
- [ ] Exported XML with All Pages and re-imported to confirm all pages are present.

**Tips from the programme's Prologue**

- Two project evaluation criteria: correctness, meaning it actually runs; and whether you are truly proud enough to show off the product and put it in your profile and CV. The project does not need to be very large; what matters is progress and continuous improvement.
- How to find and do a project:
    1. Choose a career direction; for example, if you want to be a data engineer, do a project building a data platform on AWS.
    2. Find ideas in AWS Solutions, AWS Reference Architecture, or ask AI to suggest projects that would impress recruiters for the position you want.
    3. Make it work, then improve it gradually.
    4. Share it at the end-of-month meetup, on your personal page, in your CV.
- The 6-month deadline is a goal so you do not give up halfway; learners must set their own deadlines and be disciplined because the team are volunteers. When stuck, you must ask in the group or on WhatsApp after searching on your own first.
- The checklist before Module 1 has 7 items:
    - [ ] Create a personal AWS account.
    - [ ] Create an AWS Builder Profile.
    - [ ] Create a WhatsApp account.
    - [ ] Create a LinkedIn Profile as early as possible.
    - [ ] Join the AWS Study Group on Facebook and LinkedIn.
    - [ ] Follow the `awsstudygroup.com` site.
    - [ ] Follow the Study Group's two YouTube channels: the theory channel and the hands-on channel.
- Look up hands-on labs by code: type the lab number, add a dot and `awsstudygroup.com`. Each module has mandatory labs; the labs on the main page are optional.

### References

* <https://www.youtube.com/watch?v=95quNuhvMT0>
* <https://www.youtube.com/watch?v=Gz56QzLQ_Yo>
* <https://www.youtube.com/watch?v=UIw8UxGZCHA>
* <https://www.youtube.com/watch?v=l8isyDe-GwY>
* <https://www.youtube.com/watch?v=mXRqgMr_97U>
* <https://www.youtube.com/watch?v=qVCF7UjYC5s>
* <https://www.youtube.com/watch?v=uAQCm4sm_1c>
* <https://aws.amazon.com/vi/architecture/icons/>
* <https://calculator.aws/#/>
* <https://docs.aws.amazon.com/wellarchitected/>

### Evidence:

![Watch the video Guide to drawing AWS architecture on draw.io: building a VPC diagram with public and private subnets across 2 Availability Zones](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0004.png)

*Watch the video Guide to drawing AWS architecture on draw.io: building a VPC diagram with public and private subnets across 2 Availability Zones*

![Watch the video Guide to building an AWS workshop: the part on installing Hugo and the Learn theme](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0005.png)

*Watch the video Guide to building an AWS workshop: the part on installing Hugo and the Learn theme*

![Watch the video Module 01-01 - Introduction to AWS](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0006.png)

*Watch the video Module 01-01 - Introduction to AWS*

![Watch the video Module 01-02 Management Console: signing in as root user or IAM user](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0007.png)

*Watch the video Module 01-02 Management Console: signing in as root user or IAM user*

![Watch the video Module 01-03 Gen AI on AWS - Kiro](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0008.png)

*Watch the video Module 01-03 Gen AI on AWS - Kiro*

![Watch the video Module 01-04 Cost optimization on AWS: checklist before moving on to the next module](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0009.png)

*Watch the video Module 01-04 Cost optimization on AWS: checklist before moving on to the next module*

![Issue: AWS icon set hidden in draw.io](/images/1-worklog/1.2-week2/1.2.1-day1/evd-0010.png)

*Issue: AWS icon set hidden in draw.io*
