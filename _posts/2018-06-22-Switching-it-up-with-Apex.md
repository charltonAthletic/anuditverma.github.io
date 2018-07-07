---
layout: post
title: Switching it Up with Apex
tags: [Apex, Switch statement]
---

# Switching it Up with Apex

*SalesforceSummaries.com is a publication that delivers the ***key*** insights
from Salesforce YouTube videos. We aim to be the
*[getAbstract.com](https://www.getabstract.com/en/)* of Salesforce tutorial
videos. These publications will save you time as you keep up to date with the
latest technological changes within the Salesforce ecosystem.*

**Introduction:**

In this presentation, you will learn more about the latest additions to the Apex
programming language and Apex compiler.

**Details: **‘[Switching it up with
Apex](https://www.youtube.com/watch?v=cusUVO9IQjc)’

**Presenter: **Chris Peterson

**Details: **32 minutes

**Key Terms:** Switch statement, Apex, syntax, compiler

![](https://cdn-images-1.medium.com/max/800/1*zwgBpYFbqOFNpGxwILW3gQ.png)

1.  @1.05 — Apex has a new compiler since the Spring ’18 release. An insightful
video of this can be found [here](https://www.salesforce.com/video/303091/).
This is the primary reason that new language constructs, like the switch
statement, have been made possible in Apex.
1.  @3.05 — The switch statement was chosen because it was a hugely requested
feature.

![](https://cdn-images-1.medium.com/max/800/1*onGKvLxMrXYsfWhdYMPHzQ.png)

3. @5.00 — There were many values and obstacles for using switch.

Helping to reduce code duplication was one of the most compelling values.

4. @7.00 — The ‘happy path’ for using switch can be found below. Single or
multiple literals can be used.

5. @13.00 — A new ENUM has been added since Spring ’18 that stores all the
trigger contexts, called Trigger.operationType.

6. @14.05 — This is what an old trigger handler looks like:

This is quite verbose. Using the switch statement, this can be made much more
concise.

The three parameters are the old rows, new rows and the new ENUM called
System.TriggerOperation; which exposes all the possible combinations of boolean
variables; enabling you to collapse all your if/else logic into a single
statement.

7. @15.30 — Implicit casting is also seen here. There is polymorphism here from
the ‘when clause’ in that if the firstRow is of the Account sObject, then assign
that to Account variable ‘acct’. There are no casts or sObject type checks that
are required now. This is a verbose saving feature that has been made possible
with the new compiler (tightly coupled with the database layer).

8. @18.25 —

The multi comma separated literals for the when conditional block is concise —
just note that literals can only be accommodated once. In this example, the
second ‘2’ won’t be allowed. Constants cannot be used yet as literals.

9. @19.20 — Due to the advanced compiler, the following additions to Apex have
been made:

The original Idea for contains and indexOf is
[here](https://success.salesforce.com/ideaView?id=08730000000b9RZAAY).

Enhancements to the [RecordTypeInfo
class](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_class_Schema_RecordTypeInfo.htm)
has also given a lot of benefit, as one can now get the API name of the record
type whereas before, only the record type name was available with this class.

10. @21.30 — A lot of work is being done to speed up tests during deployment.

One of the most compelling improvements is that Salesforce are planning on a
‘skip code coverage’ option. This will make it easier and faster (by 20%) to see
if any change(s) that you made broke some tests.

11. @23.00 — Another performance improvement is in ‘compile on deploy’. After
you make changes to the UI or metadata deployments or packaging operations, you
might notice that the next request that runs Apex might run a bit slower.

When a change is made to your Apex org (schema, enabled features etc), it
invalidates the compiler output to make sure it isn’t running Apex bytecode that
is no longer valid for the new shape of your org. Previously, the Apex bytecode
cache would be ‘flushed’ and rebuilt on the next use; which meant that end users
would get a performance hit as the compiler would rebuild the Apex bytecode
cache. This doesn’t scale very well, especially with large organizations.

So, to alleviate this, the compile on deploy will compile the Apex and commit
the bytecode upon a change to a meta-data deployment. This offers a high
performance benefit.

This will be turned on for all production orgs, always from Summer ’18.

12. @26.00 — There is a lot of work being done by Salesforce to enhance secure
development.

FinancialForce have opensourced a library —
[https://github.com/financialforcedev/fflib-apex-common](https://github.com/financialforcedev/fflib-apex-common)
— that enables easy CRUD checks with a single method call, enables FLS
enforcement and also allows you to disable FLS checks.

