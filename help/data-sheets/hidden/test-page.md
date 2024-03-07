---
title: Test page (hidden)
description: Test page for internal testing purposes
hide: true
hidefromtoc: true
---
# Test page (hidden)

Hidden test page

## Colonoscopy

**Emoji**

Looks like this is ignored.

That is so funny! :joy:

:smiley:

## Buttons

[Button Default](https://www.adobe.com/)

**[Button Primary](https://www.adobe.com/)**

_[Button Secondary](https://www.adobe.com/)_

**_[Button Tertiary](https://www.adobe.com/)_**

## Images (EXLM-412)

### Image with hover text

![alt text - package.png](assets/package.png "Hover text - This is package.png")

### Center text

<p align="center">I am centered</p>

<center>I am centered</center>

### Zoomable images

`![Dive image](assets/maui-dive.jpg "Diving in Maui"){width=100 zoomable}`

**Plain**

![Dive image](assets/maui-dive.jpg "Diving in Maui"){width=100 zoomable}

**Note**

>[!NOTE]
>
>Click the following image to see a diver:
>
>![Dive image](assets/maui-dive.jpg "Diving in Maui"){width=100 zoomable}

**Table**

|  | Number | Colors |
|---|---|---|
| Juanya | 17 | Green<br>Red<br>Blue |
| Maria | 23 | Yellow<br>Brown |
| Bob | 60 | See image<br>![Dive image](assets/maui-dive.jpg "Diving in Maui"){width=100 zoomable} |

{style="table-layout:fixed"}

### Basic image tests

width=200 (compare to table below)

![alt text](assets/maui-dive.jpg "width = 200"){width=200}

width=50% (compare to table below)

![alt text](assets/maui-flip.jpg "width = 50%"){width=50%}

### Wrap testing ![alt text](assets/package.png "right-aligned"){align="right"}

**No align**

![alt text](assets/maui-dive.jpg "width = 100"){width=100} Cliff diving in Maui is not as difficult as one might think. There are really four steps for making a dive, and five steps for making a safe dive. First, jump hard away from the cliff and immediately extend your arms and point your toes. This is the pose for the camera. Second, maneuver your body into a reasonable landing position. This might look like panic, but it's merely an emotion-based adjustment. Third, splash in a way that doesn't hurt your body. Fourth, pop up as if you've done this a million times, and are a little bored.

**Align right**

Cliff diving in Maui is not as difficult as one might think. There are really four steps for making a dive, and five steps for making a safe dive. First, jump hard away from the cliff and immediately extend your arms and point your toes. This is the pose for the camera. Second, maneuver your body into a reasonable landing position. This might look like panic, but it's merely an emotion-based adjustment. Third, splash in a way that doesn't hurt your body. Fourth, pop up as if you've done this a million times, and are a little bored. ![alt text](assets/maui-dive.jpg "100 width right align"){width="100" align="right"}

**Align left**

![alt text](assets/maui-dive.jpg "100 width left align"){width="100" align="left"} Cliff diving in Maui is not as difficult as one might think. There are really four steps for making a dive, and five steps for making a safe dive. First, jump hard away from the cliff and immediately extend your arms and point your toes. This is the pose for the camera. Second, maneuver your body into a reasonable landing position. This might look like panic, but it's merely an emotion-based adjustment. Third, splash in a way that doesn't hurt your body. Fourth, pop up as if you've done this a million times, and are a little bored.

**Faked align right**

Cliff diving in Maui is not difficult. ![alt text](assets/maui-dive.jpg "100 width right align"){width="100" align="right"}

There are really four steps for making a dive, and five steps for making a safe dive. First, jump hard away from the cliff and immediately extend your arms and point your toes. This is the pose for the camera. Second, maneuver your body into a reasonable landing position. This might look like panic, but it's merely an emotion-based adjustment. Third, splash in a way that doesn't hurt your body. Fourth, pop up as if you've done this a million times, and are a little bored.


### Image alignment 

Normal

![alt text](assets/package.png "hover text for icon")

Align right below

![alt text](assets/package.png "align=right"){align="right"}

Align right inline ![alt text](assets/package.png "align=right"){align="right"}

center width = 250

![alt text](assets/maui-dive.jpg "align=center"){align="center" width=250}

### Heading alignment 

**Bold heading** ![alt text](assets/package.png "align=right"){align="right"}

See bold heading above.

### Images in tables

Icon is right-aligned, dive image is centered 200 pixels, flip image is right 50%.

|<center>Left|Middle|Right</center>|
|---|---|---|
|![alt text](assets/package.png "align=right"){align=right}|![alt text](assets/maui-dive.jpg "align=center width=200"){align="center" width="200"}|![alt text](assets/maui-flip.jpg "align=right width=50%"){align="right" width="50%"}|

## File attachments (EXLM-1124)

Download [PDF](/help/data-sheets/assets/BusinessSupportDatasheet.pdf)

Download [JS](assets/main.js)

Download [CSS](assets/main.css)

Download [TXT file](assets/dots.txt)

Download [XLSX file](assets/4-module_version.xlsx)

Download [ZIP file](assets/2-Factor-Authentication-DataSource-and-FDM.zip)

## HTML table with divs

<table>
<tr>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Release Information" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Release Information</strong></a>
      <p>Review all release information for Adobe Commerce patches and services.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Installation" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Installation</strong></a>
      <p>Learn how to install Adobe Commerce for on-premises deployments.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Configuration" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Configuration</strong></a>
      <p>Configure features and services for your Adobe Commerce application.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Data Migration" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Data Migration</strong></a>
      <p>Learn about the data migration process between Magento 1 and Magento 2.</p>
    </div>
  </td>
</tr>
<tr>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Upgrade" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Upgrade</strong></a>
      <p>Learn how to upgrade your Adobe Commerce project to keep your storefront secure and operating efficiently.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Command-line tools reference" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Command-Line Tools Reference</strong></a>
      <p>Learn about commands, arguments, and options for the Adobe Commerce command-line tools.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Performance" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Performance Best Practices</strong></a>
      <p>Use these recommendations to optimize the performance of your Adobe Commerce deployment.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Tools" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Tools</strong></a>
      <p>Learn about tools you can use with Adobe Commerce.</p>
    </div>
  </td>
</tr>
<tr>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Implementation" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Implementation Playbook</strong></a>
      <p>Learn about strategies for planning and implementing a successful Adobe Commerce site.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Operations" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Operational Playbook</strong></a>
      <p>Learn how to get your businesses operationally ready to run a successful ecommerce site.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Enterprise" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Commerce at Scale</strong></a>
      <p>Learn how to deliver experiences at scale using Adobe Commerce with Adobe Experience Manager.</p>
    </div>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Enterprise" src="assets/package.png" width="40" height="40"/>
    </a>
    <div>
      <a href="/help/data-sheets/business.md"><strong>Security and Compliance</strong></a>
      <p>Learn how Adobe Commerce merchants are responsible for maintaining a secure environment.</p>
    </div>
  </td>
</tr>
</table>

## HTML table without divs

<table>
<tr>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Release Information" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Release Information</strong></a>
    <p>Review all release information for Adobe Commerce patches and services.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Installation" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Installation</strong></a>
    <p>Learn how to install Adobe Commerce for on-premises deployments.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Configuration" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Configuration</strong></a>
    <p>Configure features and services for your Adobe Commerce application.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Data Migration" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Data Migration</strong></a>
    <p>Learn about the data migration process between Magento 1 and Magento 2.</p>
  </td>
</tr>
<tr>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Upgrade" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Upgrade</strong></a>
    <p>Learn how to upgrade your Adobe Commerce project to keep your storefront secure and operating efficiently.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Command-line tools reference" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Command-Line Tools Reference</strong></a>
    <p>Learn about commands, arguments, and options for the Adobe Commerce command-line tools.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Performance" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Performance Best Practices</strong></a>
    <p>Use these recommendations to optimize the performance of your Adobe Commerce deployment.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Tools" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Tools</strong></a>
    <p>Learn about tools you can use with Adobe Commerce.</p>
  </td>
</tr>
<tr>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
      <img alt="Implementation" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Implementation Playbook</strong></a>
    <p>Learn about strategies for planning and implementing a successful Adobe Commerce site.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Operations" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Operational Playbook</strong></a>
    <p>Learn how to get your businesses operationally ready to run a successful ecommerce site.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Enterprise" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Commerce at Scale</strong></a>
    <p>Learn how to deliver experiences at scale using Adobe Commerce with Adobe Experience Manager.</p>
  </td>
  <td valign="top">
    <a href="/help/data-sheets/business.md">
       <img alt="Enterprise" src="assets/package.png" width="40" height="40"/>
    </a>
    <br>
    <a href="/help/data-sheets/business.md"><strong>Security and Compliance</strong></a>
    <p>Learn how Adobe Commerce merchants are responsible for maintaining a secure environment.</p>
  </td>
</tr>
</table>
