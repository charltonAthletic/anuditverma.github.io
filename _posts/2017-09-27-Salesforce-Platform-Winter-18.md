---
layout: post
title: Salesforce Platform Winter 18 - Release Readiness Summary
tags: [Lightning App Builder, Lightning Experience, SFDX, Trailhead]
image: https://cdn-images-1.medium.com/max/2000/1*CRFFf5yRXs6In83Fu3glxw.png
share-img: https://cdn-images-1.medium.com/max/2000/1*CRFFf5yRXs6In83Fu3glxw.png 
---

*SalesforceSummaries is a publication that delivers the **key** insights from
Salesforce YouTube videos. We aim to be the
[getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

## Salesforce Platform Winter 18 — Release Readiness Summary

*SalesforceSummaries is a publication that delivers the **key **insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

As per the [Release Readiness webcast](https://www.salesforce.com/form/event/release-readiness-winter-18.jsp) on the Salesforce Platform Winter 18 release, there are some significant changes and improvements that have been made to the Lightning UI, Lightning App Builder and [Salesforce DX](https://trailhead.salesforce.com/en/trails/sfdx_get_started).

This serves as a brief summary on the most significant changes. Great resources for getting more comprehensive overviews of these changes can be found on the [Cloud Services Event Calendar](https://pages.mail.salesforce.com/cloud-services/event-calendar#&eventType=.webinar&search=winter '18) and the [Release Readiness & Feature Adoption](https://success.salesforce.com/_ui/core/chatter/groups/GroupProfilePage?g=0F9300000001okuCAA) pages.

 1. The Lightning UI has been improved in a number of different ways.

![](https://cdn-images-1.medium.com/max/2000/1*clIvMKOodR4zV1NynNHOkQ.png)

2. A big improvement has been made on List Views in Lightning Experience (LEX). Going forward, Admin users can also clone existing list views in LEX without having to revert back to Salesforce Classic. Mass inline editing can give a huge productivity boost to users and dynamically sized columns allow more efficient use of page real estate.

![](https://cdn-images-1.medium.com/max/2000/1*KvVrmY3yVcQ_sCQdpj0uKA.png)

![The mass inline editor can be used to update a set of records quickly all from a list view.](https://cdn-images-1.medium.com/max/2000/1*kPwmPj_I0Hq_0Z66UcM_JQ.png)

3. Related List Quick Links are also a new feature for LEX.

![](https://cdn-images-1.medium.com/max/2000/1*RcbfVdUzwM3dvmcG1GL3XQ.png)

4. There is a huge focus on customers being able to brand their Lightning pages.

![Going forward, you can define a theme to use in Lightning Experience.](https://cdn-images-1.medium.com/max/2000/1*os7pIpHiF4tbCqpjH1UzZg.png)

5. On the [Lightning App Builder](https://trailhead.salesforce.com/en/modules/lightning_app_builder) front, one can now create dynamic record pages, custom templates on home pages and have more flexibility around dashboard components on Lightning pages.

Custom templates give you a lot more branding flexibility. Custom templates are essentially Lightning components, so a developer resource would still be required for this; although for dynamic Lightning pages this can be done via point-n-click.

![](https://cdn-images-1.medium.com/max/2000/1*4wWThZgOFTLCA6I3ZCQXUg.png)

![Although dynamic pages will only work for record pages for Winter 18, the road-map is to make them available for any other type of page in later releases.](https://cdn-images-1.medium.com/max/2000/1*IHwNPYBG73ruFLSYrZhjZQ.png)

![](https://cdn-images-1.medium.com/max/2000/1*8u-MLVTcZ6KbrIzDT848dQ.png)

![You can create contemporary looking dashboard components on Lightning pages.](https://cdn-images-1.medium.com/max/2000/1*Q2Ub-GoKU9ZtD_pDtqMcqw.png)

6. [Salesforce DX](https://trailhead.salesforce.com/en/trails/sfdx_get_started) also has received a number of critical improvements. Salesforce DX is a new development mechanism:

![](https://cdn-images-1.medium.com/max/2000/1*ijaGKQOF_V6RyrYEvxveYg.png)

With Salesforce DX, one can have a truly continuous integration experience. One can compare 2 orgs (org A and org B) to see what the differences are between them, download the differences to your local machine and push those differences back to org B. This is a far improved approach instead of having to manually make changes in the UI for some features that can’t be referenced in change sets.

Trailhead is the best step to getting started with Salesforce DX. You can use Github to download the repo.

![](https://cdn-images-1.medium.com/max/2000/1*CRFFf5yRXs6In83Fu3glxw.png)

And in your command line, you’ll find a lot of available sfdx commands:

![One of the items on the road-map for Salesforce DX is to rely less on the command line functionality to increase adoption. This will help abstract away from the complexities of the tool.](https://cdn-images-1.medium.com/max/2000/1*7NG7A1cGCOzAfGwrEj5LrA.png)

There is now also a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode) which helps improve usability:

![](https://cdn-images-1.medium.com/max/2000/1*_pCWl1Acytncr2ax-lMN-A.png)
