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