## Table of Contents

- [Introduction](#introduction)
- [What are Text and Font Properties?](#what-are-text-and-font-properties)
- [Font Family](#font-family)
- [Web Safe Fonts](#web-safe-fonts)
- [Google Fonts](#google-fonts)
- [Font Size](#font-size)
- [Font Weight](#font-weight)
- [Font Style](#font-style)
- [Line Height](#line-height)
- [Letter Spacing](#letter-spacing)
- [Word Spacing](#word-spacing)
- [Text Align](#text-align)
- [Text Decoration](#text-decoration)
- [Text Transform](#text-transform)
- [Text Shadow](#text-shadow)
- [White Space](#white-space)
- [Text Overflow](#text-overflow)
- [Overflow Wrap](#overflow-wrap)
- [Word Break](#word-break)
- [Font Stacks](#font-stacks)
- [Choosing the Right Typography](#choosing-the-right-typography)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)


---


## Introduction

Typography is one of the most important aspects of web design. Even a beautifully designed website can become difficult to use if the text is hard to read or poorly formatted.

CSS provides a rich set of properties that allow developers to control how text appears on a webpage. From choosing the right font family to adjusting spacing, alignment, and decoration, these properties help create interfaces that are both visually appealing and easy to read.

In this chapter, you'll learn how to style text effectively, choose appropriate fonts, improve readability, and apply typography best practices used in modern web development.

> 💡 **Pro Tip:** Great typography often goes unnoticed. When users can read content comfortably without effort, your typography is doing its job well.


---


## What are Text and Font Properties?

**Text and Font Properties** are CSS properties used to control how text appears on a webpage. They allow you to change the font, size, spacing, alignment, decoration, and many other aspects of typography.

Good typography is more than making text look attractive—it's about making content easy to read, understand, and navigate.

### Why Are Text and Font Properties Important?

Typography has a significant impact on user experience.

Using the right text styles helps you:

- Improve readability.
- Create a clear visual hierarchy.
- Make content easier to scan.
- Build a consistent design.
- Improve accessibility for all users.

### Common Text and Font Properties

| Property | Purpose |
|----------|---------|
| `font-family` | Specifies the typeface used for text. |
| `font-size` | Sets the size of the text. |
| `font-weight` | Controls the thickness of characters. |
| `font-style` | Applies styles such as italic text. |
| `line-height` | Controls the space between lines of text. |
| `letter-spacing` | Adjusts the spacing between letters. |
| `word-spacing` | Adjusts the spacing between words. |
| `text-align` | Aligns text horizontally. |
| `text-decoration` | Adds or removes decorations such as underlines. |
| `text-transform` | Changes the capitalization of text. |
| `text-shadow` | Adds shadow effects to text. |

### Example

```css
h1 {
    font-family: Arial, sans-serif;
    font-size: 32px;
    font-weight: bold;
    text-align: center;
}

p {
    line-height: 1.6;
    letter-spacing: 0.5px;
}
```

### Before vs After

**Without Typography**

```text
WELCOME TO DEVELOPER NOTES
this text is difficult to read because everything looks the same.
```

**With Typography**

```text
Welcome to Developer Notes

This text is easier to read because it has a clear heading,
proper spacing, and improved formatting.
```

Notice how typography improves readability without changing the actual content.

> 💡 **Pro Tip:** Users often decide whether to continue reading within a few seconds. Good typography encourages them to stay, while poor typography can make even great content difficult to read.

### 🌍 Real-World Usage

Text and font properties are used on every website, including:

- Blogs
- Documentation websites
- E-commerce stores
- Dashboards
- Landing pages
- News websites
- Portfolio websites

Whether you're building a personal portfolio or a large application, typography is one of the most important parts of the user interface.


---


## Font Family

The **`font-family`** property specifies the typeface used to display text on a webpage.

Different fonts create different visual styles and can influence the readability, personality, and overall user experience of a website.

### Syntax

```css
selector {
    font-family: font-name;
}
```

### Example

```css
h1 {
    font-family: Arial, sans-serif;
}

p {
    font-family: Georgia, serif;
}
```

### Common Font Categories

CSS groups fonts into several generic families.

| Font Family | Description | Common Examples |
|-------------|-------------|-----------------|
| `serif` | Letters have small decorative strokes (serifs). | Times New Roman, Georgia |
| `sans-serif` | Clean fonts without decorative strokes. | Arial, Helvetica, Verdana |
| `monospace` | Every character has the same width. | Courier New, Consolas |
| `cursive` | Handwriting-style fonts. | Brush Script MT |
| `fantasy` | Decorative or artistic fonts. | Papyrus *(varies by system)* |

### Looks Like

```text
Serif
The quick brown fox jumps over the lazy dog.

Sans-serif
The quick brown fox jumps over the lazy dog.

Monospace
The quick brown fox jumps over the lazy dog.
```

Although the text looks the same here, these font families have very different appearances when rendered by the browser.

### Font Fallback

It is good practice to specify more than one font.

```css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```

The browser checks the fonts from left to right.

- If **Arial** is available, it is used.
- Otherwise, it tries **Helvetica**.
- If neither is available, it uses the generic **sans-serif** font.

This is known as a **font fallback**.

### Advantages

- Gives your website a unique visual identity.
- Improves readability.
- Helps maintain a consistent design across pages.
- Allows fallback fonts if the preferred font is unavailable.

### Limitations

- Not every computer has the same fonts installed.
- Decorative fonts can reduce readability when overused.
- Some custom fonts require additional downloads.

> 💡 **Pro Tip:** Use **sans-serif** fonts for most websites because they are generally easier to read on digital screens. Reserve decorative fonts for logos, headings, or special design elements.

### 🌍 Real-World Usage

Different font families are commonly used for different purposes.

| Font Family | Common Usage |
|-------------|--------------|
| Serif | Books, newspapers, editorial websites |
| Sans-serif | Modern websites, dashboards, applications |
| Monospace | Code editors, technical documentation, terminals |
| Cursive | Invitations, signatures, decorative headings |
| Fantasy | Posters, games, creative designs |

### 📌 Did You Know?

Almost every modern website uses a **font stack** instead of a single font.

This ensures that if a preferred font isn't available, the browser automatically chooses the next best option, keeping the design readable and consistent.

### ⚠️ Important

Never rely on a single font.

Always provide one or more fallback fonts, ending with a **generic font family** such as:

- `serif`
- `sans-serif`
- `monospace`

This improves compatibility across different operating systems and browsers.


---

## Web Safe Fonts

**Web Safe Fonts** are fonts that are commonly pre-installed on most operating systems and devices.

Because these fonts are already available on the user's computer, the browser can display them immediately without downloading additional font files.

This makes them reliable and compatible across different browsers and platforms.

### Why Use Web Safe Fonts?

Web Safe Fonts offer several advantages:

- Fast loading because no font download is required.
- Good compatibility across operating systems.
- Simple to use.
- Reliable fallback option when custom fonts are unavailable.

### Common Web Safe Fonts

| Font | Category | Common Usage |
|------|----------|--------------|
| Arial | Sans-serif | Websites, applications |
| Helvetica | Sans-serif | Modern interfaces (mainly macOS) |
| Verdana | Sans-serif | Websites with improved readability |
| Tahoma | Sans-serif | User interfaces |
| Trebuchet MS | Sans-serif | Headings and websites |
| Times New Roman | Serif | Articles, documents |
| Georgia | Serif | Blogs and editorial content |
| Courier New | Monospace | Code examples |
| Consolas | Monospace | Programming editors (Windows) |

### Example

```css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```

In this example:

- The browser first looks for **Arial**.
- If Arial is unavailable, it tries **Helvetica**.
- If neither is available, it uses the default **sans-serif** font.

### Web Safe Font Stack

A **font stack** is a list of fonts arranged in order of preference.

```css
font-family: Arial, Helvetica, sans-serif;
```

This ensures your website remains readable even if the preferred font is unavailable.

### Advantages

- No additional downloads.
- Faster page loading.
- Excellent browser compatibility.
- Easy to implement.

### Limitations

- Limited design choices.
- Different operating systems may display fonts slightly differently.
- Less unique compared to custom web fonts.

> 💡 **Pro Tip:** Even if you're using Google Fonts or other custom fonts, always include Web Safe Fonts as fallbacks. This ensures your content remains readable if the custom font fails to load.

### 🌍 Real-World Usage

Web Safe Fonts are commonly used for:

- Fallback fonts
- Internal business applications
- Documentation websites
- Performance-focused websites
- Email templates, where custom fonts may not be supported

### 📌 Did You Know?

Not every operating system includes the same fonts.

For example, **Helvetica** is common on macOS but isn't installed by default on many Windows systems. That's why developers use **font stacks** instead of relying on a single font.

### ⚠️ Important

Web Safe Fonts improve compatibility, but they don't guarantee identical rendering on every device.

Font smoothing, operating system rendering, and browser differences can still cause slight variations in appearance.


---


## Google Fonts

**Google Fonts** is a free library of web fonts that allows developers to use high-quality typography without requiring users to install fonts on their devices.

Unlike Web Safe Fonts, Google Fonts are downloaded by the browser when the webpage loads, allowing websites to use a much wider variety of typefaces.

### Why Use Google Fonts?

Google Fonts provide:

- Hundreds of free fonts.
- Consistent appearance across devices.
- Easy integration with websites.
- Professional typography without purchasing licenses.

### Method 1: Using the `<link>` Element (Recommended)

Visit **Google Fonts**, choose a font, and copy the generated `<link>` element into the `<head>` section of your HTML.

**HTML**

```html
<head>
    <link
        rel="preconnect"
        href="https://fonts.googleapis.com"
    >

    <link
        rel="preconnect"
        href="https://fonts.gstatic.com"
        crossorigin
    >

    <link
        href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
        rel="stylesheet"
    >
</head>
```

**CSS**

```css
body {
    font-family: "Roboto", sans-serif;
}
```

---

### Method 2: Using `@import`

Google Fonts can also be imported directly into a CSS file.

```css
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

body {
    font-family: "Roboto", sans-serif;
}
```

Although this method works, the `<link>` method is generally preferred because it allows browsers to start downloading fonts earlier.

### Advantages

- Large collection of free fonts.
- Easy to integrate.
- Consistent appearance across devices.
- Regularly updated and maintained.
- Excellent browser support.

### Limitations

- Requires an internet connection unless fonts are self-hosted.
- Additional font files increase page size.
- Loading many font families or weights can affect performance.

> 🚀 **Performance Tip:** Load only the font weights you actually use (for example, `400` and `700`) instead of importing every available weight. This reduces download size and improves page load performance.

### 🌍 Real-World Usage

Google Fonts are commonly used for:

- Business websites
- Portfolio websites
- Blogs
- Landing pages
- E-commerce websites
- Dashboards
- Documentation sites

### 📌 Did You Know?

Many modern websites combine **Google Fonts** with **Web Safe Fonts**.

Example:

```css
body {
    font-family: "Roboto", Arial, sans-serif;
}
```

If Roboto fails to load, the browser automatically falls back to Arial or another sans-serif font.

### ⚠️ Important

Avoid importing too many fonts.

Using multiple font families and numerous font weights increases download size, which can slow down page loading and negatively affect user experience.


---


## Font Size

The **`font-size`** property specifies the size of text displayed on a webpage.

Choosing an appropriate font size is important for readability, accessibility, and creating a clear visual hierarchy.

### Syntax

```css
selector {
    font-size: value;
}
```

### Example

```css
h1 {
    font-size: 36px;
}

h2 {
    font-size: 28px;
}

p {
    font-size: 16px;
}
```

### Before vs After

**Without `font-size`**

```text
Heading
Subheading
Paragraph text
```

**With `font-size`**

```text
LARGE HEADING

Medium Subheading

Regular paragraph text.
```

Different font sizes help users quickly understand the importance of each piece of content.

### Common Units

| Unit | Description | Example |
|------|-------------|---------|
| `px` | Fixed pixel size | `16px` |
| `em` | Relative to the parent element | `1.2em` |
| `rem` | Relative to the root (`html`) font size | `1rem` |
| `%` | Percentage of the parent font size | `120%` |

### Advantages

- Creates a clear visual hierarchy.
- Improves readability.
- Helps build responsive designs.
- Gives precise control over typography.

### Limitations

- Fixed units like `px` are less flexible for responsive designs.
- Inconsistent sizing can make a webpage look unbalanced.

> 💡 **Pro Tip:** Prefer using **`rem`** for most projects because it scales consistently across the website and respects the user's browser font size settings.

### 🌍 Real-World Usage

Developers commonly use different font sizes for different types of content.

| Element | Typical Size |
|---------|--------------|
| Main Heading (`h1`) | `2rem`–`3rem` |
| Section Heading (`h2`) | `1.5rem`–`2rem` |
| Paragraph | `1rem` |
| Small Text | `0.875rem` |

These values vary depending on the design, but they provide a common starting point.

### 📌 Did You Know?

The default font size in most browsers is **16px**.

Because of this, the following values are typically equivalent:

```css
16px
```

```css
1rem
```

```css
100%
```

Understanding this relationship makes it easier to work with relative units.

### ⚠️ Important

Avoid making text too small.

Very small text can reduce readability and create accessibility issues, especially on mobile devices or high-resolution screens.


---


## Font Weight

The **`font-weight`** property controls the **thickness (boldness)** of text.

It is commonly used to emphasize important content, create visual hierarchy, and improve readability.

### Syntax

```css
selector {
    font-weight: value;
}
```

### Example

```css
h1 {
    font-weight: bold;
}

h2 {
    font-weight: 600;
}

p {
    font-weight: normal;
}
```

### Before vs After

**Without `font-weight`**

```text
Developer Notes
CSS Typography
This is a paragraph.
```

**With `font-weight`**

```text
Developer Notes      ← Bold

CSS Typography       ← Semi-bold

This is a paragraph. ← Normal
```

Different font weights help users quickly identify headings, subheadings, and body text.

### Common Values

| Value | Meaning |
|--------|---------|
| `normal` | Normal text (equivalent to `400`) |
| `bold` | Bold text (equivalent to `700`) |
| `100` | Thin |
| `200` | Extra Light |
| `300` | Light |
| `400` | Normal |
| `500` | Medium |
| `600` | Semi Bold |
| `700` | Bold |
| `800` | Extra Bold |
| `900` | Black / Heavy |

> Not every font supports all weight values. Available weights depend on the font family being used.

### Example Using Numeric Values

```css
h1 {
    font-weight: 700;
}

h2 {
    font-weight: 600;
}

p {
    font-weight: 400;
}
```

### Recommended Values

| Content | Common Weight |
|---------|---------------|
| Main Heading | `700` |
| Section Heading | `600` |
| Body Text | `400` |
| Small Labels | `500` |

These are common conventions, not strict rules.

### Advantages

- Creates a clear visual hierarchy.
- Highlights important content.
- Improves readability.
- Gives a more professional appearance.

### Limitations

- Very heavy text can become difficult to read.
- Not all fonts provide every weight.
- Loading many font weights from Google Fonts can increase page size.

> 💡 **Pro Tip:** Load only the font weights you actually use. If your website only needs `400` and `700`, avoid importing every available weight.

### 🌍 Real-World Usage

Developers commonly use different font weights for:

- Headings
- Buttons
- Navigation menus
- Labels
- Cards
- Tables

Using different weights helps users quickly distinguish between different types of content.

### 📌 Did You Know?

The keywords:

```css
font-weight: normal;
```

and

```css
font-weight: 400;
```

produce the same result.

Similarly,

```css
font-weight: bold;
```

is equivalent to:

```css
font-weight: 700;
```

Many developers prefer numeric values because they provide finer control over typography.

### ⚠️ Important

Avoid making every heading and paragraph bold.

Using too many bold elements reduces emphasis because nothing stands out anymore. Reserve heavier weights for content that genuinely needs attention.


---


## Font Style

The **`font-style`** property specifies the style of a font.

It is commonly used to make text **italic** or **oblique**, helping emphasize words or phrases without changing the font family or weight.

### Syntax

```css
selector {
    font-style: value;
}
```

### Example

```css
h1 {
    font-style: normal;
}

em {
    font-style: italic;
}

.quote {
    font-style: oblique;
}
```

### Before vs After

**Without `font-style`**

```text
This is an important note.
```

**With `font-style: italic`**

```text
*This is an important note.*
```

**With `font-style: oblique`**

```text
/This is an important note./
```

> *Markdown cannot accurately display the visual difference between **italic** and **oblique**. In browsers, `oblique` is a slanted version of the font, while `italic` usually uses a specially designed italic typeface.*

### Common Values

| Value | Description |
|--------|-------------|
| `normal` | Displays the default font style. |
| `italic` | Displays the italic version of the font, if available. |
| `oblique` | Displays a slanted version of the font. |

### Example Using Different Styles

```css
.normal {
    font-style: normal;
}

.italic {
    font-style: italic;
}

.oblique {
    font-style: oblique;
}
```

### Italic vs Oblique

| Italic | Oblique |
|---------|----------|
| Uses a specially designed italic font (if available). | Slants the regular font. |
| More common in web development. | Less commonly used. |
| Better typography for supported fonts. | Used when no true italic version exists. |

### Advantages

- Highlights important content.
- Improves readability when used appropriately.
- Creates visual distinction without changing font size or weight.
- Supported by all modern browsers.

### Limitations

- Overusing italic text reduces its emphasis.
- Some fonts do not include a true italic version.
- The difference between `italic` and `oblique` may be difficult to notice with certain fonts.

> 💡 **Pro Tip:** Use **italic** for emphasis, quotes, book titles, or foreign words. Avoid styling large paragraphs in italic because they can become harder to read.

### 🌍 Real-World Usage

The `font-style` property is commonly used for:

- Quotes
- Captions
- Book and movie titles
- Foreign words and phrases
- `<em>` elements for emphasized text

### 📌 Did You Know?

The HTML `<em>` element is **emphasized text**, not "italic text."

Browsers display `<em>` in italic by default, but the emphasis comes from the HTML semantics. CSS simply controls how that emphasis is visually presented.

### ⚠️ Important

Don't use `font-style: italic` just to make text look different.

If the content is **semantically important**, use the appropriate HTML element (such as `<em>`) and then style it with CSS if needed. This improves accessibility and gives the content meaningful structure.


---


## Line Height

The **`line-height`** property controls the amount of vertical space between lines of text.

A well-chosen line height improves readability by preventing lines from appearing too close together or too far apart.

### Syntax

```css
selector {
    line-height: value;
}
```

### Example

```css
p {
    font-size: 16px;
    line-height: 1.6;
}
```

### Before vs After

**Without `line-height`**

```text
This is the first line of text.
This is the second line of text.
This is the third line of text.
```

**With `line-height: 1.8`**

```text
This is the first line of text.

This is the second line of text.

This is the third line of text.
```

Notice how increasing the line height makes paragraphs easier to read.

### Common Values

| Value | Description | Example |
|--------|-------------|---------|
| Number | Multiplies the current font size | `1.5` |
| Length | Fixed spacing | `24px` |
| Percentage | Relative to the font size | `150%` |
| `normal` | Browser default spacing | `normal` |

### Recommended Values

| Content | Recommended Line Height |
|----------|-------------------------|
| Headings | `1.2`–`1.4` |
| Paragraphs | `1.5`–`1.8` |
| Long articles | `1.6`–`2` |

These values are common guidelines and may vary depending on the font and design.

### Advantages

- Improves readability.
- Makes long paragraphs easier to scan.
- Creates a cleaner and more professional layout.
- Enhances accessibility.

### Limitations

- Very small values make text crowded.
- Very large values can make paragraphs feel disconnected.
- The ideal value depends on the font, font size, and layout.

> 💡 **Pro Tip:** For body text, a `line-height` between **1.5** and **1.8** is a great starting point. It usually provides a comfortable reading experience on both desktop and mobile devices.

### 🌍 Real-World Usage

Developers commonly adjust `line-height` for:

- Blog posts
- Documentation websites
- News articles
- Product descriptions
- Long-form content
- E-books and online guides

### 📌 Did You Know?

When you use a **unitless number**, such as:

```css
line-height: 1.5;
```

the value is multiplied by the current `font-size`.

For example:

```css
font-size: 20px;
line-height: 1.5;
```

Results in a computed line height of:

```text
30px
```

Using a unitless value is generally recommended because it scales automatically if the font size changes.

### ⚠️ Important

Prefer **unitless values** (such as `1.5`) over fixed values (such as `24px`) whenever possible.

Unitless values are more flexible, easier to maintain, and work better in responsive layouts because they automatically adapt to different font sizes.


---


## Letter Spacing

The **`letter-spacing`** property controls the amount of horizontal space between individual characters in text.

Adjusting letter spacing can improve readability, create emphasis, and give text a modern or elegant appearance.

### Syntax

```css
selector {
    letter-spacing: value;
}
```

### Example

```css
h1 {
    letter-spacing: 3px;
}

p {
    letter-spacing: 0.5px;
}
```

### Before vs After

**Without `letter-spacing`**

```text
Developer Notes
```

**With `letter-spacing: 5px`**

```text
D e v e l o p e r   N o t e s
```

Increasing the spacing makes each character more visually separated.

### Common Values

| Value | Description | Example |
|--------|-------------|---------|
| `normal` | Default spacing | `normal` |
| Positive value | Increases spacing | `2px` |
| Negative value | Decreases spacing | `-1px` |

### Example Using Different Values

```css
.normal {
    letter-spacing: normal;
}

.wide {
    letter-spacing: 4px;
}

.tight {
    letter-spacing: -0.5px;
}
```

### Recommended Values

| Content | Recommended Value |
|----------|-------------------|
| Main Headings | `1px`–`3px` |
| Buttons | `0.5px`–`1px` |
| Body Text | `0px`–`0.5px` |

These values are general guidelines and may vary depending on the font and design.

### Advantages

- Improves readability for headings.
- Creates a clean and modern appearance.
- Helps emphasize important text.
- Gives designers more control over typography.

### Limitations

- Too much spacing makes words harder to recognize.
- Negative spacing can reduce readability.
- Different fonts respond differently to spacing adjustments.

> 💡 **Pro Tip:** Use subtle letter spacing for headings and buttons, but avoid applying large spacing to long paragraphs because it slows reading.

### 🌍 Real-World Usage

The `letter-spacing` property is commonly used for:

- Website headings
- Navigation menus
- Buttons
- Logos
- Hero sections
- Marketing landing pages

### 📌 Did You Know?

Many premium brands use **slightly increased letter spacing** in headings and logos to create a clean, elegant, and premium visual style.

Small adjustments often have a bigger impact than large ones.

### ⚠️ Important

Use `letter-spacing` carefully.

Large positive values can make text difficult to read, while negative values may cause characters to overlap. Always preview the result on different screen sizes and devices.