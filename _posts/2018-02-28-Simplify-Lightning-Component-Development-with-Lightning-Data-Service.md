---
layout: post
title: Simplify Lightning Component Development with Lightning Data Service
tags: [Lightning Components, Lightning Data Service, Lightning Experience]
---

# Simplify Lightning Component Development with Lightning Data Service

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Lightning is a new development paradigm for Salesforce that depends heavily on
JavaScript. Since its release, the benefits of adopting Lightning and building
bespoke, mobile friendly Lightning components have been made clear. However, one
downside was that a lot of duplicitous JavaScript and Apex code was required for
fairly simple Lightning components because there was no Lightning equivalent of
the
[standardController](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/apex_pages_standardcontroller.htm).

However, [Lighting Data
Service](https://trailhead.salesforce.com/en/modules/lightning_data_service)
solves that problem as it is in effect, the Lighting version of the standard
controller. There is no need to write Apex, SOQL statements or JavaScript
methods to update records now.

**Details**: ‘[Simplify Lightning Component Development with Lightning Data
Service](https://www.youtube.com/watch?v=nHYnt0t0_NI)’

![](https://cdn-images-1.medium.com/max/720/1*4AbAQ8cjBI1r6LAhqqcVHw.png)

**Presenter**: Marcus Torres and Carolyn Grabhill

**Details**: 33 minutes

**Key Terms**: Lightning Data Service, force:recordData

1. @1.50 — There are many considerations for custom Lightning components. And there
are many considerations that are related to data, such as SOQL, field level
security and record updates etc. However, you don’t need to consider those when
using the Lightning Data Service.

2.@3.05 — Every single component keeps a copy of its own record data. The
components essentially ask the Salesforce server via the client side controller
for some data, which is actioned by SOQL in the server side controller. So there
are many steps involved to get the data.

3.@4.20 — The Lightning Data Service is effectively the standard controller for
Lightning.

So instead of n number of Lightning components all keeping their own copy of the
data, they all essentially have a pointer to a shared instance, so it’s
effectively a shared cache.

4.@5.25 — Because it’s a pointer, auto-notifications on record changes are
possible. Also, offline access for Salesforce1 is possible with the Lightning
Data Service (LDS). In fact, offline access for Salesforce1 is powered by LDS.

5.@6.00 — The data flow looks like this, with LDS:

Your Lightning components will use <force:recorddata> to leverage LDS. LDS
connects back and forth with Salesforce.

6.@6.40 — The status of
[LDS](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/data_service.htm)
as of the time of the presentation (July, 2017) was:

7.@7.30 — <force:recorddata> is the flagship component of LDS.

8.@7.50 — You will need to give the recorddata component an aura id, so that it
can be referenced in JavaScript.

You will also need to pass in the recordId, and the fields that you want to
load. This approach is fine but if you like, you can pass in a
[layoutType](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/data_service_load_record.htm)
instead of passing in hard-coded field values. layoutType = FULL] is all the
fields defined on the page layout editor and compact is all the fields in the
highlights panel at the top of pages in LEX (Lightning Experience). Or you can
pass in both, and you would get the super set.

targetFields should be used if you want just the field API names whereas
targetRecord is a JSON response with API names, field values, record type Ids
etc. If you are using a lot of JavaScript logic, then you’ll want to use
targetRecord.

targetError is where any error response will be loaded, which can then be
referenced in your Lightning page.

Lastly, you need to give a mode. This will be ‘VIEW’ or ‘EDIT’. This controls
whether LDS can automatically re-render data for you.

9.@11.25 — In the demo coming up now, there are three different Lightning
components which leverage LDS to show you the power of this functionality. None
of them use Apex controllers.

10.@11.50 — In this component, the Account Temperature icon is being pulled
from the ‘Rating’ field on the record. This using LDS and has no Apex or
JavaScript controller or JavaScript handlers.

11.@12.05 — If the ‘Rating’ changes from ‘Hot’ to ‘Cold’, then the icon updates
automatically:

12.@12.30 — This component references the force:hasRecordId interface:

This interface will give the component the record Id attribute of the record
being viewed. That record Id attribute can be passed to the <force:recorddata>
component. This way, no SOQL is required to get the Id of the record being
viewed.

Since the mode of this component is ‘VIEW’, if any change to the record is mine
whilst we are viewing it, then LDS will auto-render it again.

13.@13.55 — Dynamic styling is being automatically applied to show different
icons depending on the value of the ‘Rating’ field. Line 19 says ‘if the record
rating is ‘Hot’, then use the ‘icon-hot’ CSS styling else if the record rating
is ‘Warm’, then use the ‘icon-warm’ CSS class. No additional JavaScript is
required for this — it’s all Lightning expressions.

14.@15.00 — The use case in this example is that a custom object has been built
which contains some fields of different data types. The salesperson is on the
phone to the potential customer and is negotiating on the price and the
discount. If the salesperson inputs some data into the ‘Discount Scratchpad’
component, then the commission that the salesperson would receive is displayed
automatically with no re-rendering of the page (because the calculation is
completed on the client).

15.@16.00 — In the below screenshot, you can see that the ‘Compute Discount’
button has been selected and so the commission value has been displayed ($1,400
commission from a $30,000 sale).

16.@16.10 — The code is below:

As per line 1, for all components that implement LDS, it implements
force:hasRecordId. This is used to get the recordId of the currently viewed
record (as per line 7) because you want to pre-populate the component with some
of those values. As per line 6, the aura:id has to be defined because this
component will need to be referenced in JavaScript this time because the record
will be saved and saving has to happen with JavaScript.

As per line 8, the layoutType is ‘FULL’ to get all the fields and the mode type
(line 9) is ‘EDIT’. Because the mode type is ‘EDIT’, if something changes on the
component, then this won’t result in automatic re-rendering of the component
that was the case in the previous component (the icon display cmp). However, you
may still want to take some action when data changes. This can be handled using
an event. As per line 10, when the record has been updated, run the
{!c.resetDiscountForm} function. This is a client side controller (as per the
‘c’). Lastly, as per line 11, once the record has been loaded, it’ll be pushed
into the targetFields attribute.

Official documentation on the force:recordData component can be found
[here](https://developer.salesforce.com/docs/atlas.en-us.lightning.meta/lightning/aura_compref_force_recordData.htm).

17.@27.40 — The roadmap is:

Bulk support will allow you to provide a list view Id and LDS will be able to
fetch all the data from that.
