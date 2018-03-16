---
layout: post
title: Large Data Management Strategies
tags: [Data Managements, Large Data Volumes, Skinny Tables]
image:  https://cdn-images-1.medium.com/max/2000/1*YJrZGGANXVbx5JkOOOH0Jw.png
share-img: https://cdn-images-1.medium.com/max/2000/1*YJrZGGANXVbx5JkOOOH0Jw.png 
---

## Large Data Management Strategies

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction: **To manage large data volumes (LDVs) in Salesforce effectively requires understanding the tools and techniques that you can leverage to be as efficient as possible.

**Details: ‘[**Large Data Management Strategies](https://www.youtube.com/watch?v=Hu44RNwN80E)’

**Presenters: **Suchin Rengan and Mahanthi Gangadhar

**Date: **November 25th 2013

**Time: **51 minutes

**Key Terms: **Indexing, skinny tables, data management

**Summary:**

 1. @2.30 — Data is one of the key element of applications.

 2. @2.45 — A huge amount of processes are completed around data. The key questions to ask ourselves when dealing with data in Salesforce are:

*· Am I using the platform’s features optimally?*

*· How do we ensure we keep up with performance?*

*· What factors do we need to consider across each topic?*

*· How can I ensure I have a scalable processes?*

![](https://cdn-images-1.medium.com/max/2000/1*YJrZGGANXVbx5JkOOOH0Jw.png)

This presentation will focus the most on Data Creation and Data Extracts.

3. @8.30 — The three step plan for Data Loads is:

![](https://cdn-images-1.medium.com/max/2000/1*evZksrU-3Gv8sN-gfI_SwA.png)

4. @10.30 — You need to consider every layer and level for the data load. You need to cut down on overheads when performing data loads or extracts. The different layers are:

![](https://cdn-images-1.medium.com/max/2000/1*2lPUanTAPrgYPKqXkUw97Q.png)

5. @10.50 — You need to understand how the system loads data. What are the sequence of activates that take place as part of a data load? There are 3 layers here: the configuration, programmatic and database layer.

![](https://cdn-images-1.medium.com/max/2000/1*vLEelAXnGFbC4vtAK1T1Xg.png)

6. @11.15 — As you start doing data loads, there is a system validation that happens. This validates to see if you as a user can transact the data, so this is a security enforcement which happens. All the events (before triggers, custom validation, assignment rules, auto-response rules etc) do take place as part of the data load. Anything that can be avoided as part of the data load activity should be considered, so some overheads get eliminated (although never at the cost of data integrity).

7. @13.30 — You need to understand the consequence of parent references. In most use cases, it’s more efficient to use a Salesforce GUID instead of using an External Id as you load data that share relationships between each other. This is because there is an additional cost with using External Ids, as a Lookup is performed whereas this is bypassed when using a GUID.

8. @15.45 — You also need to identify the most optimal API to use. The BULK API should be used if the data set is over 50,000 records but the downside is that it is not real time (as it is asynchronous).

9. @16.45 — Try to avoid upserts, as it is a two-step process (a lookup then an insert). This means that there is an overhead that is consumed which you may want to avoid. It’s better to do an Insert or an Update. Insert operation is the fastest.

10. @17.40 — Sharing rules are being calculated as you are loading data synchronously. It may therefore be preferable in some use cases to defer sharing calculation rules.

11. @18.50 — You want to identify how you can perform the data loads in a very deterministic manner. Testing makes things more deterministic. However, it’s very difficult for one to extrapolate the performance in a sandbox.

12. @20. 00 — Indexes help to make searching faster however, they have a cost as indexes are calculated at the time of data loading.

13. @20.50 — Are there layers of logic that you can bypass such that data load is performing more optimally? But remember, you don’t want to do this at the cost of data integrity.

![](https://cdn-images-1.medium.com/max/2000/1*7HiLYPrth1WLqnTOpxR3Vg.png)

14. @22.00 — [You cannot access the Salesforce database directly as there is a layer of abstraction](https://medium.com/salesforcesummaries/an-insider-view-of-the-salesforce-architecture-36af104ac064), there is no ODBC driver functionality. So what does Salesforce have in terms of getting data in and out of the system? There is the BULK API and the SOAP API.

![](https://cdn-images-1.medium.com/max/2000/1*BVyzvLe64WhWpiswP633ug.png)

15. @22.40 — The SOAP API is more for realtime and few number of records. The batch size of the SOAP API is set to 200 records, as a default. You can reduce this though, depending on the situation. You may want to reduce this batch size to reduce timeouts and this depends on the volume of data in the org, data model that you have and the volumes of data that you are trying to load. You have to test and plan to determine a suitable batch size number.

16. @23.40 — The BULK API is predominantly asynchronous. If you have over 250k records, you should use the BULK API. You have up to 10,000 records per batch. And the default BULK API batch size is 3,000 records. You need to do testing and planning to ensure that you have the optimum batch size as you have a rolling 24 hour clock for batch inserts; this means you can’t determine when your batches would be available again.

![](https://cdn-images-1.medium.com/max/2000/1*J0GToRlBZbHYm6L9IC6pZQ.png)

17. @25.40 — Another important thing to note about the BULK API is that you the order in which the batches are processed is not deterministic (because it’s asynchronous).

18. @27.30 — It can take a long time just to get the results back from the processing of the batches. So if you depend on the GUIDs, which would be available in the success files, you need to consider this.

19. @28.40 — You have a few options for an initial load. You can either do object by object or you can do all objects in one go.

![](https://cdn-images-1.medium.com/max/2000/1*-R9yKbrFWqA5Yjf7dPxdkg.png)

20. @33.00 — One option to efficiently query large data sets and reduce the number of API requests is to leverage the Bulk Query. A bulk query can retrieve up to 15gb of data into 15 1-GB files.

![](https://cdn-images-1.medium.com/max/2000/1*BEbGJIvOk1wDuTAt5daRHg.png)

21. @34.00 — Another option is to use auto number or PK chunking. Both are the same except that for auto number chunking, you are using a field that already exists in your object whereas in the other, you are using the primary key itself.

![](https://cdn-images-1.medium.com/max/2000/1*a2vEtdG8Ye3dEpJ1qw_FJA.png)

22. @37.40 — Data deletion can be one of the most resource intensive data operations. Truncating and bulk hard delete are 2 options available to speed up the data deletion process.

![](https://cdn-images-1.medium.com/max/2000/1*gwx91jNdeT6YLRT3_a9U1A.png)

In addition, there are several recommendations around cleaning up data:

![](https://cdn-images-1.medium.com/max/2000/1*RSbILtgBObiPHnMpvDw6ag.png)

23. @39.40 — All of the functionality below helps to reduce the data set that you are querying on to be the definitive data that you want. When managing LDV, you should always ask *‘how can I make this more efficient?’*.

![](https://cdn-images-1.medium.com/max/2000/1*Q75iUFnYMkC83OxiWRDYXg.png)
