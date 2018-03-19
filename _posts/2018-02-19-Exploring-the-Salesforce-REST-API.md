---
layout: post
title: Exploring the Salesforce REST API
tags: [Composite API, Batching REST Resource, Salesforce APIs, Salesforce REST API]
---

## Exploring the Salesforce REST API

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

The Salesforce REST API is the most common way to integrate with third party services. This presentation discusses the Salesforce REST API and the different approaches to create more efficient REST API requests; which are especially helpful for mobile users.

**Details**: ‘[Exploring the Salesforce REST API](https://www.youtube.com/watch?v=R6eVlc3Dwco)’

**Presenter**: Jay Hurst

**Time:** 48 minutes

**Key Terms:** Salesforce REST API, Composite API, Batching REST Resource

 1.@1.45 — Salesforce have done a lot of work to improve the Salesforce REST API to make it more efficient and less cumbersome to work with.

![](https://cdn-images-1.medium.com/max/2000/1*lxs4peS_mqX2BCGiKyMzAA.png)

2.@2.40 — The integration layer (on the right) is the API. The Salesforce system has been built to be API first. The integration layer is the programmatic entry point if you are coming into the Salesforce system from outside of Salesforce.

![](https://cdn-images-1.medium.com/max/2000/1*H3Ur0GEyqOQS4qzNEfpPpQ.png)

3.@5.30 — About 9 years ago, Salesforce came out with the Salesforce REST API (api version 22.0). The Salesforce SOAP API was created before the Salesforce REST API. What Salesforce wanted was to take the existing functionality of the SOAP API which is proven to work very well and expose REST endpoints of top of it. So anytime you call the Salesforce SOAP or REST API to create an Account record, for example, you’re actually calling the same API inside of the Salesforce Java layer. So Salesforce are building just one API layer but with two different entry points.

![](https://cdn-images-1.medium.com/max/2000/1*kDOCarAMMM_BAeAfQg3AeA.png)

4.@6.20 — The Salesforce REST API is synchronous but there are RESTful Salesforce APIs which process asynchronously (for example, the BULK API). The [Salesforce REST API](https://developer.salesforce.com/page/Creating_REST_APIs_using_Apex_REST) is best suited for browser or mobile apps which don’t need access to high amounts of records.

The Salesforce REST API supports both XML and JSON.

5.@11.40 — The anatomy of a REST API call is as per below:

![](https://cdn-images-1.medium.com/max/2000/1*aqoBXUi573Sr4yL3Y0gixw.png)

**/services/data** is the Salesforce REST API. If you’re using /services/async, then that is the BULK API and /services/SOAP is the SOAP API.

Every time Salesforce do a new release (3 a year), then the API version will increase incrementally. If new functionality comes out in a particular Salesforce release, then that is tied to that version, and not to previous versions. But all your existing code that is running on an older version will keep running (backwards compatible). Salesforce traditionally do not retire API versions. It’s recommended to keep your API versions up to later API versions (try not be less than 6 API versions old).

6.@11.50 — With the REST API, from a single request you get a single response.

![](https://cdn-images-1.medium.com/max/2000/1*DigS3b1DV2pq9klRdCcZxA.png)

In this diagram, the user is doing a CREATE, DESCRIBE and a LIMITS call. The user sends the CREATE request, which goes to the Salesforce REST endpoint, which then returns a response from the Salesforce database back to the client. The user can then make a DESCRIBE call and then a LIMITs call. This is the traditional pattern with REST — you have a resource, you make the call, you get a response and then you do something with that response.

Salesforce are asking ‘*how can we make this REST process more efficient?*’.

7.@12.35 — A composite API is an API that is built by combing existing API functions. So instead of having 3 distinct calls (as per the above diagram which showed the CREATE, DESCRIBE and LIMITS call), perhaps that can be boiled down to two or even one call, and have the server run the logic that goes behind those calls. So instead of incurring the cost of going from client to server multiple times, you can have just one round trip from the client to server but have the server can do multiple processing.

![](https://cdn-images-1.medium.com/max/2000/1*jPY_Oy_8OCrxexCXYs8auQ.png)

![](https://cdn-images-1.medium.com/max/2000/1*rDqWZmha6iNNTuECDQuK6Q.png)

If you wanted to create a contact, you would first need to have an account to be associated with that contact. And so you would need two calls: one to create the account, return the account.id, and then create the contact record against the account.id. This isn’t as efficient as it could be because ideally, a developer would use responses from one API method as inputs into another method. In this way, multiple APIs can be used in a single call to improve performance.

[Compositions](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/resources_composite.htm) are increasingly important for designing efficient API for use in mobile development. Calls which push less data = more efficient.

8.@14.15 — One of the composite resources available is the [batching REST resource](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/resources_composite_batch.htm). You can batch up to 25 request calls into a single JSON call which the Salesforce server processes serially. Salesforce will return a serialized response. This can reduce round trips. The request in a batch are called subrequests, and are all executed in the context of the same user. Subrequests are independent, and so you cannot pass information between them.

![](https://cdn-images-1.medium.com/max/2000/1*nvlKidypuR3dmLIPGeo4Vw.png)

9.@15.20 — With the [TreeSave](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/resources_composite_sobject_tree.htm) REST resource, you can insert multiple records in a single call. For example, create one account, and then 3 contacts against that account.

10.@15.40 — You have the ability to define whatever you want and expose it as a REST endpoint. So you can build a composite for example to build multiple things, but it will be easier to leverage the already existing Salesforce composite resources.

11.@16.20 — The Batch REST resource is not suitable if you want to do transactional manipulation because it’s not an ‘all or nothing’ approach. Instead, if a sub request fails, it will move onto the next sub request and all successful sub requests before that do not get reverted.

There is an optional parameter — haltOnError — which would prevent the other serial calls from being executed.

![](https://cdn-images-1.medium.com/max/2000/1*M2FxDAtEA1p_JQC4crVU8g.png)

12.@17.50 — In the below example, if one wanted to create 2 accounts, 3 contacts, 2 cases and 2 tasks via the REST API, this would take 9 different API calls. This is what that would look like:

![](https://cdn-images-1.medium.com/max/2000/1*WL76P20F9yA4HSR-rzUgnA.png)

However, using the batch REST API, one can bundle the requests into a single .json file (body) and then send that body to a single API call.

![](https://cdn-images-1.medium.com/max/2000/1*f6HK7BeIsLIHurXXHBoa-Q.png)

The Salesforce server will process each of the sub requests serially and then pass the results back into .json format.

13.@18.00 — This is what an example batch request looks like:

![](https://cdn-images-1.medium.com/max/2000/1*8IPaYutuw6QRSIidi139pA.png)

14.@19.00 — [Workbench](https://workbench.developerforce.com/) continues to be one of the most popular ways to explore the Salesforce REST API. If you navigate to the Rest Explorer in Workbench and make a GET request to /services/data/vXX.X (for example, v41.0) then you will return a list of all the API types that are available to you.

You will notice that different functionalities are only available in later API versions. For example, if you compare API version 41.0 (current, as of Spring ’18) against the earliest REST API version (22.0), you can see how the Salesforce REST offering has grown.

![](https://cdn-images-1.medium.com/max/2000/1*EASQ0hBDZlY5v_5pN8uBEQ.png)

You can click into one of the API types, and then you’ll see a sub-tree list of the different options to you. For example, if you click on the limits API type, you’ll be navigated to a page which looks like this. This page details all the limits to you.

![](https://cdn-images-1.medium.com/max/2000/1*YWDONuj5hD59v3Riplo8Ew.png)

15.@20.00 — To do a batch request, input /services/data/v37.0/**composite**/batch, select ‘POST’ and input a request body like so:

![](https://cdn-images-1.medium.com/max/2000/1*zXeyBK-qt2Z1lY9GubFG_A.png)

As per the request body, this is in JSON format and three independent calls are written. You’ll notice that you don’t need to bind to the same API version that the callout is coming from.

The first call is a POST (create) on the Account sObject. Two fields are being populated: Name and Industry. The second call is getting all the metadata from the Account sObject. The final call is a GET to the query resource and running a query for all accounts that are ordered by the createddate.

16.@22.10 — Upon executing this, the results are returned. You can select ‘Show Raw Response’, which returns the response in JSON, or you can use the sub-tree file structure instead.

![](https://cdn-images-1.medium.com/max/2000/1*YX6xBzKaKsZzdUWJvAheSw.png)

17.@22.50 — You can see for the response from the third call that it was a success (200 Http response) and you can see the list of accounts that were selected in the query. You’ll notice that ‘NewName’ account has been pulled into the response as it was created at the time the query was run (as the account was created in the first call and the query was in the third call).

![](https://cdn-images-1.medium.com/max/2000/1*BiAVqPCTrR7Xp-sC-wvXzg.png)

If you input an incorrect syntax for one of the API calls in the request body, you’ll note that the response will have errors.

![](https://cdn-images-1.medium.com/max/2000/1*SVjQKPk3SBy3gCzR5P9Kcw.png)

18.@24.40 — The way the Salesforce REST API is designed at this moment is that it can only take a single URI per request and so you cannot pass in an array into the URI.

19.@24.45 — The TreeSave resource is a recursive data structure. A single request can contain up to 200 records across all trees. For example, you could create 1 account record and 199 contacts.

![](https://cdn-images-1.medium.com/max/2000/1*j-Ofb2qJHf7gEAQDWM0abw.png)

20.@26.00 — The TreeSave API diagram looks like:

![](https://cdn-images-1.medium.com/max/2000/1*EsyIqD8MRxAcvSddLSAZqg.png)

To POST contacts under the account, the URI would be /services/data/v37.0/composite/tree/**Account**

21.@26.30 — At this moment, only the INSERT DML operation is supported for TreeSave. Partial saves are not supported. The transaction is not completed until it is 100% successful. Everything will be rolled back if there was an error.

Separate governor limits are applied to each level of the tree.

![](https://cdn-images-1.medium.com/max/2000/1*u25_lIlmrqSCY7pKvxIPpA.png)

22.@32.00 — In this example, an array of accounts are being inserted and some contacts (children).

![](https://cdn-images-1.medium.com/max/2000/1*bUngnPmyshGCY95ykA8mDg.png)

The top of each level has an attribute tag, which references the sObject type and reference Id. Afterwards, the field name — values are specified.

23.@34.00 — The response looks like below:

![](https://cdn-images-1.medium.com/max/2000/1*1hcA-MgNaZSNYj-jEakNvg.png)

The top level sObject would return first in the response, but the processing of child records isn’t deterministic and you can’t write any logic to say ‘this child sObject should be created first’.

![](https://cdn-images-1.medium.com/max/2000/1*7rXhkUbPpJGiRMJKGtKNYQ.png)

24.@38.40 –

![](https://cdn-images-1.medium.com/max/2000/1*Uf4uP1sd3-21TlWDWljouQ.png)

25.@41.00 –

With a [Composite API,](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/resources_composite_composite.htm) you can take the benefits of the batch request and the TreeSave together. This results in web structure (not a Tree structure), in that you can do different REST API methods on related or unrelated data.

![](https://cdn-images-1.medium.com/max/2000/1*oat8JW0Bpbwu2i9dzhs0yw.png)

26.@42.15 — An example of a composite API request is below:

![](https://cdn-images-1.medium.com/max/2000/1*eue-H2qnrBQAWe1RqFz0xA.png)
