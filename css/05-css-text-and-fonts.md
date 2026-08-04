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