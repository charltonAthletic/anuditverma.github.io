---
layout: post
title: A Developer’s Guide to Heroku Connect
tags: [Business Intelligence, Heroku, Heroku Connect, Salesforce Canvas, Tableau]
---

## A Developer’s Guide to Heroku Connect

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Heroku makes the scaling of cloud computing resources much easier and efficient, with the concept of ‘dynos’. However, Heroku also offers a service to connect to Salesforce very efficiently. Leveraging this with Salesforce Canvas results in compelling applications. In addition to this summary, the links [here ](https://www.youtube.com/watch?v=9XzOAEiTW8M)and [here ](https://www.tableau.com/about/blog/2015/2/salesforce-canvas-connector-tableau-server-online-live-36973)will also help you to understand more about the power of leveraging Heroku with Salesforce.

**Details:**‘[A Developer’s Guide to Heroku Connect](https://www.youtube.com/watch?v=SwPgh7cjfLM)’

**Presenter:** William Gradin

**Details:** 20 minutes

**Key Terms:** Heroku, Heroku Connect, Salesforce Canvas, Business Intelligence, Tableau

 1.@0.35 — Force.com is a great platform to build apps that extend business processes. If you need an app that requires all the security and granular controls, then Force.com is a fantastic platform to build the app on. Force.com is especially great for employee facing apps.

![](https://cdn-images-1.medium.com/max/2000/1*HpZtDFlFGt7hGteQxNFNWw.png)

2.@1.05 — [Heroku](https://www.heroku.com/) is a platform to develop customer apps on. You can build apps using a large set of programming languages as Heroku is language agnostic. You can scale cloud computing resources easily to match your demand.

3.@1.35 — Lyft (the ridesharing app) is built on the Heroku platform.

![](https://cdn-images-1.medium.com/max/2000/1*yo0JtrLoCkGgd-wivBXycA.png)

4.@2.20 — The best customer apps connect two critical elements: customer engagement and business process. You can leverage Heroku for customer engagement and Force.com for business processes.

![](https://cdn-images-1.medium.com/max/2000/1*6Z_9mKxtroq_imNR4uY9TQ.png)

5.@3.00 — To achieve this, you can leverage [Heroku Connect](https://www.heroku.com/connect). Heroku Connect is the data synchronisation engine between Heroku and Salesforce and shuttles data back and forth and syncs it between these 2 platforms.

In the use case of Lyft, new drivers would use the app that has been deployed to Heroku to sign up to Lyft. Then, this data is synced with the corresponding Salesforce org and that’s where apps and functionality in this org (Force.com platform) can be leveraged. For example, an approval process is initiated whenever a new driver signs up.

![](https://cdn-images-1.medium.com/max/2000/1*SPSpb-OWUxQgEY4EoN6qqQ.png)

6.@4.05 — As per the code [here](https://github.com/scottpersinger/mcontacts), the following node.js app with Angular front end has been deployed to Heroku which simply displays the contact list from a Salesforce developer org. The syncing is bi-directional and so if one edits a contact record on the node.js app, then that is displayed in Salesforce and vice-versa.

![](https://cdn-images-1.medium.com/max/2000/1*qXLbbTEbZleWxd-QrLG5RQ.png)

7.@5.15 — The screenshot below shows the Heroku Connect product. OAuth has been used to authenticate into Force.com so that Heroku Connect can talk to the Force.com APIs. And Heroku Connect has also been connected to the Postgres database that sits underneath the Heroku application.

![](https://cdn-images-1.medium.com/max/2000/1*2orFsu9d2vNZPFukj9_Pow.png)

8.@5.45 — By selecting the ‘Add’ button, all of the Salesforce sObjects will be displayed.

![](https://cdn-images-1.medium.com/max/2000/1*d5Ge2I5OffyfdkJxiI_fHw.png)

![](https://cdn-images-1.medium.com/max/2000/1*iQiYIG6WpoQa5yDN7HEerQ.png)

9.@6.50 — In this example, the Contact sObject has been queried and then the following screen is displayed with all of the Contact fields.

![](https://cdn-images-1.medium.com/max/2000/1*wPOIfe2L-L9nYrBhmEeJEw.png)

10.@7.05 — For the purposes of the demo, just a few fields from the Contact sObject has been selected. On the next screen, the access mode displays:

![](https://cdn-images-1.medium.com/max/2000/1*nWzKkVYRSDqP3RCzkPVtuA.png)

This is where you can specify the sync’ing direction (either bi-directional or just one way).

![](https://cdn-images-1.medium.com/max/2000/1*NK7vi4pFnkyayebzf88zUA.png)

The Heroku spinner icon is going; which indicates that Heroku Connect is connecting to Force.com and pulling down all of the Contact records into the Postgres database.

![](https://cdn-images-1.medium.com/max/2000/1*VOqTOAx_ZognBP1DW8PpfA.png)

11.@8.05 — Leveraging the command line, one can see the table has been created in Heroku and using SQL, you can query the data in this table.

![](https://cdn-images-1.medium.com/max/2000/1*nuSJW6o96DKIsX5VNQjzdw.png)

![](https://cdn-images-1.medium.com/max/2000/1*ddVPBZAu9bnA06YCkotRSQ.png)

12.@8.15 — Leveraging the Heroku dashboard, one can see the number of records in the database.

![](https://cdn-images-1.medium.com/max/2000/1*l307VWQw86yt1lJuQzw9uw.png)

13.@8.30 — The node.js app is returning the contact data from the Heroku database. The response is in JSON format, which is then returned to the client.

![](https://cdn-images-1.medium.com/max/2000/1*uAl_3EL8rsw0bXvmnK4k3Q.png)

![](https://cdn-images-1.medium.com/max/2000/1*tsxsnju75X3IDGf7-yUxUA.png)

14.@9.15 — Because the sync has been to set bi-directionally, one can update a contact record in the node.js app and this will consequently update the Heroku database and therefore, via Heroku Connect, update the record in Salesforce. The code for the contact update from the node.js app is:

![](https://cdn-images-1.medium.com/max/2000/1*pfHVqy-NPLeBh5CiPvgHpw.png)

15.@11.05 — Heroku Connect is built on a synchronization engine. It is running 24/7, sync’ing data back and forth between Heroku and Force.com. Heroku Connect is able to leverage the Salesforce streaming, SOAP and bulk API. Heroku Connect is, in effect, giving you an alternative API into the Force.com platform. And that API is just SQL because Heroku Connect hides all the complexities of dealing with the Force.com system.

![](https://cdn-images-1.medium.com/max/2000/1*4g6bT1JUQp8ljh8SJWZ9fA.png)

16.@11.40 — This other presentation will walkthrough how Tableau leverages Heroku Connect.

![](https://cdn-images-1.medium.com/max/2000/1*Kpgz3FrtxEtJRa0T3YPVew.png)

17.@12.10 — The vision from Tableau is to help people to see and understand their data. Tableau was created in 2003 and is the fastest growing BI (business intelligence) company.

![](https://cdn-images-1.medium.com/max/2000/1*Fghr9bp1N27VcmberLfWZg.png)

18.@12.30 — A big question that Tableau asked was ‘how can we provide users the power of Tableau and embed it within Salesforce?’.

![](https://cdn-images-1.medium.com/max/2000/1*RYxK2kaxDrYTiSue3_BjOQ.png)

19.@13.05 — The technologies that are used to achieve this are:

![](https://cdn-images-1.medium.com/max/2000/1*FD5tCUMnRl47AamLtiD41w.png)

20.@13.50 — Here is an architecture diagram to show the data flow between the different systems.

![](https://cdn-images-1.medium.com/max/2000/1*DdvK_oDDca4yFd_5gex-wQ.png)

The [Salesforce Canvas connector](https://developer.salesforce.com/docs/atlas.en-us.platform_connect.meta/platform_connect/canvas_framework_intro.htm) establishes the trusted relationship between Tableau and Salesforce. This is where communication between the two systems takes place over HTTPS. [SAML](https://help.salesforce.com/articleView?id=sso_saml.htm&type=5) can be leveraged with this process too, so that you can use Single Sign On.

21.@15.00 — The Salesforce data is posted to the Heroku postgres database via Heroku Connect. Tableau establishes a live connection with Heroku and the end result is that near real-time data visualisations are displayed in Salesforce via Canvas.

22.@17.30 — As per the demo, the results are compelling:

![Tableau rendering inside Salesforce Canvas with near real-time data via Heroku Connect](https://cdn-images-1.medium.com/max/2000/1*v2YwkaCoRW9v-Xb2MGt20w.png)
