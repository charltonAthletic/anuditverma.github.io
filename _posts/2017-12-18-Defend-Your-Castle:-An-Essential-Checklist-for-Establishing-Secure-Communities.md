---
layout: post
title: Defend Your Castle: An Essential Checklist for Establishing Secure Communities
tags: [Salesforce Communities, Salesforce Security]
image: 
---

# Defend Your Castle: An Essential Checklist for Establishing Secure Communities

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

This summary goes through the key attacks that can impact Communities and how to
protect yourself from them.

**Details: ‘**[Defend Your Castle: An Essential Checklist for Establishing
Secure Communities](https://www.youtube.com/watch?v=5eWhvQR0Dbs)’

![](https://cdn-images-1.medium.com/max/720/1*MDDestVFYIMvVP04pVClvg.png)

**Presenter: **Matt Sherman and Jared Snyder

**Time: **20 minutes

**Key Terms**: SOQL injection, Cross-Site Scripting, Communities, Security

**Summary:**

1.  @0.30 — In this session, you will learn about how to prevent attackers from
coming after your Community.
2.  @1.20 — You need to consider the following, with regards to creating and
maintaining a successful Salesforce Community: Audience, Technology, Engagement,
Growth and Security.

You need to think about who the audience is (will it be a public or internal
community), you will need to think about what technology will be used in the
Community (code or declarative, Classic or Lightning etc), you need to think
about how you will engage, if at all, with the community. You will also need to
think about how you can measure adoption, understand why people are interacting
with the community. And last but not least, you need to consider security. Who
should be able to do what and see what records? How can you keep your Community
secure?

![](https://cdn-images-1.medium.com/max/720/1*TAfZQmSFgh2P4oiTEm64Pw.png)

3. @3.05 — There are some risks associated with implementing Chatter in your
Community. Chatter is a fantastic engagement tool and has some great
functionality to prevent ‘attacks’. For example, [Member and Content
criteria](https://help.salesforce.com/articleView?id=networks_moderator_manage_rules_content.htm&language=en_us&r=https://www.google.co.uk/&type=0)
help prevent your Community from offensive language (a reputational risk) and
inappropriate content created by spammers or malicious members.

Also, assigned Community moderators can manage malicious posts and block
particular users. Malicious posts can be flagged by Community users and so in
this way, the Community can self-police itself.

![](https://cdn-images-1.medium.com/max/720/1*D2Z0AhxOzN3HkyffYeWHBw.png)

4. @4.00 — [Event
Monitoring](https://trailhead.salesforce.com/en/modules/event_monitoring/units/event_monitoring_intro)
is a paid for Salesforce add-on that gives you a huge amount of insight into who
did what, when. You can leverage Event Monitoring with [Transaction
Security](https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/security_overview_transactions.htm)
or a third party app, such as
[FairWarning](https://appexchange.salesforce.com/listingDetail?listingId=a0N3000000B5YHjEAN).

You can also use Community User Monitoring to see the login history of your
Community users. In the logs, you’ll be able to see what browsers and TLS
protocol they typically use.

![](https://cdn-images-1.medium.com/max/720/1*aGzN_XgXJ5CkgJpzlEOPPg.png)

5. @4.45 — The first line of defence to your Community is the Org-Wide Defaults
(OWDs).You can consider OWDs to be like the castle walls. You will want to
enable an external sharing model for external Communities.

A key thing that you may want to review is the Community User Visibility. By
default, all Community users can see all other users in the Community. This may
be great for Chatter collaboration but may be too open for what you want. So you
can edit this so as to make Users only see who they should see. More info
[here](https://help.salesforce.com/articleView?id=security_sharing_owd_external_user_settings.htm&type=0).

![](https://cdn-images-1.medium.com/max/720/1*A-sH0CbCSTbPBDmA56UfcQ.png)

6. @8.30 — When writing code for Communities (for example, you may have a
Visualforce page or Lightning page that you want to be displayed on a Community
page), be very careful with the ‘sharing’ keyword in your controller. ‘With
Sharing’ respects the OWDs whilst ‘without sharing’ does not. By default,
classes are ‘with sharing’. More info
[here](https://salesforce.stackexchange.com/questions/11768/when-to-use-with-sharing-or-without-sharing).

So potentially, ‘without sharing’ can be a huge security issue (although there
are some valid reasons why a controller would have ‘without sharing’).

7. @9.25 — You can use the Security Health Check in Salesforce Setup to identify
and fix vulnerabilities. The ‘How is the Health Check Score Calculated’
documentation is
[here](https://help.salesforce.com/articleView?id=security_health_check_score.htm&type=0).

![](https://cdn-images-1.medium.com/max/720/1*Ta32amaOahqyw4vorpvQig.png)

![](https://cdn-images-1.medium.com/max/720/1*cPaM1D9SFhj7ommh6CpPLA.png)

8. @10.00 — There is also a paid add-on as part of Salesforce Shield which will
enable you to encrypt data at rest and not just at transmission (it’s important
to be aware that there are pros and cons to this, though). More info
[here](https://trailhead.salesforce.com/en/modules/spe_admins).

9. @10.30 — From a coding perspective, you should refer to the [Apex Coding
Guidelines](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_dev_guide.htm).

10. @11.00 — You need to be aware of [SOQL injection
attacks](https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_security_tips_soql_injection.htm).
SOQL is the Salesforce version of SQL. It is a query language. A very good eBook
resource for learning about SOQL is
[here](https://www.packtpub.com/application-development/getting-started-soql).

![](https://cdn-images-1.medium.com/max/720/1*rOvN29JJ-mkCk6w61W1GhA.png)

At a high level, a SOQL injection attack is where one can change the ‘WHERE’
criteria by inputting SOQL into the search criteria itself.

For example, in the below screenshot, the query of ‘Sir’ works as intended.

![](https://cdn-images-1.medium.com/max/720/1*uZQU51SGTy4Gp3Qf33kP7A.png)

However, if one inputs SOQL into the search query itself (*Sir%’ OR Name LIKE
‘%),* then the below results are displayed. This is because the query has been
extended by the user; and is showing results that the developer may not have
intended the user to see.

![](https://cdn-images-1.medium.com/max/720/1*XM741CyI4wS4vqMrfu80bw.png)

This is happening because the query in the underlying code is merely
concatenating the input from the user. There is no check in place to query the
input query before it is executed at run time.

![](https://cdn-images-1.medium.com/max/720/1*Tz3zD9yl7gg7Q0H7gj3PUw.png)

![](https://cdn-images-1.medium.com/max/720/1*zG7zyPZl53j3EI8G0nN23Q.png)

To resolve this, your query method that executes the SOQL should use verifiable
binding instead of merely concatenating. This maintains the structure of the
query and it will query the string that the user input literally.

*whereclause_records = [SELECT Name, Role__c, Title__c, Age__c FROM Personnel__c
WHERE Title__c LIKE :titleSearch];*

![](https://cdn-images-1.medium.com/max/720/1*tQ8Mj8X0WDH4gaWZWsECxw.png)

So let’s try it again with the verifiable binding example, and we can see that
no results are returned:

![](https://cdn-images-1.medium.com/max/720/1*snOn-CCvJMyr3jMR-W0amw.png)

11. @14.20 — Another security threat that you need to be aware of is [cross-site
scripting](https://developer.salesforce.com/page/Secure_Coding_Cross_Site_Scripting)
(XSS). This may be more of a concern than the SOQL injection attack because with
XSS, there is the risk of data being copied out of the Org. There is a lot of
malicious intent one can achieve with XSS attacks with JavaScript.

If you use a <script> tag, then you are responsible for everything that goes on
inside of this.

![](https://cdn-images-1.medium.com/max/720/1*VKSYGXtg3b0BsOgQx-z0og.png)

To handle the JavaScript inside a script tag correctly, Salesforce has provided
a [set of
functions](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/pages_security_tips_scontrols.htm)
to escape potentially insecure strings.

For example, using ‘<i>{!JSINHTMLENCODE(outputText)}</i> ensures protection to
ensure the input is taken literally.

![](https://cdn-images-1.medium.com/max/720/1*Yfr6oNjkyEXVkpQ9gpc9TQ.png)

12. @17.30 — So, just to recap, as per below screenshot, this is an example of
code that is vulnerable to a SOQL injection.

![](https://cdn-images-1.medium.com/max/720/1*Uj6bMNzXSzyUQAkAGNX7eA.png)

13. @17.40 — And the fix is here:

![](https://cdn-images-1.medium.com/max/720/1*wJ--J4z5UbQJBjdhDezNlA.png)

14. @17.50 — There is another type of XSS, called Cross Site Request Forgery
(CSRF). The difference is that, in CSRF, the user is already authenticated.

![](https://cdn-images-1.medium.com/max/720/1*hcThiz8a7T5sMEjEJKrVFA.png)

15. @19.25 — You should take the [Trailhead
Trailmix](https://trailhead.salesforce.com/en/modules/secdev_injection_vulnerabilities/units/secdev_inject_get_started_wappsec)
for more information and experience on dealing with these kind of attacks.

* [Security](https://medium.com/tag/security?source=post)
* [Salesforce
Productivity](https://medium.com/tag/salesforce-productivity?source=post)
* [Salesforce](https://medium.com/tag/salesforce?source=post)
* [Salesforce Lightning](https://medium.com/tag/salesforce-lightning?source=post)

By clapping more or less, you can signal to us which stories really stand out.

### [Andy Hitchings](https://medium.com/@andyhitchings)

Salesforce & JavaScript Developer

### [Salesforce
Summaries](https://medium.com/salesforcesummaries?source=footer_card)

Save time with our key insights from Salesforce YouTube videos.
