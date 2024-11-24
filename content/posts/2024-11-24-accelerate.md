---
type: page
title: "Accelerate"
description: "notes on Accelerate, by Forsgren, Humble, and Kim"
date: 2024-11-24
tags:
- books
- productivity
---

# _Accelerate: Building and Scaling High Performing Technology Organizations_

Organizations need to accelerate delivery, engagement, and responses to remain competitive. Software is at the heart of the acceleration. To improve software delivery, companies need to focus on capabilities, not maturity models. Capability models focus on key outcomes, not vanity metrics, unrelated to business outcomes.

## Measuring Performance

Traditional attempts to measure the performance of software teams, usually focus on productivity and in general suffer from two mistakes: focusing on outputs (instead of outcomes) and measuring individual performance (instead of team performance). The following measures focus on global outcomes:

1. Delivery lead time
2. Deployment frequency
3. Time to restore service
4. Change fail rate

### Tempo

Lead time is a key element of Lean theory. However, it’s hard to know when to start the clock. We focus on the delivery part (the time it takes to go from code committed to code successfully running in production). 

Reducing batch size is another key element of Lean theory. However, batch sizes are hard to estimate with software. Instead, we measure deployment frequency as a proxy for batch size (it’s easier to measure and has low variability). Deployment frequency is inversely proportional to batch size; when we deploy more frequently, the size of the batch tends to be smaller.

### Reliability

Software systems are complex, so failure is inevitable. Instead of measuring time between failures (a typical reliability measure), we focus on how quickly the service can be restored (MTTR).

The final measure, another Lean quality metric, is the percentage of changes that result in a degraded service or require remediation. 

### No trade-off 

Research demonstrates that there is no trade-off between improving performance and achieving higher levels of stability and quality. 

### Impact

Research shows that software delivery performance is a predictor of both organizational performance (profitability, market share) and non-commercial performance (quantity of services, operating efficiency, quality of products). 

These measures and tools enable the pursuit of ever higher performance. However, we can’t use them blindly. In an organization that does not have a learning culture, but rather one that is pathological and bureaucratic, the effort will likely fail. Before attempting to improve performance, we need to understand and develop the culture. 

## Culture

In addition to being able to measure software delivery performance, there are ways to measure culture quantitatively. This requires a carefully crafted survey (with statistical tests for confirming validity) and the use of strongly worded Likert-type questions (described in more detail in the book).

Organizational culture has three levels:

1. Basic assumptions (formed overtime, things we just “know” but can’t articulate)
2. Values (collective values and norms, a lens through which we interpret relationships, events, and activities)
3. Artifacts (written mission statements, formal procedures)

### Culture Types

Level two is the culture we often think about and is of high importance. We model this level according to Westrum’s typology:

* Pathological (power-oriented)
    * Characterized by fear and threat. People hoard and withhold information to make themselves look better.
* Bureaucratic (rule-oriented)
    * Departments strive to maintain their turf and insist on following their own rules.
* Generative (performance-oriented)
    * Focus on the mission. Everything is subordinated to good performance.

Good information flow is critical to a safe and effective operation at high tempo. It answers questions that the receiver needs answered, in a timely manner, and is presented such that it can be used effectively. Organizational culture predicts information flows.

### Takeaways

The Westrum organizational culture predicts both software delivery performance and organizational performance. It also leads to higher levels of job satisfaction. 

**To change culture, start by changing how people behave.** Applying both technical practices (**Continuous Delivery**) and management practices (**Lean Management**) predicts a better culture. 

## Technical Practices

Continuous Delivery (CD) is a set of capabilities that enable changes to reach users safely, quickly, and sustainably. There are five key principles of CD:

1. Build quality in
2. Work in small batches
3. Computers perform repetitive tasks; people solve problems
4. Relentlessly pursue continuous improvement
5. Everyone is responsible

There are three foundations to implementing CD:

