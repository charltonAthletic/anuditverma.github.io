---
layout: post
title: An Insider View of the Salesforce Architecture
tags: [API, Distributed Systems]
image: https://cdn-images-1.medium.com/max/2000/1*ht_2mJnm9KpVgCVKKPFFXA.png
share-img:  https://cdn-images-1.medium.com/max/2000/1*ht_2mJnm9KpVgCVKKPFFXA.png
---

## An Insider View of the Salesforce Architecture

*SalesforceSummaries is a publication that delivers the **key **insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Salesforce is now many different things, having grown from an exclusively CRM product back in 2000. One of the compelling aspects to Salesforce is that users don’t need to know what Salesforce does under the hood as it ‘just works’. However, a tremendous amount of exciting and complicated work happens in the background to power Salesforce and the data and Org of customers.

**Details: ‘[**An Insider View of the Salesforce Architecture](https://www.youtube.com/watch?v=GMwHqQtqEys)’

![](https://cdn-images-1.medium.com/max/2000/1*ht_2mJnm9KpVgCVKKPFFXA.png)

**Presenter: **Ian Varley

**Date: **July 6th 2017

**Time: **30 minutes

**Key Terms:** Salesforce architecture, application container, SaaS

**Summary:**

 1. @2.30 — Trust is the most important value within Salesforce. Because Salesforce customers trust us with really important data, the paramount things Salesforce think about are the security, the availability and correctness of your data.

 2. @2.56 — Salesforce operates at web scale. There are, as per trust.salesforce.com, billions of transactions completed per day.

 3. @3.05 — The unique thing that Salesforce does is the combination of trust and web scale.

![](https://cdn-images-1.medium.com/max/2000/1*55797nxmaMqC9a4qEfib5A.png)

4. @3.30 — SaaS (Software as a Service) enables you to use it while we (Salesforce) run it. A *lot* goes into making sure that Salesforce runs it correctly. This includes database maintenance, upgrades, capacity, troubleshooting, infrastructure etc.

![](https://cdn-images-1.medium.com/max/2000/1*WswaZcK283-J8ncHKbph-g.png)

5. @3.40 — The other big concept in the world of Salesforce is multitenancy. Multitenancy is where you have groups of users that share data with each other but not with other groups of users. Your data, while it is shared hardware and software in the same tenant, is separate to other customer’s data.

![](https://cdn-images-1.medium.com/max/2000/1*Om1PFvdYQxHG1zxSfE7zvg.png)

6. @4.50 — You can think of Salesforce as one massive distributed system.

There are many different **tenants** and when you work with that tenant and make requests to it, those requests are running in multiple different **services**; such as application and data storage services. Those services are then grouped into many different **instances** and these groups, known to Salesforce as **properties**, are architecturally diverse parts of Salesforce (e.g. Heroku) which run in dozens of **data centres** of many thousands of global servers to make this one big software product that runs **globally**.

![](https://cdn-images-1.medium.com/max/2000/1*9UioBJcTR0hRzga1xhng3w.png)

7. @6.00 — The way data is logically (not physically) separated in tenants is using identifiers. The tenants use different identifiers.

![](https://cdn-images-1.medium.com/max/2000/1*ckRCHD6MYwuVtaGDo2Bwtw.png)

8. @6.15 — Salesforce like to use the term ‘meso service architecture’. There are a lot of different software services running in containers, physical hardware and datacentres that do lots of different services.

![](https://cdn-images-1.medium.com/max/2000/1*LUfNy9t52UiKq5fX9GD6hA.png)

9. @7.35 — Instances are separate stacks of hardware and software. Salesforce have over 100 different instances for the core Salesforce products alone. The main reason for having lots of instances is scaling. And since tenants are logically separate, we can shard them into different instances.

![](https://cdn-images-1.medium.com/max/2000/1*RXfb__BvftPW-7E__yQQEg.png)

10. @8.25 — Salesforce have different stacks for different kinds of purposes. And this allows Salesforce to make different types or architectural trade-offs regarding data caching and performance degradation.

![](https://cdn-images-1.medium.com/max/2000/1*zZFMn8YGK-s2-2EIlv029w.png)

11. @8.55 — If you go to trust.salesforce.com, there are a few of the different stacks that you will see. Here, you will see the different properties. This is an indication of different architectural stacks that are used for different purposes.

![](https://cdn-images-1.medium.com/max/2000/1*Phz7BdmuNxBuxCpaavJvSQ.png)

12. @9.40 — The relational database is the core of each of our instances. We have a whole suite of different applications that depend on the relational database as the primary record system.

![](https://cdn-images-1.medium.com/max/2000/1*Avo7N94lQv22ydTMDj96rA.png)

13. @10.20 — The kernal gives us a few critical things.

![](https://cdn-images-1.medium.com/max/2000/1*3PClLhfGGVXjN4HyURHopw.png)

14. @10.25 — When you make a request to Salesforce, such as an API or UI request, then a few things *must* happen. When the request has been received, it reaches a stateless pool of application servers. Stateless means that a server is malfunctioning, then all the traffic will move to another server. This is managed by a load balancer, which distributes the traffic from a malfunctioning server to a functional server.

![](https://cdn-images-1.medium.com/max/2000/1*jXZ-JPGBtxWdHUDjqOVQzg.png)

15. @12.00 — Dealing with requests that ask ‘I want something Salesforce’ to ‘what do I get back?’ is powered by the Application Container.

16. @12.20 — Another important function of the kernel is Access Control. Although the tenant is the outer boundary, there are a lot of other internal tenant access controls. For example, you can set CRUD permissions, field level permissions and row level sharing etc. All of this is handled by the Access Control function of the kernel.

![](https://cdn-images-1.medium.com/max/2000/1*sS0CooIZeb0lj_QtmLzSUw.png)

17. @14.20 — The Universal Data Dictionary (UDD) is an abstraction inside of the application server that allows the Salesforce engineering team and the Salesforce customers to define the metadata shape of your org (objects, field types, relationships etc).

The UDD is a declarative entity model. This means that it is in a format that says ‘this is the name of the entity, these are the names of the attributes etc’. This allows interactions on entities by both internal and external platform developers.

18. @17.20 — At runtime, the UDD functions as an object relational mapping layer between the data on the database layer and what you see in your Org. What’s actually in the database looks very little like what you see coming out. If you were to look at the data in the database layer without the application container intermediary, the data would be useless to you.

![](https://cdn-images-1.medium.com/max/2000/1*dS0PC2YzwLKbxgyoG2yf2Q.png)

19. @18.25 — ID fields in the Salesforce user interface contain 15-character, base-62, case-sensitive strings. The structure of a Salesforce Id is as follows:

![](https://cdn-images-1.medium.com/max/2000/1*hSA-MVVOCBm9Dh0bIdcobQ.png)

An 18 digit, case-safe version of the ID is returned by all API calls. Best practice is to use the 18 character Id.

20. @22.10 — Salesforce models a virtual database on top of a physical database. It does a lot of things that a physical database does. But none of the entities, attributes and relationships are manifested at the physical database layer. When you create an entity, there is no DDL (data definition language) — there isn’t a physical structure that is created in the relational database. Rather, what happens is that a few rows and a few tables are inserted and then the system behaves as if there’s a whole new entity there. This is done because Salesforce is an online system and we don’t want any downtime to occur when one updates an entity. (When one does DDL in a physical database, the object is locked while the DDL is happening).

A lot of pros and cons occur due to this virtualization. What you may expect in the Salesforce database may actually not be there. For example, all the foreign keys and unique indexes are enforced at the software level and not by the database.

21. @24.00 — This means that there is a lot of database portability (a good thing).

![](https://cdn-images-1.medium.com/max/2000/1*PxdlGkhECQPk2lPIsUyqOA.png)

22. @24.40 — But under the covers, Salesforce is a bona fide relational database. Most of this is run on Oracle hardware stack and the majority of the Oracle instances is running a few thousand tenants. This is a heavy workload to ask of for one physical database so a lot of tricks are implemented to make this work.

One of the tricks that Salesforce implement is multi-level portioning. So, Salesforce have partitioning with the database instance itself.

Salesforce have created their own database optimizer because if Salesforce were to use the actual database query planner, it just returns nonsense because this is a multi-tenant system and so the physical database can’t respond to that. Salesforce also created skinny tables, which is essentially taking one dimension of a table and spawning it out for faster index performance.

A transaction at the database level means that one can do multiple kinds of work in the database and then one can atomically commit or roll those back together. You can leverage database transactions with Apex.

![](https://cdn-images-1.medium.com/max/2000/1*E9kBRnHmFYQ0g0QaoAo-YQ.png)
