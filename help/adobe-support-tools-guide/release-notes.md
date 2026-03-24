---
title: New EXL case form release notes
description: The latest release information for the EXL case form.
feature: Release Notes
---

# New EXL case form release notes

The new Case Creation experience introduces a refreshed form designed to streamline issue resolution and includes:

![New](../adobe-support-tools-guide/assets/new.svg) - New features
![Fix](../adobe-support-tools-guide/assets/fix.svg) - Fixes and improvements
![Bug](../adobe-support-tools-guide/assets/bug.svg) - Known issues

## Release 1.0 – Enhanced Case Creation Form

*March 30, 2026*  

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
    - Site URL (Tags Property Name) / HAR or Assurance log  
- **Adobe Analytics**  
    - RSID  
    - Site URL (Tags Property Name) / HAR or Assurance log / cURL / Debug Log  
    - Workspace shortlink  
- **Adobe Journey Optimizer (AJO)**  
    - Journey ID or Journey URL  
    - Example profile  
- **Real-Time Customer Data Platform (RTCDP)**  
    - Affected Component ID (Destination ID, Profile ID, Audience ID, Dataset ID, or Dataflow ID)  
    - HAR file / Assurance logs  
- **Customer Journey Analytics (CJA)**  
    - Workspace project  
    - Tags Property Name  


![New](../adobe-support-tools-guide/assets/new.svg) Added an **AI-Driven [!UICONTROL Recommendations Panel]** to display helpful guidance without interrupting the case creation flow.

![New](../adobe-support-tools-guide/assets/new.svg) Added a **[!UICONTROL Review Summary]** step to provide a consolidated view of all entered information and allow users to:

- Review case details in one place  
- Navigate back to previous steps to make edits  
- Return to the summary without losing progress

![Fix](../adobe-support-tools-guide/assets/fix.svg) Renamed Case Description field to *[!UICONTROL "Please describe the issue"]* for improved clarity.

![Fix](../adobe-support-tools-guide/assets/fix.svg) Added asterisk (*) as mandatory field indicators to ensure completeness and reduce submission errors.
