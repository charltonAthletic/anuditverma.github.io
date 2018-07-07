---
layout: post
title: Leverage Apex to Extract IoT Value from Your Data
tags: [Apex, Gateway, IoT, Platform Event]
---

# Leverage Apex to Extract IoT Value from Your Data

*SalesforceSummaries.com is a publication that delivers the ***key*** insights
from Salesforce YouTube videos. We aim to be the
*[getAbstract.com](https://www.getabstract.com/en/)* of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

**Introduction:**

In this presentation, you will learn more about how to leverage Apex to extract
IoT value from your data.

**Details: ‘**[Leverage Apex to Extract IoT Value from Your
Data](https://www.youtube.com/watch?v=A67aNPwE5P8)’

**Presenter: **Michelle Szucs, Tim Peng

**Details: **20 minutes

**Key Terms:** IoT, Gateway

![](https://cdn-images-1.medium.com/max/800/1*bJ1Jk8qolcv0IBjBaSw3lw.png)

1.  @1.00 — The talk will focus most on how to get data from IoT devices into
Salesforce. Salesforce IoT helps you get value from the data that you have
already collected from IoT devices — it isn’t a platform.

![](https://cdn-images-1.medium.com/max/800/1*8DGDlGAp0Qd46nid6i02uw.png)

2. @2.10 — Salesforce takes in your data via Platform Events and from there, you
can apply all the Salesforce features to your data. The 4 steps on how
Salesforce IoT works is:

3. @3.15 — A gateway device offers many advantages for connecting IoT devices.
Heroku can act as a gateway. To connect with Salesforce, authentication is
mandatory. If you set up a connected app via OAuth, you have many steps to take:
you need a client secret, the token, callback url etc. The reason for these
steps and the emphasis on security is to ensure that the right devices are
connected, that the right apps are sending the right data and that the right
people are making the right actions in your org. So, it is challenging at times
to connect to Salesforce because some configuration and sometimes development is
required. This level of complexity is not suitable for many small IoT devices
because the authentication process would become overly burdensome for them. It
takes a lot of bandwidth to perform the OAuth handshake. So, what is the
solution?

You can leverage a proxy gateway or an IoT device platform, such as AWS, to
handle the authentication for the IoT devices for you into Salesforce. In other
words, the gateway is a connector (bridge) between Salesforce and the IoT
devices.

4. @10.15 — In this example, we will see how you can leverage Apex to convert a
single gateway event into individual events.

5. @10.30 — The high level steps to take are:

6. @10.50 — All of the events that come into Salesforce come in via [Platform
Events](https://trailhead.salesforce.com/en/modules/platform_events_basics). Any
service that produces event driven data that needs to be input into Salesforce
would leverage Platform Events. An event is defined as a change in state that is
meaningful in a business process.

7. @11.20 — Typically, IoT devices that will have its data feed into Salesforce
via Platform Events do this by creating a JSON which is sent to an endpoint.

8. @13.00 — To create a Platform Event trigger to handle any automation that
needs to happen once the IoT data has come into Salesforce, you can just select
‘new trigger’ from the Platform Event page. Platform Event triggers run in
‘after’ execution context because they fire once data has been received.

The trigger parses the JSON that is sent to Salesforce via Platform Events.
[JSON2Apex](http://json2apex.herokuapp.com/) can help to generate the Apex
required to parse the JSON. More info on serializing and de-serializing Apex can
be found
[here](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_methods_system_json_overview.htm).
To see how if this works, let’s POST the JSON that the IoT devices sends via
Workbench.

We can see that the trigger has fired and that this has impacted the data:

There are so many use cases for leveraging IoT data with Salesforce.

