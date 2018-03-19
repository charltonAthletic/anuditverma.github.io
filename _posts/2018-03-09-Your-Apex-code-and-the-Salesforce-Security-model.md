---
layout: post
title: Your Apex Code and the Salesforce Security Model
tags: [Apex Code, Field Level Security, Indirect Reference, Security Model]
image: https://cdn-images-1.medium.com/max/2000/1*u3IGsNxIYXpjLAOBxX8SUw.png
share-img: https://cdn-images-1.medium.com/max/2000/1*u3IGsNxIYXpjLAOBxX8SUw.png
---

## Your Apex Code and the Salesforce Security Model

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

In this presentation, a quick review of how the Salesforce security model will be presented. Then, an overview on how Apex code runs followed by best practices that you should adopt to ensure your Apex code is secure from a field level security perspective.

![](https://cdn-images-1.medium.com/max/2000/1*pM95hvpQ5NSLTAX9cbueaA.png)

**Details:** ‘[Your Apex Code and the Salesforce Security Model](https://www.youtube.com/watch?v=NamHEJIbzWQ)’

**Presenter:** Matt Quagliana

**Details:** 18 minutes

**Key Terms:** Apex code, security model, field level security, indirect reference

 1.@1.50 — Every Salesforce user is assigned a Profile. Profiles determine the base CRUD (create, read, update, delete) access for different Salesforce objects (sObjects).

![](https://cdn-images-1.medium.com/max/2000/1*UVqb3Eyf1pdf78AZWZjSAA.png)

2.@2.20 — Profiles in Salesforce also determine read/write access to fields. This is known as field level security (FLS).

![](https://cdn-images-1.medium.com/max/2000/1*2zzxNmnwSPrYMOasOk7ygA.png)

3.@2.40 — Permission sets enable you to extend access to other users without having the need to create more Profiles.

![](https://cdn-images-1.medium.com/max/2000/1*xgAPlojKGGh3s9lb2eKc3Q.png)

4.@3.20 — Org Wide Defaults (OWD) determine access for records where you are not the owner.

![](https://cdn-images-1.medium.com/max/2000/1*wvnQV1FgPIQtfwpunQzagA.png)

5.@4.10 — Roles extend ownership. If your manager needs to see/edit your records, then this can be achieved via the role hierarchy.

![](https://cdn-images-1.medium.com/max/2000/1*jvM6gl-RiZdTyTVC_TA3Ug.png)

6.@4.40 — Another important Salesforce security feature is sharing rules. Sharing rules also extend access to certain groups.

![](https://cdn-images-1.medium.com/max/2000/1*GvUKJZrtSzsPu2mlftpiiQ.png)

7.@5.40 — Contacts inherit the security settings from the account. And if you have contacts that aren’t related to an account, then that contact is private (only the owner has access to the account).

![](https://cdn-images-1.medium.com/max/2000/1*odZduzgVuiXEJjWV22-AOA.png)

8.@7.40 — In summary, there are a number of different features that can be leveraged in Salesforce confirmatively to determine who can see and do what in the application. Crucially, all declarative configuration runs inside the **user context**. Meaning, that it runs within the bounds of all these settings and rules.

![](https://cdn-images-1.medium.com/max/2000/1*NHbKElrRIDP92JZW3Omy4w.png)

9.@8.00 — However, with regards to Apex code, this is slightly different. There are some special variations to point out when it comes to Salesforce security with Apex.

The most important distinction is that Apex runs in the **system context** and not the user context. Furthermore, in some situations, Apex lets you decide how to handle security.

![](https://cdn-images-1.medium.com/max/2000/1*qoB643Md3y6ZKbJ_ARF4PQ.png)

10.@8.50 — Controllers are typically how you get access to data from Apex code. It is not best practice to use an indirect reference as this is a way in which data could be leaked.

![](https://cdn-images-1.medium.com/max/2000/1*7RsfrbszbhbClLRW7RxyDw.png)

11.@10.05 — An example of an indirect reference is line 11 in the code example below.

![](https://cdn-images-1.medium.com/max/2000/1*u3IGsNxIYXpjLAOBxX8SUw.png)

There is nothing in this code which ensures that people who should not have access to the value from the ‘Favorite_Color__c’ field do not see it.

12.@11.00 — The way to resolve this is, as per line 10, to add a single test. The [isAccessible()](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_methods_system_sobject_describe.htm) method from the Schema sObject can be used to test whether a user has access to any object and/or field.

![](https://cdn-images-1.medium.com/max/2000/1*S9ZbMFCYgEO6W9914H5BNA.png)

13.@11.40 — You should only write code for requirements that configurations cannot handle. Being able to leverage isAccessible() is helpful because you may want to write logic to say that ‘*these sets of users can only access these sets of fields during business hours, and/or these sets of users can only access these sets of fields if these fields on the same record are of a certain value*’.

14.@13.00 — Adopting the [**with sharing](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_keywords_sharing.htm)** keywords make your custom code respect OWD, role hierarchy and sharing rules.

![](https://cdn-images-1.medium.com/max/2000/1*veG5C8M2Wcw77HEdVwLU7g.png)

15.@14.10 — The best practices are:

![](https://cdn-images-1.medium.com/max/2000/1*8Wa0urvMNevrbyJ2ARvM9A.png)

Leveraging **apex:inputField** conforms to field level security etc whereas apex:InputText does not.

16. @15.20 —

![](https://cdn-images-1.medium.com/max/2000/1*7cn8W9go4CoA7AmOK7wlug.png)

17. @16.10 — The official guidance from Salesforce is below. This [link](https://developer.salesforce.com/page/Testing_CRUD_and_FLS_Enforcement) has some great information.

![](https://cdn-images-1.medium.com/max/2000/1*Z5S0O554JkUCG5PUp9bFdA.png)

18. @17.20 — In summary,

![](https://cdn-images-1.medium.com/max/2000/1*S-g4vvMjEIHm6IsTJptQSg.png)

Also, these trailhead modules are very informative on this particular topic too:

![](https://cdn-images-1.medium.com/max/2000/1*KX_mlfePr6JCHoiT_YNBEw.png)
