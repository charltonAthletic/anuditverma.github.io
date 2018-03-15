---
layout: post
title: Introduction To Lightning LockerService
tags: [JavaScript, Lightning LockerService]
---

## Introduction To Lightning LockerService

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

LockerService is a relatively new security feature from Salesforce that enforces JavasScript best practices for Lightning components.

![](https://cdn-images-1.medium.com/max/2000/1*-X5FVbBF9aQS0R9yk4F5xw.png)

**Details:**

Video: ‘[Introduction to LockerService](https://www.youtube.com/watch?v=5HNPGuRKzzM)’

Presenter: Farhan Tahir

Date: November 29 2016

Time: 18 minutes

Key terms: LockerService, cross-site scripting, real DOM, security, isolate namespaces

**Summary:**

 1. @2.15 — Aura is an open source JavaScript framework. JavaScript has been around for about 20 years and is one of the most popular programming languages. Because of the way JavaScript interacts with and opens up the [DOM](https://salesforce.stackexchange.com/questions/70754/what-is-the-use-dom-in-sales-force-where-we-can-use-that) (Document Object Model), this opens up a lot of risk for end users and customer data. The DOM is an abstraction of the HTML structure of a page.

![](https://cdn-images-1.medium.com/max/2000/1*wcyvO5tc-A5h2Jf5WEGPqQ.png)

2. @2.50 — One of the most important things to note when deploying JavaScript is risks around cross site scripting (XSS). This is source JavaScript (JS) injection. XSS is a common website attack. It is essentially loading a command and malicious script into your website.

3. @3.10 — An example of an XSS attack is: let’s say you have an eCommerce website that has been attacked by XSS. When a customer goes to your website and inputs some sensitive data (e.g. their billing information), that data doesn’t go to your website anymore, it will go to the attacker.

4. @3.45 — Out of all website attacks, XSS accounts for 84% of them.

![](https://cdn-images-1.medium.com/max/2000/1*4k-TOFkp8_uRJGLDNVhOtA.png)

5. @4.10 — In the example below, the Lightning App has multiple components from different namespaces. The issue here is that all of these components have *unrestricted *access to the DOM. This means that any component can read the rendered data from another component. Note — the components cannot access server data.

![](https://cdn-images-1.medium.com/max/2000/1*dEsitGnlBiR7fomxGHrsxA.png)

6. @4.35 — Another issue is that none of these components are siloed in anyway; which means if there is an issue in any component, then that has the ability to affect other components.

7. @5.00 — In order to solve these issues, LockerService has been introduced; which will be enabled automatically for Lightning components on API version 40 and above. For components on an API version less than 39.0, LockerService is *not *enabled. You can upgrade the API version of Lightning components to be at least API version 40, although you should do tests first.

8. @5.15 — LockerService combines a few JavaScript techniques such as scope shading, strict mode and wrappers to give you secure and fine grained access control. LockerService doesn’t use iFrame.

9. @5.50 — LockerService enforces strict mode and enforces best practice. With LockerService, you have to define variables and types, so a strongly-typed paradigm is adopted. Also, if you are using any third party libraries in your components, then they too must use strict mode.

![](https://cdn-images-1.medium.com/max/2000/1*zlhZj106osAfV2H27wKhIg.png)

10. @6.20 — LockerService limits access to the DOM to your own namespace, so that you can’t create data off of other components.

11. @6.55 — LockerService restricts you from using JavaScript APIs that are Aura enabled but not Lightning enabled. Lightning enabled APIs are a subset of the Aura enabled APIs and not all Aura enabled APIs are supported with LockerService.

12. @7.50 — If you use third party libraries, you should ensure that you are on the latest version.

13. @8.20 — What LockerService enables one to do is to expedite testing of your code. This will be helpful for ISV partners because the time taken to test code, with LockerService, will reduce rapidly.

![](https://cdn-images-1.medium.com/max/2000/1*XI4Ga0AuJ-5V0cprMxJjNw.png)

14. @9.45 — In this particular example, the weather and map components share the same namespace and the finance component has a different namespace.

![](https://cdn-images-1.medium.com/max/2000/1*qZ7RjhGygFkJUO--kHIH_Q.png)

15. @10.00 — This is what the workings of the app look like when LockerService is not enabled:

![](https://cdn-images-1.medium.com/max/2000/1*lI6Do3Dq7Lp1HBfHycJSOw.png)

You can see that all of the JavaScript can access each other, the DOM and Window; which creates security issues. The sensitive data from the finance component can be accessed from any of the other components, even though they have different namespaces.

16. @10.46 — With LockerService enabled, the workings of the app look very different:

![](https://cdn-images-1.medium.com/max/2000/1*hU0nQIKvHuV0CMP_coUAfw.png)

The UI button on the right side of the screen, which is a Salesforce provided component, runs in system mode. Access to system mode enables one to have access to the DOM.

When the weather or map components (on the left side of the page) request the DOM, they don’t get the real DOM as they get the shadow (secure) DOM instead. In addition, the elements of namespace1 can no longer access the elements of namespace2 and vice versa. Every component has been isolated within its own namespace.

17. @12.30 — Because IE 11 doesn’t support CSP (Content Security Policy), starting from December ’17, you won’t be able to use IE 11 for Lightning Experience.
