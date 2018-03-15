---
layout: post
title: Building Efficient Visualforce Pages
tags: [Lightning, Performance Profiling, Visualforce]
image:  https://cdn-images-1.medium.com/max/2000/1*tO5aNuOi4IX2bggAO9c4dw.png
share-img:  https://cdn-images-1.medium.com/max/2000/1*tO5aNuOi4IX2bggAO9c4dw.png
---

## Introduction to Performance Profiling of Visualforce and Lightning

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

The purpose of this overview is to introduce the reader to the concept of performance profiling in Visualforce and Lightning pages using the Salesforce Developer Console and the Salesforce Lightning Inspector Chrome extension.

**Details:**

![](https://cdn-images-1.medium.com/max/2000/1*tO5aNuOi4IX2bggAO9c4dw.png)

Video: ‘[Introduction to Performance Profiling of Visualforce and Lightning](https://www.youtube.com/watch?v=DL2Nuy-fl5U ])’

Presenter: Rajesh Thakur

Date: November 14th 2016

Time: 12 minutes

Key terms: Performance profiling

Key points: There can be many reasons why your Visualforce and Lightning pages aren’t as performant as they could be. You can use the Salesforce Developer Console and the Salesforce Lightning Inspector to debug these issues.

 1. @1.20 — It is best practice to conduct performance profiling for Visualforce and Lightning pages.

 2. @1.30 — Performance profiling is a broad subject and there are a lot of challenges related to this.

 3. @2.20 — The most common challenges with Performance Profiling are below:

![](https://cdn-images-1.medium.com/max/2000/1*704TnAWqWUrzCSDtkfYCuw.png)

4. @2.45 — To conduct performance profiling for Visualforce pages, you should enable Visualforce page Debug Logs in the Developer Console and this will enable you to use this tool to profile Visualforce pages.

![](https://cdn-images-1.medium.com/max/2000/1*uVswhBMWNBn9JJxjsve4Lg.png)

5. @3.40 — You should follow the below steps to then start the performance profiling.

![](https://cdn-images-1.medium.com/max/2000/1*8HZGAeaFU78s_9nZ1xOXkA.png)

6. @5.15 — Go to the Timeline tab in the Developer console. This gives a breakdown on the time for the page to load and identifies what the root cause is for a longer page load.

![](https://cdn-images-1.medium.com/max/2000/1*83jW51dbhux651klfJ3Hog.png)

7. @7.00 — Look at the following slides to see how to use the other features of the Developer Console to get a clearer understanding as to what good be more performant in your Visualforce pages:

![](https://cdn-images-1.medium.com/max/2000/1*nRi8MiaO08ZyN5ox-9Bt-g.png)

![](https://cdn-images-1.medium.com/max/2000/1*1-ZgjEph0ktEM1ICR5PwHA.png)

![](https://cdn-images-1.medium.com/max/2000/1*iPNK1moP4k1sPfj3qo2Exg.png)

8. @8.30 — Conducting performance profiling for Lightning pages is slightly different. Instead of the Developer Console, you should use the Chrome extension ‘[Salesforce Lightning Inspector’](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/inspector_intro.htm).

![](https://cdn-images-1.medium.com/max/2000/1*Mt4W_jKP9RSZG4xzbdGzgA.png)

9. @9.40 — After installing the Salesforce Lightning Inspector Chrome extension, when you go to Chrome Developer tools, you’ll see a new tab ‘Lightning’.

![](https://cdn-images-1.medium.com/max/2000/1*vAtbOZguQlauJoEnYm-_JQ.png)

10. @9.55 — When you select the ‘Lightning’ tab, you can see all of the components that are being executed as part of that Lightning page.

11. @10.05 — Using the Performance tab in the Salesforce Lightning Inspector, one can isolate inspection to just the component code, allowing one to identify which components are slower and locate where in the component hierarchy the slowness is occurring.

12. @10.30 — You can also select the Transactions tab, which will give additional information about the Lightning page.

![](https://cdn-images-1.medium.com/max/2000/1*X7Ciat_ILfFOgaUYvkV5Xw.png)
