---
layout: post
title: Migrating Visualforce Pages to Lightning
tags: [Lightning Experience, Salesforce Lightning Design System, Visualforce]
image:  https://cdn-images-1.medium.com/max/720/1*Opr2VkjACltzilCv11wy_Q.png
share-img:  https://cdn-images-1.medium.com/max/720/1*Opr2VkjACltzilCv11wy_Q.png
---
# Migrating Visualforce Pages to Lightning — A ‘Salesforce Summary’

_SalesforceSummaries is a publication that delivers the  __**key**__  insights from Salesforce YouTube videos. We aim to be the _ [_getAbstract.com_](https://www.getabstract.com/en/)_ of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem._

**Introduction:**

![](https://cdn-images-1.medium.com/max/720/1*Opr2VkjACltzilCv11wy_Q.png)

With the release of [Salesforce Lightning back in Winter &#39;16](https://www.salesforce.com/blog/2015/08/future-of-crm-salesforce-lightning.html), it has become increasingly important to be aware of the latest pros and cons of adopting either Lightning (Salesforce Lightning) or continuing to use Visualforce (Salesforce Classic).

This article summarises the excellent &#39; [Migrating to Visualforce Pages to Lightning](https://www.youtube.com/watch?v=6uQPV7Xf9PI)&#39; video by Salesforce Principal Developer Evangelist, [Greg Rewis](https://www.linkedin.com/in/gregrewis); which goes into detail on how one can migrate from Salesforce Classic to Lightning, how one can leverage Visualforce within Lightning and also how one can leverage Lightning within Salesforce Classic.

**Details:**

Video: &#39; [Migrating to Visualforce Pages to Lightning](https://www.youtube.com/watch?v=6uQPV7Xf9PI)&#39;

Presenter: [Greg Rewis](https://www.linkedin.com/in/gregrewis)

Date: June 1st 2017

Time: 54 minutes

Key terms: Visualforce, Lightning Experience, Salesforce Lightning Design System

Key points:

1) Although Visualforce is still supported, Salesforce are focusing and will continue to focus primarily on Salesforce Lightning because this is new technology, it is more secure (less risk of JavaScript injection attacks) and it has a more contemporary and engaging UI and UX.

2) A Salesforce Developer has a lot of freedom to migrate most Visualforce pages and components to Lightning Experience by adopting conditional logic and the Salesforce Lightning Design System.

**Summary:**

1) @1.40 — Visualforce will still be supported for the long term.

2) @1.50 — However, Lightning is the technology of today and the future at Salesforce.

3) @2.00 — All the new features and functionality and great ideas that Salesforce are coming up with are going in Lightning.

4) @4.10 — Some functionality simply doesn&#39;t work when migrating from Visualforce to Salesforce Lightning.

5) @4.20 — For example, JavaScript buttons won&#39;t work in Lightning due to the security challenges with combing untrusted JavaScript from multiple sources with the application source code.

6) @4.35 — Refer to the &#39; [Lightning Alternatives to JavaScript buttons](https://trailhead.salesforce.com/en/modules/lex_javascript_button_migration)&#39; trailhead badge to assist you with understanding what functionality you will have to replace before migrating to Lightning.

7) @6.25 — Despite JavaScript buttons and custom URLs not being permitted the same in Lightning as in Visualforce, for the most part, using Visualforce in Lightning Experience mostly &#39;just works&#39;.

8) @6.50 — For example, you can use Visualforce pages in Lightning Experience to override a standard button or link.

9) @7.25 — You can also use Visualforce tabs in Lightning Experience, Visualforce pages embedded in a page layout, use Visualforce in global actions and even Visualforce components in the Lightning App builder.

10) @7.55 — You can use Lightning Components inside of Visualforce too, using [Lightning Out](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/lightning_out.htm).

11) @8.15– Lightning Out allows you to use a Lightning Component inside any external web application outside a Salesforce org.

12) @8.50 — The [Dreamhouse app](https://developer.salesforce.com/dreamhouse/) has been built by the Salesforce team to show all the things one can do with Salesforce Lightning.

13) @12.20 — It&#39;s a process to migrate all Visualforce pages to Lightning Experience. It&#39;s OK to migrate page by page.

14) @14.00 — The HTML influences the structure of a page (model). CSS influences the styling of a page (view).

15) @16.00 — Lightning has its own look and feel. A Lightning table and a Visualforce table with the same HTML, as per the demo, look completely different because of the styles that are applied to the page.

16) @16.45 — You can use the [Salesforce Lightning Design System (SLDS)](https://www.lightningdesignsystem.com/)to apply the Lightning style to pages.

17) @18.00 — Prior to Spring &#39;17, to migrate a Visualforce page to a Lightning page, you would have had to have generated a custom version of the Salesforce Lightning Design System (SLDS), download it and then re-upload it as a static resource in Salesforce.

18) @20.20 — However, since Spring &#39;17 release, you can simply use the **&lt;apex:slds&gt;** tag in your Visualforce page followed by a **&lt;div class=&quot;slds-scope&quot;&gt;** , which is best practice because this is dynamic (if the SLDS design changes, the changes will automatically be made in your Visualforce page).

19) @25.00 — To change the style of a button in a Visualforce page to match the Lightning Experience, you can use the SLDS site, navigate to &#39; [Buttons&#39;](https://www.lightningdesignsystem.com/components/buttons/) and refer to the &#39;Developer Guidelines&#39; section for a particular type of button. You can copy and paste that attribute into the **&lt;apex:commandButton&gt;** tag such that the Visualforce markup is now: **&lt;apex:commandButton value=&quot;New&quot; styleClass=&quot;slds-button slds-button — neutral&quot;/&gt;.**

20) @28.30 — CSS stands for cascading style sheets but for Lightning Experience, you could say that the &#39;C&#39; stands for &#39;collision&#39;. This is because some styles can come from Lightning but some other styles can from Classic, and can merge on the page. We don&#39;t want this to happen.

21) @29.55 –To control this, you can add code to an Apex controller which returns a Boolean determining if the current logged in user viewing a page is using Classic or Lightning.

22) @31.40 — You can reference the Apex method from the controller in an **outputPanel** tag like this: **&lt;apex:outputPanel rendered=&quot;{!isClassic}&quot;&gt;** to display either a Classic or Lightning experience to different users.

23) @40.40 — For a Visualforce page to be available in Lightning Experience, select the &#39;Available for Salesforce mobile apps and Lightning Pages&#39; checkbox.

24) @46.00 — Not only can we use Visualforce in Lightning Experience, we can also use Lightning in Salesforce Classic. This can be done using the **&lt;apex:includeLightning /&gt;** tag in a Visualforce page.

25) @51.00 — You can use conditional logic in a Visualforce page to handle events correctly depending on whether the logged in user is using Classic (theme3) or Lightning (theme4).

26) @52.00 — You can earn the &#39; [Quick Start: Lightning Components](https://trailhead.salesforce.com/en/projects/quickstart-lightning-components)&#39; badge to learn much about how migrating from Classic to Lightning.

27) @53.30 — This [TrailheadDX link](https://developer.salesforce.com/trailheadx/sessions) has some great content on Lightning Experience too.
