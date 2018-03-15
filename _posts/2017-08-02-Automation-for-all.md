---
layout: post
title: Automation for All
tags: [Lightning Process Builder, Workflows, Visual Flow]
---

# Automation for All: Using Flow & Process Builder Together

*SalesforceSummaries is a publication that delivers the **key** insights from
Salesforce YouTube videos. We aim to be the
[getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Salesforce have invested heavily in facilitating automation with a ‘clicks, not
code’ approach to deliver more value to customers by helping to reduce the
dependency on having Salesforce developer resources.

This article summarises the insightful presentation about the different
Salesforce declarative automation tools by [Matthew
Schutz](https://www.linkedin.com/in/matthewkschutz/?ppe=1), founder of award
winning Salesforce consultancy partner: [Pracedo](https://www.pracedo.com/).

![](https://cdn-images-1.medium.com/max/540/1*bcbqQ8vEhUvhOJd8WM_fuw.png)

![](https://cdn-images-1.medium.com/max/540/1*_gb6LklL1Mb1_9azOJz13A.png)

**Details:**

Video: ‘[Automation for All: Using Flow and Process Builder
Together](https://www.youtube.com/watch?v=mDuu4vNqzMU)’

Presenter: [Matthew Schutz](https://www.linkedin.com/in/matthewkschutz/?ppe=1)

Date: October 21st 2016

Time: 20 minutes

Key terms: Workflows, Visual Flow, Lightning Process Builder

**Summary**:

1) @0.50 — Workflow, Process Builder and Flow are all point and click (aka
declarative) Salesforce tools.

2) @2 — Approvals — Workflows — Lightning Process Builder — Visual Workflow —
Apex Code (simple to complex). The automation tool you need depends on the type
of business process that you’re automating.

3) @3 — Lightning Process Builder is ‘workflow on steroids’. A big benefit with
Lightning Process Builder is that you, in effect, merge multiple workflow rules
together. There are limits on how many workflow rules your Org can have, and so
replacing multiple workflow rules with a single Process Builder can be very
beneficial.

4) @3.40 — with Lightning Process Builder you can create records, submit records
for approval, update child records, post to Chatter, and also have multiple
related workflows merged into 1 process (this is powerful as you can determine
the order in which the workflow rule enters).

5) @5.40- Visual Flow is more complex than Process Builder or Workflows.
Generally, Flow is used to take input from users in a ‘form like’ structure. A
flow is an application that can execute logic, interact with the SF database,
call Apex classes and collect data from users. You can build flows by using the
Cloud Flow Designer.

6) @9.00- Combining a Process with Flow(s) brings admins closer to the power of
Apex with ‘point-n-click’ functionality.

7) @9.10 —Combining a Process with Flow(s) means that you can run Flows without
user interaction (no need to press a button) and pass values to variables from
your Process to Flows. Being able to determine the order of execution for
multiple Processes and Flows is so helpful. In contrast, workflow rules don’t
have a determined execution order and this can be incredibly detrimental because
it can have ramifications on Apex triggers if those triggers don’t leverage best
practices to avoid recursion; which would increase the likelihood of hitting
governor limits.

**Summary:**

Matthew’s presentation covers the different declarative automation tools with
information on their respective pros and cons and use cases. The Salesforce
declarative tools are improving with each release and they enable customers to
‘do more with less’ and enable customers to have a [lower technical
deb](https://en.wikipedia.org/wiki/Technical_debt)t.

However, as is the case with many technologies, if they solve a set of problems
(‘how can we automate in Salesforce without hiring developers or consultants?’),
a new set of problems are created. The new set of problems can be discovered in
very complicated Salesforce orgs which rely *hugely* on the declarative
automation tools and consequently, debugging becomes increasingly challenging.
This is a topic which is discussed in several podcast episodes from the
excellent ‘[Good Day, Sir](http://www.gooddaysirpodcast.com/)’ series.

In addition to Matthew’s presentation, ‘[Learning Salesforce Visual
Flow](https://www.packtpub.com/application-development/learning-salesforce-visual-workflow)’
and ‘[Learning Salesforce Visual Flow and Process
Builder](https://www.packtpub.com/application-development/learning-salesforce-visual-workflow-and-process-builder-second-edition)’
by [Rakesh Gupta](https://automationchampion.com/) are some very comprehensive
resources for learning more about the Salesforce declarative tools.

![](https://cdn-images-1.medium.com/max/720/1*M58c9tIFRSbm077Jf7Ay5A.png)
