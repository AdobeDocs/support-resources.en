---
title: Collapse sections bug
description: UGP-13446 collapsible sections not rendering, perhaps due to embedded page tabs
hide: yes
hidefromtoc: yes
exl-id: 297a5183-7448-43a8-b641-8099e1db3b6b
---
# Collapsible sections

<http://jira.corp.adobe.com/browse/UGP-13446> UGP-13446 collapsible sections not rendering, perhaps due to embedded page tabs

## Examples

First with page tabs; second without

### Option 2: With page tabs

+++ Manual Hotfix Installation for 6.5.18.0 - 6.5.22.0

**Step 1: Download and Extract the Hotfix Package**

- Download the [hotfix for 6.5.18.0 - 6.5.22](https://www.adobe.com) from the Adobe Software Distribution Portal
- Extract it locally

**Step 2: Navigate to the Correct Version Folder**

- Based on the Service Pack version installed on your environment, go to the matching folder.

   Example for Service Pack 20 the folder is:

   ```
   <extracted-hotfix>/SP20/
   ```

**Step 3: Locate the Deployment Directory**

- On your AEM Forms on JEE server, go to:

   ```
   [AEM installation directory]/deploy
   ```

   Example: `adobe/adobe-experience-manager-forms/deploy`



**Step 4: Update and replace the EAR files**

>[!BEGINTABS]

>[!TAB JBoss]

1. Open `adobe-core-jboss.ear` and replace `adminui.war` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/jboss/adminui.war
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/jboss/adminui.war`

1. Inside the `adobe-core-jboss.ear`, go to the `lib/` folder and replace `adobe-uisupport.jar` with:

   ```
   adobe-xxe-configuration-hotfix/SP[version]/adobe-uisupport.jar
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/adobe-uisupport.jar`

1. Save the EAR. Ensure changes are saved properly. 


1. Replace `adobe-edcserver-jboss.ear` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/jboss/adobe-edcserver-jboss.ear
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/jboss/adobe-edcserver-jboss.ear`

1. Replace `adobe-forms-jboss.ear` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/jboss/adobe-forms-jboss.ear
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/jboss/adobe-forms-jboss.ear`



>[!TAB WebLogic]

1. Open `adobe-core-weblogic.ear` and replace `adminui.war` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/weblogic/adminui.war
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/weblogic/adminui.war`

1. Inside the `adobe-core-weblogic.ear`, replace `adobe-uisupport.jar` with:

   ```
   adobe-xxe-configuration-hotfix/SP[version]/adobe-uisupport.jar
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/adobe-uisupport.jar`

1. Save the EAR. Ensure changes are saved properly. 


1. Replace `adobe-edcserver-weblogic.ear` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/weblogic/adobe-edcserver-weblogic.ear
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/weblogic/adobe-edcserver-weblogic.ear`

1. Replace `adobe-forms-weblogic.ear` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/weblogic/adobe-forms-weblogic.ear
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/weblogic/adobe-forms-weblogic.ear`

>[!TAB WebSphere]

1. Open `adobe-core-websphere.ear` and replace `adminui.war` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/websphere/adminui.war
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/websphere/adminui.war`

1. Inside the `adobe-core-websphere.ear`, replace `adobe-uisupport.jar` with:

   ```
   adobe-xxe-configuration-hotfix/SP[version]/adobe-uisupport.jar
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/adobe-uisupport.jar`

1. Save the EAR. Ensure changes are saved properly. 


1. Replace `adobe-edcserver-websphere.ear` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/websphere/adobe-edcserver-websphere.ear
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/websphere/adobe-edcserver-websphere.ear`

1. Replace `adobe-forms-websphere.ear` with 

   ```
   adobe-xxe-configuration-hotfix/SP[version]/websphere/adobe-forms-websphere.ear
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/websphere/adobe-forms-websphere.ear`

>[!ENDTABS]



**Step 5: Update `adobe-rightsmanagement-<appserver>-dsc.jar`file with**

   ```
   adobe-xxe-configuration-hotfix/SP[version]/<appserver>/adobe-rightsmanagement-<appserver>-dsc.jar
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/jboss/adobe-rightsmanagement-jboss-dsc.jar`

**Step 6: Additional Configuration for Document Security on WebSphere and WebLogic**: 

If you are using Document Security (formerly Rights Management), set the following Java system property (JVM argument) before starting the AEM Forms server:

   ```
   -Dcom.adobe.forms.jee.services.allowDoctypeDeclaration=true
   ```


**Step 7: Re-run the Configuration Manager**

- Launch the Configuration Manager to re-deploy the updated EAR and apply the hotfix

+++

### Option 2: Without page tabs

+++ Manual Hotfix Installation for 6.5.18.0 - 6.5.22.0

**Step 1: Download and Extract the Hotfix Package**

- Download the [hotfix for 6.5.18.0 - 6.5.22](https://www.adobe.com) from the Adobe Software Distribution Portal
- Extract it locally

**Step 2: Navigate to the Correct Version Folder**

- Based on the Service Pack version installed on your environment, go to the matching folder.

   Example for Service Pack 20 the folder is:

   ```
   <extracted-hotfix>/SP20/
   ```

**Step 3: Locate the Deployment Directory**

- On your AEM Forms on JEE server, go to:

   ```
   [AEM installation directory]/deploy
   ```

   Example: `adobe/adobe-experience-manager-forms/deploy`



**Step 4: Update and replace the EAR files**

Page tabs deleted

**Step 5: Update `adobe-rightsmanagement-<appserver>-dsc.jar`file with**

   ```
   adobe-xxe-configuration-hotfix/SP[version]/<appserver>/adobe-rightsmanagement-<appserver>-dsc.jar
   ```

   For example, `adobe-xxe-configuration-hotfix/SP20/jboss/adobe-rightsmanagement-jboss-dsc.jar`

**Step 6: Additional Configuration for Document Security on WebSphere and WebLogic**: 

If you are using Document Security (formerly Rights Management), set the following Java system property (JVM argument) before starting the AEM Forms server:

   ```
   -Dcom.adobe.forms.jee.services.allowDoctypeDeclaration=true
   ```


**Step 7: Re-run the Configuration Manager**

- Launch the Configuration Manager to re-deploy the updated EAR and apply the hotfix

+++

Fin
