---
layout: post
title: How to Manage Large Data Volumes to Deliver a Superior Customer Experience
tags: [Data Archival Strategy, Data Storage Strategy, Large Data Volumes]
image:  https://cdn-images-1.medium.com/max/2000/1*nnirfenjh439zPUGdz6bFw.png
share-img:  https://cdn-images-1.medium.com/max/2000/1*nnirfenjh439zPUGdz6bFw.png
---

## How to Manage Large Data Volumes to Deliver a Superior Customer Experience

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

With the ***exponential ***growth of data in the age of IoT, it’s becoming more and more important for customers to have integrated, end to end solutions in place for storing, archiving and analyzing their data. There are a number of Salesforce recent releases (Salesforce Shield field history module and Salesforce Connect etc) that help to facilitate this. **However, storing large data volumes on Salesforce isn’t always practical or cost effective.** Salesforce data and file storage, due to the multi-tenancy architecture, is relatively expensive and there are also many downsides to storing large data volumes in a single Salesforce org (data skew, performance degradation on queries, list views and reports etc). Thankfully, there are many ways in which customers can achieve an integrated, end to end data archival and data storage solution. This summary discusses various implementations that some large Salesforce customers with incredibly complex data archival and data storage have achieved.

**Details: ‘[**How to Manage Large Data Volumes to Deliver a Superior Customer Experience](https://www.youtube.com/watch?v=OSDrnObJl8k)’

![](https://cdn-images-1.medium.com/max/2000/1*nnirfenjh439zPUGdz6bFw.png)

**Presenter: **Mary Ann Novosel, Meg Hadlock, Ravi Salgadoe, Hector Perez Jr, Bichitresh Saha, Jonathan Bruce

**Date:** November 25 2013

**Time:** 56 minutes

**Key Terms**: Data archival strategy, data storage strategy, large data volumes (LDV)

**Summary:**

 1. @3.00 — The term ‘large data volume’ is imprecise and elastic but typically refers to millions of records and tens of thousands of users.

![](https://cdn-images-1.medium.com/max/2000/1*iVXKnkafCzZaNvB0dl-SBQ.png)

2. @3.20 — There are many symptoms of large data volumes. Generally, you will experience slower query performance especially for search, list views and reports.

Large data volumes have a significant detrimental impact on the speed of sharing rules.

![](https://cdn-images-1.medium.com/max/2000/1*h9hyGrMlgan82icfiGETlw.png)

3. @5.00 — The first step to deal with large data volumes is to come up with a mitigation plan.

You will want to establish and implement an archiving strategy.

![](https://cdn-images-1.medium.com/max/2000/1*-xCA3F-MSMqBzDzTtvthSA.png)

4. @5.30 — It is very important to know what your operational data set is.

![](https://cdn-images-1.medium.com/max/2000/1*YlC4pl5X5k2abUmGowkRTg.png)

5. @6.00 — You should specify criteria to determine what data sets should be kept and what data sets should be archived. If you choose to archive data, you will need to have a formal archiving process in place which considers how the data will be archived and how this can be done automatically.

Forecasting data growth rate is beneficial too, to ensure that you never hit your Salesforce storage capacity maximum.

![](https://cdn-images-1.medium.com/max/2000/1*C0_3Fg1zYyoFJdKzAtiqqQ.png)

6. @8.00 — There are a number of different options for implementing an archival strategy.

![](https://cdn-images-1.medium.com/max/2000/1*Xq9lwmpHfCJWBb4fi2f5eg.png)

7. @8.30 — One option is to create custom sObjects for the purposes of storing archival records. This will help to narrow the set of records down that make up the operational data set of an org.

![](https://cdn-images-1.medium.com/max/2000/1*flFNBCeYn2SF9EmySdaRog.png)

8. @8.50 — Another option that you can use is to have a flag on archival records. This way, you can see and filter out archived data vs current data.

![](https://cdn-images-1.medium.com/max/2000/1*0RGB7jF55GhWzhq2EtTg8A.png)

9. @9.30 — Another option is external archiving. You can replicate records to a local repository and then delete them from Salesforce. You can use ETL tools (Informatica, Jitterbit, and CastIron etc) to assist with replication. You can also use sqlLite as an option to replicate the schema for these archived records.

![](https://cdn-images-1.medium.com/max/2000/1*anwHJ5KaAai9EM6rcjXu8A.png)

10. @10.30 — A hybrid option involves dividing data into the different sets (operational/historical/archived) and the latter set can be accessed in an external cloud repository. Salesforce Connect (fka Lightning Connect) is a good example of this.

![](https://cdn-images-1.medium.com/max/2000/1*DYFwtVk4RPrOMzsQCnwW2Q.png)

11. @10.55 — Managing large data volumes (LDV) should be an integral part of solution development. You should have eyes and ears on this and make sure this is a point of conversation. With the introduction of various different policies, governance is increasingly important and so you need to consider who should access what types of data etc.

![](https://cdn-images-1.medium.com/max/2000/1*Nczic5oex6kNV0956mzm5Q.png)

12. @17.50 — Dell have a very complicated set of Salesforce orgs and one of the pain points from a LDV perspective was the huge number of opportunities which they had; which prevented reports and list views from generating and reduced the UX as the org performed slower.

The solution was to work with the relevant teams (on the left hand side) to develop and effective and scalable archival strategy. A lot of considerations had to be made, for example ‘*What kind of data can we archive? What kind of contracts do we have with our customers?’**.***

From an implementation perspective, the archival strategy was benchmarked (you get what you measure) and a proof of concept was conducted.

![](https://cdn-images-1.medium.com/max/2000/1*wpej8LnfyXqVtVUmTloXmw.png)

13. @19.20 — The solution that Dell designed was to flag data that was to be archived. Business rules were agreed upon and signed off and then reports and queries were modified to filter on the operational data set of opportunities. After doing this, it is critical to communicate and train users on this impact because otherwise, users may expect to see data that isn’t being returned.

![](https://cdn-images-1.medium.com/max/2000/1*XoNMJAxLZScJ6GrTBrszvA.png)

Remember to then benchmark post deployment as this helps to provide ‘value add’ metrics.

14. @22.00 — Dell have a huge Salesforce implementation and have consolidated huge volumes of customer data into a single master data system with real time integration. This approach has been the cost effective and performant for Dell’s needs.

![](https://cdn-images-1.medium.com/max/2000/1*5_0KBv-pQKsU9tAbZ1-xaQ.png)

![](https://cdn-images-1.medium.com/max/2000/1*-oJLzJ2Jb-1N9Z94AVesUQ.png)

15. @26.00 — The implementation of how this was achieved can be seen, at a high level, below. A Visualforce page was created for use by agents to provide search parameters. An external call was made to the master data system only if an internal call did not return any results.

![](https://cdn-images-1.medium.com/max/2000/1*wvaR_RQc5QIzcuWs7W8EvQ.png)

16. @29.00 — Informatica middleware solution is used to batch ETL data from Salesforce to the master data system. The master data system isn’t just for archived data but also for all data — it’s considered the single golden source.

![](https://cdn-images-1.medium.com/max/2000/1*B11O4nToPHBGLnuBRNKiKw.png)

17. @30.00 — @30.00 — There are many application integration security considerations when implementing these kinds of flows.

![](https://cdn-images-1.medium.com/max/2000/1*qe9RTn6B3G7gDnfo2Yu0Og.png)

18. @31.00 — Dell implemented a hybrid solution from a data archival perspective. It’s critical that the right data can be seen and used at the right time in a quick and efficient manner. Data is exported from Salesforce into a data store via Informatica. Informatica completes this parse and deploy scheduled job every 2 hours. A large volume of data must be part of an integrated / end to end solution, so that you can make use of the data when you want it.
