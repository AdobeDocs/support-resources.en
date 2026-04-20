---
title: Experience League support release notes
description: The latest release information on the Experience League support.
feature: Release Notes
exl-id: 875ad82e-56b5-4d58-9237-bb7aa0d9ffaf
---
# Experience League support release notes

These release notes contain updates to the Experience League support and include:

![New](../adobe-support-tools-guide/assets/new.svg) New features
![Fix](../adobe-support-tools-guide/assets/fix.svg) Fixes and improvements
![Bug](../adobe-support-tools-guide/assets/bug.svg) Known issues

## April 27, 2026 

### Support Insights in case creation form for Adobe Commerce

1. Support Insights automatically surfaces detected issues in your environment. It includes performance slowdowns, security risks, and misconfigurations using telemetry data from APIs, New Relic, and Splunk. This helps you identify and resolve issues faster.

1. Support Insights are currently available exclusively for Adobe Commerce on Experience League Support during the case creation process. 

1. Insights are scoped to your specific project instance, ensuring the information surfaced is relevant to your environment. 

1. Insights include a detailed description, steps to resolve, root cause analysis, and links to relevant Adobe documentation. 

1. Users can submit feedback on individual insights to help Adobe continuously improve the accuracy and relevance of Support Insights.

### Escalation Management

1. Escalation Management on Experience League Support provides a new set of self-service capabilities to give you greater visibility into your support cases with a streamlined, system-driven workflow built around your needs. 

1. Get an instant, AI-powered snapshot of your support case including current status, next steps, key updates, and a full case summary without having to read through the entire case history.  

1. A new Get Help option offers a centralized experience for customers to collaborate seamlessly with Support teams—covering troubleshooting, callback requests, self-service issue urgency updates, and requests for management attention. 

1. **[!UICONTROL Request Callback]** – For P1 cases, request an immediate callback from a Technical Support Engineer directly from your case list. Simply provide your phone number and a brief description of your issue, and a support engineer will reach out as soon as they are available.

1. **[!UICONTROL Schedule a Troubleshooting Call]** – For P2 and P3 cases, schedule a web meeting with a Technical Support Engineer at a date and time that works for you. A Microsoft Teams screen share session will be confirmed with all meeting details upon booking. 

1. **[!UICONTROL Change in Issue Urgency]** - For P3 and P4 cases, self-service escalate your case priority from P4 up to P2 by providing a brief justification. Your case will be immediately reassigned for priority handling upon submission. 

1. **[!UICONTROL I Have an Issue Not Listed]** – For all priorities, raise an escalation for any scenario not covered by the above options such as prolonged time to resolution, critical business impact, or unclear case ownership and have it routed directly to a support engineer. 

## April 8, 2026 - Expansion of Request for Callback feature 

The Request for Callback feature is now available for Marketo product users.

## March 30, 2026 – Enhanced Case Form

![New](../adobe-support-tools-guide/assets/new.svg) The case form is organized into a guided flow that helps users understand what information is required at each stage:

- [!UICONTROL Product Selection]  
- [!UICONTROL Problem Description]  
- [!UICONTROL System Information]  
- [!UICONTROL Priority and Business Impact]  
- [!UICONTROL Contact Information & Watchers List]
- [!UICONTROL Review and Submit]

![New](../adobe-support-tools-guide/assets/new.svg) Added automatic title generation based on the **[!UICONTROL Issue Description]**, allowing the title to be generated automatically while still giving users the option to edit it before submitting the case.

![New](../adobe-support-tools-guide/assets/new.svg) Added an **[!UICONTROL "Is the issue reproducible?"]** option to help improve troubleshooting. If users select **[!UICONTROL Yes]**, they are prompted to provide the steps taken to reproduce the issue. If *No* is selected, users can proceed with the case submission.

![New](../adobe-support-tools-guide/assets/new.svg) Added an option to indicate whether any recent changes were made to the environment or instance. If **[!UICONTROL Yes]** is selected, users are prompted to provide additional details about the changes.

![New](../adobe-support-tools-guide/assets/new.svg) Added **Additional [!UICONTROL Environment Context] Fields** for entitled products to capture critical details:

- **Marketo**
    - Munchkin ID
- **Adobe Target**
    - Activity Name
    - Site URL(Tags Property Name)
- **Adobe Analytics**
    - RSID
    - Site URL(Tags Property Name) / cURL
    - Workspace Shortlink
- **Adobe Journey Optimizer (AJO)**
    - Journey ID or URL/Campaign ID or URL/Channel ID or URL/Offer Decisioning ID or URL
    - Example profile
    - Sandbox Name
- **Real-Time Customer Data Platform (RTCDP)**
    - Affected Component ID (Destination ID/Audience ID/Dataset ID/Dataflow ID/Merge Policy ID/Schema ID/Source ID/Batch ID)
    - Example profile
    - Sandbox Name
- **Adobe Experience Platform (AEP)**
    - Affected Component ID (Destination ID/Audience ID/Dataset ID/Dataflow ID/Merge Policy ID/Schema ID/Source ID/Batch ID)
    - Example profile
    - Sandbox Name       
- **Customer Journey Analytics (CJA)**
    - Workspace project URL
    - Connection ID / Error message / Code
    - Data View ID

![New](../adobe-support-tools-guide/assets/new.svg) Added an **AI-Driven [!UICONTROL Recommendations Panel]** to display helpful guidance without interrupting the case creation flow.

![New](../adobe-support-tools-guide/assets/new.svg) Added a **[!UICONTROL Review Summary]** step to provide a consolidated view of all entered information and allow users to:

- Review case details in one place  
- Navigate back to previous steps to make edits  
- Return to the summary without losing progress

![Fix](../adobe-support-tools-guide/assets/fix.svg) Renamed Case Description field to *[!UICONTROL "Please describe the issue"]* for improved clarity.

![Fix](../adobe-support-tools-guide/assets/fix.svg) Added asterisks (*) as mandatory field indicators to ensure completeness and reduce submission errors.

## March 18, 2026 - Expansion of Request for Callback feature

Experience League now offers a Request for Callback option, enabling self-service web meeting scheduling with screen sharing capabilities for faster issue resolution.

- This feature is available for Adobe Experience Manager, Campaign, and Workfront. 
- Customers can schedule meetings at their convenience and receive instant invites. 
- For Adobe Experience Manager P1 cases, immediate callbacks ensure faster engagement during critical issues, helping minimize downtime and business impact.
