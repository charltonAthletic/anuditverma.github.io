---
layout: post
title: Async SOQL and Big Data Computing for the Salesforce Platform
tags: [Async SOQL, Big Data, Large Data Volumes, Salesforce Platform]
image: 
share-img:  
---

## Async SOQL: Big Data Computing for the Salesforce Platform

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

With the exponential increase of data, it is becoming more and more important to be able to easily and efficiently frequently process millions and billions records. Since Big Objects [has become generally available in the Winter ’18 release](https://releasenotes.docs.salesforce.com/en-us/winter18/release-notes/rn_api_data_services_bigobjects.htm), it is opportune to go through Async SOQL; which is the query language used to process big data into the target big objects.

**Details:** ‘[Async SOQL: Big Data Computing for the Salesforce Platform](https://www.youtube.com/watch?v=TffHL8HplQM)’

![](https://cdn-images-1.medium.com/max/2000/1*yezv860PYMh4EKk5YLjQPw.png)

**Presenter**: James Ferguson

**Time:** 21 minutes

**Key Terms**: Async SOQL, Big Objects

**Summary:**

 1.@0.30 — Async SOQL is a new feature that Salesforce have created to help bring big data processing into the platform.

 2.@0.40 — **The fundamental challenge is that there is more and more data that is being created.** You are creating more customers, you are collecting more information about customers and you want to keep the data for longer (for historical trending, for compliance with new regulatory frameworks etc). Consequently, what starts to happen is that the data volumes increase and new sets of tools and techniques are required to manage these large data volumes.

![](https://cdn-images-1.medium.com/max/2000/1*l7jCDFFixGnwVFqToWW7Cg.png)

3.@1.55 — Big data has traditionally been very challenging to manage. It takes dedicated resources and infrastructure to achieve the efficient management of large data volumes and Salesforce are providing this infrastructure at a much lower cost and much more easily.

![](https://cdn-images-1.medium.com/max/2000/1*3N4aPIxXjQn67kyvLWSnLw.png)

4.@2.40 — There is no longer a learning curve of ‘how do I create a map reduce job?’. Although, with an Async SOQL request, that is what one effectively does albeit so much more easily.

![](https://cdn-images-1.medium.com/max/2000/1*CbNg5cI1VrAQdJHKr2nLcg.png)

5.@3.30 — There are many use cases of leveraging large data volumes to provide more value to the business. For example, many Salesforce customers are capturing every single customer touch point (extend customer 360), tracking all the changes made in a Salesforce org and also storing historical data for many years (10 years +) and none of this would be feasible without the Salesforce infrastructure to support large data volumes ([Salesforce Big Objects](https://resources.docs.salesforce.com/210/latest/en-us/sfdc/pdf/big_objects_guide.pdf) and Async SOQL etc) that number into the hundreds of millions of rows.

![](https://cdn-images-1.medium.com/max/2000/1*M0MiyM1RYSDMfwfesuX_Zw.png)

6.@4.20 — The simple example for this demo is that we have a standard object — Orders — and a related Salesforce Big object.

![](https://cdn-images-1.medium.com/max/2000/1*63OefJYHvndIQW6OEYNGZA.png)

7.@5.20 — Salesforce Big Objects and Async SOQL were built to look like standard Salesforce objects and standard SOQL.

8.@6.00 — In this demo, there are 10 million Order records:

![](https://cdn-images-1.medium.com/max/2000/1*3khsSgCjkvhGZu6KvkBOlA.png)

And there are over a billion records (the ‘three comma club’) in the custom Big Object:

![](https://cdn-images-1.medium.com/max/2000/1*6jF-DhyE8aTZCRLmpzqRFw.png)

However, despite this large number of records, navigating to the different Orders and related records in the UI is flawless. This is because the related Big Object (Big Order Items) has been designed to support synchronous queries.

9.@7.40 — To be able to process a billion records, you cannot use regular SOQL as you’ll reach a time out. Nor can you use batch Apex as it is limited to 50 million records.

10.@8.15 — However, you can use Async SOQL to process a billion records and more.

11.@9.00 — Login to Workbench and select ‘Async SOQL Query’:

![](https://cdn-images-1.medium.com/max/2000/1*bas1wNS1nPiwQCBI9pJaPw.png)

Now use the following Async SOQL:

![](https://cdn-images-1.medium.com/max/2000/1*8CoNgk8p-hYScgciRr88gw.png)

![](https://cdn-images-1.medium.com/max/2000/1*s_KiaRY5BjcyaUyJTkbgqw.png)

12.@9.20 — Because this is an asynchronous process (it’ll take about 15–20 minutes to process a billion + records) and so instead of just firing it, you need to specify a target object to return the results to.

13.@10.40 — So create a custom object and map the alias fields from the aforementioned async SOQL query to the fields of that custom object (the target object).

![This query will be essentially turned into a map reduce job and the result set will be used to create new records of the target object.](https://cdn-images-1.medium.com/max/2000/1*C-vx21F4zu-pj-K1R_NN4w.png)

14.@10.50 — However, if you were to run this again, duplicate records would be created and so you can use the ‘Upsert’ operation type instead.

15.@15.00 — For another example, let’s us this Async SOQL to group by year and month:

![](https://cdn-images-1.medium.com/max/2000/1*B3LC2RGuSIEdPo217h-IgQ.png)

In order to do an Upsert operation for this, you can assign target values to fields:

![](https://cdn-images-1.medium.com/max/2000/1*L8IDt2iJTKTVvOfpC5nIbA.png)

The aggregation result works very fast:

![](https://cdn-images-1.medium.com/max/2000/1*xDY4VtagVlohTybDSLVQ_A.png)

16. @20.00 — Big Objects is now generally available (GA) and the Trailhead ‘[Big Objects Basics](https://trailhead.salesforce.com/en/modules/big_objects/units/big_objects_get_started)’ is a fantastic place to start to learn about this feature.
