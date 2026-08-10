## Table of Contents

- [Introduction](#introduction)
- [What Are CSS Backgrounds?](#what-are-css-backgrounds)
- [Why Are CSS Backgrounds Important?](#why-are-css-backgrounds-important)
- [Background Color](#background-color)
- [Background Image](#background-image)
- [Background Repeat](#background-repeat)
- [Background Position](#background-position)
- [Background Size](#background-size)
- [Background Attachment](#background-attachment)
- [Background Shorthand](#background-shorthand)
- [Multiple Backgrounds](#multiple-backgrounds)
- [Background Origin](#background-origin)
- [Background Clip](#background-clip)
- [Background Blend Mode](#background-blend-mode)
- [Common Use Cases](#common-use-cases)
- [Key Takeaways](#key-takeaways)
- [References](#references)
- [Quick Revision](#quick-revision)
- [Best Practices](#best-practices)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Exercises](#practice-exercises)
- [Related Topics](#related-topics)

---

# Introduction

CSS backgrounds are used to control the **background appearance of HTML elements**.

They allow you to add visual backgrounds such as:

- Colors
- Images
- Patterns
- Multiple background layers

For example:

```css
body {
    background-color: lightblue;
}
```

This applies a light blue background to the `<body>` element.

A background image can also be added:

```css
.hero {
    background-image: url("hero.jpg");
}
```

CSS provides several properties to control how backgrounds are displayed.

Some commonly used background properties are:

```css
background-color
background-image
background-repeat
background-position
background-size
background-attachment
```

These properties can be used individually or combined to create different background effects.

---

> 💡 **Pro Tip:** Learn the individual background properties first. Once you understand how each property works, the `background` shorthand becomes much easier to use.

---

> 💡 **Remember:** CSS backgrounds control the visual background of an element without changing the actual HTML content inside it.