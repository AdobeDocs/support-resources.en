---
title: System Insights
description: System Insights proactively identify potential issues in Adobe Commerce environments. Reviewing insights during case creation reduces resolution time, helps prevent outages, and supports a stable and secure deployment.
---
# System Insights

System Insights provide proactive findings that help identify potential issues across performance, security, and functionality in an Adobe product setup. These insights surface risks such as performance degradation, security vulnerabilities, or incorrect configurations based on telemetry data collected from observability tools, including APIs, New Relic, and [!DNL Splunk].

System Insights appear during the case creation process and help accelerate diagnosis and resolution.

## How System Insights are created

Adobe teams continuously analyze common support issues and emerging trends. Based on these findings, Adobe adds automated checks to the system.

These checks scan the product setup to detect issues such as misconfigurations, stuck jobs, or conditions that could result in functional problems or system outages.

When a check identifies a value or state outside the safe range defined by Adobe product and support teams, the system surfaces it as a System Insight.

## Why System Insights matter

Regularly reviewing System Insights helps identify problems early, before they affect system stability or customer experience. This proactive approach:

- Improves platform reliability
- Reduces downtime
- Helps maintain Adobe‑recommended best practices

## Availability and scope

System Insights are currently available for Adobe Commerce only. These insights appear during the case creation process on Experience League Support and are also available through the [Site‑Wide Analysis Tool (SWAT)](https://experienceleague.adobe.com/en/docs/commerce-operations/tools/site-wide-analysis-tool/intro).

>[!Note]
>
>System Insights display data for production environments only.

## Accessing System Insights

System Insights appear throughout the case creation workflow. As issue details are entered, the **[!UICONTROL System Insights]** panel appears on the right side of the screen, below the AI‑powered recommendations section. To learn more about AI‑powered recommendations, see [Fill out the support ticket](https://experienceleague.adobe.com/en/docs/support-resources/adobe-support-tools-guide/adobe-customer-support-experience#fill-out-the-support-ticket) in the Adobe Customer Support Experience article.

The panel displays a scrollable list of insights scoped to the specific project instance. Scoping is based on the information entered in the **[!UICONTROL Project URL]** field. Enter the **[!UICONTROL Project URL]** accurately to ensure insights reflect the correct environment.

After the panel loads, it displays a scrollable list of insight cards flagged for your environment. Each insight card includes:

- A title that summarizes the issue
- A brief description of the insight

![Access Support Resources](/help/adobe-support-tools-guide/assets/access-support-resources.png)

To view full insight details, select an insight card from the list. The detailed view provides the following information:

- Insight name
- Adobe product where the insight is flagged
- Insight type, categorized as:
  - [!UICONTROL Functionality]
  - [!UICONTROL Performance]
  - [!UICONTROL Security]
- [!UICONTROL Risk level] indicating the severity
- [!UICONTROL Last Check Run] indicates when the finding was detected.
- [!UICONTROL Insight Source], provided by the Site‑Wide Analysis Tool (SWAT)
- A detailed explanation of the issue and its potential impact, along with actionable steps to investigate and address the issue. The detailed view also explains the typical causes of this type of issue and includes links to relevant Adobe documentation for additional reference.

![Click Case Card](/help/adobe-support-tools-guide/assets/click-case-card.png)

Review all insights in the panel before proceeding, as an insight may directly address the issue being experienced.

## Taking action on an insight

After reviewing an insight, choose one of the following actions.

### Continue case creation

If the issue persists or requires additional assistance, select **[!UICONTROL Continue Case Creation]**. The system retains all previously entered case information.

### Mark issue as resolved

If the insight resolves the issue and a support case is no longer required, select **[!UICONTROL Issue Resolved]**.

When this option is selected:

- A confirmation dialog appears.
- The dialog indicates that all entered case data will be permanently cleared.

![Action on an insight](/help/adobe-support-tools-guide/assets/issue-resolved.png)

Select **[!UICONTROL Done]** to confirm and return to the **[!UICONTROL My Cases]** page. Select **[!UICONTROL Cancel]** to return to the insight detail view.

![Clear Case Form](/help/adobe-support-tools-guide/assets/clear-case-form.png)

## Providing feedback on an insight

At the bottom of each insight detail view, feedback can be provided on whether the insight was helpful. This feedback helps Adobe continuously improve the relevance and accuracy of System Insights.

![Provide feedback](/help/adobe-support-tools-guide/assets/submit-feedback.png)

To provide feedback:

1. Open an insight detail view.
2. Scroll to the bottom of the panel.
3. Locate the prompt **[!UICONTROL Was this helpful? Send feedback.]**
4. Select one of the following options:
   - **Thumbs up** icon if the insight was helpful
   - **Thumbs down** icon if the insight was not helpful
5. (Optional) Enter additional comments.
6. Select **[!UICONTROL Submit]** to send feedback, or **[!UICONTROL Dismiss]** to close the feedback section without submitting.
