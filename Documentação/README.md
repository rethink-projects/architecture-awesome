# Padrão de documentação Software GuideBook. EN-US
## Context
A context section should be the first section of the software documentation and simply used to set the scene for the remainder of the document.

### Intent
A context section should answer the following types of questions:

What is this software project/product/system all about?

What is it that's being built?

How does it fit into the existing environment? (e.g. systems, business processes, etc)

Who is using it? (users, roles, actors, personas, etc)

### Structure
The context section doesn't need to be long; a page or two is sufficient and a context diagram is a great way to tell most of the story.

### Motivation
It's surprisingly common to see software documentation that doesn't start by setting the scene and, 30 pages in, you're still none the wiser as to why the software exists and where it fits into the existing IT environment. A context section doesn't take long to create but can be immensely useful, especially for those outside of the team.

### Audience
Technical and non-technical people, inside and outside of the immediate software development team.

### Required
Yes, all software documentation should include an initial context section to set the scene.

## Functional Overview
Even though the purpose of technical software documentation isn't to explain what the software does in detail, it can be useful to expand on the context and summarise what the major functions of the software are.

### Intent
This section allows you to summarise what the key functions of the system are (use cases, user stories, etc). A functional overview should answer the following types of questions:

Is it clear what the system actually does?

Is it clear who the important users are (roles, actors, personas, etc) and how the system caters for their needs?

Alternatively, if your software automates a business process or workflow, a functional view should answer questions like the following:

Is it clear what the system does from a process perspective?

What are the major processes and flows of information through the system?

### Structure
By all means refer to existing documentation if it's available, whether that's in the form of functional specifications, use case documents, lists of user stories, etc. However, it's often useful to summarise the business domain and the functionality provided by the system. Again, diagrams can help, and you could use a UML use case diagram or a collection of simple wireframes showing the important parts of the user interface. Either way, the purpose of this section is to provide a functional overview.

Alternatively, if your software automates a business process or workflow, you could use a flow chart or UML activity diagram to show the smaller steps within the process and how they fit together. This is particularly useful to highlight aspects such as parallelism, concurrency, where businesses processes fork or join, etc.

### Motivation
This doesn't necessarily need to be a long section, with diagrams being used to provide an overview. Where a context section summarises how the software fits into the existing environment, this section describes what the system actually does. Again, this is about providing a summary and setting the scene rather than comprehensively describing every user/system interaction.

### Audience
Technical and non-technical people, inside and outside of the immediate software development team.

### Required
Yes, all software documentation should include a summary of the functionality provided by the software.

## Quality Attributes
With the functional overview section summarising the functionality, it's also worth including a separate section to summarise the quality attributes (also referred to as "non-functional requirements").

### Intent
This section is about summarising the key quality attributes and should answer the following types of questions:

Is there a clear understanding of the quality attributes that the architecture must satisfy?

Are the quality attributes SMART (specific, measurable, achievable, relevant and timely)?

Have quality attributes that are usually taken for granted been explicitly marked as out of scope if they are not needed? (e.g. "user interface elements will only be presented in English" to indicate that multi-language support is not explicitly catered for)

Are any of the quality attributes unrealistic? (e.g. true 24x7 availability is typically very costly to implement inside many organisations)

In addition, if any of the quality attributes are deemed as "architecturally significant" and therefore influence the architecture, why not make a note of them so that you can refer back to them later in the documentation.

### Structure
Simply listing out each of the quality attributes is a good starting point. Examples include:

Performance (e.g. latency and throughput)

Scalability (e.g. data and traffic volumes)

Availability (e.g. uptime, downtime, scheduled maintenance, 24x7, 99.9%, etc)

Security (e.g. authentication, authorisation, data confidentiality, etc)

Extensibility

Flexibility

Auditing

Monitoring and management

Reliability

Failover/disaster recovery targets (e.g. manual vs automatic, how long will this take?)

Business continuity

Interoperability

Legal, compliance and regulatory requirements (e.g. data protection act)

Internationalisation (i18n) and localisation (L10n)

Accessibility

Usability

...

