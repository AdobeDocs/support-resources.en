---
title: Self Service Excellence Collaborative Documentation Syntax and Formatting Guide
description: A basic introduction to Markdown styling
mini-toc-levels: 1
hide: true
hidefromtoc: true
exl-id: 9f15436b-156a-4c07-bfaf-8557cd948197
---
# Markdown Syntax Style Guide

This page illustrates the markdown componentry for Digital Experience Technical Documentation Authoring using the markdown (.md) format. This page includes details for Adobe employees.

EDS 

See here: [Adobe.com](https://www.adobe.com){rel=nofollow}

<!--
* You can [view a basic sample file](sample.md) or [view a sample file with advanced syntax examples](sample-full.md)
-->

>[!TIP]
>
>Watch this [AdobeDocs Markdown video](https://video.tv.adobe.com/v/26165).

For the most part, we follow standard git-flavored markdown (GFM) syntax for formatting text. However, some syntax (such as horizontal lines) is not supported, and we've extended Markdown in a number of ways to suit our documentation needs.

## Basic text formatting

A paragraph requires no special syntax in Markdown. Add a blank line between each paragraph.

To format text as **bold**, you enclose it in two asterisks:

```
This text is **bold**.
```

To format text as *italic*, you enclose it in a single asterisk:

```
This text is *italic*.
```

To format text as both ***bold and italic***, you enclose it in three asterisks:

```
This is text is both ***bold and italic***.
```

To ignore Markdown formatting characters, use `\` before the character:

`This is not \*italicized\* type.`

Rendered: This is not \*italicized\* type.

## Badges

In progress. Waiting on Loc.

<!--

See the [dev version of this article](https://experienceleague-dev.corp.adobe.com/docs/authoring-guide-exl/using/markdown/syntax-style-guide.html#badges) for an example. Or [this one](https://experienceleague-dev.corp.adobe.com/docs/internal-test/test/badge.html).

There are two ways to create badges:

* **Metadata badge** - Specify the badge information in metadata so that the badge appears above the title in the article. This is especially useful for adding a badge to all articles in a guide or repo via the TOC.md or metadata.me files.
* **Inline badge** - Specify the badge information on its own line or in a heading, table, or other page element.

![badge examples](assets/badge-examples.png)

**Badge syntax**

*Metadata*: `badge: "Beta Content" type="Informative" url="https://www.example.com" tooltip="Go to example.com"`

*Inline*: `[!BADGE Beta Content]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

**Examples**

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off his horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

**Rendered**

|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off his horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|

**More details**

* Only the badge label is required. The `type`, `url`, and `tooltip` parameters are optional. The `type` parameter determines the color. The `url` parameter lets users click the badge to open an article. The `tooltip` parameter displays the tooltip text on mouseover.
* If you want multiple badges to appear at the top of the page, use different badge names. For example, you can create badge names such as `badgeBeta` or `badgeWeb`. Example:

  ```
  badge1: "Beta"
  badge2: "Campaign Web"
  ```

* For metadata badges, make sure that all values are wrapped in quotes. For inline badges, make sure that `url` and `tooltip` are wrapped in quotes.
* Valid type values include *Informative* (default, blue), *Positive* (green), *Negative* (red), *Neutral* (dark gray), and *Caution* (yellow). 

-->

## Blockquotes

Our authoring system uses blockquotes syntax (`>` at the beginning of lines) to identify custom markdown extensions for tips, notes, and videos. You can create actual blockquotes by adding a `>` character in front of a paragraph.

>This is a blockquote quotation.

```
>This is a blockquote quotation.
```

## Code Block (in line){#code-block}

**When to use**

Used to render a piece of code in-line in a sentence. Ideal to call out a cookie name, file name, value, or command that does not require a full-fenced code block.

Content within code blocks in rendered as is and not localized. (The one exception to this rule is `!UICONTROL` and `!DNL` syntax, which is stripped out during packaging for publication.)

Also use code blocks for sample URLs that should not be validated: `https://www.example.com`

**Syntax**

A code block uses single backticks to enclose the code element you would like to highlight. 

```
This is `inline code` within a paragraph of text.
```

**Example**

This is `inline code` within a paragraph of text.

>[!TIP]
>
>You can also wrap text in triple back ticks (&grave;&grave;&grave;) to create an inline code block. This is especially useful when you need to reference a back tick character within an inline code block. Example:
>
>&grave;&grave;&grave;`Use a back tick (`&grave;`) for formatting`&grave;&grave;&grave;

## Code Block (fenced)

**When to use**

Use a code block to display code syntax. A fenced code block uses triple backticks to enclose the code element you want to highlight. Add blank lines above and below the fenced code block.

Note that code blocks are not localized.

>[!TIP]
>
>Specify a language when you create a fenced code block. Specifying a language allows syntax highlighting specific to that language and displays a **Copy** button for the users. You can also display line numbers if you specify a language.

**Syntax**

Use three back ticks ( &grave;&grave;&grave; ) before and after the code lines. Make sure that the open and close back ticks are indented the same number of spaces. For optimal rendering, specify a code language.

&grave;&grave;&grave;`javascript`

**Example**

```javascript
var visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ORGANIZATION ID-HERE", {
     trackingServer: "INSERT-TRACKING-SERVER-HERE", // same as s.trackingServer
     trackingServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE", // same as s.trackingServerSecure

     // To enable CNAME support, add the following configuration variables
     // If you are not using CNAME, DO NOT include these variables
     marketingCloudServer: "INSERT-TRACKING-SERVER-HERE",
     marketingCloudServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE" // same as s.trackingServerSecure
});
```

### Syntax highlighting for code blocks

Experience League supports syntax highlighting for code blocks. Make sure that you specify a language such as `java` after the opening set of back ticks to make sure that the syntax is highlighted properly. For a list of valid languages, see [https://prismjs.com](https://prismjs.com/#supported-languages). If any languages are missing, please log a jira ticket.

### Line numbering in code blocks

Add `{line-numbers="true"}` after the language to enable line numbering.

Example with line numbers (&grave;&grave;&grave;`html {line-numbers="true"}`): 

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Start numbering on line _**

Add `start-number="n"` after line number syntax to start the numbering on a number other than 1.

Example with new start line (&grave;&grave;&grave;`html {line-numbers="true" start-line="7"}`): 

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Line highlighting in code blocks

Add `highlight="n"` after line number syntax to highlight rows within a code block. Specifying `11-13, 16` will highlight lines 11 through 13 and 16.

Example with line highlighting (&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`): 

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Variable formatting in code blocks

Variable syntax such as `<i>italic</i>` is not supported in code blocks. To indicate variable text, one option is to use angle brackets `< >`.

## Collapsible sections

You can create a collapsible section (sometimes called an **accordion**) that is hidden by default. The user can click the title to expand or collapse the section.

Collapsible text can be used to simplify complex content, such as streamlining an FAQ page or de-cluttering a complex procedure with nested lists. For example, instead of displaying a set of sub-steps, you can collapse the sub-steps into a "View details" section.

**Syntax**

```
+++See details
This is text inside a collapsible section.

* Bullet one
* Bullet two
* Bullet three

+++
```

**Example**

+++See details
This is text inside a collapsible section.

* Bullet one
* Bullet two
* Bullet three

+++

**Notes**

* Do not nest collapsible sections within collapsible sections. Nested collapsible sections do not render properly. However, they don't cause validation to fail, so users will see the `+++` syntax of the nested section.
* Make sure that you add blank lines above and below items like bullet lists and code blocks inside the collapsible section, or you'll get a validation error.
* You can add headings inside collapsible sections, but it's not recommended.
* [Accordions Are Not Always the Answer for Complex Content on Desktops](https://www.nngroup.com/articles/accordions-complex-content/)
* One historical drawback of collapsible sections is that **Find in Page** (Ctrl/Cmd+F) ignores collapsed text. While that's still true in Safari, it's no longer true in Chrome; Find in Page detects collapsed text in Chrome.
* Example of a [maintenance updates](https://experienceleague.adobe.com/docs/workfront-known-issues/releases/current-updates.html?lang=en) page using collapsible sections.

## Comments and Remarks

Comments do not appear in the rendered help system. Use comments to leave notes for yourself or other writers. You can also use comments for draft sections of text.

For comments, keep in mind that while they are not rendered in the help system, they are visible to users who edit Markdown files on GitHub.com. Don't include confidential information in comments.

```
<!-- standard comment code -->

DO NOT USE the following:
<!--> bad comment syntax <-->
```

You shouldn't be able to see text below this ("You can't see me") unless you're editing the document.

<!--
You can't see me (unless you're editing in Git).
-->

**Reminder:** Comments (remarks) do not appear in the public-facing help articles. However, comments do appear in the public-facing Markdown files that users can see and edit.

>[!IMPORTANT]
>
>Avoid adding comments within block components such as bullet lists, especially nested bullet lists. The comment can change how the bullet list is rendered.
>
>In the TOC.md file, do not comment out lines in the middle of the TOC list. This might break up the TOC list and cause validation errors. Instead, move comments in the TOC to the end of the file.

## CONTEXTUALHELP

Authors can work with product teams to add help popovers in the Experience Cloud or Experience Platform product UI. Example:

```markdown
>[!CONTEXTUALHELP]
>id="platform_destinations_activate_mandatorykey_4"
>title="About mandatory attributes"
>abstract="Select the XDM schema attributes that all exported profiles should include. Profiles without the mandatory key are not exported to the destination. Not selecting a mandatory key exports all qualified profiles regardless of their attributes."
>additional-url="http://www.adobe.com/go/destinations-mandatory-attributes-en" text="Learn more in documentation"
```

## Definition Lists

For definition lists, we do not yet support standard Markdown syntax. Instead, use manual formatting such as this:

```
**Frog** - An amphibious green creature. Likes flies.
```

Rendered: 

**Frog** - An amphibious green creature. Likes flies.

<!--
A definition list is a Markdown extension that supports the Definition List component in AEM. A definition list consists of a term and its definition.

**When to use**

Using a definition list is optional. To define lists of features or options, you can use either the definition list syntax or use basic Markdown formatting, such as applying bold to option names.

**Syntax**

```
Frog
: An amphibious green creature. Likes flies.

Cat
: A less amphibious creature than frogs.
```

**Example**

Frog
: An amphibious green creature. Likes flies.

Cat
: A less amphibious creature than frogs.
-->

## Download Files

Upload the .zip or other downloadable file to the assets directory, and then link to it. If it's a .zip file, clicking the link will download the file. If it's file type such as PDF or PNG that can be opened in a browser, clicking the link will open a new tab. For such files, consider zipping them or providing instructions to right-click the link and download.

`Download` &lbrack;`download-test.zip`&rbrack;`(assets/download-test.zip)`

Rendered:

Download [download-test.zip](assets/download-test.zip)

>[!NOTE]
>
>The maximum file size for download files and images is 100 MB. That's the github.com limit. The git.corp.adobe.com limit is higher (250 MB), but we need to be able to copy files to the github.com mirror.

## Headings {#headings}

In Markdown, you use pound signs (`#`) to identify heading levels. The first level (`#`) is the article title, which is also specified in the metadata header—keep these the same. The second level (`##`) represents the main headings on the page that will be included in the mini-TOC. If you're accustomed to writing in AEM (chl-author), the level 2 headings (`##`) map to the "Heading 1" component in AEM.

Maximum character count for headings: 69 characters (English) / 120 characters (LOC).

```
# This is level 1 (article title)

## This is level 2
   
### This is level 3
```

**Heading best practices**

* Make sure that a level 1 heading (`#`) follows a blank line after the metadata in each article.
* Don't skip levels, such as jumping from level 2 (`##`) to level 4 (`####`).
* Include a blank line *before* and *after* each heading.
* If a heading includes numerals, specify an explicit heading ID that does not begin with a number, such as `## Release notes for 2016 {#release-notes-2016}`.
* We recommend only 3 heading levels. Levels 4 and beyond are not rendering properly at this time.
* Headings are displayed in the right nav so that users can click to jump to a section. By default, two levels of headings appear in the right nav. If you want to change the number of levels, use `mini-toc-levels` metadata, such as `mini-toc-levels: 3`. 

**Heading IDs**

Heading IDs (also called *anchor IDs*) are used to create custom deep links to sections within articles. To specify a heading ID, use this format:

```
## Creating processing rules {#processing-rules}
```

Heading IDs should be lowercase and hyphenated. 

If you don't specify a heading ID for a heading, the default heading ID is the "slugified" (lowercase and hyphenated) heading. For example, the `## Creating widgets and Such` heading will have a `#creating-widgets-and-such` anchor.

## HTML syntax {#html}

For various reasons, including security and accessibility, we limit the HTML syntax that can be used in markdown. The following list shows supported HTML syntax. Any HTML syntax not on this list will result in a validation error.

```html
<table>
<tbody>
<td>
<tfoot>
<thead>
<th>
<tr>
<col>
<colgroup>
<p> (paragraph break)
<ul> (unordered list / numbered list)
<ol> (ordered list / bullet list)
<li> (list item)
<br> (line break)
<b>
<caption>
<i>
<strong> (bold)
<u> (underline)
<s> (strikethrough)
<span>
<sub> (subscript)
<sup> (superscript)
<a>
<img>
<div>
<em> (emphasis, italics)
<pre> (codeblock)
<code>
<codeblock>
```

<!--
Bob: Check above no space char. (ignore the space; I can't add a codeblock inside this codeblock)
-->

If you want HTML syntax to be added to this list, please log a ticket or contact the SSE team.

## Images {#images}

Use the `![]()` syntax for images. The brackets `[ ]` include alt text, and the parentheses `( )` include the image location and optional hover text (tooltip). The exclamation mark distinguishes an image from a link. 

```
![alt text](assets/logo.png "Hover text")
```

![alt text](assets/logo.png "Hover text")

For shared images, you can place the images in a root assets folder and then use a root link that works from any file within a repo:

```
/help/assets/imagename.png
```

### Resizing and aligning images

**Image properties (with right-aligned image)** ![alt text](assets/premium.png "Premium hover text"){align="right"}

Use syntax such as the following to change the default image width or center or right-align the image within the page view or table cell.

```
![Dive image alt text](assets/maui-dive.jpg "Hover text - Maui dive width is 300 pixels and centered"){width="300" align="center"}
```

Rendered:

![Dive image alt text](assets/maui-dive.jpg "Hover text - Maui dive width is 300 pixels and centered"){width="300" align="center"}

* For large images, we recommend that you create images large enough to be scaled down to fit within the page width&mdash;at least 640 pixels wide. Recommended width is 1500 pixels. There is no need to create images larger than 2500 pixels or 500 kilobytes. The maximum file size for images is 100 MB.
* For small images, create images using the desired width in pixels, or use the width parameter, such as `{width="250"}` (pixels) or `{width="50%"}` (percentage of view area, not original image size). Images are scaled proportionally. Note that images can be scaled up or down, so be careful about pixelation.
* In some cases, images from the same interface will look out of proportion on the page because wider images (such as a toolbar) are scaled down while narrow images (such as a panel) are not scaled down. In such cases, consider scaling down the wider images to improve visual consistency.
* You can change the alignment of an image within the view area. Use either `{align="center"}` or `{align="right"}`. The `valign` parameter is not supported.

>[!NOTE]
>
>The maximum file size for images is 100 MB. That's the github.com limit. The git.corp.adobe.com limit is higher (250 MB), but we need to be able to copy files to the github.com mirror.

### Image Links

If you want to allow users to click an image to jump to a different page, use this format.

**Syntax**

```
[![image](assets/core-services_96.png)](https://www.adobe.com)
```

**Example**

Click this image to go to the Adobe website.

[![image](assets/core-services_96.png)](https://www.adobe.com)

<!--
### Click-to-zoom images

Use the `zoomable` parameter to allow users to click an image to view an enlarged version of the image. When the user mouses over a zoomable image, the pointer becomes a magnifying glass. When clicked, the image expands to the full width of the browser. It can be dismissed with a close button.

**Example**

![Diving image](/help/test-guide/assets/maui-dive.jpg "Diving in Maui"){width="100" zoomable="yes"}

**Syntax**

```
![Diving image](/help/test-guide/assets/maui-dive.jpg "Diving in Maui"){width="100" zoomable="yes"}
```

-->

## Links and Cross-References {#links-and-cross-references}

External links are straight-forward and can be rendered as a linked caption or a pure URL.

```
[Adobe](https://www.adobe.com)
```

Rendered:

[Adobe](https://www.adobe.com)

If you add a URL directly to text, it is not converted to a link automatically. If you want a URL to appear as a link, add `< >` syntax. Examples:

```
https://www.adobe.com

<https://www.adobe.com>
```

Rendered:

https://www.adobe.com

<https://www.adobe.com>

Links to articles (cross-references) can be a little more complex.

**Option 1: Standard relative link**

Here's what a standard relative link looks like:

```
See [Overview example article](collaborative-doc-instructions/overview.md)
```

The pathname needs to account for both the location of the source file and the target file. You can use all relative link operands, such as `./` (current directory), `../` (back one directory), and `../../` (back two directories).

**Option 2: Root relative link**

The advantage to this type of link is that it needs to account for only the target file. It works from any source file within the repo regardless of source file location.

```
/help/using/docile-rules/introduction.md
```

**Deep linking**

To link to a heading within an article, the target heading must have an explicit heading ID (also called an "anchor ID"). Example:

`## Creating audience segments {#creating-audience-segments}`

To link to this heading within the same page, use the heading ID as the link:

`See [Creating audience segments](#creating-audience-segments)`

To link to this heading from a different article in the repo, add the heading ID suffix to the end of the link:

`See [Audiences: Creating audience segments](audiences.md#creating-audience-segments)`

**Open in new tab**

If you want a link to open a new tab, such as when you jump to a different guide, use the `{target="_blank"}` property in the link.

Example:

`[See What's new](whats-new.md){target="_blank"}`

## Metadata

Add metadata to the top of the markdown file. The next line after the metadata line (and blank line) MUST be the article title (# Title).

```
---
title: Title for search optimization
description: This is the article description used for search optimization. Use common search keywords and synonyms.
---

# Article title
```

## Localization tags: UICONTROL, DNL, and DONOTLOCALIZE

All of our Markdown help content is localized using machine translation initially. If the help has never been localized, then we keep the machine translation. However, if the help content has been localized in the past, then the machine translated content will act as a placeholder while the content is in the process of human translation.

## More Like This

Use the "More Like This" component to display related links at the end of an article. When rendered, the MORELIKETHIS component is rendered as "Related Articles" (and localized in other languages).

**Syntax**

![More Like This syntax](assets/morelikethis.png)

**Example**

>[!MORELIKETHIS]
>
>* [Article 1](https://helpx.adobe.com/support/analytics.html)
>* [Article 2](https://helpx.adobe.com/support/audience-manager.html)

## Notes / admonitions

We extended Markdown to format various types of notes: Note, Tip, Important, and Warning.

**Syntax**

```
>[!NOTE]
>
>This is a standard NOTE block.
```

**Example**

>[!NOTE]
>
>This is a standard NOTE block.

**Syntax**

```
>[!TIP]
>
>This is a standard tip.
```

**Example**

>[!TIP]
>
>This is a standard tip.

**Syntax**

```
>[!WARNING]
>
>This is a standard warning block.
```

**Example**

>[!WARNING]
>
>This is a standard warning block.

**Syntax**

```
>[!IMPORTANT]
>
>This is a standard important block.
```

**Example**

>[!IMPORTANT]
>
>This is a standard important block.

**Syntax**

```
>[!NOTE]
>
>This is a standard NOTE block.
>
>It includes multiple paragraphs.
```

**Example**

>[!NOTE]
>
>This is a standard NOTE block.
>
>It includes multiple paragraphs.

New supported note types:

>[!ADMIN]
>
>This is an admin note. EXL only.

>[!AVAILABILITY]
>
>This is an availability note. EXL only.

>[!PREREQUISITES]
>
>This is a Prerequisites note. EXL only.

>[!INFO]
>
>This is an Info note. EXL only.

>[!ERROR]
>
>This is an Error note. EXL only.

>[!SUCCESS]
>
>This is a Success note. EXL only.

## Numbered Lists and Bullet Lists {#lists}

To create numbered lists, begin a line with `1.` or `1)`, but pick one method and use it consistently within the article. You don't need to specify the numbers. GitHub does that for you.

Use the number `1` for every step in the numbered list.

Add blank lines before and after lists.

**Syntax**

```
1. This is step 1.

1. This is the next step.

   1. This is a sub-step

   1. This is a sub-step

1. This is yet another step, the third.
```

**Example**

1. This is step 1.

   1. Sub-step

   1. Sub-step

1. This is the next step.

1. This is yet another step, the third.

To create bullet lists, begin a line with `*` or `-` or `+`, but pick one method and use it consistently within the article. (If you mix the formats, such as `*` and `+`, you'll get a Markdown validation error when you check in the file.)

**Best practice:** Use `*` for bullets. Visual Studio Code applies the asterisk for bullets, so it's easier to stay with asterisks to automate creating an unordered list. (You might have noticed that the TOC.md file uses plus signs `+` for lists. That's a holdover from migration. Any valid bullet character would work as long as it's consistent within the article.)

**Syntax**

```
* First item in an unordered list.
* Another item.
* Here we go again.
```

**Example**

* First item in an unordered list.
* Another item.
* Here we go again.

You can also embed lists within lists and add content between list items. Indent content between list items to avoid starting a new list. Items between steps should be indented to the start of the text&mdash;3 spaces for numbered lists, 2 spaces for bullet lists.

```
1. Set up your table and code blocks.
1. Perform this step.

   ![screen](assets/core-services_96.png)
   
1. Make sure that your table looks like this: 

   | Hello | World |
   |---|---|
   | How | are you? |
   
1. This is the fourth step.

   >[!NOTE]
   >
   >This is note text.
   
1. Do another step.

   This is an indented line.
```

**Example**

1. Set up your table and code blocks.
1. Perform this step.

   ![screen](assets/core-services_96.png)

1. Make sure that your table looks like this: 

   | Hello | World |
   |---|---|
   | How | are you? |

1. This is the fourth step.

   >[!NOTE]
   >
   >This is note text.

1. Do another step.

   This is an indented line.

NOTE: If you indent too far, such as 6 spaces instead of 3, the content in that line will be treated as a code block.

## Shade Boxes

Shade boxes are useful for setting off a section of content from the rest of the page. For example, the Workfront team likes to add "Example" boxes that contains text, images, and code samples to achieve a specific purpose. A shade box might also be useful for "On Your Own" or "Use Case" sections, or for extended notes or tips.

To create a shade box, add `>[!BEGINSHADEBOX]` at the beginning of the section and `>[!ENDSHADEBOX]` at the end. All content between these begin and end tags will have a gray background. Adding a label to `BEGINSHADEBOX` (such as `>[!BEGINSHADEBOX "Use Case]` is an optional way to create a bolded shade box title. You can also just add bold text or a heading on the next line.

Example:

>[!BEGINSHADEBOX]

**Removing the border in an HTML table**

In some cases, you use an HTML table to create a balanced design, but you don't want the content to look like a table. To turn off a border for a one-row HTML table, use this syntax:

```
<table>
<tr style="border: 0;">
```

>[!NOTE]
>
>Don't overuse. For normal tables, we want to keep a consistent design across content.

![table tip](assets/table-no-border.png)

In a three-column table, you can also add `<td align="center">` and `<td align="right">` to distribute the cell content evenly across the view area. If it were not so, I would have told you.

This is the last line of the shade box.

>[!ENDSHADEBOX]

## Snippets and includes

To share text among articles in a repo, you create a `_includes` folder in the `help` folder. This `_includes` folder can have .md files that can be referenced (included) from other files in the repo. In addition, a `snippets.md` file in this repo can include Head2 anchors that can be referenced from any file in the repo.

Reference to H2 in snippets.md file: `{{id-name}}`

Reference to include file: `{{$include /help/_includes/filename.md}}`

## Tables

Tables can be problematic in Markdown. When tables are migrated from the previous authoring system, simple tables (one line per cell) are formatted as native Markdown tables (preferred). More advanced tables are formatted as HTML.

>[!TIP]
>
>Watch the [Markdown Tables video](https://video.tv.adobe.com/v/26220)

Native tables frequently look better in Markdown. Columns are sized according to their content. HTML tables are rendered with equal-width columns.

By default, Markdown doesn't support multiple lines or lists in cells. However, we have extended Markdown tables to allow multiple lines in cells (using `<p>` or `<br>`) or basic lists (using `<ul><li>` etc.). 

>[!IMPORTANT]
>
>Be careful when adding these HTML codes to Markdown tables. If your syntax is incorrect, you'll get a confusing validation error that doesn't accurately describe the problem. Check your HTML syntax to make sure that it's well-formed.

Not allowed in any table: iframes, spans of cells, embedded tables.

Not allowed in native Markdown table: nested or complex lists.

See [Tables](tables.md)

**Syntax**

```
| Header | Another header | Yet another header |
|--- |--- |--- |
| row 1 | row 1 column 2 | row 1 column 3 |
| row 2 | row 2 column 2 | row 2 column 3 |
```

**Example**

| Header | Another header | Yet another header |
|--- |--- |--- |
| row 1 | row 1 column 2 | row 1 column 3 |
| row 2 | row 2 column 2 | row 2 column 3 |

Simple tables work adequately in Markdown. However, tables that include multiple paragraphs or lists within a cell are difficult to work with. For such content, we recommend using a different format, such as headings & text.

**Markdown table with paragraph breaks and lists**

```
| Header | Another header | Yet another header |
|------------|----------|----------------|
| row 1 | first paragraph in cell<p>second paragraph in cell(`<p>`)<br>line break (`br`) | row 1 column 3 |
| row 2 | bullet list<ul><li>item 1</li><li>item 2</li><li>item 3</li></ul> | row 2 column 3 |
```

**Example**

| Header | Another header | Yet another header |
|------------|----------|----------------|
| row 1 | first paragraph in cell<p>second paragraph in cell(`<p>`)<br>line break (`br`) | row 1 column 3 |
| row 2 | bullet list<ul><li>item 1</li><li>item 2</li><li>item 3</li></ul> | row 2 column 3 |

**Markdown table with line breaks and fake list**

Workaround with manual bullets.

```
| Color | Things to Do |
|--- |--- |
| Red | * Read <br> * Write <br> * Study |
| Blue | * Swim <br> * Run <br> * Lift <br> **Note**: Remember to train smart.|
```

**Example**

| Color | Things to Do |
|--- |--- |
| Red | * Read <br> * Write <br> * Study |
| Blue | * Swim <br> * Run <br> * Lift <br> **Note**: Remember to train smart.|
.32


## Tabs

A tab is a clickable area at the top of a section that shows different content. When a tab is clicked, the tab's contents are shown, and the contents of other tabs is hidden. 

To create a tab set, add `>[!BEGINTABS]` at the beginning of the tab set and `>[!ENDTABS]` after the last tab. Add `>[!TAB <tab title>]` tags for each tab section, and add the contents of each tab below it.

**Tab syntax**

```
>[!BEGINTABS]

>[!TAB iOS]

This content appears in the iOS tab.

>[!TAB Android]

This content appears in the Android tab.

>[!TAB Windows]

This content appears in the Windows tab.

>[!TAB MacOS]

This content appears in the MacOS tab.

>[!TAB Linux]

This content appears in the Linux tab.

>[!ENDTABS]
```

**Rendered**

>[!BEGINTABS]

>[!TAB iOS]

This content appears in the iOS tab.

>[!TAB Android]

This content appears in the Android tab.

>[!TAB Windows]

This content appears in the Windows tab.

>[!TAB MacOS]

This content appears in the MacOS tab.

>[!TAB Linux]

This content appears in the Linux tab.

>[!ENDTABS]

**Tab notes**

* Users cannot use in-page search (Ctrl+F/Cmd+F) to locate content within tabs that are not displayed.
* If the tab titles extend beyond the page view width in the user's browser, a horizontal scroll bar appears.
* You cannot format the tab titles. Any syntax you add will be passed through as part of the title. For example, `>[!TAB **iOS**]` will be displayed as `**iOS**`. 
* You can create multiple tab sets on a page, but you cannot nest a tab set within another tab set.
* A shaded background is applied to the tab set so that users can see distinguish the tab content from other content.

## Text highlighting

The Workfront team asked to be able to use yellow highlighting to indicate the preview of upcoming features. Here's how it works.

Example:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Rendered:

This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.

As a general rule, use `<span class="preview">` to highlight a paragraph or text within a paragraph, and use `<div class="preview">` for multiple paragraphs and components.

>[!NOTE]
>
>We're still working on improving the highlighting display of certain page elements such as notes and tables. Feel free to log JIRA bugs if you see improper rendering. In progress.
>
>VSC preview does not yet support highlighting.

## Video

Videos won't natively render in Markdown. To display a video inline, use the component indicator `[!VIDEO]` and then the url.

**Syntax**

```
>[!VIDEO](https://video.tv.adobe.com/v/29770/?quality=12)
```

**Example**

>[!VIDEO](https://video.tv.adobe.com/v/29770/?quality=12)

## Additional markdown syntax information

### Extended Markdown Components

We need to extend Markdown to support items that aren't included in common Markdown.

Special components are declared in a containing block quote using square brackets and an exclamation mark plus the reference for the type of block it is. For example, here's how to declare a note:  

```
>[!NOTE]
>
>This is a note.
```

* Notes (admonitions), including Note, Important, Tip, Caution, and Warning
* Embedded video
* More Like This (Related articles)
* Various UI tags for localization
* Component properties for headings, images, and code blocks
* Collapsible sections
* Text highlighting
* Page tabs

Use the Markdown block quote ( `>` ) at the beginning of every line to tie together a paragraph-based component, such as a note. To improve preview, add a line immediately after the start of the section that has only a block quote symbol (`>`). To end the section, add a blank line.

If you need to use subcomponents within components, add an extra level of block quotes (`>  >`) for that subcomponent section. For example, a NOTE within a DONOTLOCALIZE section should begin with `>  >`.

In some cases, we need to support specific settings for Markdown elements such as headings. If you need to change default settings, add the parameters in french braces `{# }` after the component.

### Blank lines

You can add some breathing room to your walls of text with blank lines. Use `<br>&nbsp;` as a workaround to add a blank line. 

Example: This is a first sentence of what could be a really long text. Let me insert a blank line between this paragraph and the next.

<br>&nbsp;

This may not seem very impressive here, but try out blank lines when you feel like your pages are too crowded.  

### Characters to "escape" {#characters-to-escape}

Several characters (`# { } [ ] < > * + - . !`) have a special meaning in Markdown or HTML for creating headings, images, lists, and other components. When you use these characters, the rendering engine thinks you're adding code. However, in some cases, you want to display these characters in your text. To do that, you need to "escape" the characters. The easiest escape method is to precede the character with a backslash (`\`). For example, if you want to start a line with a `#` character so that it's not interpreted as a heading, you would type `\#`:

`\# This is not a heading`

**Rendered:**

\# This is not a heading

The backslash works only with these characters: `# { } [ ] * + - . !`. If you need to escape characters such as angle brackets (such as `<yourname>`), you can either enclose the text in back ticks to apply an inline code block, or use the HTML entity code instead of the character. Examples of common HTML codes:

* `&lt;` (<)
* `&gt;` (>)
* `&amp;` (&)
* `&Hat;` (^)
* `&mdash;` (&mdash;)
* `&ndash;` (&ndash;)

A full list of HTML entities is available on the [Freeformatter website](https://www.freeformatter.com/html-entities.html). This will allow you to look up all special characters.

>[!NOTE]
>
>For chain steps such as "Choose File > Save As," you don't need to escape the `>` character because it's not next to other characters. For variables such as `<filename>` you'll want to escape the angle brackets using either code block `backticks` or character codes (`&lt;filename&gt;`).

If you use HTML entities in code blocks, the entity text is not converted to the special character. For example, `&gt;` appears in a code block as " `&gt;` " instead of " > ".

To escape back ticks ( &grave; ), use `&grave;` or insert the back tick within triple back ticks that wrap an inline code block.

### Unsupported items

There are a few Git-flavored Markdown items that we don't plan to support. The preview tool you use might enable some of these features, but don't rely on that.

**Task List**

Not supported

```
* [x] Set up Jersey Shore recording
* [x] Buy donuts with sprinkles
* [x] Take nap
* [ ] Wash ferret
```

**Emoji**

Not supported

```
:bowtie:
```

**Horizontal rule**

Not supported

```
***
```

**Block quotes**

We use block quotes (`>` at the beginning of a line) to indicated extended Markdown syntax such as notes and videos, described next. But you can also use `>` syntax to create a block quote section.

>[!NOTE]
>
>If you indent too far, such as six spaces instead of three, the content is rendered as a block quotes. Use the proper amount of indenting to avoid having the content rendered mistakely as a block quote.
