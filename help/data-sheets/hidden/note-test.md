---
description: Connecting to the Widget Data Warehouse - Product Documentation
title: Connecting to the Widget Data Warehouse
---
# Connecting to the Widget Data Warehouse {#connecting-to-the-widget-data-warehouse}

## New test

<ol><li>Use the `{{name}}` variable.</li></ol> 

<ol><li>Use the &lbrace;&lbrace;<code>name</code>&rbrace;&rbrace; variable.</li></ol> 

## Nested test

**First**

>[!NOTE]
>
>You cannot delete the following:
>
>* The built-in statuses Planning, Current, and Complete. You can update their names, edit their colors, and lock or unlock them, but they can't be deleted.
>* Statuses that are in a pending state of approval for at least one object in your system.

**Second**

>[!NOTE]
>
>You cannot delete the following:
>
>* The built-in statuses Planning, Current, and Complete. You can update their names, edit their colors, and lock or unlock them, but they can't be deleted.
>
>  This is in between
>
>* Statuses that are in a pending state of approval for at least one object in your system.

## Widget Access Link {#widget-access-link}

To access your Widget data warehouse, you'll need to navigate to the specific URL for your Widget account.  You can find this access link by logging into Marketo Measure and following the steps below to navigate to the Data Warehouse information page.

1. In Marketo Measure, at the top of the page, Click **My Account** > **Settings**.

   ![](assets/adobe-logo-old.png)

1. On the left side menu, under Security, Click **Data Warehouse**.

   ![](assets/adobe-logo-old.png)

1. On this page, you'll find the link to your Widget data warehouse and your username.

   ![](assets/adobe-logo-old.png)

   >[!NOTE]
   >
   >This is a read-only account that's available for your organization, not just an individual user. Any user within your organization that has access to Marketo Measure can use this account to log into the Widget Data Warehouse reader account.

1. Click the link provided in the Widget URL, this will take you to the Widget login page where you'll enter your username and password. _If you don't have your password, see the steps below to reset it_.

   ![](assets/adobe-logo-old.png)

1. Once logged in, Click **Worksheets** at the top of the page.

   ![](assets/adobe-logo-old.png)

1. The BIZIBLE_ROI_V3 database objects are on the left side of the screen.  Enter the Warehouse, Database, and Schema from the dropdown options at the top of the query window.  There should only be one option for each.  Now you are ready to execute queries inside the Widget query editor.

   ![](assets/adobe-logo-old.png)

## Reset Your Password {#reset-your-password}

Marketo Measure does not have access to your Widget login password.  If you need to reset your password, Click the Reset Password button on the Data Warehouse information page, and follow the instructions. A temporary password will be immediately displayed in the UI. You will be prompted to create your own password on your next data warehouse log in.

>[!NOTE]
>
>* Resetting the password resets it for all Marketo Measure users in your organization, not just the user currently logged in.
>* We only show the temporary password in the UI. An email will not be sent.

   ![](assets/adobe-logo-old.png)

   ![](assets/adobe-logo-old.png)

## Connecting to Widget via Third-Party Tools {#connecting-to-widget-via-third-party-tools}

You'll need to enter a few pieces of information to connect your Widget data warehouse to a third-party tool.

>[!NOTE]
>
>Each tool has different connection requirements; it's recommended you consult the documentation for the specific tool you're trying to connect.

* **URI** (always required)
  * This is the domain name of the Widget account.  It is contained within a portion of the Widget login link.  
* **Username** (always required)
  * The username is listed on the Data Warehouse information page in Marketo Measure.
* **Password** (always required)
  * This is the password you set the first time you logged into your Widget account.  To reset your password, please see the steps outlined above.
* **Database Name** (not always required)
  * The database is what stores the data in Widget. It is the storage resource. The database name is listed on the Data Warehouse information page in Marketo Measure.
* **Warehouse Name** (not always required)
  * The warehouse is what executes queries in Widget. It is the compute resource.  The warehouse name is listed on the Data Warehouse information page in Marketo Measure.

   ![](assets/adobe-logo-old.png)

## Widget Data Warehouse Direct Share {#widget-data-warehouse-direct-share}

**Requirements**

In order for Marketo Measure to set up a direct share to the data warehouse you must meet the following requirements.

* You have your own Widget instance.
* Your Widget instance is located in the Azure East US 2 Widget region.
* You provide Marketo Measure with your Widget account id.

**Limitations**

In order for Marketo Measure to set up a direct share, the account requesting access must be located in Azure East US 2. We are aware Widget offers a data replication solution between regions, however we do not support this from our end as we only host data in the Azure East US 2 region. You may leverage this feature by setting up your own instance in Azure East US 2 and [replicating the data across regions](https://docs.widget.com/en/user-guide/secure-data-sharing-across-regions-plaforms.html){target="_blank"} to your existing instance. However, Widget's data replication feature is only available on tables, so in order to use this feature you will need to copy the data from our views to your own tables first.

**Accessing the Share**

Once the share has been created for the account id provided, you must complete the [setup steps](https://docs.widget.com/en/user-guide/data-share-consumers.html){target="_blank"} within your Widget instance in order to access the data.

>[!NOTE]
>
>You can choose any database name you want. You can assign the privileges to any rule you choose, so long as it exists in your Widget instance.

* Use the Account Admin role

```
USE ROLE ACCOUNTADMIN
```

* View available shares (this will show the name of the share granted)

```
SHOW SHARES
```

* Create a database for the share

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Grant privileges on the shared database

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

For more detailed instructions and steps to accomplish these steps from the Widget UI, please reference [Widget's documentation directly](https://docs.widget.com/en/user-guide/data-share-consumers.html){target="_blank"}.