Each quality attribute should be precise, leaving no interpretation to the reader. Examples where this isn't the case include:

"the request must be serviced quickly"

"there should be no overhead"

"as fast as possible"

"as small as possible"

"as many customers as possible"

...

### Motivation
If you've proactively considered the quality attributes and let them influence the software architecture, why not write them down too? Typically, quality attributes are not given to you on a plate and an amount of exploration and refinement is usually needed to come up with a list of them. Put simply, writing down the quality attributes removes any ambiguity both now and during maintenance/enhancement work in the future.

### Audience
Since quality attributes are mostly technical in nature, this section is really targeted at technical people in the software development team.

### Required
Yes, all technical software documentation should include a summary of the quality attributes/non-functional requirements as they usually shape the resulting software architecture in some way.

## Constraints
Software lives within the context of the real-world, and the real-world has constraints. This section allows you to state these constraints so it's clear that you are working within them and obvious how they affect your architecture decisions.

### Intent
Constraints are typically imposed upon you but they aren't necessarily "bad", as reducing the number of available options often makes your job designing software easier. This section allows you to explicitly summarise the constraints that you're working within and the decisions that have already been made for you.

### Structure
As with the quality attributes section, simply listing the known constraints and briefly summarising them will work. Example constraints include:

Time, budget and resources.

Approved technology lists and technology constraints.

Target deployment platform.

Existing systems and integration standards.

Local standards (e.g. development, coding, etc).

Public standards (e.g. HTTP, SOAP, XML, XML Schema, WSDL, etc).

Standard protocols.

Standard message formats.

Size of the software development team.

Skill profile of the software development team.

Nature of the software being built (e.g. tactical or strategic).

Political constraints.

Use of internal intellectual property.

...

If constraints do have an impact, it's worth summarising them (e.g. what they are, why they are being imposed and who is imposing them) and stating how they are significant to your architecture.

### Motivation
Constraints have the power to massively influence the architecture, particularly if they limit the technology that can be used to build the solution. Documenting them prevents you having to answer questions in the future about why you've seemingly made some odd decisions.

### Audience
The audience for this section includes everybody involved with the software development process, since some constraints are technical and some aren't.

### Required
Yes, all technical software documentation should include a summary of the constraints as they usually shape the resulting software architecture in some way. It's worth making these constraints explicit at all times, even in environments that have a very well known set of constraints (e.g. "all of our software is ASP.NET against a SQL Server database") because constraints have a habit of changing over time.

## Principles
The principles section allows you to summarise those principles that have been used (or you are using) to design and build the software.

### Intent
The purpose of this section is to simply make it explicit which principles you are following. These could have been explicitly asked for by a stakeholder or they could be principles that you (i.e. the software development team) want to adopt and follow.

### Structure
If you have an existing set of software development principles (e.g. on a development wiki), by all means simply reference it. Otherwise, list out the principles that you are following and accompany each with a short explanation or link to further information. Example principles include:

Architectural layering strategy.

No business logic in views.

No database access in views.

Use of interfaces.

Always use an ORM.

Dependency injection.

The Hollywood principle (don't call us, we'll call you).

High cohesion, low coupling.

Follow SOLID (Single responsibility principle, Open/closed principle, Liskov substitution principle, Interface segregation principle, Dependency inversion principle).

