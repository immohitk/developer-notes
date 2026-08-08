## Table of Contents

- [Introduction](#introduction)
- [What is CSS Position?](#what-is-css-position)
- [Why is CSS Position Important?](#why-is-css-position-important)
- [Position Property Overview](#position-property-overview)
- [`static`](#static)
- [`relative`](#relative)
- [`absolute`](#absolute)
- [`fixed`](#fixed)
- [`sticky`](#sticky)
- [Comparison Table](#comparison-table)
- [Real-World Examples](#real-world-examples)
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

CSS positioning controls how elements are placed within a webpage.

By default, elements follow the normal document flow. The CSS `position` property allows developers to change how an element participates in that flow and how its location is calculated.

CSS positioning is commonly used to create:

- Navigation bars
- Dropdown menus
- Tooltips
- Modals
- Floating buttons
- Overlays
- Sticky headers
- Badges
- Custom layouts

Understanding positioning is an important part of building modern CSS layouts.


---


# What is CSS Position?

The CSS `position` property specifies how an element is positioned in a document.

The main values are:

```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

These values determine how the element behaves in relation to:

- The normal document flow
- Its containing element
- The viewport
- The scrolling position

Positioning can be combined with the following offset properties:

```css
top
right
bottom
left
```

Example:

```css
.box {
    position: relative;
    top: 20px;
    left: 30px;
}
```


---


# Why is CSS Position Important?

CSS positioning allows developers to precisely control the location and behavior of elements.

It is especially useful when creating interfaces that contain elements that need to:

- Move relative to their original position.
- Be positioned inside another element.
- Stay visible while scrolling.
- Overlay other elements.
- Remain fixed to the viewport.

For example, a notification badge can be positioned relative to an icon:

```css
.icon {
    position: relative;
}

.badge {
    position: absolute;
    top: 0;
    right: 0;
}
```

Understanding positioning also makes it easier to work with advanced layouts and UI components.


---


# Position Property Overview

The five main `position` values behave differently.

| Value | Normal Flow | Positioned Relative To |
|-------|--------------|------------------------|
| `static` | Yes | Normal document flow |
| `relative` | Yes | Its normal position |
| `absolute` | No | Nearest positioned ancestor |
| `fixed` | No | Viewport |
| `sticky` | Yes, until stuck | Scroll container / containing block |

The following sections explain each value in detail.

---

> 💡 **Chapter Goal:** By the end of this chapter, you should be able to understand how each CSS positioning mode works, choose the appropriate positioning method, and build common UI components using `position`.