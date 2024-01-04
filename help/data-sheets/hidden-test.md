---
title: Hidden test page
description: This page is hidden from search and from the TOC
hide: yes
hidefromtoc: yes
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
---
# Hidden test page

Activate? Recheck submit around 3:10 PM. Will it go live at 3:30 PM?

## Preview issue 

The following paragraph fails to render properly in VSC Preview. I'm not sure why.

If your password is managed by [!DNL Adobe], you can [change the password in your Adobe account](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## Note Types

All supported note types.

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>This is an important note.

>[!WARNING]
>
>This is a warning.

>[!CAUTION]
>
>This is a caution.

>[!ADMIN]
>
>This is an admin note which renders as ADMINISTRATION. EXL only.

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

>[!MORELIKETHIS]
>
>* Page 1
>* Page 2

## Badges

A badge is a colored label used as a content indicator. For example, you can add a badge to mark an article as _Beta_ or a section as _Premium_. You can change the color of a badge and associate a URL and tooltip.

[!BADGE Badge Example]

There are two types of badges, each with differing syntax:

* **Metadata** - Displays the badge near the top of a page
* **Inline** - Displays the badge where the syntax is located

### Metadata badges

Adding badge syntax in metadata places a badge above the page title (H1) in the article. 

You can name badges, for example, using _badge1_ or _badge2_. Or, you can be more creative (as long as the name begins with _badge_).

Metadata examples:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** This example displays a Premium badge with a URL and tool tip. 

* **badgeExam:** This example displays a dark badge with an exam ID number.

#### Inline badges

Specify the badge information on its own line or in a heading, table, or other page element. 

Here's the syntax for an inline badge with a beta label, blue color, URL, and tooltip:

   `[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Available badge colors

Badges use colors defined in Adobe Spectrum:

|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|

Syntax examples

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Requirements for badges

* Only two badges are allowed in metadata. This rule is configurable, so let us know if you need an exception.
* Only the badge label is required. The `type`, `url`, and `tooltip` parameters are optional. The `type` parameter determines the color. The `url` parameter lets users click the badge to open an article or page. The `tooltip` parameter displays the tooltip text on mouseover.
* Adding a badge to the `TOC.md` file displays the badge on every article in the guide. If you specify a URL for the badge to jump to an article, make sure that you use a root link (e.g., `/help/guide/article.md`) not a relative link (e.g., `article.md`) to account for articles in different folders.
* Adding a badge to `metadata-new.md` displays the badge on every article in a repo. 
* For metadata badges, make sure that all values are wrapped in quotes. For inline badges, make sure that `url` and `tooltip` are wrapped in quotes.
* Valid type values include *Informative* (default, blue), *Positive* (green), *Negative* (red), *Neutral* (dark gray), and *Caution* (yellow).
* Badge labels are localized.
* If multiple metadata badges are specified, badges are displayed in alphabetical order based on the badge name, such as `badge1:` or `badgeWeb`.
* If you want the URL to open in a new tab, use this syntax:

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  Rendered:

  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}

## Text highlighting

The Workfront team asked to be able to use yellow highlighting to indicate the preview of upcoming features. Here's how it works.

Example 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Rendered:

This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.

Example 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/data-sheets/assets/BusinessSupportThumbnail.png)

Last highlighted item.

</div>

Not highlighted
```

Rendered:

Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted

## Syntax highlighting for code blocks

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
