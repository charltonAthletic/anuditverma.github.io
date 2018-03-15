---
layout: post
title: Techniques and Tools to Improve the Salesforce Development Cycle
tags: [Continuous Integration, Salesforce Development Cycle, Source Code Management]
---

## Techniques and Tools to Improve the Salesforce Development Cycle (pre Salesforce DX)

*SalesforceSummaries is a publication that delivers the **key **insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

Since the Salesforce Winter ’18 release, [Salesforce DX has become generally available (GA)](https://developer.salesforce.com/blogs/2017/10/salesforce-dx-is-now-generally-available.html).
>  As you know, we approached Salesforce DX with a principled perspective about how to write software. Everything is driven from source code, environments are easily created and disposable, and development is organized around team collaboration. We also focused on source-driven development and agile distribution, through the organization of your existing orgs and adoption of next generation packaging.

[Salesforce DX](https://developer.salesforce.com/platform/dx) (sfdx) looks set to *hugely* assist the Salesforce development cycle. It’s worth remembering that pre-sfdx, this cycle was more challenging to implement.

Sometimes, it’s hard to see how far a technology and methodology has grown without reflecting on the past. With that in mind, the excellent presentation by Stefan Goor back in 2014 discusses some tools and approaches that were used to facilitate the Salesforce development cycle. Even with Salesforce DX, so many of the points made in the presentation are still relevant and applicable.

**Details:**

![](https://cdn-images-1.medium.com/max/2000/1*LZ7S2zyMXBhi8hDAUGoGPA.png)

Video: ‘[Techniques and Tools to Improve the Salesforce Development Cycle](https://www.youtube.com/watch?v=NMwygVAE4kg)’

Presenter: Stefan Goor

Date: November 15th 2014

Time: 41 minutes

Key terms: Source code management, collaborative development, continuous integration, isolated feature development

Key points: A combination of agile methodology, assisted by certain technologies, can rapidly increase Salesforce development.

 1. @3.50 — The typical challenges for managing large code bases in Salesforce are related to **source code management and collaborative development**. Although Salesforce (pre Salesforce DX) does offer a lot of tools and processes that help, some things are lacking.

 2. @5.20 — Coming from a Java background there were a number of challenges when first getting introduced to Salesforce development.

![](https://cdn-images-1.medium.com/max/2000/1*L9B8sTm3nWpdKsu7_engGg.png)

3. @5.40 — For ‘**Learning Salesforce Technologies’**: The Salesforce documentation and Salesforce community is very comprehensive and Trailhead is a fantastic resource for learning, so there wasn’t a challenge finding good resources to learn Salesforce.

4. @6.00 — For ‘**Organisation restrictions’**: As files aren’t local anymore (as is the case in Java development), how does one best manage the process of developing in an org with lots of other developers?

5. @6.20 — For ‘**Version Control’**: How to manage multiple sandboxes which have multiple developers working in them? How can you rollback changes that were made by mistake? How can developers work in a single org but in isolation?

6. @6.50 — For ‘**Automated Testing’**: Testing is so important. Manual testing won’t give the same quality of results as automated testing will. You need automated testing to facilitate end to end Salesforce development.

7. @7.20 — For ‘**Isolated Feature Development’**: How can one minimize conflict between developers and reduce the unwanted dependencies?

8. @7.45 — For ‘**Continuous Integration’**: How can one reintegrate code easily? If you have different versions of code and integrations in different environments, testing becomes much more complicated. Continuous integration is best practice.

![](https://cdn-images-1.medium.com/max/2000/1*14jaP6MXHLiQPAHlgzmdoA.png)

9. @8.30 — When you have lots of developers working on one org, you end up with lots of conflicts.

10. @10.30 — A solution for all of the aforementioned issues to create a collection of reusable orgs. A way to manage all your developer orgs is to maintain a list of the orgs and specify a set of the developer orgs for different purposes. One option is to use a wiki page that lists all the org details with a reservation system which helps to identify if an org is being used by users or not. The reservation details includes a link to the source code, the project name and who has reserved the sandbox.

![](https://cdn-images-1.medium.com/max/2000/1*vkFuK37HKl-ktk39KU7WLg.png)

![](https://cdn-images-1.medium.com/max/2000/1*csaXhJE6JEwB9WP9H68SHg.png)

11. @13.30 — You can use the Salesforce migration tool to facilitate moving your code from org to org. The force.com Salesforce migration tool leverages Apache Ant. [Apache Ant](http://ant.apache.org/) is a Java library and command line tool that automates software build processes.

![](https://cdn-images-1.medium.com/max/2000/1*LVrLw-0P-c-TniCqyCmfxw.png)

12. @13.40 — The 3 main functions of the migration tool are deploy (push), retrieve (pull) and undeploy (delete).

13. @14.20 — However, there are some minor manual steps before successful use of the migration tool can be achieved. These manual steps are around updating the wiki page list of all the Salesforce developer orgs in use.

![](https://cdn-images-1.medium.com/max/2000/1*z6UYQVZhMBW6Z4QqxvcCRw.png)

14. @15.30 — Some file manipulation tasks via ANT can then be used before the 3 main ANT functions are called.

![](https://cdn-images-1.medium.com/max/2000/1*vQChWCosA9wqDZThZfygyg.png)

For example, each developer org in the wiki page list will have a namespace and so when code is being deployed into an org, the generic code namespace is substituted to be the correct one. Also, when code is retrieved from a dev org, an automated task updates the dev namespace back to the generic one.

15. @16.20 — Trying to undeploy is slightly harder though. Destructive changes XML won’t always be successful due to the huge number of dependencies. For example, you’re trying to delete a field and a class at the same time but the field is referenced in the class. So ANT can be used to blank all code and then deletion of the code can be achieved as there won’t be any dependencies.

16. @16.40 — Then finally, the migration tool tasks can be initiated. Again, undeploying is the trickiest operation. Since trying to undeploy hierarchical rollups isn’t possible with destructive changes XML, deleting each rollup one by one can be automated by ANT.

![](https://cdn-images-1.medium.com/max/2000/1*BlQ407EX2jyRZ1AuCgHY-g.png)

17. @17.40 — Version control is very helpful for a number of reasons. Firstly, branching enables developers to isolate features. Secondly, version control also gives an audit as to who made what change when, and this is helpful for keeping track on changes. Thirdly, version control facilitates collaborative development as code can be shared very easily and also helps to prevent code from being lost, as you have a local copy of the codebase.

![](https://cdn-images-1.medium.com/max/2000/1*nVI-GeO5FdD4oPcN-NQIaQ.png)

There are many different version control vendors and they will generally offer the same core features.

18. @20.25 — Code in a version control system is just a collection of files and folders, with metadata. And the metadata is used by the system to track what happens to the files and to track changes that have been. When you create a branch, you are creating a clone of those files and folders. And extra metadata is generated to track this.

![](https://cdn-images-1.medium.com/max/2000/1*-mqdYJpHZlm_cJ-tLGRV6g.png)

19. @21.20 — Merging is when you bring the work that you have done on a branch back into its source. However, merging isn’t only one way as you can also merge from the source (the trunk) into a branch. This can create merging conflicts, as someone has to decide what is the right code to merge.

![](https://cdn-images-1.medium.com/max/2000/1*bbyp5KjVKE8UY1NE3qiiLg.png)

![](https://cdn-images-1.medium.com/max/2000/1*NZW3fYUdGb1Wmkb8guS03Q.png)

20. @22.00 — Automated version control is more advanced but incredibly beneficial.

Let’s say the developer pushed in code to a Salesforce developer org via ANT and is now making changes using an IDE. But how does one ensure that those changes don’t get lost? One can use the [Jenkins server](https://developer.salesforce.com/blogs/developer-relations/2013/03/setting-up-jenkins-for-force-com-continuous-integration.html), which is a continuous integration server. This means a server which periodically or on a schedule runs a job. So in this case, it will do an ANT retrieve job to pull the code from the Salesforce developer org and commits those files and folders to a version control system.

**Developer -> Salesforce -> Jenkins -> VCS**

![](https://cdn-images-1.medium.com/max/2000/1*W_f31aG0UnZ-cv83BzxbRw.png)

So the developer doesn’t actually have to do anything — all the scheduled jobs are happening in the background, which inputs their code into the version control system.

21. @23.00— However, this can get much more complicated as multiple developers could be working with multiple tools in multiple Salesforce environments.

![](https://cdn-images-1.medium.com/max/2000/1*jyepX3sXnm-ZBVVADCm9eg.png)

However, Jenkins knows which org corresponds to which branch in the version control system. So metadata will keep being pulled from the Jenkins server to the version control system (VCS) so changes don’t get lost.

22. @24.10 — Automated testing is needed to ensure that changed code or new code can be validated. This is achieved via Apex test code. And a good approach is to have a single org that is reserved for testing which has restricted access ensuring that only the automated test user account has access to it. Also, it is preferable to ensure that code isn’t persisted in this org.

This is achieved via migration tools and use a feature called ‘Test Deploy’. This packages all the test code, pushes (but doesn’t deploy) it into the reserved org, tests everything and ensures the code compiles. Then, once the package has been validated, all tests will be run in the org and once all tests have been run, the org will still be empty. Again, this is handled by Jenkins. Notifications of any test failures will be sent including logs.

![](https://cdn-images-1.medium.com/max/2000/1*F-OzkiHvn73YHqzQYx26vw.png)

The way that automated testing can be handled is that Jenkins retrieves all the metadata from the version control system, then runs a test deploy to the Salesforce testing org with the ‘Run All Tests’ flag, the Salesforce testing org sends a response to the Jenkins server with pass or fail for all tests. If all tests were passed, Jenkins marks the test as successful. Else, if there were some tests failed, then Jenkins will email the developer team with an email that contains the logs. The developers will then allocate the failures amongst each other and work to resolve the failures as soon as possible, as the longer a bug is left, the harder it is to resolve it.

![](https://cdn-images-1.medium.com/max/2000/1*Bx_oPJEs0QcDIqGgcNktww.png)

23. @27.20 — Isolated feature development can rapidly improve development speed. Isolated feature development is a modular approach that prevents multiple features being developer in the same org.

A good approach is 1 feature per development org and to use one branch in your version control system per dev org. And then, you can deploy the branch code into the dev org.

![](https://cdn-images-1.medium.com/max/2000/1*16z7qIWd_e_hZQcMFZpUkA.png)

24. @28.30 — This approach also helps to prevent accidental dependencies; and this saves a lot of time as trying to unpick code that has dependencies is tricky and not that straight forward. By adopting this modular ‘1 dev org per feature’ then if some code is not required anymore, then that branch can just be left alone and doesn’t get merged.

25. @28.50 — Also, because of the ‘1 dev org per feature’, there is a massive reduction of source code conflicts.

26. @29.05 — The trunk (aka master) is the source branch in SVN (a popular version control system vendor) and the trunk corresponds to the publishing org. So whenever a branch is about to be created, the trunk first retrieves all metadata from the publishing org so that the latest changes from that org are reflected in SVN.

![](https://cdn-images-1.medium.com/max/2000/1*pp6k2lS0EDOTKxyyZ0crtw.png)

27. @29.20 — After this, a branch is created in SVN and that branch is pushed to a reserved Salesforce dev org.

![](https://cdn-images-1.medium.com/max/2000/1*lb1yjm38ZEtiyY2XWscUQQ.png)

28. @29.45 — As the developers are working, the Jenkins server is retrieving all the changes that have been made and is pushing them onto the branch.

![](https://cdn-images-1.medium.com/max/2000/1*r8cp2FzrU5s4JqVYmWbt2w.png)

29. @29.55 — Once the feature is ready, the branch will be merged back to trunk. At this stage, the metadata is only in SVN and so will now be deployed to the Salesforce publishing org. At it’s at this stage that the Salesforce dev org can be undeployed, so that it can be used again as a blank slate.

![](https://cdn-images-1.medium.com/max/2000/1*9_z8_6Lep89DkDxkv4HHSg.png)

![](https://cdn-images-1.medium.com/max/2000/1*uQP9TbOaGhBmRed8KmAHmw.png)

30. @30.00 — Continuous Integration as an approach does not want very different branches to be sitting out on their own or branches that are being worked on but aren’t be synced, because this can result in difficult or incompatible merging. It is highly preferable to have the changes that you are making synced up across your branches frequently.

From a Salesforce ISV perspective, a number of Salesforce orgs are used and if a bug fix has been made, then it will need to be propagated to all of these different orgs. Jenkins does this automatically but only if there are no conflicts in a merge and only if there are no test failures in the branch that is being merged.

![](https://cdn-images-1.medium.com/max/2000/1*0RlrWMjmNAcNlP8-i_pXUw.png)

![](https://cdn-images-1.medium.com/max/2000/1*pzx3unVEBoCamgT5XMRqMw.png)

31. @32.20 — This is achieved automatically with Jenkins via a number of different ANT tasks.

32. @37.00 — A link to some tools that help are:

![](https://cdn-images-1.medium.com/max/2000/1*9lMfJxMLCjSq5HfXABRtNg.png)
