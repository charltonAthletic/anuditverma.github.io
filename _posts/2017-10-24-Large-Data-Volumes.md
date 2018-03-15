---
layout: post
title: Large Data Volumes CodeTalk
tags: [Indexing, Large Data Volumes, SOQL]
image:  https://cdn-images-1.medium.com/max/720/1*0G2Bizt3Nija457FBhYdgQ.png
share-img:  https://cdn-images-1.medium.com/max/720/1*0G2Bizt3Nija457FBhYdgQ.png
---

## Large Data Volumes CodeTalk

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

There are many considerations when dealing with large data volumes in Salesforce. As per the Salesforce data architect [guide](http://certification.salesforce.com/dataarchitect), the ‘[Large Data Volumes CodeTalk](https://www.youtube.com/watch?v=sa6WVVRDml0)’ video discusses several key best practices in more detail.

![](https://cdn-images-1.medium.com/max/2000/1*dryhREpNj9CYGUA9URFbJw.png)

**Details:**

Video: ‘[Large Data Volumes CodeTalk](https://www.youtube.com/watch?v=sa6WVVRDml0)’

Presenter: Sandeep Bhanot, Bud Vieira, Steve Bobrowski

Date: May 7 2013

Time: 32 minutes

Key terms: Large Data Volumes (LDV), performance and usability, indexing, non deterministic formulas.

**Summary**:

 1. @3.00 — The idea of what a ‘large data volume’ (LDV) in Salesforce is changing all the time because of how the platform has grown. However, generally, it is considered to be around 10m records and more.

 2. @5.00 — The approach that a customer should adopt for meeting Salesforce best practices for large data volumes depends on the current status of the Salesforce org. There are a number of strategies which can be implemented to meet best practices including using mashups, selective queries, archiving unnecessary data and adopting the most efficient ways to load large data volumes into Salesforce.

 3. @8.00 — Some of these best practices are also applicable to data sets which aren’t ‘large data volumes’. For example, leveraging selective indexes and indexing.

 4. @9.50 — It is beneficial to leverage the standard indexed fields in your SOQL queries. This cheat sheet [here](http://resources.docs.salesforce.com/rel1/doc/en-us/static/pdf/salesforce_query_search_optimization_developer_cheatsheet.pdf) can help you to create the most optimum queries.

 5. @12.15 — The process of meeting best practices for large data volumes starts with the design phase. You need to consider **performance** and **usability**.

 6. @15.00 — The first limit for displaying data on Visualforce pages that you will face is that you cannot retrieve more than 50,000 records from your SOQL calls in a single context. However, to by-pass this, you can set the [readOnly attribute](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_controller_readonly_context_pagelevel.htm) to the page which would enable you to query up to 1 million records.

 7. @17.00 — Although you can create custom indexes on fields which are referenced in a SOQL WHERE clause to increase the speed of a query, the consideration is that you will have to maintain this index. So don’t create a whole set of custom indexes on the fly — there are considerations that must be made.

 8. @18.00 — Salesforce Support create custom indexes after the requests have been logged by customers. A reason why Salesforce don’t enable customers to do this themselves is that there can be many unintended consequences to creating lots of custom indexes.

 9. @19.00 — *Given a choice between using a formula field or a trigger to update a field, what should you use?* Firstly, you should distinguish the use case. If you want to just display at run time the computed value, then you should use a formula. If you want to mass update a field on a large collection of records, you would want to consider using a trigger solution as you can then turn the trigger on and off. So you can perform the data load during a maintenance window and have the trigger turned on, then once complete you can turn the trigger back off. Note: if you are trying to query a non-deterministic formula, then you should also use a trigger.

 10. @23.00 — *What are the best practices around archiving and purging data? *The first principle is that you need to take your first actions in the design phase. How much data does the org need to maintain live? Establish archiving timelines and identify what archival store and access to the archival store will be. Once you have established all of those requirements in the design phase, then you can leverage automate processes to change owners of records, de-activate records, can leverage triggers with an aging date in mind that automatically moves records to the archival store at the correct time etc.

 11. @23.30 — The best practice is keep your org as lean as possible and part of this means purging data in your org. So you can leverage the hard-delete option in the Bulk API. The default behavior is soft delete but soft deleted records still contribute to the performance cost. For example, sharing rules are still calculated in soft deleted records. If you don’t need the data that you have identified to be deleted, then you should leverage the hard delete function.

The [Architect Core Resources](https://developer.salesforce.com/page/Architect_Core_Resources) is a great resource for learning more about best practices around large data volumes.
