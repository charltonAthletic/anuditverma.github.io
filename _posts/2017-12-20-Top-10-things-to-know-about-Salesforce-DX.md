---
layout: post
title: Top 10 Things to Know About Salesforce DX
tags: [Continuous Integration, Salesforce DX]
---

## Top 10 Things to Know About Salesforce DX

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Salesforce DX was released during Winter ’18 and offers a new paradigm for Salesforce development. This summary discusses some interesting things to note about the history and functionality of Salesforce DX.

**Details**: ‘[Top 10 Things to Know About Salesforce DX](https://www.youtube.com/watch?v=UaPPhFWHBQ0)’

![](https://cdn-images-1.medium.com/max/2000/1*0YEk54TYYnWaZWEz6C1Ibg.png)

**Presenter**: Josh Kaplan

**Time:** 20 minutes

**Key Terms**: Salesforce DX, Continuous Integration

 1.@0.40 — The history of Salesforce DX is important to note. People were historically doing Continuous Integration (CI) on the Salesforce platform by deploying lots of code to lots of orgs all at one time. These monster deployments would cause a ‘traffic jam’. This was bad because deployments wouldn’t be timely. There was a clear need to have more environments do more work and things weren’t working with the way they were. This spurned Salesforce into investing in a different set of tools to facilitate timely and easier CI.

 2.@1.50 — Also, Salesforce got inspired by [Heroku Pipelines](https://devcenter.heroku.com/articles/pipelines) and could see how a similar concept would benefit Salesforce CI.

 3.@2.20 — The etymology history of Salesforce DX is quite interesting to note. Salesforce DX was referred to as ‘Project Janus’ in the beginning. The logic behind using ‘Project Janus’ is that Janus is the Roman god of transitions. Salesforce DX was also known internally as ACDX (App Cloud Developer Experience). Meanwhile, Scratch Orgs were known previously as the Developer Server.

![](https://cdn-images-1.medium.com/max/2000/1*T0zqw7FpIMejzpxSLoZ4kA.png)

4.@3.10 — Also, the App Hub had some previous name such as ‘Dev Hub’ and ‘Dev Lodge’ among others.

5.@3.30 — Finally, ‘[New Packaging’](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_build_package_checklist.htm) used to be known as Salesforce Archives (very similar to Java Archives, or JARS). This would mean that Salesforce Archives would be known colloquially as SARs; which is the name of a human virus and so instead, ‘New Packaging’ or ‘Packaging 2’ was settled on.

6.@5.20 — You can keep your old tools for Salesforce DX (with a few exceptions). For the most part, all the tools that you use today for Salesforce CI are still available. Sandboxes and change sets still work in the new paradigm and are in fact, very important as Scratch orgs aren’t a substitute for sandboxes — they serve different needs.

![](https://cdn-images-1.medium.com/max/2000/1*PN5aRLv4SuhQSAD-aSJNiw.png)

7.@6.20 — Salesforce DX is not ‘all or nothing’ because you choose to use just a portion of your application with Salesforce DX while you can have the other portion of your application served by change sets and sandboxes.

8.@6.35 — You need to set up a very good project directory structure for Salesforce DX. Different sets of logically connected metadata will be in DX Projects (for example, Lightning DX Project, Apex Class DX Project). And you can control who make changes to what project.

9.@7.40 — There’s no right way to divide up your org — there are many different ways.

10.@9.00 — [Developer-Controlled Packages](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_dev2gp_plan_pkg_types_locked_unlocked.htm) with Salesforce DX enabled you deploy these individual projects and can version them. You can have dependency management with these different projects. So setting up your directory structure correctly is a pre-requisite to efficient using Salesforce DX.

![](https://cdn-images-1.medium.com/max/2000/1*g-xoc736oWpbOvM3fcDjUw.png)

11.@10.00 — You can go back with Salesforce DX. You are not stuck. If you make some revisions but things aren’t working out, you can deploy everything into your Org, delete your repo and start all over again. You can back to square one whenever you like.

![](https://cdn-images-1.medium.com/max/2000/1*If1DuzGdbiFWo91QulJgbQ.png)

12.@10.50 — With Salesforce DX, you can make use of the whole world of tools. You can integrate any tool you like with the CLI.

![](https://cdn-images-1.medium.com/max/2000/1*_o1oposzT5ETY-du81HBdw.png)

13.@12.00 — There are tools in the partner ecosystem that complement Salesforce DX, such as [Auto Rabit](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N30000000ptkwEAA). Also, Visual Studio Code is an excellent tool for using Salesforce DX. This [summary](https://medium.com/salesforcesummaries/vs-code-ide-for-eclipse-users-65fe0b7b0a84) highlights Visual Studio Code and how it differs to Eclipse.

14.@14.00 — Everyone can have their own scratch org. This prevents situations where everyone is trying to develop in one place (particular developer or full copy sandboxes).

15.@17.00 — Salesforce DX isn’t just for developers although the road map for Salesforce DX is to make it an easier tool for admins via UI functionality.

![](https://cdn-images-1.medium.com/max/2000/1*_wg8uhSg7YgLTOxatjc5OQ.png)

16.@20.00 — Usually, [GitHub private repos are $7 per month](https://github.com/pricing). However, in conjunction with the Salesforce DX release, GitHub are offering unlimited private repos for 5 users for 6 months. The link is [here](https://developer.salesforce.com/github).

![](https://cdn-images-1.medium.com/max/2000/1*5fO59edGR-a44obdGu9vQA.png)
