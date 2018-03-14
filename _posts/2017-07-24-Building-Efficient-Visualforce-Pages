
---
layout: post
title: Building Efficient Visualforce Pages
tags: [API, Salesforce, Visualforce]
image:  https://cdn-images-1.medium.com/max/720/1*0G2Bizt3Nija457FBhYdgQ.png
share-img:  https://cdn-images-1.medium.com/max/720/1*0G2Bizt3Nija457FBhYdgQ.png
---

# Building Efficient Visualforce Pages — A ‘Salesforce Summary’

*SalesforceSummaries is a publication that delivers the ***key*** insights from
Salesforce YouTube videos. We aim to be the
*[getAbstract.com](https://www.getabstract.com/en/)* of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

**Introduction:**

As per the ‘[Migrating from Visualforce pages to
Lightning](https://medium.com/salesforcesummaries/migrating-visualforce-pages-to-lightning-a-salesforce-summary-9ef6375baf29)’
summary, although Lightning Experience is the future, a significant amount of
customers are still on Salesforce Classic and will continue to use Visualforce
pages for providing a more customised UI experience to users. Therefore,
understanding about how Salesforce developers can deliver efficient Visualforce
pages remains a very important topic.

This article summarises the very comprehensive ‘[Building Efficient Visualforce
Pages](https://www.youtube.com/watch?v=D2dAk99Yxvs&t=2393s)’ tutorial from the
[Dreamforce YouTube](https://www.youtube.com/channel/UCMSfoJzq24tEKNfdB4GaIqg)
channel. You will learn how to best improve the speed of Visualforce pages by
reducing the [view
state](https://developer.salesforce.com/page/An_Introduction_to_Visualforce_View_State)
as much as possible.

![](https://cdn-images-1.medium.com/max/720/1*0G2Bizt3Nija457FBhYdgQ.png)

**Details:**

Video: ‘[Building Efficient Visualforce
Pages](https://www.youtube.com/watch?v=D2dAk99Yxvs&t=2393s)’

Presenter: [Steve Bobrowski](https://www.linkedin.com/in/stevebobrowski/),
[Markus Spohn](https://www.linkedin.com/in/mspohn/)

Date: November 25th 2013

Time: 45 minutes

Key terms: Visualforce, View State, Force.com Query Optimiser

Key points:

1) To design memory efficient Visualforce pages, one needs to build database
efficient Visualforce pages, design efficient controller logic and make
efficient design choices.

2) More efficient Visualforce pages mean happy customers, as a faster user
experience is delivered.

3) The Streaming API can be leveraged to update Visualforce pages in real-time
in a very efficient manner, compared to traditional polling via the actionPoller
tag which is less efficient.

**Summary:**

1.  @3: The 2 most common things which impede Visualforce page performance is high
memory on the page and how the page accesses the database
1.  @6: The view state is something that Visualforce automatically maintains as soon
as you use an
[<apex:form>](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_compref_form.htm)
component on the page. The <apex:form> tag is used when requesting input from
the user.
1.  @6.20: The max view state of a Visualforce page is 135kb. If your page exceed
this limit, the user will receive a ‘*maximum view state size limit (135KB)
exceeded*’ error on the page.
1.  @6.25: The view state is very helpful because the inputs are saved on the page.
Let’s say there’s a validation rule on the sObject that is referenced in the
controller and the user inputs data into the <apex:form> fields and selects the
[commandButton](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_compref_commandButton.htm),
the server would come back with any errors and post these back to the browser
(client).
1.  @6.30: The Visualforce page uses the view state to rebuild the page so that no
input data is lost. This way, the user doesn’t lose any data that have been
populated in the
[<apex:inputFields>](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_compref_inputField.htm).

6. @6.50: The Visualforce page view state is encrypted and travels back and
forth between client and server. Therefore, the lower the view state, the better
as it results in a faster response time. This is especially true for mobile
customers.

7. @7.15: To view the view state on a page, enable ‘[Development
Mode](https://help.salesforce.com/articleView?id=pages_dev_mode.htm&type=0)’ on
the user record and select the ‘View State in Development Mode’.

8. @7.20: In the Development footer, you’ll see a third tab that shows the view
state inspector. The view state enables you to see which component on the page
is contributing to the view state size.

9.@9.45: Minimize data, so as to ensure that your SOQL queries only have the
fields that you absolutely need for the Visualforce page.

10. @10.30: Analyze your controllers and ensure that you’re only querying the
fields that your page requires. In the demo, this reduced the view state from
27kb to 4kb.

11. @10.50: Use WHERE clauses to reduce the data set to reduce the view state
further.

12. @13.30: You can tell Visualforce to not maintain view state for data which
should only be visible and not editable (so to all intents and purposes it is
read-only data on the page). This can be achieved by using the [transient
](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/apex_classes_keywords_transient.htm)key
word in front of your collection or sObject variables.

13. @14.30: Traditional polling, which typically leverages the [actionPoller
Visualforce
tag](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_compref_actionPoller.htm),
will always require view state as it requires an <apex:form> tag. However, is
there a more benefical approach which we can adopt which doesn’t maintain a view
state at all?

14. @15: One can use the Streaming API in your Visualforce pages, which will
enable you to push a notification to the browser (client) whenever a change has
happened in the database. This notification is stored in JavaScript in the page,
and this will refresh the browser.

15. @15.40: Minimise your data (force the field list in SOQL queries, use WHERE
clauses), use the transient keyword for read-only variables and consider
alternative page designs which don’t use <apex:forms>.

16. @16.20: Visualforce pages are built for data-driven applications and so we
want to ensure the database is not in a bottle neck. So it is critical to build
database efficient Visualforce pages.

17. @16.50: The key things to make database efficient Visualforce controllers is
efficient SOQL and logic.

18. @17.40: The [force.com query
optimiser](https://help.salesforce.com/articleView?id=000181277&r=https://www.google.co.uk/&type=1)
won’t use an available index on a field if you use non optimisable operators.
Negative operators go after a much larger dataset and so indexes won’t be used.
Refer to developer.force.com/architect where these concepts are published.

19. @19.40: The easiest way to optimise a SOQL would be to ‘flip’ it from NOT
Closed to Open — meaning if there’s an index on this field, then it will be used
in the query.

20. @19.50: There are three steps to build a selective WHERE query: a)
Optimisable operator b) The set of values you’re searching for are selected in
the record set c) Ensure you have an index in place.

21. @20.00: You will to work with the support team to add a custom index. There
are standard fields already in the Salesforce schema, but if you’re using a
custom field, you will need to create one yourself.

22. @21.30: There are selectivity thresholds to consider when querying large
datasets.

23. @22.00: The sharing architecture is used by the query optimiser.

24. @22.15: Public **with sharing **(‘sharing’ key word) can help to optimise
the query further. For example, if you have a private sharing model, using the
‘with sharing’ keyword in your controller would reduce the data set for the
Visualforce page further. So, you can take advantage of the sharing architecture
for objects which have a private OWD.

25. @23.30: To recap, execute efficient SOQL queries by using optimisable
operators, filtering on selective field values, leverage indexed fields and
leverage the sharing architecture when possible.

26. @23.40: Use [standard set
controllers](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/apex_pages_standardsetcontroller.htm)
in your logic when possible as these are optimised for large data sets, they
play nicely with list views and they provide robust paging capabilities.

27. @23.50: A standard set controller enables ‘query more’; which works best
with pagination as it queries once and keeps the curser in a cache. And when the
next page is requested, instead of requerying, the next set of records is taken
by incrementing the curser in the cache.

28. @25.00: In your logic, ensure that you place DML and SOQL outside of loops.
Make sure you use bulk processing principals when you can when creating custom
controllers.

29. @27.00: Long polling is a much more modern version of traditional polling.
Whenver an update is received on the database, a push is sent to the page (so
this is very impactful and efficient).

30. @28.00: By using long polling via the Streaming API, you can update a page
in real-time without the need of the <apex:form> tag (providing that user input
isn’t required). Therefore, this reduces the view state and offers a very
efficient page. This
[developer.salesforce](https://developer.salesforce.com/page/Alert!_Salesforce_Event_Notification_Designs_for_Force.com_Apps)
article covers this extensively.

31. @35.15: How can one scan a Salesforce environment and determine where a
Visualforce’s page could be made more efficient? This can be achieved with the
help of the [MavensMate IDE](http://mavensmate.com/).