DRY (don't repeat yourself).

Ensure all components are stateless (e.g. to ease scaling).

Prefer a rich domain model.

Prefer an anaemic domain model.

Always prefer stored procedures.

Never use stored procedures.

Don't reinvent the wheel.

Common approaches for error handling, logging, etc.

Buy rather than build.

...

### Motivation
The motivation for writing down the list of principles is to make them explicit so that everybody involved with the software development understands what they are. Why? Put simply, principles help to introduce consistency into a codebase by ensuring that common problems are approached in the same way.

### Audience
The audience for this section is predominantly the technical people in the software development team.

### Required
Yes, all technical software documentation should include a summary of the principles that have been or are being used to develop the software.

## Software Architecture
The software architecture section is your "big picture" view and allows you to present the structure of the software. Traditional software architecture documents typically refer to this as a "conceptual view" or "logical view", and there is often confusion about whether such views should refer to implementation details such as technology choices.

### Intent
The purpose of this section is to summarise the software architecture of your software system so that the following questions can be answered:

What does the "big picture" look like?

Is there are clear structure?

Is it clear how the system works from the "30,000 foot view"?

Does it show the major containers and technology choices?

Does it show the major components and their interactions?

What are the key internal interfaces? (e.g. a web service between your web and business tiers)

### Structure
The container diagram(s) and component diagrams are the main focus for this section, accompanied by a short narrative explaining what the diagram is showing plus a summary of each container/component.

Sometimes UML sequence or collaboration diagrams showing component interactions can be a useful way to illustrate how the software satisfies the major use cases/user stories/etc. Only do this if it adds value though and resist the temptation to describe how every use case/user story works.

### Motivation
The motivation for writing this section is that it provides the "maps" that people can use to get an overview of the software and help developers navigate the codebase.

### Audience
The audience for this section is predominantly the technical people in the software development team.

### Required
Yes, all technical software documentation should include a software architecture section because it's essential that the overall software structure is well understood by everybody on the development team.

## Code
Although other sections of the documentation describe the overall architecture of the software, often you'll want to present lower level details to explain how things work. This is what the code section is for. Some software architecture documentation templates call this the "implementation view" or the "development view".

### Intent
The purpose of the code section is to describe the implementation details for parts of the software system that are important, complex, significant, etc. Examples include:

Generating/rendering HTML: a short description of the framework that was created for generating HTML, including the major classes and concepts.

Data binding: the approach to updating business objects as the result of HTTP POST requests.

Multi-page data collection: a short description of the framework used for building forms that spanned multiple web pages.

Web MVC: an example usage of the web MVC framework being used.

Security: the approach to using Windows Identity Foundation (WIF) for authentication and authorisation.

Domain model: an overview of the important parts of the domain model.

Component framework: a short description of the framework that we built to allow components to be reconfigured at runtime.

Configuration: a short description of the standard component configuration mechanism in use across the codebase.

Architectural layering: an overview of the layering strategy and the patterns in use to implement it.

Exceptions and logging: a summary of the approach to exception handling and logging across the various architectural layers.

Patterns and principles: an explanation of how patterns and principles are implemented.

...

### Structure
Keep it simple, with a short section for each element that you want to describe and include diagrams if they help the reader. For example, a high-level UML class and/or sequence diagram can be useful to help explain how a bespoke/hand-written in-house framework works. Resist the temptation to include all of the detail though, and don't feel that your diagrams need to show everything. Instead, spend a few minutes sketching out a high-level UML class diagram that shows selected (important) attributes and methods rather than using the complex diagrams that can be generated automatically from your codebase with UML tools or IDE plugins. Keeping any diagrams at a high-level of detail means that they're less volatile and remain up to date for longer because they can tolerate small changes to the code and yet remain valid.

### Motivation
The motivation for writing this section is to ensure that everybody understands how the important/significant/complex parts of the software system work so that they can maintain, enhance and extend them in a consistent and coherent manner. This section also helps new members of the team get up to speed quickly.

### Audience
The audience for this section is predominantly the technical people in the software development team.

### Required
No, but there are usually parts of a large, non-trivial software system that can benefit from some explanation.

## Data
The data associated with a software system is usually not the primary point of focus yet it's arguably more important than the software itself, so often it's useful to document something about it.

### Intent
The purpose of the data section is to record anything that is important from a data perspective, answering the following types of questions:

What does the data model look like?

Where is data stored?

Who owns the data?

How much storage space is needed for the data? (e.g. especially if you're dealing with "big data")

What are the archiving and back-up strategies?

Are there any regulatory requirements for the long term archival of business data?

Likewise for log files and audit trails?

Are flat files being used for storage? If so, what format is being used?

### Structure
Keep it simple, with a short section for each element that you want to describe and include domain models or entity relationship diagrams if they help the reader. As with the advice for including class diagrams in the code section, keep any diagrams at a high level of abstraction rather than including every field and property. If people need this type of information, they can find it in the code or database (for example).

### Motivation
The motivation for writing this section is that the data in most software systems tends to outlive the software. This section can help anybody that needs to maintain and support the data on an ongoing basis, plus anybody that needs to extract reports or undertake business intelligence activities on the data. This section can also serve as a starting point for when the software system is inevitably rewritten in the future.

### Audience
The audience for this section is predominantly the technical people in the software development team along with others that may help deploy, support and operate the software system.

### Required
No, but most software systems are not small or trivial, and the data will likely outlive the code that created it.

## Infrastructure Architecture
While most of the documentation is focused on the software itself, we do also need to consider the infrastructure because software architecture is about software and infrastructure.

### Intent
This section is used to describe the physical/virtual hardware and networks on which the software will be deployed. Although, as a software architect, you may not be involved in designing the infrastructure, you do need to understand that it's sufficient to enable you to satisfy your goals. The purpose of this section is to answer the following types of questions:

Is there a clear physical architecture?

What hardware (virtual or physical) does this include across all tiers?

Does it cater for redundancy, failover and disaster recovery if applicable?

Is it clear how the chosen hardware components have been sized and selected?

If multiple servers and sites are used, what are the network links between them?

Who is responsible for support and maintenance of the infrastructure?

Are there central teams to look after common infrastructure (e.g. databases, message buses, application servers, networks, routers, switches, load balancers, reverse proxies, internet connections, etc)?

Who owns the resources?

Are there sufficient environments for development, testing, acceptance, pre-production, production, etc?

### Structure
The main focus for this section is usually an infrastructure/network diagram showing the various hardware/network components (servers, routers, firewalls, load balancers, etc) and how they fit together, with a short narrative to accompany the diagram.

### Motivation
The motivation for writing this section is to document the infrastructure and confirm that it supports the software architecture.

### Audience
The audience for this section is predominantly the technical people in the software development team along with others that may help deploy, support and operate the software system.

### Required
Yes, an infrastructure architecture section should be included in technical software documentation because it illustrates that the infrastructure is understood and has been considered.

## Deployment
The deployment section is simply the mapping between the software architecture and the infrastructure architecture.

### Intent
This section is used to describe the mapping between the software (e.g. containers) and the infrastructure. Sometimes this will be a simple one-to-one mapping (e.g. deploy a web application to a single web server) and at other times it will be more complex (e.g. deploy a web application across a number of servers in a server farm). This section answers the following types of questions:

How and where is the software installed and configured?

Is it clear how the software will be deployed across the infrastructure elements described in the infrastructure architecture section? (e.g. one-to-one mapping, multiple containers per server, etc)

If this is still to be decided, what are the options and have they been documented?

Is it understood how memory and CPU will be partitioned between the processes running on a single piece of infrastructure?

Are any containers and/or components running in an active-active, active-passive, hot-standby, cold-standby, etc formation?

Has the deployment and rollback strategy been defined?

What happens in the event of a software or infrastructure failure?

Is it clear how data is replicated across sites?

### Structure
There are a few ways to structure this section:

Tables: simple textual tables that show the mapping between software containers and/or components with the infrastructure they will be deployed on.

Diagrams: UML deployment diagrams or modified versions of the diagrams from the infrastructure architecture section showing where software will be running.

You can additionally use notation, colour coding, etc to the designate the runtime status of software and infrastructure (e.g. active, passive, hot-standby, warm-standby, cold-standby, etc).

### Motivation
The motivation for writing this section is to ensure that everybody understands how the software is going to work once it gets out of the development environment and also to document the often complex deployment of enterprise software systems.

This section can provide a useful overview, even for those teams that have adopted continuous delivery and have all of their deployment scripted using tools such as Puppet, Chef, Vagrant, Docker, etc.

### Audience
The audience for this section is predominantly the technical people in the software development team along with others that may help deploy, support and operate the software system.

### Required
Yes, a deployment section should be included in all technical software documentation because it can help to solve the often mysterious question of where the software will be, or has been, deployed.

## Development Environment
The development environment section allows you to summarise how people new to your team install tools and setup a development environment in order to work on the software.

### Intent
The purpose of this section is to provide instructions that take somebody from a blank operating system installation to a fully-fledged development environment.

### Structure
The type of things you might want to include are:

Pre-requisite versions of software needed.

Links to software downloads (either on the Internet or locally stored).

Links to virtual machine images.

Environment variables, Windows registry settings, etc.

Host name entries.

IDE configuration.

Build and test instructions.

Database population scripts.

Usernames, passwords and certificates for connecting to development and test services.

Links to build servers.

...

If you're using automated solutions (such as Vagrant, Docker, Puppet, Chef, Rundeck, etc), it's still worth including some brief information about how these solutions work, where to find the scripts and how to run them.

### Motivation
The motivation for this section is to ensure that new developers can be productive as quickly as possible.

### Audience
The audience for this section is the technical people in the software development team, especially those who are new to the team.

### Required
Yes, because this information is usually lost and it's essential if the software will be maintained by a different set of people from the original developers.

## Operation and Support
The operations and support section allows you to describe how people will run, monitor and manage your software.

### Intent
Most systems will be subject to support and operational requirements, particularly around how they are monitored, managed and administered. Including a dedicated section in the software guidebook lets you be explicit about how your software will or does support those requirements. This section should address the following types of questions:

Is it clear how the software provides the ability for operation/support teams to monitor and manage the system?

How is this achieved across all tiers of the architecture?

How can operational staff diagnose problems?

Where are errors and information logged? (e.g. log files, Windows Event Log, SMNP, JMX, WMI, custom diagnostics, etc)

Do configuration changes require a restart?

Are there any manual housekeeping tasks that need to be performed on a regular basis?

Does old data need to be periodically archived?

### Structure
This section is usually fairly narrative in nature, with a heading for each related set of information (e.g. monitoring, diagnostics, configuration, etc).

### Motivation
Times change and team members move on, so recording this information can help prevent those situations in the future where nobody understands how to operate the software. It also helps to quickly answer basic questions such as, "where are the log files?".

### Audience
The audience for this section is predominantly the technical people in the software development team along with others that may help deploy, support and operate the software system.

### Required
Yes, an operations and support section should be included in all technical software documentation, unless you like throwing software into a black hole and hoping for the best.

## Decision Log
The final thing you might consider including in technical software documentation is a log of the decisions that have been made during the development of the software system.

### Intent
The purpose of this section is to simply record the major decisions that have been made, including both the technology choices (e.g. products, frameworks, etc) and the overall architecture (e.g. the structure of the software, architectural style, decomposition, patterns, etc). For example:

Why did you choose technology or framework "X" over "Y" and "Z"?

How did you do this? Product evaluation or proof of concept?

Were you forced into making a decision about "X" based upon corporate policy or enterprise architecture strategies?

Why did you choose the selected software architecture? What other options did you consider?

How do you know that the solution satisfies the major quality attributes?

...

### Structure
Keep it simple, with a short paragraph or an architecture decision record describing each decision that you want to record. Do refer to other resources such as proof of concepts, performance testing results or product evaluations if you have them.

### Motivation
The motivation for recording the significant decisions is that this section can act as a point of reference in the future. All decisions are made given a specific context and usually have trade-offs. There is usually never a perfect solution to a given problem. Articulating the decision making process after the event is often complex, particularly if you're explaining the decision to people who are joining the team or you're in an environment where the context changes on a regular basis.

Although "nobody ever gets fired for buying IBM", perhaps writing down the fact that corporate policy forced you into using IBM WebSphere over Apache Tomcat will save you some tricky conversations in the future.

### Audience
The audience for this section is predominantly the technical people in the software development team along with others that may help deploy, support and operate the software system.

### Required
No, but it can be useful to include this section if the team spend more than a few minutes thinking about something significant such as a technology choice or an architectural style. If in doubt, spend a couple of minutes writing it down, especially if you work for a consulting organisation who is building a software system under an outsourcing agreement for a customer.
