---
title: Bug fixes (hidden)
description: Test page for internal testing purposes
hide: true
hidefromtoc: true
---
# Bug fixes

## UGP-10584 Inline badges not working

These badges should be on the same line as the bullet items.

* [[!DNL Mixpanel]](note-test.md) [!BADGE Notes]{type=Informative}
* [[!DNL Pendo]](tables.md) [!BADGE Tables]{type=Positive}
* [[!DNL RainFocus]](syntax-style-guide.md) [!BADGE Syntax Style Guide]{type=Positive}

## UGP-10560 - Badges in collapsible sections

+++ Previous versions

### V1.16 Release

_Feb 13, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Product videos are now supported by the Catalog Service API.
![Fix](assets/package.png) Bundle products with fixed prices are now supported.
![Fix](assets/package.png) Out-of-stock options are now shown in the PDP widget.

#### Known limitations

These features are not yet supported:

* Maximum size for dynamic attributes payload is 9 MB.
* Group product price. Can be calculated with simple product prices.
* In an image array, only the first image contains roles.

The following limitations can be solved by using the API Mesh and the Core GraphQL API:

* Minimum Advertised Price
* [Tier pricing](https://www.adobe.com)

### V1.13 Release

_October 12, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Catalog Service supports the `inStock` flag for product variants.
![New](assets/package.png) `urlKey` and `externalId` have been added to the GraphQL schema.
![New](assets/package.png) Downloadable products and gift cards are now supported.

### V1.12 Release

_September 19, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](https://www.adobe.com).
![Fix](assets/package.png) This release contains bug fixes and improvements on the service side.

### V1.11 Release

_July 18, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Catalog Service now supports the [`recommendations`](https://developer.adobe.com/commerce/services/graphql/recommendations/recommendations/) GraphQL query for Product Recommendations.

### V1.10 Release

_June 27, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Catalog Service API now supports "related products".

### V1.7 Release

_April 12, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Catalog Service now cleans up deleted product variants.
![Fix](assets/package.png) Infrastructure scalability and performance improvements.

### V1.6 Release

_March 28, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Added swatches to the [`products`](https://developer.adobe.com/commerce/services/graphql/catalog-service/products/) query.
![New](https://www.adobe.com).

### V1.5 Release

_March 6, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.4 and newer

![New](assets/package.png) Added [`categories`](https://developer.adobe.com/commerce/services/graphql/schema/catalog-service/categories/) GraphQL functionality.
![Fix](assets/package.png) Improved performance and API scalability.

### V1.4 Release

_February 7, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.x and newer

![New](assets/package.png) Published catalog-service metapackage to simplify installation steps.
![Fix](assets/package.png) API scalability and performance improvements.

### V1.3 Release

_January 17, 2023_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.x and newer

![New](assets/package.png) Simplified and improved the onboarding experience.
![New](assets/package.png) New customer sandbox endpoints are available for pre-production testing.
![New](assets/package.png) Support added for virtual products.
![Fix](assets/package.png) API scalability and performance improvements.

### V1.1 Release

_November 18, 2022_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.x and newer

![New](assets/package.png) Catalog Service now supports Adobe's [API Mesh](https://developer.adobe.com/graphql-mesh-gateway/).
![Fix](assets/package.png) Improved API scalability and overall performance.

### V1.0 Release

_October 4, 2022_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.x and newer

![New](assets/package.png) Now support bundled and grouped products.
![New](assets/package.png) Added B2B visibility overrides. Products are now searchable and can be added to the cart for specific customer groups.
![Fix](assets/package.png) Service is now more stable and has improved performance.

### 0.3 Release - Beta+

_September 12, 2022_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.x and newer

![New](assets/package.png) Images for variants support: product images are returned based on the selected options
![New](assets/package.png) Roles for prices support: allow only members of specific customer groups to see the price of products
![Fix](assets/package.png) Improved stability and performance of the service
![New](assets/package.png) Updates are received when products are deleted from the catalog 

### Beta Release

_August 9, 2022_

[!BADGE Supported]{type=Informative tooltip="Supported"} Adobe Commerce versions 2.4.x and newer

![New](assets/package.png) The `products` and `refineProduct` queries return the following data:

* Predefined (system) product attributes.
* Dynamic product attributes and filter them by role (product display page/product list page).
* Product options.
* Product images and filter them by role (PDP/PLP).
* A specific price for simple products and price ranges for configurable products.
* Customer group prices and price ranges. They return a fallback default price on shoppers without a customer group.
* Product types that use B2B customer-specific pricing.

+++

## UGP-10565 - Text highlighting

Text before `<div class="preview">`

<div class="preview">

### Add Workfront native fields

You can add Workfront native fields to your custom forms. When the custom form is attached to an object, the field is populated from the object data. For example, the Description field on a custom form attached to a project will pull in the project description. (The field may show "N/A" if no data is available.)

1. On the left side of the screen, find **Native field** and drag it to a section on the canvas.
1. On the right side of the screen, configure the options for the custom field:

   <table style="table-layout:auto"> 
    <col> 
    <col> 
    <tbody> 
     <tr> 
      <td role="rowheader">Label</td> 
      <td> <p>(Required) Type a descriptive label to display above the field. You can change the label at any time.</p> <p><b>IMPORTANT</b>: Avoid using special characters in this label. They don't display correctly in reports.</p> </td> 
     </tr> 
     <tr> 
      <td role="rowheader">Name</td> 
      <td> <p>(Required) This name is how the system identifies the field.</p><p> When you are configuring the field for the first time and you type the label, the Name field populates automatically to match it. But the Label and Name fields are not synchronized—this gives you the freedom to change the label that your users see without having to change the name that the system sees.</p>
      <p><b>IMPORTANT</b>:
      <ul> 
      <li>Though it's possible to do so, we recommend that you do not change this name after you or other users start using the custom form in Workfront. If you do, the system will no longer recognize the field where it might now be referenced in other areas of Workfront.</p> </li>
      <li> <p>Each field name must be unique in your organization's Workfront instance. This way, you can reuse one that was already created for another custom form.</p> </li>
      <li><p>We recommend that you do not use the period/dot character in the custom field name, to prevent errors when using the field in different areas of Workfront.</p></td> 
     </tr> 
     <tr> 
      <td role="rowheader">Instructions</td> 
      <td> <p>Type any additional information about the field. When users fill out the custom form, they can hover over the question mark icon to view a tool tip containing the information you type here.</td> 
     </tr> 
     <tr> 
      <td role="rowheader">Reference Field</td> 
      <td><p>(Required) Select a Workfront native field.<p><p>Only native fields for the form's objects are available. For example, if the Object Types list at the top of the form designer shows Project, you will be able to select native fields for projects but not fields that are specific to tasks.</p></td>
     </tr>
     <tr> 
      <td role="rowheader">Size</td> 
      <td>(Optional) Change the display size of the field as needed.</td> 
     </tr> 
    </tbody> 
   </table>

1. To save your changes, click **Apply** and move on to another section to continue building your form.

    or

    Click **Save and Close**.

</div>

Text after highlighting

## UGP-10566 - Link text is smaller than regular text in HTML tables

See also UGP-9780

<table style="table-layout:auto"> 
<tbody> 
<tr>
<td>Input into</td>
<td>Description</td>
<td>Available for </td>
</tr>
<tr> 
    <td role="rowheader">Label</td> 
    <td> <p>(Required) Type a descriptive label to display above the custom field. You can change the label at any time. For more information, see <a href="https://www.adobe.com" class="MCXref xref">Add a custom field to a custom form</a> in this article.</p> <p><b>IMPORTANT</b>: Avoid using special characters in this label. They don't display correctly in reports.</p> </td> 
    <td>
    <ul>
    <li>Radio buttons. For more information, see <a href="https://www.adobe.com">Add a custom field to a custom form</a> in this article. (No class)</li>
    <li>Checkbox Group</li>
    <li>Dropdown</li>
    </ul></td>
</tr> 
</tbody> 
</table>

## UGP-9176 - Old bug

The "span" tag is not working quite well in a NOTE (and list)

For information about what features are available in the new commenting experience and for what objects, see [New commenting experience](note-test.md). 

1. Go to the object to which you want to add a reply.
1. Click **Updates**, then click the **Comments** tab for the object and find the comment or reply to which you want to reply

   Or

   <span class="preview">Click the **All** tab, then click **Reply in Comments** to open the comment in the Comments tab and reply to it. You cannot reply in the All tab.</span>

1. (Optional) To include text from a previous update in your reply, click the **More** menu in the upper-right corner of the comment you want to reply to, then click **Quote reply**. Text from the previous update appears in the input area, marked with a vertical gray line.
1. Click **Reply**.

   ![](assets/package.png)

   You can see the users who are actively engaged in the conversation at the bottom of the **Add reply...** box and you can add more, or remove the ones that are no longer relevant. These users, along with any users subscribed to the object, receive a notification whenever an update or reply is made on the object. You can also tag more users to include them in your reply.  To tag more users, see [Tag others on updates](note-test.md).

   >[!TIP]
   >
   >   To add additional replies to an existing reply, you can start typing in the **Add reply ...** box, or click **Reply** on the original comment. Your reply is added at the end of the thread.
   
1. Start typing your reply and use any additional options from the Rich Text toolbar. For information about using Rich Text or other updating capabilities, see [Update work](note-test.md). 

1. Click **Submit** to save the reply.

1. (Optional) Click the **More** menu in the upper-right corner of the comment you want to reply to for more options to manage the reply. For more information, see [Update work](note-test.md). 
