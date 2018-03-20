---
layout: post
title: Integrating Third-party APIs Using APEX RESTful Callouts
tags: [API Integration, RESTful Callouts, Salesforce APIs, Salesforce Integration, Salesforce REST API]
---

## Integrating Third-party APIs Using APEX RESTful Callouts

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

In this presentation, you will learn how to integrate the Force.com platform with data stored on a third party web service.

![](https://cdn-images-1.medium.com/max/2000/1*puDHq65QvlJZbYqOaPBvbQ.png)

**Details**: ‘[Integrating Third-party APIs Using APEX RESTful Callouts](https://www.youtube.com/watch?v=705SeyjpoFs)’

**Presenter**: Matt Kaufman, Jenna Tucker

**Details**: 25 minutes

**Key Terms:** REST API, RESTful Callouts, HttpResponse

 1.@1.00 — You will learn how to pull outside data into Salesforce.

 2.@1.05 — In this presentation, you will learn how to integrate the Force.com platform with StackExchange to work with Force.com related questions.

![](https://cdn-images-1.medium.com/max/2000/1*fRmzXtGoegNsAxAgIQNzrw.png)

3.@2.00 — It’s important to know about RESTful callouts. REST stands for Representational State Transfer, and it is a way which web services talk to each other.

![](https://cdn-images-1.medium.com/max/2000/1*2fxmkuU8r1TCoLeVkWXz3w.png)

So even if you have two web services that have been built with different technologies, they can still communicate with each other using REST.

Information is typically transferred as HTML, XML or JSON.

4.@2.30 — JSON stands for JavaScript Object Notation and is typically a much faster way to transfer data than using XML, which is a bit more rigid.

![](https://cdn-images-1.medium.com/max/2000/1*y0TWqpqbmIGu66mA1N4Lew.png)

5.@2.50 — This is a high level diagram of what is happening when we perform an Apex callout to a third party web service. A callout from the Force.com server to another server is completed over the internet. The server will then return a response to the Force.com server.

![](https://cdn-images-1.medium.com/max/2000/1*o9o5rGMgI3yrz7th-KO6HQ.png)

This could be used for processing credit cards, validating data, or even augmenting data (bringing data into the Force.com server).

6.@3.15 — Built into Apex, we have an HttpRequest, Http and HttpResponse class. These classes can be used to perform a callout. In addition, Apex also includes a JSON class that makes it very easy to work with JSON strings to help make the response very humanly readable.

![](https://cdn-images-1.medium.com/max/2000/1*SlnfpUJdeTrSQFPA93KRTQ.png)

7.@3.55 — However, before any callout can be achieved, you will first have to create a remote site setting. A remote site setting says ‘this is a URL that we will allow our code to contact’. This helps data from being sent from your Salesforce org to an incorrect endpoint by mistake.

![](https://cdn-images-1.medium.com/max/2000/1*LyYlmS8YY9ifO7AAogRtYg.png)

8.@4.25 — Using the HttpRequest class, we instantiate an object which defines what we want to do (how we want to communicate to the web server, what attributes should be specified etc). In the below example, you can see that we instantiate an httpRequest() object and we use the setMethod method to specify a GET call to a specific endpoint.

![](https://cdn-images-1.medium.com/max/2000/1*fPgU_K8mZxglWrlgLr1G5w.png)

9.@5.00 — The easiest class to work with for calling out to a web service is the Http class. It’s very simple. You instantiate it and then send the request. You receive an httpResponse.

![](https://cdn-images-1.medium.com/max/2000/1*cQr7omaqedc8WKMpTBA7Tw.png)

10.@5.10 — Finally, there is the HttpResponse class. This class includes methods to read the response from the 3rd party service. You can turn the response into an Apex object which your code can read.

![](https://cdn-images-1.medium.com/max/2000/1*8jOOTUZUbp0pSw-xjDBYTA.png)

11.@6.00 — A preferable approach is to create a single method which completes all of the operations that you want in order to communicate with the third party service.

An example is below, as per the GitHub repo [here](https://github.com/mkplabs/StackExchange-API-for-Force.com/blob/master/src/classes/stackExchangeAPI.cls).

In the below snippet of code, the method ‘callout’ passes in the verb of the httpMethod, the endpoint and the body of the message.

    public with sharing class stackExchangeAPI {

    public static String BASE_URL = ‘https://api.stackexchange.com/2.2/';

    //Method to perform a callout and return an httpResponse

    public static httpResponse callout(String httpMethod, String endpoint, String body){

    //Instantiate an httpRequest and set the required attributes

    httpRequest req = new httpRequest();

    req.setMethod(httpMethod);

    req.setEndpoint(endpoint);

    //Optional attributes are often required to conform to the 3rd Party Web Service Requirements

    req.setHeader(‘Accept-Encoding’,’gzip, deflate’);

    //You can adjust the timeout duration (in milliseconds) to deal with slow servers or large payloads

    req.setTimeout(120000);

    //Use the HTTP Class to send the httpRequest and receive an httpResposne

    /*If you are not using an HttpCalloutMock:

    if (!test.isRunningTest){

    */

    httpResponse res = new http().send(req);

    /*If you are not using an HttpCalloutMock:

    }

    */

    system.debug(res.toString());

    system.debug(res.getBody());

    return res;

    }

12.@7.40 — Typically, HttpResponse bodies are not human readable.

![](https://cdn-images-1.medium.com/max/2000/1*0ybunD__YI3aOz_TSk6aMQ.png)

13.@9.15 — To understand more about what the raw response will typically look like, you can go to the URI [http://api.stackexchange.com/2.2/questions?order=desc&sort=activity&site=salesforce](http://api.stackexchange.com/2.2/questions?order=desc&sort=activity&site=salesforce).

![](https://cdn-images-1.medium.com/max/2000/1*Cz9ysH28KP879PSFMGGPOg.png)

You can make this more human readable using the ‘parse’ option in Google Chrome or you can use a tool like [JSON Pretty Print](http://jsonprettyprint.com/). Alternatively, you could use a Chrome extension like Postman or ARC (Advanced REST Client); which gives you additional information as well as the option to choose the raw or prettified response.

![](https://cdn-images-1.medium.com/max/2000/1*oAXwvbJMvTBY_iELJJd9kA.png)

![](https://cdn-images-1.medium.com/max/2000/1*y3U0LgsxoPizSKctPX6XGg.png)

14.@10.20 — So having looked at the response and looking at the definition and attributes of the response, once we understand what we should be getting back, all we need to do is to code that in Apex.

This can be achieved by serializing and deserialising the JSON strings into Apex objects.

![](https://cdn-images-1.medium.com/max/2000/1*E6T8xIHD5iWwvOcV9Sfb-A.png)

So in this example, by de-serialising the httpResponse from a JSON string into an object, we can use Apex to work with the response.

15.@11.10 — So let’s delve into the code in more detail to see how we will handle this in Apex. In the outermost class ‘responseResource’, we have attributes which represent the attributes that are in the body of the message returned from the API.

For example, if you change the request URL from [http://api.stackexchange.com/2.2/questions?order=desc&sort=activity&site=salesforce](http://api.stackexchange.com/2.2/questions?order=desc&sort=activity&site=salesforce) to an incorrect URL, say, [http://api.stackexchange.com/2.2/questionsTHISISWRONG?order=desc&sort=activity&site=salesforce](http://api.stackexchange.com/2.2/questionsTHISISWRONG?order=desc&sort=activity&site=salesforce), then the response returns the following:

![](https://cdn-images-1.medium.com/max/2000/1*OtZItaQtjthaI_i0kOEz7w.png)

Whereas, if the request is success (a ‘200’ response), then the response returns the following attributes:

![](https://cdn-images-1.medium.com/max/2000/1*9JtPdNHkk1IjNql5mU_29w.png)

These attributes make up the response resource; which you can see are defined in the Apex code of the method below:

In addition to these attributes, a List is also specified: public List<questionResource> items {get; set;}

This list is populated with the questionResource records; which are also defined in the API response.

![](https://cdn-images-1.medium.com/max/2000/1*AvxCV6aiLb_n5x9bkcgqCw.png)

16.@11.30 — By looking at the response from a successful GET call to the URI, we can see the following:

![](https://cdn-images-1.medium.com/max/2000/1*PhCr_tmeaCdCDeQnPrRjTQ.png)

Some of these attributes are specified in the questionResource class in the Apex code. What’s interesting to point out here is that you do not need to specify all of the attributes from the API response, only those that you care about. This is in sharp contrast to XML, which must be in alignment.

![](https://cdn-images-1.medium.com/max/2000/1*kUsCuQKETfBRBJ3TjVAr_g.png)

17.@12.00 — What you’ll notice is that the ‘owner’ attribute of the questionResource class is also a class ‘userResource’. This is because, as per the API response, the ‘owner’ attribute is represented as an object:

![](https://cdn-images-1.medium.com/max/2000/1*F2pq2c-M6R1D_P4e_cs6oQ.png)

So, overall, we are working with 3 different objects. This is quite hard to read because we have multiple nested objects. However, to make this easier to read, we can create a Visualforce page and a controller.

Also, please note: if the JSON string that comes back as part of your response has an attribute that isn’t defined in the code, then your code just ignores it but if it’s the wrong data type, then an exception will be thrown. Conversely, if you’ve defined an attribute in your class but the response doesn’t contain that attribute, then it’ll be set to null.

![](https://cdn-images-1.medium.com/max/2000/1*ORiZgEzYckN9oaQdXTzBcA.png)

18.@13.00 — As per the constructor, the endpoint is being defined ahead of time. You may choose to have the endpoint defined on the fly, though.

![](https://cdn-images-1.medium.com/max/2000/1*rl8KHZ5SbN3n3Ok0xsXLvQ.png)

19.@13.10 — When performing the callout, the same code that was written before is being leveraged.

![](https://cdn-images-1.medium.com/max/2000/1*oV-AzYRsH0xCk0JazorGiA.png)

20.@13.40 — Then, the response is deserialized.

21.@14.30 — The code for the Visualforce page looks very typical. There’s a section called ‘JSON Deserializer’, which outputs the instances of the responses in a tabular format.

![](https://cdn-images-1.medium.com/max/2000/1*zd7m5m3H8xF4CEoBVPHMMg.png)

22.@15.10 — So when one selects ‘Callout’ on the page, the getBody() responses returns the raw JSON:

![](https://cdn-images-1.medium.com/max/2000/1*yLe81el2ONCGBoFt4yY0Pg.png)

And by selecting ‘Deserialize’, the JSON is deserialized into an Apex object; which the code is working on.

![](https://cdn-images-1.medium.com/max/2000/1*H4B35qYHlRHKbf-Ntj3EzQ.png)

23.@16.00 — An important thing to note is that you cannot perform a callout in a test method.

![](https://cdn-images-1.medium.com/max/2000/1*WIESC6RIWw2_fFXOnSA5AA.png)

In this example, the code coverage is only 8% as the callout itself hasn’t been tested. This means that you cannot deploy to Production.

![](https://cdn-images-1.medium.com/max/2000/1*MxaJkcjhLhwvINLNWihygw.png)

24.@17.20 — The problem here is that the callout is in the test method itself, hence, it isn’t being run.

![](https://cdn-images-1.medium.com/max/2000/1*w6ejyvTlpFd3iAEb27ryaQ.png)

25.@18.00 — In the past, you would just add a condition to say ‘if the test is not running, perform this callout’.

![](https://cdn-images-1.medium.com/max/2000/1*xsBzBTpsTUp8ocxrF6yjWQ.png)

However, this means that a proper test is not in place. The test should test that the response that is given back is properly parsed.

26.@18.15 — So Salesforce created a way to perform meaningful tests on callouts using the httpCalloutMock interface. This interface enables you to mock the callout to test the response.

![](https://cdn-images-1.medium.com/max/2000/1*nWM3STFf7BMrRgXaIfJnUQ.png)

27.@19.00 — And so in the code of the testHttpCalloutMock.cls, we create instances of questionResources.

![](https://cdn-images-1.medium.com/max/2000/1*AE5S8XTHPcbDEYiz08R5Wg.png)

This allows you to do a meaningful test on the callout. This time around, the code coverage passes.

28.@20.15 — At a high level, this is how the httpCalloutMock interface works:

![](https://cdn-images-1.medium.com/max/2000/1*H7RGOKCzLn_deWTZ4oJggQ.png)

Instead of calling out to the web service via the internet and saying ‘*I’m calling you, but please don’t take this seriously, this is just a test*’, the mock callout is done on the Force.com servers.

29.@20.50 — Remember to use the setMock() method in your test method.

![](https://cdn-images-1.medium.com/max/2000/1*5JSuXCqEkK8RvmdVA2m22g.png)

30.@23.55 — You can set multiple mock interfaces, but it’s the last mock interface that you set that will be used. However, a smart approach would be to have a single Mock Interface and then query the endpoint. If the endpoint was A, then set the object in the response to X, but if the endpoint was B, then set the object in the response to Y.
