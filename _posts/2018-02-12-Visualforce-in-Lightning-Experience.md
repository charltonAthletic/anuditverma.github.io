---
layout: post
title: Visualforce in Lightning Experience
tags: [Lightning Experience, Lightning Out, Visualforce]
---

## Visualforce in Lightning Experience

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

![](https://cdn-images-1.medium.com/max/2000/1*4KIip5mTRqwBHKnOYmBMKg.png)

Visualforce and Lightning can be used to compliment each other to deliver compelling pages. This has become easier than ever with the introduction of the lightningStylesheets attribute in Visualforce, that upgrades the styling of a page to look like Lightning. [In the past](https://medium.com/salesforcesummaries/migrating-visualforce-pages-to-lightning-a-salesforce-summary-9ef6375baf29), it was more challenging and time intensive to upgrade a Visualforce page to Lightning however, the introduction of the lightningStylesheets attribute makes it easier than ever to upgrade a Visualforce page to have the Lightning feel and design.

Furthermore, by using Lightning Out, you can leverage standard and custom Lightning components in Visualforce pages to deliver an even more compelling user experience.

The slides and code for this presentation can be found [here](https://github.com/mpsenn/dreamforce2017).

**Details**: ‘[Visualforce in Lightning Experience](https://www.youtube.com/watch?v=766OBLmf3oE)’

**Presenter**: Mike Senn

**Time**: 30 minutes

**Key Terms**: Visualforce, Lightning, Lightning Out, native UX

 1.@0.20 — There are three topics in this discussion.

The first topic is to show that there are a variety of ways to use Visualforce in Lightning Experience (LEX). These are either in Lighting tabs, page layouts, custom actions and standard actions.

The second topic is to demo a new Visualforce tag that will style a Visualforce page just like a Lightning page very quickly and easily. In contrast, as per this [video](https://www.youtube.com/watch?v=6uQPV7Xf9PI) that was summarized [here](https://medium.com/salesforcesummaries/migrating-visualforce-pages-to-lightning-a-salesforce-summary-9ef6375baf29), in the past, it was quite a lengthy process to migrate a Visualforce page to have Lightning styling. So by simply leveraging the [lightingStyleSheets tag](https://releasenotes.docs.salesforce.com/en-us/winter18/release-notes/rn_vf_lightningstylesheets.htm) in your Visualforce pages is a huge efficiency win.

The third topic is about how you can bring Lightning into Visualforce via [Lightning Out](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/components_visualforce.htm).

![](https://cdn-images-1.medium.com/max/2000/1*IM2WJr0S0J991qO0MqRn_g.png)

2.@0.50 — There are many different ways in which Visualforce works in Lightning.

![](https://cdn-images-1.medium.com/max/2000/1*SoU2ApKozhlwwRD78_oF_w.png)

3.@1.40 — This Lighting tab shows a Visualforce page. The orange dotted border represents a Visualforce page. And so a Visualforce page can be displayed in Lightning Experience (LEX) on a tab.

![](https://cdn-images-1.medium.com/max/2000/1*ceAyeikNHr7KMEjcANyFkw.png)

4.@2.05 — Upon clicking on the frog icon, the user will be navigated to the Lightning record page for the campaign.

![](https://cdn-images-1.medium.com/max/2000/1*sc8EYQYfjT9s2Jb8QpxI9w.png)

So you can see here that Visualforce is being used in a standard Lightning page layout and as a small part of the page layout, as the rest of the page is a Lightning component.

5.@2.35 — Another way to display Visualforce inside LEX is as the target of a [quick action](https://trailhead.salesforce.com/en/modules/lex_migration_customization/units/lex_migration_customization_actions).

![](https://cdn-images-1.medium.com/max/2000/1*0MzN5qWoPrPjZpJsTrIm5w.png)

Upon clicking this button, a Visualforce page will be navigated to. Again, everything within the orange border is a Visualforce page and so we can see that the Visualforce page is taking up most of this Lightning page.

![](https://cdn-images-1.medium.com/max/2000/1*fZxsODrfcG791OUu6PMqWw.png)

The Visualforce page has a related list with multiple columns and then 3 different columns below which contain different information and one Visualforce chart. To accomplish something like this isn’t possible with the standard Lightning page layout.

6.@3.45 — You can also override a standard action in LEX with a Visualforce page.

7.@4.40 — You can also use a Visualforce component on a Lightning page via the Lightning app builder.

![](https://cdn-images-1.medium.com/max/2000/1*zEqkW5jgt1szb02NMjAaAg.png)

8.@5.20 — With the lightningStyleSheets tag, it’s possible to quickly and easily upgrade the look and feel of a Visualforce page to look like a Lightning page.

![](https://cdn-images-1.medium.com/max/2000/1*Yfy0S6GCHqSO-L6QMUCilA.png)

9.@6.15 — To upgrade a Visualforce page to match the style of a Lightning page, simply add the relevant tag (lightningStylesheets=”true”).

![](https://cdn-images-1.medium.com/max/2000/1*RZYfu4CcTyjG1jfQ4swFrA.png)

![](https://cdn-images-1.medium.com/max/2000/1*DloqxaAu3bs-qcaSMzU45g.png)

10.@6.30 — Having made this change, the page looks vastly different now:

![](https://cdn-images-1.medium.com/max/2000/1*Xk2g1IZ1lR3xz-Cx5EMa7w.png)

![](https://cdn-images-1.medium.com/max/2000/1*30xKGFhx4eV46eBQR3xV2g.png)

11.@7.50 — For users who don’t have the Lightning Experience user permission, they would still see such a page as it would look like in Classic.

12.@10.00 — By leveraging the lightningStylesheets tag, you’ll notice that the font size will tend be larger and at certain browser widths, the text may run into each other. And so you shouldn’t just turn this tag on for every page and expect it to work seamlessly without doing any testing.

![](https://cdn-images-1.medium.com/max/2000/1*y53DCqgorwRrM1vb9bOuzg.png)

However, by leveraging this tag, the Visualforce page will follow the SLDS design.

13.@12.25 — Some notes on leveraging the tag are:

![](https://cdn-images-1.medium.com/max/2000/1*vTaQlRY7LZMoxNZsluG-Yw.png)

14.@13.45 — You can use conditional styling in your Visualforce pages to render specific styling.

![](https://cdn-images-1.medium.com/max/2000/1*zT-_IZrQMVpzxA_YqSNQmA.png)

15.@15.15 — It’s important to note some subtle differences when developing Visualforce pages for a Lightning Experience. If you’re creating a Visualforce page for Lightning, you’ll have to create a Visualforce tab first.

![](https://cdn-images-1.medium.com/max/2000/1*rOYyDXQ6MxAD9_ytkqe77w.png)

16.@16.20 — You can use Lightning Out to bring standard and custom Lightning components into Visualforce. This way, you can have a Visualforce page that looks a lot more like Lightning. By using the aforementioned lightningStylesheets tag, you can get 70% of the way there (in terms of migrating a VF page to a Lightning style) but you can get the other 30% of the way there via Lightning Out.

![](https://cdn-images-1.medium.com/max/2000/1*k-CO28i8uEiCK1gCkp1fiA.png)

17.@17.15 — There are 3 steps to using [Lightning Out](https://developer.salesforce.com/blogs/developer-relations/2016/02/lightning-components-visualforce-lightning.html). You first have to create a Lightning dependency application, then load the dependency app in the Visualforce page and finally create the Lightning components for your page. In this example, the [force:recordView component](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/aura_compref_force_recordView.htm) will be displayed in a Visualforce page. This particular component represents a read-only view of a record. In the above screenshot, the force:recordView component is the component that says ‘Charles Bleakley’.

18.@17.35 — This is the Lightning dependency application; which defines all of the Lightning components that will be defined in the Visualforce page. In the below example, only one standard Lightning component is defined however, you can have multiple standard and even custom Lightning components defined.

![](https://cdn-images-1.medium.com/max/2000/1*D6HUWXpvnmJkqutmt5PoXQ.png)

19.@17.50 — The above screenshot shows a Lightning aura application that extends the Lightning out application: — *extends=”ltng:outApp”*. This tells the Lightning app that this is a Lightning out app that will use the standard force:recordView component.

20.@18.50 — For the second step — loading the dependency app in the Visualforce page — this is achieved by loading the Lightning app library into the Visualforce page via the <apex:includeLightning/> component.

![](https://cdn-images-1.medium.com/max/2000/1*Yt9LK7P5_N-Fq8GAh3kEcQ.png)

21.@19.20 — Then an empty div with an Id is defined as per line 11 of the code. It’s important to give this empty div an Id as this is where the standard component, as defined in the Lightning Out application, will be displayed.

![](https://cdn-images-1.medium.com/max/2000/1*LzAjk9KKXDaysaUnzu0OYA.png)

22.@19.35 — As per line 14 of the code, there is some JavaScript used to load the standard Lightning component and display it on the page. The $Lightning.use() method in JavaScript is used to refer to an Lightning Application which extends ltng:outApp.

In the code above, the first parameter passed is the reference to the Lightning app and the second parameter is a callback function, which will be called whenever the dependency app has been loaded.

23.@20.00 — The callback function defines any attributes that the Lightning component must have during initialization.

The standard Lightning component force:recordView must have 2 attributes: the recordId and type. The recordId is the id of the record to load and the type attribute is the type of layout to use to display the record. Possible values are FULL or MINI. The default is MINI.

![](https://cdn-images-1.medium.com/max/2000/1*eT1JRIfvke3eKz9vc5l50w.png)

24.@21.05 — Finally, the $Lightning.createComponent is called to create the Lightning component. An empty callback is also passed. You could pass in a callback to deal with event handlers to the Lightning component etc. But that isn’t required in this example because the force:recordView component is a read-only component.

![](https://cdn-images-1.medium.com/max/2000/1*7IiZ1RsPHXOfRYoTvHJkjA.png)

25.@21.40 — And now, upon refreshing the Visualforce page, we can see the force:recordView component displayed. This is how you can combine standard and custom Lightning components into a Visualforce page with the lightningStylesheets.

![](https://cdn-images-1.medium.com/max/2000/1*kQ2YjDoqOF1C65FaocFYag.png)

26.@22.40 — By turning on lightningStylesheets in the Visualforce page, the impact is that the page has been re-designed and looks more native to Lightning.

![](https://cdn-images-1.medium.com/max/2000/1*lb-jbwXx6qA7j5xQGseHjw.png)

27.@23.00 — A summary of the steps that were taken are:

![](https://cdn-images-1.medium.com/max/2000/1*GxEkhl7swzT842vmvsniVQ.png)

![](https://cdn-images-1.medium.com/max/2000/1*uojFvrkfCkvfX_J8fw-PDw.png)

![](https://cdn-images-1.medium.com/max/2000/1*Zh_HRULpMGrisXXHChJuPg.png)

28.@28.00 — Remember to use [LockerService](https://medium.com/salesforcesummaries/introduction-to-lightning-lockerservice-fcaf90fe96ae) on your Lightning components for extra security.
