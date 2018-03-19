---
layout: post
title: Salesforce Integration and API Overview
tags: [Salesforce APIs, Salesforce Communities, Salesforce Integration]
---

## Salesforce Integration and API Overview

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:** You’ll learn about the different Salesforce APIs and their use cases.

![](https://cdn-images-1.medium.com/max/2000/1*wsvimzkIOXy1upcGVURz9Q.png)

**Details:** ‘[Salesforce Integration and API Overview](https://www.youtube.com/watch?v=pHLDxRQCV08)’

**Presenter**: Cleston Oliveria

**Time:** 18 minutes

**Key Terms**: REST, SOAP, Platform.

 1.@1.25 — What makes a platform? Today a platform is something that can multiply the reach of information and functionality. A platform is reachable and utilizable from any device. A platform is something that sets functionality in motion. It turns ideas into functionality that can be utilized from wherever.

![](https://cdn-images-1.medium.com/max/2000/1*Yrs5gsMidxiG3Z1Z05CmaA.png)

2.@2.05 — A platform enables devices to speak at the speed that they talk in a deterministic and undeterministic way, and the platform will handle all of that and the transactional data gracefully. This will be done in a multi-channel fashion, a mobile fashion and a platform will sustain all the different means of communicating in tandem.

![](https://cdn-images-1.medium.com/max/2000/1*x9pNVPAe_WRX8n1OC_ahqg.png)

3.@3.30 — The Salesforce API set will enable you to co-ordinate all the exchanges in the most optimum way, so that the user that is being served will have the data and/or functionality that they are after seamlessly.

4.@4.15 — As the Salesforce architect or developer, you need to understand a huge number of questions. For example, some questions are: what is the data that the user is after, how is the user going to reach for it, which devices and channels are they going to need, where is the data mastered, how will the data be retrieved, what are the points of change, what are the points of volatility, what is the speed of each type of data that is being integrated, and if the communication link doesn’t work for whatever reason(s) in the future, what is the compensation strategy?

5.@5.00 — Let’s discuss some of the different ways in which the Salesforce platform communicates with other systems; which makes users productive.

![](https://cdn-images-1.medium.com/max/2000/1*deraRvNhd205k9KfQf_0ew.png)

In this green grid, we can see that different applications, devices and middleware talk to Salesforce via different protocols. For example, we can see Java SDK and Ruby Gem reach out to Salesforce to retrieve data. The retrieving of data can be achieved with SOAP or REST calls. The BULK API uses REST to asynchronously perform CRUD operations. This is the ideal API for dealing with large data sets.

6.@5.55 — Odata stands for [Open Data Protocol](http://www.odata.org/) and is a modern, REST-based protocol for integrated data. [Salesforce Connect](https://trailhead.salesforce.com/en/modules/lightning_connect/units/lightning_connect_introduction) leverages this protocol to federate data from third party systems.

This means that the data can be used in Salesforce like a native object but in actual fact, the data resides outside of Salesforce. The data can be inspected as it comes into from a third party system. The meta-data will be treated as if it was Salesforce native, even though at no point is the data persisted in Salesforce.

7.@6.35 — The Bayeux client protocol is used with the Streaming API. Real time data can be consumed and changed between different systems, and everyone can be informed of changes.

8.@7.50 — Apex can be leveraged to call third party REST or SOAP services and that data can be inspected and/or persisted as required. However, communicating to external systems from Salesforce can also be achieved declaratively using Outbound Messaging. You configure a message that you associate with an event in Salesforce, when the event is triggered, the message will fire. There is a schema in the form of a [WSDL](https://www.w3schools.com/xml/xml_wsdl.asp) that the third party will receive. This is the shape of the message. The third party will acknowledge receiving the message.

![](https://cdn-images-1.medium.com/max/2000/1*bRPG_IFAmKyzW9-RzIvj2w.png)

9.@8.50 — In order to take advantage of these Salesforce APIs, you’ll need a toolkit. APIs are not very interface-able in the way that they look, so these tools help to expedite development.

![](https://cdn-images-1.medium.com/max/2000/1*G-KtvwM8MOzLVonHuSNTAw.png)

The [Salesforce API Explorer](https://developer.salesforce.com/docs/api-explorer/sobject/Account) will enable developers to more easily navigate and model the different Salesforce APIs.

10.@9.30 — You need to understand the integration dependencies, not just in terms of security but also the permissions within the security. Within Salesforce, every piece of data was created by someone, belongs to someone and last modified by someone — all with a date/time stamp. Whether you are using an API or interacting with data at the UI level, access to that data is based on whether or not you have the record access. So what an API user can do is dependent on the OWD (org wide defaults) and how the sharing settings have been setup (profiles, permissions etc).

![](https://cdn-images-1.medium.com/max/2000/1*0z9W38mHQbuzjZ5jZzSRWg.png)

You also need to consider the context of the session from which your API is talking to the Salesforce platform or from which an API is talking to another system. This is important for auditing and authorization purposes. You need to consider that the usage of the session is true to form — you don’t want an API acting on your behalf on a record that is under someone else’s session. A generic API session is detrimental as you are losing the fine grained detail of data interaction.

There was a time in the past where the username and passwords were persisted and an additional security token on top of the password of the API user was used. This was before [OAuth](https://en.wikipedia.org/wiki/OAuth). Now, OAuth grants a verified session token of your connected app. This is an identity aware and much more secure protocol.

![](https://cdn-images-1.medium.com/max/2000/1*x6GHCr-BycmJTE9-BpBxzg.png)

11.@13.15 — We can query using either SOQL and SOSL through an API too.

![](https://cdn-images-1.medium.com/max/2000/1*uO0NmEUv7uPuh7_Hm14j3Q.png)

12.@14.20 — Just to re-cap, our APIs come in two flavours: REST or SOAP. Also, every time you create a new sObject in the Salesforce Platform, it will automatically be available in the API.

![](https://cdn-images-1.medium.com/max/2000/1*VtUO-gOyZ5ArESaS2QTncQ.png)

All the information in this slide is also in the trailhead API Basics badge: [https://trailhead.salesforce.com/en/modules/api_basics](https://trailhead.salesforce.com/en/modules/api_basics)

![](https://cdn-images-1.medium.com/max/2000/1*wCozx6Q9c8ji0gSDbto5vA.png)
