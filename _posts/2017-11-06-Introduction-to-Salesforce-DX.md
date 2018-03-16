---
layout: post
title: Introduction to Salesforce DX
tags: [Development Lifecycle, Salesforce DX, Source development]  
---

## Introduction to Salesforce DX

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

With the release of Salesforce DX, Salesforce now offers an incredibly easy and end to end development process.

**Details:**

![](https://cdn-images-1.medium.com/max/2000/1*ALPRVB6pYkamwaWnOx4i3A.png)

**Presenter: [**Wade Wegner](http://www.wadewegner.com/2017/09/deploy-to-salesforce-dx/)

**Date: **July 3rd 2017

**Time: **40 minutes

**Key Terms:** Salesforce Command Line (CLI), Salesforce DX, Continuous Integration

**Summary:**

 1. @0.40 — It has taken about 2 years to develop Salesforce DX.

 2. @2.15 — The journey of SalesforceDX began with understanding how developers are building software on the force.com platform. From these investigations and conversations, Salesforce began to ask how they could define and apply the software development principles that they and the Salesforce community want to the force.com platform.

![](https://cdn-images-1.medium.com/max/2000/1*2rrHKsGXDx5mkukDAfuQrA.png)

3. @2.50 — **Everything is driven from source code. **The first principle is that developers live in code and live in source. And so Salesforce want to make sure that the development experience revolves around the source. The source of truth for the app that you’re building is the source that you have in your file system, the source that you’re committing to your version control system.

4. @3.30 — **Environments are easily created and disposable.** The second principle, that follows on from the first, is that the orgs that you create (containers of the source), are easy to create and dispose of. The notion of ephemeral environments is a very important principle.

5. @4.20 — **Development is based on open standards and extensibility**. You can use the tools that you want to use.

6. @4.30 — **Processes and tools facilitate continuous delivery.** How does Salesforce make it easier for developers to implement continuous delivery? This was a big question that Salesforce DX answers.

7. @5.00 — **Development is organized around team collaboration. **How can Salesforce make it easier for a team of developers and admins to work together in a way that leads to success?

8. @5.15 — **Metadata and code is modular. **Salesforce DX helps to modularize specific pieces so that you have a code base which reflects what you’re building on, instead of the ‘*happy soup’*; which refers to where everything lives in the org and there isn’t a notion of how the code and customizations that you’re working on relate to the specific app that you’re building.

9. @6.00 — **Flexible packaging supports agile distribution model. **Salesforce DX makes it easier to distribute changes across environments. With the next generation packaging, you can use Salesforce DX to deploy your modularized code from your file system or version control system to other environments.

10. @6.40 — These aforementioned concepts aren’t new — they are common to many other development environments and programming languages. However, with the introduction of Salesforce DX, these concepts can be implemented from the same single tool for the first time with the Salesforce platform. [Compare this to how implementing continuous integration was before Salesforce DX](https://medium.com/salesforcesummaries/techniques-and-tools-to-improve-the-salesforce-development-cycle-pre-salesforce-dx-a31edb703a1e); which was much more complex and depended on more tools.

11. @7.05 — Salesforce DX is a set of tools and practices that can help to facilitate collaboration and continuous integration.

![](https://cdn-images-1.medium.com/max/2000/1*sVMRZMJ9yDnyF_PDnLNwdA.png)

12. @7.25 — **Source-driven development: **It starts with your source; which is the source of truth for your application in your file directory or version control system instead of relying on the metadata that resides in an org.

13. @7.50 — **Team collaboration: **By enabling source-driven development, this in turn facilitates team collaboration and ease of using version control systems to track file changes and branching.

14. @8.05 — **Continuous integration and delivery: **The aforementioned points enable continuous integration and delivery; which results in higher quality code and more automation.

15. @8.35 — **Open and prescriptive: **Salesforce remains flexible enough so that you can adopt tools that you want.

![](https://cdn-images-1.medium.com/max/2000/1*KonzorcwO6u7AFWNDf3CtQ.png)

16. @9.20 — Salesforce have focused on ‘*how can we make it better to express all metadata through an API and how can we make it easier for developers to synchronize source locally to environments?*’. So source-driven development approach isn’t just a better expression of source, but it’s a set of updated APIs that make it faster and easier to deploy source to an org so that you’re not waiting behind a metadata deploy. So a huge amount of work in the background has been done to ensure source-driven development.

17. @10.30 — To facilitate the ephemeral environments, Salesforce have introduced Scratch orgs. Scratch orgs can be created very quickly and you can load sample data and source into this org, so you can test it in many different ways very quickly. You can then load this source into your file system and/or version control system and then delete the scratch org.

18. @11.40 — The Salesforce CLI has been optimized to work with Salesforce DX in working with source-driven development and scratch orgs but it also works with your test sandboxes and production org too because a lot of the existing APIs and tools have been consolidated into Salesforce DX. The Salesforce CLI can also be used to create shell scripts to automate tasks.

19. @12.40 — The force.com IDE has been updated to work with Salesforce DX.

20. @14.15 — You can use the continuous integration process of your choice.

21. @14.25 — Packaging 2 is a smarter way to deploy changes to and from different environments. More information on this is [here](https://releasenotes.docs.salesforce.com/en-us/summer17/release-notes/rn_sfdx_pack2.htm).

22. @15.40 — Once you get up and running with Salesforce DX, you’ll find that you are able to implement continuous delivery more frequently and easily.

23. @16.30 — As you become more proficient with continuous integration and continuous delivery, you’ll be able to leverage the different types of sandboxes faster and more easily, too.

24. @18.00 — The image on the left shows all your metadata in a container; which is comprised of lots of different changes that have been made over time. With Salesforce DX, the specific components that you want can be taken out of the ‘happy soup’ and organised and built upon can be implemented easily and quickly into a single (modular) unit of work. This is shown from the image on the right. Salesforce DX facilitates this modularizing of your code because you can take and build the components that you want (the codebase of your app) instead of having everything in a single container of work (the codebase of your entire org).

![](https://cdn-images-1.medium.com/max/2000/1*k-orMKoMMfeuIxDgbyZdVQ.png)

25. @18.50 — When you install the Salesforce CLI, you will get the binary Salesforce DX file. So you can input the command:

sfdx force –-help

which will output a list of available commands:

![](https://cdn-images-1.medium.com/max/2000/1*3NfFgbWyaz8hFhqr2VSCrw.png)

The Salesforce CLI has been built on the same foundations as the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli). So if you have hybrid services that require Salesforce CLI and Heroku CLI, you’ll notice that they work very well with each other.

There are a lot of commands available in the Salesforce CLI. You can use commands like force:apex, to use execute anonymous or force:data to create a SOQL query.

26. @20.30 — To create a project, use the command:

sfdx force:project:create –n Demo1

This create a sfdx project with the name ‘Demo1’. You use the –n command to give your project a name.

![](https://cdn-images-1.medium.com/max/2000/1*q6ZGHm_NXUfZ2vIUmC-c8Q.png)

This quickly scaffolds a project; which has a README file and some JSON files too.

![](https://cdn-images-1.medium.com/max/2000/1*Hv_oDflgaBi_CPvtwLYEyg.png)

27. @20.55 — The sfdx-project.json file is a very important file as it has some key attributes which describe the project which is being built.

![](https://cdn-images-1.medium.com/max/2000/1*I2M80DNL3N6mUgmk9Rkm0g.png)

28. @21.00 — The sfdcLoginUrl attribute can be overridden if required, to point to another end point. Also, the sourceAiVersion can be changed to target a different API version.

29. @21.10 — The ‘packageDirectories’ is linked to the force-app folder. You can re-name the force-app folder whatever you like, though.

30. @22.00 — Another important .json file is in the config folder of the project and is called project-scratch-def.json.

![](https://cdn-images-1.medium.com/max/2000/1*K42-4NCGWj9njABRedI2Zg.png)

Not only can you create and delete scratch orgs, but you can also shape them so that they have the features and org preferences that you want; especially for Salesforce ISV partners.

31. @22.40 — You can create many different config files (up to 100) and when you create a scratch orgs, you pass in the config files so that the features and org preferences that you want are turned on. From a continuous integration and testing perspective, this is a *huge* time saver as you don’t need to login to a hundred different orgs to test your code but rather you can create a script to do this for you. There are many different attributes in config files and the [documentation](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_scratch_orgs_def_file.htm) is an excellent resource.

32. @23.30 — In the context of a project, there are 2 things that you care about. The first is the Dev Hub. A Dev Hub is the environment which you’ll create all the scratch orgs in. Think of it like a parent-child org (scratch orgs are children to the Dev Hub). There are limits as to how many scratch orgs can be associated to a single Dev Hub. Through the Dev Hub you can see the different metadata for all the scratch orgs. The Dev Hub is your Production environment. To set it up, navigate to Setup | Dev Hub | Enable.

![](https://cdn-images-1.medium.com/max/2000/1*0yumQ1R5OFR3sIKR61IIvA.png)

33. @25.00 — If you are an ISV, you won’t have a Production org but you will have a Business org and so the Business org will become the Dev Hub.

34. @25.20 — If you don’t want to enable this in Production, you can leverage a Trial org; which will give you a limit of up to 40 scratch orgs to relate it to.

35. @25.40 — Once you have setup your Dev Hub and scratch orgs, you can input the DX command: **sfdx force:config:list **to see your Dev Hub and related scratch orgs in the command line.

![](https://cdn-images-1.medium.com/max/2000/1*0lqNylpoZSbSGFVSW7BE7g.png)

36. @26.20 — Another helpful DX command is **sfdx force:lightning –help**; which outputs the list of force:lightning commands that can be leveraged. The –help command will give you a lot of information.

![](https://cdn-images-1.medium.com/max/2000/1*p4MJgGirCxY_cznkjynmpg.png)

37. @27.00 — There is a lot of code scaffolding functionality with DX, in the sense that you can easily create a Lightning component and then have it as a child component of a particular Lightning app. And you can do this all with one command. For example: **sfdx force:lightning:component:create –n DemoComponent –d force-app/main/default/aura** is the single command and this creates a new Lightning component in the force.app of the Aura directory.

![](https://cdn-images-1.medium.com/max/2000/1*ZCrkiqBr89wXqPa_R0sqIA.png)

38. @27.10 — Having input this command, as per the screenshot below of the IDE that is being used, the **local** metadata has been created for this Lightning component.

![](https://cdn-images-1.medium.com/max/2000/1*vAhlEWYeDrQwCYM2WV5ZQA.png)

39. @27.15 — To push this local metadata into the scratch org that was created, one can use the command **sfdx foce:source:push**

![](https://cdn-images-1.medium.com/max/2000/1*at4C5-Uw8ImsejZBu2VKKw.png)

The semantics are very similar to Git. Once you push the source from local to your scratch org, you can test it.

40. @27.35 — To open up the scratch org, you can input the command **sfdx force:org:open** from the scratch (project) directory that was created.

![](https://cdn-images-1.medium.com/max/2000/1*J5keWSCSV-5Uo_do96LkBQ.png)

41. @27.50 — One of the very helpful things about scratch orgs is that you don’t need to configure a username or password. SF DX auto-creates a username and it manages the Access and Refresh encrypted token. So when you input the **push **or **open** command, SF DX is using the information stored in the CLI to authenticate logging into the respective scratch org. When you start to create aliases for the different scratch orgs, you will find this interactivity even more helpful and efficient.

42. @30.00 — Another interesting command is **sfdx force:source:status**

![](https://cdn-images-1.medium.com/max/2000/1*_LFNw_qWgmVO1SGnfn11SA.png)

The powerful part of this is that as you’re making changes locally, you don’t have to push all your source all the time. DX knows what you have changed and will only push those changes. With change sets, you have to tell Salesforce what has changed whereas now, all the changes are being tracked and so DX does this for you. Also, when you input a pull request — **sfdx force:source:pull — **Salesforce will only pull the metadata components that have changed from the environment.

43. @31.00 — The [sfdx-dreamhouse](https://github.com/forcedotcom/sfdx-dreamhouse) sample app was developed by Developer Evangelism in 2016 and the force components were put into Salesforce DX.

The first thing that is interesting about this is code modularity as seen by the multiple folders you can put under the src parent folder. The idea is that you can organise your code base in a more efficient way. Some customers have created ‘ApexTest’ folders were all the Apex tests are instead of being stored in a single codebase folder alongside other non-test classes.

![](https://cdn-images-1.medium.com/max/2000/1*Qrwc-rU6wCXC0Na8O2lk2Q.png)

44. @32.20 — As you can see from the .json file, there are different paths for the different folders in the src parent folder. And the ‘default’ attribute must be defined, which means that if you don’t explicitly reference the path with your pull request, then the pull request will load to the default package directory.

![](https://cdn-images-1.medium.com/max/2000/1*QuQzBdARegzaxV5lDcOOhw.png)

45. @33.00 — Scratch orgs don’t have data because Salesforce want scratch orgs to perform as quick as possible. However, you need test data in order to run tests successfully. So to accommodate this, there are 2 exciting commands with Salesforce DX.

One command is to do an sObject tree import. Sample data, represented as JSON, can be imported into a scratch org. For example: **sfdx force:data:tree:import –plan data/sample-data-plan.json**

![](https://cdn-images-1.medium.com/max/2000/1*l5KIllvj0hXYvuQKzRAc2A.png)

46. @34.50 — You can see from the file **sample-data-plan.json** that this file references the other JSON files; which actually have the data.

![](https://cdn-images-1.medium.com/max/2000/1*Bpy7GW4MYKo1E8p0dvUUXA.png)

And each of those files have the sample data.

![](https://cdn-images-1.medium.com/max/2000/1*8_DUji8iUQdXlnPCduPHaA.png)

47. @35.10 — The CLI is great for running tests. For example, **sfdx force:apex:test:run –help **will show you a lot of different capabilities for testing. You can input sfdx force:apex:test:run –r human. The **–r human** input means the result format will be ‘human’ (i.e. easy to read). This will execute all of the Apex tests which have been pushed to the scratch org.

![](https://cdn-images-1.medium.com/max/2000/1*aEBx3pfWr3zBK3R3NGCsLw.png)

48. @35.50 — The CLI has been built for developers but also for build automation. Every command in the CLI will return a result in .JSON if you add an annotation of — json

This is exciting because you can a CLI command, pipe it and then use tools like [jq](https://stedolan.github.io/jq/) to parse and extract the details that you want from that response.

49. @37.00 — There are a few ways to get up and running with Salesforce DX. You can enable the Dev Hub and/or sign up for a Trial org and furthermore, you can look at the brilliant Trailhead badges on this topic.

![](https://cdn-images-1.medium.com/max/2000/1*TMGX08cdX-CdOUvooeq6Ww.png)

![](https://cdn-images-1.medium.com/max/2000/1*LAuNOxvzlL6o3a3KIaWocA.png)
