---
layout: post
title: Einstein Bots: Build a CRM Powered Chatbot
tags: [Chatbots, Einstein]
---

# Einstein Bots: Build a CRM Powered Chatbot

*SalesforceSummaries.com is a publication that delivers the ***key*** insights
from Salesforce YouTube videos. We aim to be the
*[getAbstract.com](https://www.getabstract.com/en/)* of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

**Introduction:**

In this presentation, you will learn more about Salesforce Einstein powered
chatbots and how they can be used to increase productivity.

**Details: ‘**[Einstein Bots: Build a CRM Powered
Chatbot](https://www.youtube.com/watch?v=i9TbAkRNNa0)’

**Presenter: **George Hu, Jonathan Rico

**Details: **20 minutes

**Key Terms:** Einstein, Chatbots

![](https://cdn-images-1.medium.com/max/800/1*bpmEJHx_HkPnDglzfpfyqg.png)

1.  @1.10 — Einstein Bots is your digital support agent. It’s designed for simple
tasks and offers 24/7 support. Einstein Bots are not designed for replacing
agents or long conversational engagements.

![](https://cdn-images-1.medium.com/max/800/1*Lrd0pvZHQN2h5oNy7F3heA.png)

2. @2.20 — The design principles of Einstein Bots are:

*Don’t pretend to be human*

*Leverage integrated data to provide user value*

*Clearly state the capabilities of the bot*

3. Escalate to an agent if the bot is unable to assist.

![](https://cdn-images-1.medium.com/max/800/1*iA47ecKavdJ2UYPtqioH_A.png)

4. @3.30 — So how does Einstein Bots work?

5. @3.50 — There are 2 types of customer interactions.

Menus are 100% accurate but offer limited coverage whereas text input is
conversational but requires training.

6. @5.00 — The first type of interaction is when the customer makes a request.
When a customer asks a question, Einstein’s Natural Language Processing (NLP)
attempts to map that to an intent. An intent is always linked to a dialog, and
the dialog is where you can script the response.

7. @5.50 — The second type of interaction is when Einstein Bot responds to a
request. For example, the bot may ask the customer ‘what is your email
address?’. The response from the customer is validated (the data type in the
customer’s response is validated).

8. @8.05 — In the demo, an example of a menu interaction looks like this:

In this example, the bot is being leveraged in [Live
Agent](https://trailhead.salesforce.com/en/modules/service_live_agent/units/service_live_agent_get_started).
Also, in this example, the dialogue is text input (as the customer inputs some
text; which has an intent).

9. We can leverage Twilio integration with Salesforce to understand more about
who the customer is; which will help us to provide an improved customer service
experience.

Now that the customer has verified his/her phone, using Apex, Salesforce can
look up the phone number that was input into the ‘slot’ (data storage) and
return the customer detail.

In Salesforce, we can now see that a new Food Order record has been created.

Now that the dialogue has completed, with the customer having ordered pizza, the
Food Order record in Salesforce has been updated now to ‘In Progress’.

10. @11.55 — You can teach Einstein Bot to deliver promo codes to customers. By
navigating to Setup > Objects > Einstein Bot, you can see a list of all the bots
in your Salesforce org. By clicking on a record, you can see the bot performance
information:

By navigating to Dialogs, you can see where all the logic for how the bot should
interact with customers is stored:

By navigating to Promo code, you can see all the ways which you can manage the
promo code process:

With bots, we only care about the conversation. Once the data is in your
Salesforce system from the conversation, that’s when you can apply automation on
those records (process builders, invocable methods, apex, flows, workflow rules
etc).

11. @17.05 — Before activating a bot, you can use the helpful ‘preview’ function
to test the bot.
