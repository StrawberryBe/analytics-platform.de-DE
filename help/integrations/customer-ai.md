---
description: Find out how AEP Customer AI integrates with Workspace in CJA.
title: Integrate Customer AI with CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 77b253390dafb27228995f339d138eb9f4fa2c56
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 8%

---

# Integrate Customer AI with CJA

>[!NOTE]
>
>This functionality will be released on May 25, 2022.

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)

Mithilfe von Einflussfaktoren kann Customer AI vorhersagen, was ein Kunde wahrscheinlich tun wird und warum. Darüber hinaus können Marketing-Experten von Prognosen und Einblicken durch Customer AI profitieren, um Kundenerlebnisse durch Bereitstellung der am besten geeigneten Angebote und Botschaften zu personalisieren.

Customer AI works by analyzing one of the following datasets to predict churn or conversion propensity scores:

* Adobe Analytics data using the Analytics source connector
* Adobe Audience Manager data using the Audience Manager source connector
* Experience Event (EE) dataset
* Consumer Experience Event (CEE) dataset

Customer AI integrates with Customer Journey Analytics (CJA) to the extent that Customer AI-enabled datasets can be leveraged in data views and reporting in CJA.

## Workflow

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA.

### Step 1: Download Customer AI scores

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores)

### Step 2: Define Customer AI inputs and outputs

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en)

### Step 3: Configure a Customer AI instance

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en)

### Step 4: Set up a CJA connection to Customer AI datasets

[](/help/connections/create-connection.md) These datasets appears with the &quot;Customer AI Scores&quot; prefix, as shown here:

![](assets/cai-scores.png)

Each prediction, such as &quot;Likelihood to upgrade account&quot; equates to one dataset.

Here is an example of a XDM schema that CJA would bring in as part of an existing or new dataset:

![](assets/cai-schema.png)

(Note that the example is a profile dataset; the same set of schema object would be part of an Experience Event dataset that CJA would grab. The Experience Event dataset would include timestamps as the score date.) Every customer scored in this model would have a score, a scoreDate, etc. associated with them.

### Step 5: Create data views based on these connections

[](/help/data-views/create-dataview.md)

### Step 6: Report on CAI scores in Workspace

Here is an example of a Workspace project with CAI data that shows score dates in a stacked bar chart:

![](assets/workspace-scores.png)

