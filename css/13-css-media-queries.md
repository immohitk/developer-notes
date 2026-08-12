## Table of Contents

1. [Introduction](#introduction)
2. [What Are Media Queries?](#what-are-media-queries)
3. [Why Are Media Queries Important?](#why-are-media-queries-important)
4. [Media Query Syntax](#media-query-syntax)
5. [Media Types](#media-types)
6. [Media Features](#media-features)
7. [Width and Height](#width-and-height)
8. [min-width](#min-width)
9. [max-width](#max-width)
10. [Combining Conditions](#combining-conditions)
11. [Logical Operators](#logical-operators)
12. [Orientation](#orientation)
13. [Responsive Breakpoints](#responsive-breakpoints)
14. [Mobile-First Approach](#mobile-first-approach)
15. [Desktop-First Approach](#desktop-first-approach)
16. [Common Responsive Patterns](#common-responsive-patterns)
17. [Practical Examples](#practical-examples)
18. [Key Takeaways](#key-takeaways)
19. [References](#references)
20. [Quick Revision](#quick-revision)
21. [Best Practices](#best-practices)
22. [Common Mistakes](#common-mistakes)
23. [Interview Questions](#interview-questions)
24. [Practice Exercises](#practice-exercises)
25. [Related Topics](#related-topics)

---

# Introduction

CSS Media Queries are an important part of responsive web design.

They allow CSS styles to be applied conditionally based on characteristics of the device, viewport, or browsing environment.

For example, a webpage can use one layout on a large screen and a different layout on a smaller screen.

```css
@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

In this example, the style inside the media query is applied when the viewport width is `600px` or less.

Media queries are commonly used to adapt:

- Layouts
- Navigation
- Typography
- Spacing
- Images
- Components
- Columns
- Flexbox layouts
- Grid layouts

They are especially useful when building websites that need to work across different screen sizes.

Responsive design allows a webpage to provide a better user experience on:

- Mobile phones
- Tablets
- Laptops
- Desktop computers
- Large displays

Media queries work together with other CSS features such as Flexbox and Grid to create layouts that can adapt to different viewport sizes.

---

## Why Responsive Design Is Important

Users access websites from devices with different screen sizes and display characteristics.

A layout that works well on a large desktop screen may not provide the same experience on a smaller mobile screen.

For example, a desktop layout may display multiple elements in a row:

```text
┌────────────┬────────────┬────────────┐
│   Item 1   │   Item 2   │   Item 3   │
└────────────┴────────────┴────────────┘
```

On a smaller screen, the same elements may need to be arranged vertically:

```text
┌────────────┐
│   Item 1   │
├────────────┤
│   Item 2   │
├────────────┤
│   Item 3   │
└────────────┘
```

Media queries allow CSS to change the presentation of these elements according to the available viewport space.

---

## Responsive Design and Media Queries

Responsive design is an approach where a webpage adapts to different screen sizes and devices.

Media queries help implement responsive designs by allowing different CSS rules to be applied under different conditions.

For example:

```css
.container {
    display: flex;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

In this example:

- Larger screens use a horizontal Flexbox layout.
- Smaller screens use a vertical Flexbox layout.
- The HTML structure remains the same.
- Only the CSS presentation changes.

---

> 💡 **Pro Tip:** Think of a media query as a condition that tells CSS when a particular set of styles should be used.

---

> 💡 **Remember:** Media queries allow CSS to respond to different conditions and are one of the fundamental tools used to create responsive websites.