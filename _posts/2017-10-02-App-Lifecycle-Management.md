---
layout: post
title: App Lifecycle Management: Three Ways to Setup Up Your Development Lifecycle
tags: [App Lifecycle, Migration Tool, Salesforce DX]
---

## App Lifecycle Management: Three Ways to Setup Up Your Development Lifecycle

*SalesforceSummaries is a publication that delivers the **key **insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

As per the [coming developments with Salesforce DX,](https://medium.com/salesforcesummaries/salesforce-platform-winter-18-release-readiness-summary-9910115b4b03) it may be worthwhile to look back at what the current change control processes there are. The [App Lifecycle Management](https://www.youtube.com/watch?v=7DCWN1YhE7g) video is almost 4 years old but still contains a lot of very helpful information.

**Details:**

![](https://cdn-images-1.medium.com/max/2000/1*ZXXCLmRhfsC05KPIM4ceyA.png)

Video: ‘[App Lifecycle Management](https://www.youtube.com/watch?v=7DCWN1YhE7g)’

Presenter: Andrew Smith

Date: November 25th 2013

Time: 52 minutes

Key terms: Change control process, governance, change sets, Force.com ANT Migration tools

Key points: There are 3 main change control processes. Which one will suit your needs best depends on a lot of different things: company risk tolerance, company resources, org complexity etc.

 1. [@1](http://twitter.com/1).20 — What is ALM? (Application lifecycle management)

 2. [@1](http://twitter.com/1).30 — ALM is about taking idea, delivering it to end users and maintaining it.

![](https://cdn-images-1.medium.com/max/2000/1*Wns-GOdVPQS2drx44FtxFQ.png)

3. [@2](http://twitter.com/2).20 — But for others, ALM is more complex and encompasses many more things. For example, if you look for ALM on Google, some more complex diagrams are returned.

![](https://cdn-images-1.medium.com/max/2000/1*3rZU_3gMOYDhfw86-CZjcw.png)

4. [@2](http://twitter.com/2).40 — Goal today is to explain what Salesforce is doing with regards to ALM and to educate the viewer more about Salesforce best practices.

5. [@](http://twitter.com/2)2.50 — The analogy of training and racing a marathon is fitting for ALM. The training is gathering requirements and producing a project plan whilst the actual racing is the development, testing, user acceptance, deployment and bug fixes.

![](https://cdn-images-1.medium.com/max/2000/1*u01r0sQn3EMH0Q6dgsQ49g.png)

6. [@3](http://twitter.com/3).50 — So it comes down to Planning and Doing. In this session, we’ll be talking about the Doing.

7. [@4](http://twitter.com/4).50 — On the planning side, Governance is arguably the most important thing for app lifecycle management. It’s not just about the development, but the training, the agreement on how frequently one will do releases. It is a conversation around business, policy and how you setup your company. Who has to sign off development processes? What constitutes development? How frequently should release cycles be implemented? What are the risks for the business when doing these? Fundamentally, it’s a conversation with your colleagues to find out how best to approach the planning of developments.

![](https://cdn-images-1.medium.com/max/2000/1*02QSzRADdz5Hw7_TdYJelg.png)

8. [@6](http://twitter.com/6).25 — The reality is that for some companies, building directly into Production is OK. It depends on the profile of the customer.

![](https://cdn-images-1.medium.com/max/2000/1*eC8Mlewc6q51XNUnWBU_jw.png)

9. [@7](http://twitter.com/7).10 — Does your company have a risk tolerance? If things go wrong in Production, then can you fix them quickly? If so, point-n-click changes may be OK in Production first. Although, generally, if the company has resources, changes should be made first in a sandbox.

10. [@8](http://twitter.com/8).30 — Ensure that you are making a weekly export of data and meta-data. You can use the Setup Audit Trail and Data Export tools to help facilitate this. Better yet, you can use an IDE to very quickly and easily export all the meta-data.

11. [@8](http://twitter.com/8).50 — Change control process can be very helpful to help standardise deployments.

12. [@10](http://twitter.com/10) — The change set process at a high level is to make outbound change sets from a dev or dev pro sandbox to a partial or full copy sandbox. Validate the change sets and then finally deploy. Then make the change set from partial / full copy sandbox to production.

13. [@15](http://twitter.com/15).00 — You can leverage sandbox connections to determine which sandboxes should be able to have in/outbound change sets. This helps companies to enforce a particular change control process.

14. @ 18.30 — Dealing with the aforementioned change set process with change sets may work if:

![](https://cdn-images-1.medium.com/max/2000/1*bppq1wNNuzjgESQAUGOoXQ.png)

15. [@22](http://twitter.com/22).00 — The below is the most complex control process. The full copy sandboxes can either be separate or their uses can all be consolidated into one (additional full copy sandboxes will cost more money, so this is something to bear in mind).

![](https://cdn-images-1.medium.com/max/2000/1*CFNJK-uOrvtYwmDPEbc20A.png)

16. [@22](http://twitter.com/22).20 — Give each developer a dev sandbox. Dev and dev pro sandboxes can refresh daily, whereas partial and full copy sandbox have much longer refresh turn arounds (once per month).

![](https://cdn-images-1.medium.com/max/2000/1*HZLUrT0x0EW8xUJcLxi6zw.png)

17. [@23](http://twitter.com/23).00 — Changes between environments in this more complex setup are best served by ANT scripts, or better yet, [Salesforce DX](https://gearset.com/blog/salesforce-dx). You will need a source control system.

![](https://cdn-images-1.medium.com/max/2000/1*LcwLChgHtODPQcJXVmzgUA.png)

18. [@](http://twitter.com/25)25:00 — There are lots of customers who have implemented a complete end to end testing process.

![](https://cdn-images-1.medium.com/max/2000/1*fw_m2cnBAg3a1371y2zgsA.png)

19. [@26](http://twitter.com/26).00 — By having the Force.com Migration tool as ANT based, this means that you can easily integrate it with other utilities and solutions. It’s entirely command line based. It’s a retrieve/deploy protocol that uses XML and can be used to programmatically check-in to a source control system.

![](https://cdn-images-1.medium.com/max/2000/1*iyJnSbhVWGe5AP3fA1HxVg.png)

20. [@29](http://twitter.com/29).00 — Package XML is an enumerated list.

![](https://cdn-images-1.medium.com/max/2000/1*Yp8n3qSDeOfK_eI6jI3XVg.png)

21. [@34](http://twitter.com/34).00 — Sometimes the below is overkill. Don’t jump to it, grow to it.

![](https://cdn-images-1.medium.com/max/2000/1*MHwgdABosJAJfZsZyQvUGw.png)

22. [@35](http://twitter.com/35).00 — The correct model (make changes straight into Production / make changes via change sets between full copy and production / have continuous integration with Force.com migration / Salesforce DX) depends on the current needs of the org.