1. Comprehensive configuration management
    1. Provision environments and build/test/deploy software automatically from source controlled info
2. Continuous integration (CI)
    1. Keep branches short-lived, merge into trunk frequently, automatically run build/test from trunk commits
3. Continuous testing
    1. Run tests on every commit, be able to test locally, testers focus on exploratory tests

Drivers of CD:

* Version control
* Deployment automation
* Continuous integration
* Trunk-based development
* Test automation
* Test data management
* Shift left on security
* Loosely coupled architecture
* Empowered teams
* Monitoring
* Proactive notification

### Architecture

High performance is possible in all kinds of systems, provided the systems and teams are loosely coupled. This architecture property enables testing and deployment of individual components or services even as the organization grows. I.e., a loosely coupled architecture enables scaling.

Low performers were more likely to work on/with software developed by another company (outsourced). Low performers were more likely to work on mainframe systems. Other than these, there was no significant correlation between system types (greenfield, systems of record, COTS, embedded, etc.) and delivery performance. Therefore, we need to focus on the following architecture characteristics (rather than implementation details):

1. **Deployability**
    * Ability to deploy and release an application independently of other apps/services it depends on
2. **Testability**
    * Ability to run most tests without requiring an integrated environment (i.e., where multiple independent services are deployed together)

To achieve these characteristics, systems must be loosely coupled (i.e., can be changed and validated independently). The biggest contributors to CD (from the 2017 analysis) were whether teams can:

* Make large-scale changes to their system design without external permission
* Make large-scale changes to their system without depending on other teams to make changes in their systems
* Complete their work without communicating/coordinating with people outside the team
* Deploy/release their service on demand, regardless of other dependent services
* Do most testing on demand, without requiring an integrated environment
* Perform deployments during normal business hours with negligible downtime

### Impact

Research shows that **CD capabilities have a strong positive impact on software delivery performance**. They also **decrease deployment pain, decrease team burnout, and increase how strongly individuals identify with their organization** (a key predictor of organizational performance). Implementing CD positively influences organizational culture (creates a generative, performance-oriented culture).

By focusing on factors that predict high delivery performance (generative culture, modular architecture, technical practices that enable CD, effective leadership) we can scale deployments per developer per day linearly (or better). The business can move faster as we add more people (not slower, as is typical). 

## Management Practices

The following components of Lean management (in combination) increase delivery performance and positively impact team culture and performance:

1. Limit work in progress (WIP)
2. Visual management (visual displays of key quality/productivity metrics aligned with operational goals)
3. Feedback from production (using monitoring tools to make daily business decisions)
4. Lightweight change approval process

Approval of changes by an external body (e.g., manager, control change board) has no correlation with MTTR or change fail rate (i.e., does not improve stability) but negatively impacts lead time and deployment frequency. A lightweight process is recommended, such as pair programming, intra-team review, combined with a good deployment pipeline to reject bad changes. 

The following components of Lean product development predict higher software delivery performance, higher organizational performance, improved organizational culture, and less burnout:

1. **Work in small batches**: slice work such that it can be completed in less than a week
2. **Make flow of work visible**: teams understand the flow of work from the business to the customer
3. **Gather & implement customer feedback**: organizations actively and regularly seek customer feedback and incorporate it into product design
4. **Team experimentation**: development teams are empowered to change specifications during development process without requiring approval

There is a virtual cycle here too; Lean product management positively impacts software delivery performance and culture, and software delivery performance drives Lean product management.


Check out this visual and tabular overview of the research results [here](https://itrevolution.com/wp-content/uploads/2022/06/transformation_practices.pdf).


## Extras

Other good info in the book:

* How to make work sustainable by
    * Reducing deployment pain
    * Reducing and/or fighting burnout
* How to measure employee engagement
* How diversity in tech relates to team performance
* Transformational leadership (highly correlated with software delivery performance)
* How to improve culture (tips for managers)
