---
layout: post
title: Introduction to Serverless Applications
tags: [Cloud computing, micro-services, Serverless]
---

## Introduction to Serverless Applications

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Serverless architecture is a new and emerging technology paradigm that is incredibly powerful and will help to democratize cloud computing.

**Details**: ‘[Introduction to Serverless Applications](https://www.youtube.com/watch?v=iSDokuZnRcI)’

**Presenter**: [Austen Collins](https://serverless.com/)

**Details**: 65 minutes

**Key Terms**: Serverless, micro-services, cloud computing

 1.@1.00 — The agenda of this presentation is:

![](https://cdn-images-1.medium.com/max/2000/1*wkCR0FsxLAQfT63d84t_uA.png)

2.@4.30 — Getting stuff done is hard. Reducing the time it takes to get stuff done is incredibly valuable.

![](https://cdn-images-1.medium.com/max/2000/1*aWuz_ZABxoSXuTGVFLpDkw.png)

3.@6.40 — The invention of the cloud was a game changer. ‘*Why should you own and maintain infrastructure? Why not just rent the virtual capacity instead? Why not interact with our services programmatically via our APIs?*’. This was a huge innovation.

![](https://cdn-images-1.medium.com/max/2000/1*6h1VDlUWKckbZGH-7Ub9ug.png)

However, there is still a lot of scaling problems to be solved, like when Black Friday happens and millions view your site at once. Or when you have AWS bill and you’re not even using half of its features.

4.@10.50 — Serverless is a chapter in cloud history. It’s an evolution from virtual infrastructure. Serverless answers the question ‘*how can we offer the infrastructure without the cost and current issues*’.

![](https://cdn-images-1.medium.com/max/2000/1*5R-BZCcQcd_869TIAk3LRg.png)

5.@11.00 — Today is the golden age of delivering value at a low cost.

![](https://cdn-images-1.medium.com/max/2000/1*PYqzg91As6WFC0bQwH3jqA.png)

6.@12.00 — Heroku had the great concept of the ‘dyno’ when scaling. You can scale up as much as you require with additional cloud computing credits (dynos). But serverless is evolving that further asking ‘*why do you even need to scale up or down in the first place? Let’s remove that constraint. You shouldn’t have to think about scaling — you should just be able to think about solving problems*’.

![](https://cdn-images-1.medium.com/max/2000/1*OJvHSenzkVoK8ebvx_nutw.png)

7.@13.00 — The big drawer of serverless is ‘pay per use’. If you put your code on ‘serverless compute’, then you only pay when your code runs. If your code runs for 1 ms, then your cost is 0.000001 cent.

8.@14.10 — The AWS Lambda started the ‘serverless’ trend in 2014.

![](https://cdn-images-1.medium.com/max/2000/1*I0nhhNV-msfFY8OjQKXbKA.png)

You can write a function and upload it to AWS Lambda. The function will do just one thing, such as send a text message to a set of users, save a user login to a database etc. You can use a handful of programming languages to achieve this — Python, Go, JavaScript, Java etc. You don’t need to worry about administration because you will only be charged when the code is run and when it does run, it’ll cost fractions of a cent.

9.@16.00 — Also, the code you upload can be event driven. You can have it run automatically whenever certain infrastructure in your AWS stack happens. So half the value comes from how well it integrates with other technologies in the AWS stack and also the other half is in how efficient the code runs.

10.@17.05 — Once the success of Lambda took off, AWS started to refactor and produce a lot of other services that have serverless qualities. These are the most efficient building blocks that you can leverage to build applications.

![](https://cdn-images-1.medium.com/max/2000/1*4UXhd2XUbcW-voVePpxYIw.png)

![](https://cdn-images-1.medium.com/max/2000/1*YzIv53DSiPjHIYRMSC5h-w.png)

![](https://cdn-images-1.medium.com/max/2000/1*DuKDV6s9Vz9rHG4FH2zVww.png)

11.@19.45 — These serverless services are like superpowers. You can leverage services to convert text to audio, real time processing of video, perform facial recognition etc. This is the golden age of the developer.

12.@21.00 — These are the types of serverless services which AWS customers are building.

![](https://cdn-images-1.medium.com/max/2000/1*ix84XD2XHmKMAHtMVNC9yQ.png)

13.@22.15 — Chatbots are very popular. Again, you won’t be charged for your chatbots until they are being used.

14.@23.00 — Because this technology is so powerful, it attracts all types of use cases. It is liberating a lot of creativity that was previously suppressed due to overhead.

15.@23.40 — One of the most compelling stories that demonstrate the power of serverless technology can be found [here](http://theconversation.com/root-of-census-failures-say-badly-done-ibm-and-abs-still-down-for-some-63845). The Australian government in 2016 contracted IBM to build an online census survey that would scale. The cost for this was just over $9 million. The Australian government spent about 5x that amount on marketing urging Australians to complete the census online during a particular time period. Unfortunately, the survey was not serverless and so because the demand was so high during the certain time period, the website crashed. Relatively little data was successfully captured and a huge fallout occurred.

A few days after the calamity, two [university students](https://eftm.com/2016/08/how-two-uni-students-built-a-better-census-site-in-just-54-hours-for-500-30752) built a replica using AWS serverless technology in less than 72 hours for less than $200 that scaled flawlessly and was able to handle even more than what the estimated demand requirement was for the census survey. In fact, they load tested the survey with 4 million page views per hour and 10,000 submissions per second. Although no data verification, audit trail or full logging functionality was implemented ([which would reduce performance](https://news.ycombinator.com/item?id=12294475)), it does clearly demonstrates the power of serverless technology — it makes the power of the cloud accessible to everyone.

![](https://cdn-images-1.medium.com/max/2000/1*YEiolqY6Ck7xMOmpG1crIQ.png)

![](https://cdn-images-1.medium.com/max/2000/1*MQIyC_RKugKwyk0OiP0s5A.png)

16.@28.00 — It is tricky to leverage all the different cloud technologies into a serverless application.

![](https://cdn-images-1.medium.com/max/2000/1*_XrNowRBVWWJ2ghKXwyOVA.png)

![](https://cdn-images-1.medium.com/max/2000/1*ov2UWi6av3aQJ0shPpE_bw.png)

17.@28.55 — In the AWS dashboard, you are presented with numerous products and it can be overwhelming. This is something that [Heroku](https://www.heroku.com/) has done so well on — they answered the question ‘*there has got to be an easier way to do this stuff*’.

18.@29.30 — The [serverless framework](https://github.com/serverless/serverless) is one of the most popular open source projects today and is an effort to make AWS more accessible.

![](https://cdn-images-1.medium.com/max/2000/1*C1SnM_gmS9PlAJROfMS67Q.png)

19.@31.00 —The serverless framework solves the following:

![](https://cdn-images-1.medium.com/max/2000/1*jFRtq21T_nT5nAo9bZKG_g.png)

20.@32.00 — Serverless is vendor agnostic. You can use AWS or Google or Azure etc. Different vendors may have different specialities. For example, Google is very strong in machine learning.

21.@32.50 — The Serverless framework is a CLI written in node.js. The goal is to help you to deploy something as fast as possible without having to look at the AWS dashboard at any point.

![](https://cdn-images-1.medium.com/max/2000/1*mP-PNUHODRKZ38Fmm9DewA.png)

22.@33.10 — Serverless is a story of functions and events. It is an aggregation of plugins. This configuration file will setup a backend of your application.

![](https://cdn-images-1.medium.com/max/2000/1*qHRBDrxJ_BiJmNpVYZxhtg.png)

23.@34.00 — Serverless comes with a number of different functions:

![](https://cdn-images-1.medium.com/max/2000/1*2KyAm3athULVme_s3Z0XkA.png)

24.@34.30 — The serverless framework comes with all types of languages:

![](https://cdn-images-1.medium.com/max/2000/1*gJIG0Ct6uLyDo_DTAQuq9w.png)

25.@35.00 — There are hundreds of serverless plugins that have been created courtesy of the fantastic open source community.

![](https://cdn-images-1.medium.com/max/2000/1*t8ngNT7Av453hf3S24siEw.png)

26.@58.00 — There is a huge demand for moving to serverless architecture. Companies like Nike and Coca-Cola already have adopted serverless architecture.

27.@61.00 — This architecture is micro-service architecture. ‘*Let’s try to separate every single piece of logic in our application so that there will be no risk to the system overall if a swathe of changes are made*’.
