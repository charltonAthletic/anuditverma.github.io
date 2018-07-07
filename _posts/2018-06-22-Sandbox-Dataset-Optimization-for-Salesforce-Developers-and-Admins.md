# Sandbox Dataset Optimization for Salesforce Developers and Admins

*SalesforceSummaries.com is a publication that delivers the ***key*** insights
from Salesforce YouTube videos. We aim to be the
*[getAbstract.com](https://www.getabstract.com/en/)* of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

**Introduction:**

In this presentation, you will learn more about the challenges when it comes to
managing sandboxes and how the
[OwnBackup](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N30000007p6RYEAY)
solution from the Salesforce AppExchange can help.

**Details: ‘**[Sandbox Dataset Optimization for Salesforce Developers and
Admins](https://www.youtube.com/watch?v=KXmTjfg2W9o)’

**Presenter: **Mat Kennedy

**Details: **15 minutes

**Key Terms:** Sandboxes, Development and deployment process

![](https://cdn-images-1.medium.com/max/800/1*YoM7MO1vV2-V41nLN9Ll9g.png)

1.  @0.35 — Sandboxes are critical for developers and admins as you should test
changes first. Full copy sandboxes can be expensive, and so at least, it’s good
to leverage developer sandboxes.
1.  @1.15 — OwnBackup app is one of the top rated backup providers on the Salesforce
AppExchange.
1.  @2.00 — There are a number of challenges when it comes to managing sandboxes.
52% of top companies release Salesforce changes at least once per month. To do
these changes properly, you want to leverage sandboxes and run tests before the
changes go into Production.
1.  @2.45–43% of app developers spend almost 25% of their time debugging production
app errors. This is hugely costly and detrimental.

![](https://cdn-images-1.medium.com/max/800/1*yJ9qlKLmkwBdT88TSLMS-A.png)

5. @3.30 — The three main benefits that leveraging sandboxes bring are that they
enable you to build new features safely, enable you to test fully and also
offers you a safe environment to do comprehensive testing.

![](https://cdn-images-1.medium.com/max/800/1*QgEdZ-5gJ_YLiZdlT_GcIw.png)

6. @4.20 — There are 5 main challenges when it comes to seeding a sandbox.

![](https://cdn-images-1.medium.com/max/800/1*YOz4L1cRziyAJBJnZGhyfg.png)

7. @4.40 — The first challenge is that it is very expensive to maintain partial
or full copy sandboxes, and so it is imperative to get the most business value
out of sandboxes. And so how can you ensure that you are getting the most value
out of your sandboxes?

8. @5.00 — The second challenge is that it is hard to test properly with
incomplete data. So moving relevant data sub-sets to the relevant sandboxes can
be time consuming. One of the reasons why this is so time consuming is that if
you need a particular sub-set of data, you cannot specify this as an option when
refreshing from production (for example, show me all accounts where the owner is
based in San Francisco).

9. @7.30 — Another challenge is how you can mask confidential data, so that you
have pure test data for an external developer/admin.

10. @8:00 — Another challenge is that it can take a significant amount of time
for your sandboxes to refresh once you initiate them to be refreshed. Also, once
you move data from Production to sandbox, you don’t want that data to fire off
triggers and workflows etc.

11. @9.15 — Another challenge is that cross-org comparisons are complex and time
consuming. [Although one can do a meta-data comparison with
Eclipse](https://salesforce.stackexchange.com/questions/63067/metadata-compare-is-there-an-easier-way-than-selecting-all-components-in-eclips),
this is simplified greatly with OwnBackup. If a developer pushes a change set to
a another sandbox, that could detrimentally impact that environment if the
meta-data between the two sandboxes is not consistent.

12. @10.20 — With OwnBackup, a much improved Sandbox seeding functionality is
offered; which can save significant amounts of money in the mid-near term due to
increased developer productivity.

13. @13.00 — Everything that OwnBackup do is through the Salesforce API and
because scratch orgs aren’t available through this, the tool doesn’t support
scratch orgs yet.
