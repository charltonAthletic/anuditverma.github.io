---
layout: post
title: Rethinking Your Architecture With Platform Events
tags: [Enterprise Level Development, Platform Events, Salesforce DX]
---
## Rethinking Your Architecture With Platform Events

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:** Platform Events is a new development paradigm that facilitates modular components and reduces dependencies in complex systems.

**Details:** ‘[Rethinking Your Architecture With Platform Events](https://www.youtube.com/watch?v=PsRQIH9yZKE)’

**Presenter**: Florian Hoehn

**Time:** 17 minutes

**Key Terms**: Salesforce DX, Platform Events, enterprise level development

 1.@0.03 — The full slides to this presentation are [here](https://github.com/florianhoehn/df17-platform-events-architecture).

 2.@0.05 —This presentation will be about how we can rethink software architecture with [Platform Events](https://trailhead.salesforce.com/en/modules/platform_events_basics).

 3.@0.25 — Salesforce has grown from a CRM application to an **enterprise level platform**.

 4.@0.55 — The Salesforce ‘Web2Lead’ feature process and system architecture looked like this:

![](https://cdn-images-1.medium.com/max/2000/1*3zvUzbw-uNm88dXMq2w1uQ.png)

This is relatively straight forward. A lead is created, gets assigned and eventually conversion to other objects happens.

5.@1.25 — However, the use of Salesforce within companies expanded and so the demand for the Web2Lead process to have more functionality was met. For example, the Web2Lead process can now work with an Order Management process. Consequently, as per the diagram below, the system architecture got more complicated.

![](https://cdn-images-1.medium.com/max/2000/1*lbRP28do3crwmFr3znPJkA.png)

6.@1.55 — Now, an integration layer is required so as to integrate Salesforce with external systems. For example, a Master Data Management (MDM) system is integrated to ensure high levels of data quality for customer information, a Shipping System is integrated to ensure that the products get shipped correctly, and a payment system is integrated so as to ensure the payment is received prior to sending out the order. This level of complexity goes on and on and on.

![](https://cdn-images-1.medium.com/max/2000/1*-oDuFOKxZHdKNgsOxM0nDQ.png)

7.@2.20 — And in the example below, this can keep expanding to the point where it becomes increasingly difficult to manage and maintain.

![](https://cdn-images-1.medium.com/max/2000/1*tQihE6V5CJBuWwDr8Dld5w.png)

8.@2.40 — The big issue with all of this is that **this is not scalable**. For every feature that gets added, the system architecture becomes increasingly complicated. This creates a scenario in which you need to understand every aspect of the system due to the increasing levels of dependencies. Just to be able to understand all the aspects of the system becomes harder and harder and frankly, not sustainable.

![](https://cdn-images-1.medium.com/max/2000/1*TaROswK5s8hUEsMts4AAJg.png)

9.@3.05 — So the big question becomes ‘how do we make this scalable?’

10.@3.20 — The resolution is to leverage Platform Events. Creating Platform Events look and feels like creating an sObject. One of the biggest differences though is these are immutable — they cannot be changed.

Platform Events open up an ‘event driven architecture’ to Salesforce developers. An event producer creates an event and that gets added onto the event bus. The event bus is a queue — it has a strict chronological order and executes each event on it one after the other.

Event consumers subscribe to an event and the moment that event gets put onto the event bus, the event consumer gets notified. This way, the event consumer doesn’t need to know about the event producer rather, just needs to know about the event record. This approach abstracts the dependencies.

![](https://cdn-images-1.medium.com/max/2000/1*lj2ejDZSQZlY4Pk7WhRXyQ.png)

11.@4.50 — This is how Platform Events look like on the force.com platform:

![](https://cdn-images-1.medium.com/max/2000/1*jDI9t6_TtN5my--nbBRXNA.png)

We can publish events (event producers) in a number of different ways, both declaratively and code. These events then get put onto the event bus.

![](https://cdn-images-1.medium.com/max/2000/1*JRRTD5izN0l4U8d0giMcOA.png)

Event consumers consist of processes, flows, apex and CometD (which is via the Streaming API). So the event consumers only need to know about the event bus and not the event producers.

12.@6.20 — The order management module from the previous system architecture diagram is below:

![](https://cdn-images-1.medium.com/max/2000/1*MQXLFsk76pJWWEUItQVTHA.png)

And the important thing we want to know here is whenever an order record has been created.

So our order management module can be re-architected like so with Platform Events:

![](https://cdn-images-1.medium.com/max/2000/1*1oOTjwjnujsVv5MSe4okIA.png)

13.@7.20 — Integrations, in particular, can be re-architected far more simply. Platform Events make integrations much easier.

![](https://cdn-images-1.medium.com/max/2000/1*FREx0ljqEnwo5DMJsqAgYQ.png)

14.@8.40 — Another use case, this time 100% on the force.com platform, can be seen below. This increases the modularity and reduces dependencies.

![](https://cdn-images-1.medium.com/max/2000/1*kvDeYhSj9WYXVwQ95jUwEg.png)

15.@10.20 — The future for Platform Events is very exciting because of all the opportunities that it offers. What if Salesforce standard events can also be subscribed to? And furthermore, what if we have an Event Sourced Platform? This is basically Git. This could be a really powerful future tool using platform events.

![](https://cdn-images-1.medium.com/max/2000/1*JCb6iWp52xVD9vtf3UQQzQ.png)

![](https://cdn-images-1.medium.com/max/2000/1*18Dhxw6_qBJx3_zWTTuQdQ.png)

16.@13.15 — Platform Events really play well with Salesforce DX. Salesforce DX wants us to create small code bases that we can handle and deploy easily.

![](https://cdn-images-1.medium.com/max/2000/1*hWpWQ8fEN8DgiBPLDTmXJg.png)

17.@14.30 — Platform Events is an attribute of enterprise level development and Salesforce is getting there (it’s continuing to become more of an enterprise level platform and not merely just CRM).
