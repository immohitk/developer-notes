## Table of Contents

- [Introduction](#introduction)
- [What is CSS Z-Index?](#what-is-css-z-index)
- [Why is CSS Z-Index Important?](#why-is-css-z-index-important)
- [Z-Index Property](#z-index-property)
- [How Z-Index Works](#how-z-index-works)
- [Stacking Order](#stacking-order)
- [Positive Z-Index](#positive-z-index)
- [Negative Z-Index](#negative-z-index)
- [Z-Index with Positioned Elements](#z-index-with-positioned-elements)
- [Stacking Context](#stacking-context)
- [Creating a Stacking Context](#creating-a-stacking-context)
- [Z-Index and Flexbox](#z-index-and-flexbox)
- [Z-Index and Grid](#z-index-and-grid)
- [Common Use Cases](#common-use-cases)
- [Comparison and Examples](#comparison-and-examples)
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

CSS `z-index` controls the **stacking order of overlapping elements**.

When multiple elements overlap, their stacking order determines which element appears in front and which element appears behind.

The `z-index` property is commonly used when working with:

- Overlapping elements
- Dropdown menus
- Modals
- Navigation bars
- Tooltips
- Notifications
- Image overlays
- Fixed and sticky elements

Understanding `z-index` is closely related to **CSS positioning**, **stacking order**, and **stacking contexts**.

> 💡 **Remember:** `z-index` controls the **stacking order of overlapping elements**.


---


## What is CSS Z-Index?

The CSS `z-index` property specifies the **stack order of an element**.

When elements overlap, the element with a higher stacking order is displayed in front of an element with a lower stacking order.

The `z-index` property accepts integer values, including:

- Positive values
- Zero
- Negative values

For example:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}


---


# Why is CSS Z-Index Important?

The `z-index` property is important when multiple elements **overlap** and their stacking order needs to be controlled.

Without controlling the stacking order, an element may appear behind another element even when it should visually appear in front.

`z-index` is commonly useful for:

- Navigation menus
- Dropdown menus
- Modal dialogs
- Tooltips
- Notifications
- Image overlays
- Badges
- Sticky elements
- Fixed elements
- Floating buttons

---

## Controlling Overlapping Elements

Consider two elements that overlap:

```css
.box-one {
    position: relative;
    z-index: 1;
}

.box-two {
    position: relative;
    z-index: 2;
}
```

When they overlap within the same stacking context, `.box-two` appears above `.box-one`.

```text
Front
  │
  └── Box Two   z-index: 2
  │
  └── Box One   z-index: 1
  │
Back
```

This allows developers to control which element should be visible on top.

---

## Dropdown Menus

`z-index` is commonly used with dropdown menus.

```css
.navbar {
    position: relative;
    z-index: 10;
}

.dropdown {
    position: absolute;
    z-index: 20;
}
```

The dropdown can appear above surrounding page content.

```text
┌─────────────────────────────┐
│ Navigation                  │
│     ┌───────────────────┐   │
│     │ Dropdown          │   │
│     │ Item 1            │   │
│     │ Item 2            │   │
│     └───────────────────┘   │
│                             │
│       Page Content          │
└─────────────────────────────┘
```

---

## Modal Dialogs

Modal windows usually need to appear above the main page content.

```css
.modal {
    position: fixed;
    z-index: 1000;
}
```

A modal can therefore be placed above other interface elements when the relevant stacking contexts allow it.

```text
┌─────────────────────────────┐
│       Page Content          │
│                             │
│     ┌─────────────────┐     │
│     │      Modal      │     │
│     │                 │     │
│     │     Close       │     │
│     └─────────────────┘     │
│                             │
└─────────────────────────────┘
```

---

## Tooltips

Tooltips often overlap nearby content.

```css
.tooltip {
    position: absolute;
    z-index: 100;
}
```

This allows the tooltip to appear above surrounding elements.

---

## Notifications

Notification messages may need to remain visible above the rest of the page.

```css
.notification {
    position: fixed;
    top: 20px;
    right: 20px;
    z-index: 1000;
}
```

For example:

```text
┌──────────────────────────────┐
│                         ┌────┐│
│                         │ 🔔 ││
│                         │New ││
│                         └────┘│
│                              │
│        Page Content          │
│                              │
└──────────────────────────────┘
```

---

## Image Overlays

`z-index` can also be used when text, buttons, or other elements need to appear over an image.

```css
.image-container {
    position: relative;
}

.image {
    position: relative;
    z-index: 1;
}

.image-label {
    position: absolute;
    bottom: 10px;
    left: 10px;
    z-index: 2;
}
```

The label can appear above the image.

---

## Fixed and Sticky Elements

Fixed and sticky elements can overlap normal page content.

For example:

```css
.header {
    position: sticky;
    top: 0;
    z-index: 100;
}
```

The `z-index` helps keep the header visually above other content when the elements overlap.

---

## Why a High `z-index` Is Not Always Enough

A common mistake is assuming that a very large `z-index` value always places an element above everything else.

For example:

```css
.element {
    position: relative;
    z-index: 9999;
}
```

Even a value such as `9999` does not automatically place the element above elements that belong to a different stacking context.

The browser considers the **stacking context** before comparing stacking levels.

> 💡 **Pro Tip:** If a high `z-index` value does not seem to work, check the element's parent stacking context instead of continuously increasing the number.

---

## Real-World Layering

A web page can contain many different layers:

```text
Highest Layer
     │
     ├── Modal
     ├── Notification
     ├── Dropdown
     ├── Sticky Header
     ├── Page Content
     └── Background
     │
Lowest Layer
```

`z-index` helps developers organize these overlapping layers.

---

## Common Layering Example

A simple layering system might use:

```css
.background {
    z-index: 0;
}

.content {
    z-index: 1;
}

.dropdown {
    z-index: 10;
}

.header {
    z-index: 20;
}

.modal {
    z-index: 100;
}
```

The exact values are not important by themselves. What matters is the intended **stacking order**.

> ⚠️ **Important:** There is no special meaning to values such as `10`, `100`, or `1000`. They are simply numbers used to establish stacking levels within the relevant stacking context.

---

## Why Understanding Z-Index Matters

Understanding `z-index` helps prevent common UI problems such as:

- Dropdowns appearing behind content
- Modals appearing behind headers
- Tooltips being hidden
- Notifications appearing underneath other elements
- Buttons becoming inaccessible because another layer covers them
- Overlays appearing behind images or containers

A good understanding of `z-index` also makes it easier to debug complex layouts.

---

> 💡 **Remember:** `z-index` is important because it gives developers control over the **visual layering of overlapping elements**. However, the final result depends on the element's **stacking context** and stacking order.