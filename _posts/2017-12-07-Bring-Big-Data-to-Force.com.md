---
layout: post
title: BigObjects — Bring Big Data to Force.com
tags: [Big Data, Big Objects, Large Data Volumes]  
---

## BigObjects — Bring Big Data to Force.com

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Since the Winter ’18 release, Big Objects are now GA (generally available). This summary highlights the key takeaways from the excellent ‘BigObjects’ video from the Salesforce Developers YouTube channel and details why this big data functionality was built and how you can best use it. This summary is linked to [this one on Async SOQL](https://medium.com/salesforcesummaries/async-soql-big-data-computing-for-the-salesforce-platform-c325b2d841ed); which is the query language used for Big Objects.

**Details:** ‘[BigObjects — Bring Big Data to Force.com](https://www.youtube.com/watch?v=1ab8mlWCPkA)’

![](https://cdn-images-1.medium.com/max/2000/1*3uEM7fcwWtFJS3BSE9jCRQ.png)

**Presenter**: James Ferguson

**Time:** 47 minutes

**Key Terms**: BigObjects, big data, Async SOQL

**Summary:**

 1.@1.00 — BigObjects is now GA (generally available) as per the Winter 18 release.

 2.@1.30 — The agenda for this talk is below:

![](https://cdn-images-1.medium.com/max/2000/1*2AWvKTS-vbknPBenGgS9sQ.png)

3.@1.30 — Customers are trying to capture hundreds of millions and billions of records. This is the ‘data challenge’ because more customers = more data = more time. This is a growing data challenge. In order to process and manage such large data sets, the right tools and needed.

![](https://cdn-images-1.medium.com/max/2000/1*4MmjYmRvNUFAoB_CxLiocg.png)

4.@2.40 — Customers want to collect and store data for various reasons. The primary use cases for this is to enhance customer 360 (know more about their customers), to capture user activity and also to retain historical data (sometimes for regulatory purposes).

![](https://cdn-images-1.medium.com/max/2000/1*qG5U7WW2r-xGFDQ_DPthjg.png)

5.@3.30 — We will now discuss the following:

![](https://cdn-images-1.medium.com/max/2000/1*Z-uk6sZfl4xcfw83u3OpEQ.png)

6.@3.50 — Under Setup | Create, you’ll notice a new tab ‘Big Objects’:

![](https://cdn-images-1.medium.com/max/2000/1*p1kQM2-CjpJxzLmviwx1iA.png)

7.@4.30 — In this demo, a Big Object has been created to store ~ 160 million weather related records. As per the screenshot, you’ll notice that the Big Object looks very similar to a custom object. And that is the point: to create new functionality that looks very much like existing functionality that Salesforce Developers are aware of.

You can create custom relationships with other standard or custom objects too.

![](https://cdn-images-1.medium.com/max/2000/1*hpvVLWKA8KdqOyg7m1dLpw.png)

8.@7.00 — You can use SOQL to return a set of results from Big Objects too (although to process all of the records from a Big Object, you would use Async SOQL).

9.@9.00 — The metadata for Big Objects is very similar to that of standard and custom objects however, the major difference is that the metadata for Big Objects contains indexes.

![](https://cdn-images-1.medium.com/max/2000/1*WuZTyTVKbj-flMlm8gPyNg.png)

10.@9.10 — A good analogy here is that indexes are like looking up a surname in a phone directory. If you know the first few characters of a surname, then you can find the surname quickly regardless of how many other surnames there are in the phone directory.

11.@10.00 — You can leverage indexes with filters in standard SOQL queries:

![](https://cdn-images-1.medium.com/max/2000/1*ONUHGqO_h0ywnqcRv5Egiw.png)

In this example, using filters, out of the ~ 160 million records, 9 records have been left that match the filter criteria:

![](https://cdn-images-1.medium.com/max/2000/1*57dBoFkcd7frPCClk8zk8Q.png)

12.@13.00 — You can also build Lightning components with data from Big Objects and display them on a page in the Lightning App Builder. In this way, you can have Big Object data being displayed directly on a page.

![](https://cdn-images-1.medium.com/max/2000/1*OKnqcu2LN9cv58cooNDwNA.png)

Looking at the metadata of the Big Object, we can see that it is very important which fields are indexed.

![](https://cdn-images-1.medium.com/max/2000/1*807Fz3sAwut19F4hY8Nk5Q.png)

When you are building a query from a Big Object that displays data immediately, you can only filter on those indexes.

13.@14.50 — Let’s take a quick recap:

![](https://cdn-images-1.medium.com/max/2000/1*hgbsilbjad76cXpMokS3-A.png)

14.@15.30 — There is a huge amount of innovation that allows developers to build apps and solve problems that couldn’t have been possible 5 years ago. However, despite this, the technology that falls under ‘Big Data’ is very segmented. There isn’t just one ‘Big Data’ stack that you can get and install. Developers are having to be system integrators to take advantage of big data. The integration and operational costs of having to maintain multiple different stacks and APIs and technologies slows us down from doing what we want to do exactly with our big data.

![](https://cdn-images-1.medium.com/max/2000/1*LEYZBn0G9VR5YYkWo8ufLw.png)

15.@17.00 — So, with that in mind, Big Objects is an answer to that problem as Salesforce says ‘let us take care of the integration and operational aspects’.

![](https://cdn-images-1.medium.com/max/2000/1*QavPz0MEZAEZFlLHa9_pLw.png)

16.@19.30 — Async SOQL works with Big Objects to process millions and billions of records. Please read [this Salesforce Summary](https://medium.com/salesforcesummaries/async-soql-big-data-computing-for-the-salesforce-platform-c325b2d841ed) to learn more about Async SOQL.

17.@25.00 — You can also use Einstein Analytics (Wave) to pull data from Big Objects. This is powerful because it enables you to visualize the data quickly and effectively.

![](https://cdn-images-1.medium.com/max/2000/1*B2hSCFm0823IKbfTW8CB3A.png)

For example, you can visualize all the 160 million records in a heat map format:

![](https://cdn-images-1.medium.com/max/2000/1*UwmUr2AKc77nXtRTqUMRAA.png)

18.@28.00 — Another use for Big Objects is to use its functionality as a means to store field history, audit trail information and historical records which you want to keep but don’t want to be detrimental to the Org speed performance.

19.@29.00 — A common use case is to use Big Objects to store (archive) millions (and sometimes billions) of tasks. You can leverage Batch Apex with Big Objects to copy the data from the tasks and create an archived record in a Big Object.

20.@30.40 — You would leverage [Database.insertImmediate](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_methods_system_database.htm#apex_System_database_insertImmediate), because the archived records aren’t in the set of standard sObjects. You can also leverage [Queueable](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_queueing_jobs.htm) with Batch Apex for Big Objects; which might be helpful for you.

21.@32.00 — Big Objects are built on a set of proven big data technologies, with [Apache HBase](https://hbase.apache.org/) at its core. Big Objects are not built on brand new technology in Salesforce. In actual fact, the big data technology stack on HBase has been running Salesforce GA (generally available) products for 2 years now. In particular, the field audit portion of Salesforce Shield uses the same technology stack. At Salesforce, we like to say that field audit was the first ‘big object’.

![](https://cdn-images-1.medium.com/max/2000/1*8GIBye-RNRfwnUddn0_DWQ.png)

22.@34.00 — Finally, Salesforce have baked in best practices around big data into the way that Big Objects work. If your application has a thousand records today but 1 billion records tomorrow, your application will still work exactly as it should.

23.@42.00 — You can use Platform Events and the Bulk API with Big Objects too.
