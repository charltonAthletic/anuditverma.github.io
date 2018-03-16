---
layout: post
title: VS Code IDE for Eclipse Users
tags: [Salesforce DX, VS Code IDE]
---

## VS Code IDE for Eclipse Users

*SalesforceSummaries is a publication that delivers the **key** insights from Salesforce YouTube videos. We aim to be the [getAbstract.com](https://www.getabstract.com/en/) of Salesforce tutorial videos. These publications will save you time as you keep up to date with the latest technological changes within the Salesforce ecosystem.*

**Introduction:**

With the release of Salesforce DX since Winter ’18, there has been a shift in the de-facto development tool from [Eclipse ](https://www.eclipse.org/ide/)to [Visual Studio Code](https://code.visualstudio.com/). This summary details the differences and similarities between the two tools.

**Details:** ‘[VS Code IDE for Eclipse Users](https://www.youtube.com/watch?v=Ez5ITRJBres)’

![](https://cdn-images-1.medium.com/max/2000/1*CswBkRybokSU475bFIVyCQ.png)

**Presenter**: Gunnar Wagenknecht

**Time:** 20 minutes

**Key Terms**: VSC, Eclipse IDE, debugging, extensions, source editor

**Summary:**

 1.@0.30 — This session will discuss ‘*what is it like switching from Eclipse to Visual Studio Code editor?*’. The differences and similarities between the two tools will be highlighted in detail.

 2.@0.45 — The motivation for this is that since the release of Salesforce DX, the development tool of choice switches from Eclipse to Visual Studio Code.

 3.@2.10 — Visual Studio Code **is not** Visual Studio. VSC is a light weight source code editor created by Microsoft to make it easier and more efficient to edit source code. It is not a fully-fledged IDE. It is free, open source and runs on Mac, Linux and Windows.

 4.@3.05 — Visual Studio Code (VSC) has multiple themes available, instead of just 2. By default, it is dark. There are far more themes in Visual Studio Code than Eclipse.

 5.@3.50 — The UI for VSC is radically different from Eclipse. The UI is far more standardised and simplified. There are no more custom perspectives rather, there is just the side bar, panel and the editors pane.

![](https://cdn-images-1.medium.com/max/2000/1*1DX_uXLAR1d2619XKeLHQA.png)

6.@4.55 — The extension marketplace is built right into VSC. It is through the marketplace that you install Salesforce DX.

![](https://cdn-images-1.medium.com/max/2000/1*NsShjQMQlLQLZsqCaveyjg.png)

7.@6.00 — This is in contrast to Eclipse because that IDE comes with different packages and some of the packages by default did not have the marketplace enabled. Also, the amount of extensions available in VSC is far more than Eclipse.

8.@6.22 — There are no more dialogs or wizards, with VSC.

![](https://cdn-images-1.medium.com/max/2000/1*FTaMWB6imEdn3V09rVtp8A.png)

9.@8.00 — You no longer need to create particular workspaces, with VSC. You simply clone a repo from Git or another source control system, and you open up the folder with VSC and the installed extensions that pertain to the code in the folder will be available to use.

You do not need to do all the prerequisite steps that you needed to do in Eclipse to get a particular project and its extensions working. With VSC, ‘it just works’.

![](https://cdn-images-1.medium.com/max/2000/1*WNPFdwAbQjSmFPpIZSpTCw.png)

10.@9.10 — A very common command that you will use in VSC is ctrl/cmd+shift+P

![](https://cdn-images-1.medium.com/max/2000/1*WMXkeWjHDyS7wr4LSDDTfw.png)

![](https://cdn-images-1.medium.com/max/2000/1*HkBbfGa-28ADxeIm5WQLaQ.png)

So, this is similar to how ‘Quick Access’ in Eclipse works.

11.@10.40 — Similarly, you can use the ctrl/cmd+P command to quickly navigate to a file. This makes working with your workspace very efficient. This is similar to the ‘Open Resource’ function in Eclipse.

![](https://cdn-images-1.medium.com/max/2000/1*lXO2CuON6F7wYOhSvGA1_g.png)

![](https://cdn-images-1.medium.com/max/2000/1*YyAknbStV34xs8Xnc8gPrA.png)

12.@11.40 — Using the ctrl/cmd+space command in VSC will bring up IntelliSense; which is like the Eclipse ‘Content Assist’. This is code completion function based on actual analysis of the current file in your workspace. In order to have code completion in VSC for Apex, you need to have the Salesforce DX extension installed.

![](https://cdn-images-1.medium.com/max/2000/1*npRBwPoTHdpIahZKyKKGaw.png)

![](https://cdn-images-1.medium.com/max/2000/1*AXyXrqxK5k8gS4kcKqC4zw.png)

13.@12.25 — The ‘Go to symbol in File’ in VSC is similar to the Eclipse Quick Outline function. This enables you to quickly navigate to a particular part of the file.

![](https://cdn-images-1.medium.com/max/2000/1*jZzGVi2XLWu2bBR4Cr-KeQ.png)

14.@14.00 — Even though VSC is an editor and not a true IDE, the debugging functionality is actually true IDE tooling. You can connect to a debugger and set break points. Once a break point is hit, you can step through the code and you can inspect the variables and review the call stack information.

All the debugging functionality in Eclipse is represented in a very similar fashion in VSC.

In our case, we connect to a debugger by connecting to a Salesforce scratch org.

![](https://cdn-images-1.medium.com/max/2000/1*gr_x7NBNStA9tKMQBuGjbQ.png)

15.@16.00 — A good resource to learn more about Salesforce DX and VSC is [here](https://github.com/forcedotcom/salesforcedx-vscode/wiki/Tips-and-Tricks). Also, the links below offer more helpful information.

![](https://cdn-images-1.medium.com/max/2000/1*KxxWV0-HT0BBOAk9W0gckA.png)
