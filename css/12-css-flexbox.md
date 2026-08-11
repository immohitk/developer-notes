## Table of Contents

1. [Introduction](#introduction)
2. [What Is Flexbox?](#what-is-flexbox)
3. [Why Is Flexbox Important?](#why-is-flexbox-important)
4. [Flex Container and Flex Items](#flex-container-and-flex-items)
5. [Creating a Flex Container](#creating-a-flex-container)
6. [Flex Direction](#flex-direction)
7. [Main Axis and Cross Axis](#main-axis-and-cross-axis)
8. [Flex Wrap](#flex-wrap)
9. [Flex Flow](#flex-flow)
10. [Justify Content](#justify-content)
11. [Align Items](#align-items)
12. [Align Content](#align-content)
13. [Gap](#gap)
14. [Row Gap and Column Gap](#row-gap-and-column-gap)
15. [Flex Item Properties](#flex-item-properties)
16. [Order](#order)
17. [Flex Grow](#flex-grow)
18. [Flex Shrink](#flex-shrink)
19. [Flex Basis](#flex-basis)
20. [Flex Shorthand](#flex-shorthand)
21. [Align Self](#align-self)
22. [Nested Flex Containers](#nested-flex-containers)
23. [Centering with Flexbox](#centering-with-flexbox)
24. [Common Flexbox Layouts](#common-flexbox-layouts)
25. [Flexbox vs Grid](#flexbox-vs-grid)
26. [Common Use Cases](#common-use-cases)
27. [Key Takeaways](#key-takeaways)
28. [References](#references)
29. [Quick Revision](#quick-revision)
30. [Best Practices](#best-practices)
31. [Common Mistakes](#common-mistakes)
32. [Interview Questions](#interview-questions)
33. [Practice Exercises](#practice-exercises)
34. [Related Topics](#related-topics)

---

# Introduction

**Flexbox**, short for **Flexible Box Layout**, is a CSS layout system designed to arrange elements efficiently within a container.

It provides a convenient way to control:

- The direction of elements
- Alignment
- Spacing
- Distribution of available space
- Sizing of elements
- Responsive layouts

A basic Flexbox container is created using:

```css
.container {
    display: flex;
}
```

When an element becomes a flex container, its **direct children** become flex items.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

The structure becomes:

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

---

## Why Was Flexbox Introduced?

Before Flexbox, developers commonly used techniques such as:

- Floats
- Inline-block
- Tables
- Positioning

These techniques could make common layout tasks unnecessarily complicated.

For example, vertically and horizontally centering an element often required additional CSS techniques.

Flexbox provides dedicated properties for these types of layout problems.

---

## One-Dimensional Layout

Flexbox is primarily a **one-dimensional layout system**.

This means it handles layout in one direction at a time:

```text
Horizontal
→ Row

Vertical
→ Column
```

For example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

arranges items horizontally.

While:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

arranges items vertically.

---

## Basic Visual Example

With:

```css
.container {
    display: flex;
}
```

the default layout is:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Item 1  │  │ Item 2  │  │ Item 3  │
└─────────┘  └─────────┘  └─────────┘
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

the layout becomes:

```text
┌─────────┐
│ Item 1  │
└─────────┘
     ↓
┌─────────┐
│ Item 2  │
└─────────┘
     ↓
┌─────────┐
│ Item 3  │
└─────────┘
```

---

## Flexbox Is Controlled by the Parent

One important concept is that many Flexbox properties are applied to the **parent container**.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

These properties control how the child elements are positioned and aligned within the container.

Individual flex items also have their own properties, which will be covered later.

---

## Common Uses of Flexbox

Flexbox is commonly used for:

- Navigation bars
- Button groups
- Card layouts
- Toolbars
- Form layouts
- Headers
- Footers
- Centering content
- Aligning icons and text
- Responsive components

---

> 💡 **Pro Tip:** Don't try to memorize every Flexbox property at once. First understand the relationship between the **container and its items**, then learn how the main axis and cross axis control their layout.

---

> 💡 **Remember:** `display: flex` turns an element into a **flex container**, and its direct children become **flex items**. Flexbox is designed primarily for arranging items in a single direction at a time.

---

# What Is Flexbox?

**Flexbox** is a CSS layout model that provides a flexible way to arrange elements inside a container.

It is designed to make it easier to control the:

- Direction of elements
- Alignment of elements
- Distribution of available space
- Size of elements
- Spacing between elements

Flexbox is especially useful when elements need to adapt to the available space.

---

## Flex Container

The element on which Flexbox is enabled is called the **flex container**.

A flex container is created using:

```css
.container {
    display: flex;
}
```

Example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

Here:

```text
.container
    ↓
Flex Container
```

---

## Flex Items

The **direct children** of a flex container automatically become **flex items**.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```text
Flex Container
      │
      ├── Item 1 → Flex Item
      ├── Item 2 → Flex Item
      └── Item 3 → Flex Item
```

You do not need to add a separate property to the children to make them flex items.

Simply using:

```css
display: flex;
```

on the parent is enough.

---

## Only Direct Children Become Flex Items

Consider:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

If:

```css
.container {
    display: flex;
}
```

then:

```text
.container
    ↓
Flex Container

.item
    ↓
Flex Item

span
    ↓
Not a flex item of .container
```

The `<span>` is a descendant of the flex container, but it is not its direct child.

This distinction is important when working with nested layouts.

---

## Flexbox Is One-Dimensional

Flexbox is primarily a **one-dimensional layout system**.

It works along one main direction at a time:

```text
Row
→ Horizontal layout

Column
→ Vertical layout
```

For example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

creates a horizontal layout.

While:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

creates a vertical layout.

---

## Default Flexbox Direction

When only:

```css
display: flex;
```

is specified, Flexbox uses:

```css
flex-direction: row;
```

Therefore:

```css
.container {
    display: flex;
}
```

is equivalent to:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

The items are placed along the horizontal main axis.

```text
Item 1 → Item 2 → Item 3
────────────────────────→
       Main Axis
```

---

## Flexbox Layout Model

A basic Flexbox layout can be visualized as:

```text
┌─────────────────────────────────────┐
│          Flex Container             │
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐   │
│  │ Item 1│  │ Item 2│  │ Item 3│   │
│  └───────┘  └───────┘  └───────┘   │
│                                     │
└─────────────────────────────────────┘
```

The container controls how its flex items are laid out.

---

## Flex Container Properties

Many important Flexbox properties are applied to the container.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

These properties control the arrangement of the flex items.

Common container properties include:

```css
display
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
gap
```

---

## Flex Item Properties

Individual flex items can also have their own Flexbox properties.

For example:

```css
.item {
    flex-grow: 1;
}
```

Common item properties include:

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

This gives Flexbox two levels of control:

```text
Flex Container
      ↓
Controls overall layout

Flex Items
      ↓
Controls individual items
```

---

## Flexbox and Available Space

One of the main strengths of Flexbox is its ability to distribute available space.

For example:

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

The available space is distributed between the flex items.

```text
┌─────────────────────────────────────┐
│ Item 1          Item 2          Item 3│
└─────────────────────────────────────┘
```

This makes Flexbox useful for layouts where spacing needs to adapt to different container sizes.

---

## Flexbox Does Not Mean "Everything Is Automatically Responsive"

Flexbox provides flexible layout behavior, but a responsive design may still require:

- Flexible widths
- `flex-wrap`
- Media queries
- Relative units
- Minimum and maximum sizes

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

allows items to move onto additional lines when necessary.

---

> 💡 **Pro Tip:** Remember the basic relationship:

```text
display: flex
      ↓
Parent becomes Flex Container
      ↓
Direct children become Flex Items
      ↓
Flexbox controls their layout
```

Once this relationship is clear, the rest of Flexbox becomes much easier to understand.

---

> 💡 **Remember:** Flexbox is not a property applied to individual elements independently. It establishes a **layout context on a parent**, which controls the arrangement of its direct children.

---

# Why Is Flexbox Important?

Flexbox is important because it provides a dedicated system for creating **flexible, efficient, and responsive one-dimensional layouts**.

Instead of relying on older layout techniques or complicated positioning, Flexbox provides properties specifically designed for controlling the relationship between a container and its items.

---

## 1. Makes Alignment Easier

One of the biggest advantages of Flexbox is that it makes alignment much easier.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This can center an item horizontally and vertically within the flex container.

```text
┌──────────────────────────────┐
│                              │
│                              │
│          ┌────────┐          │
│          │  Item  │          │
│          └────────┘          │
│                              │
│                              │
└──────────────────────────────┘
```

Without Flexbox, achieving this kind of alignment often required more complicated CSS.

---

## 2. Controls Space Distribution

Flexbox provides properties for distributing available space between items.

For example:

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

The first item is placed at the beginning, the last item at the end, and the remaining space is distributed between them.

```text
┌──────────────────────────────────────┐
│ Item 1          Item 2          Item 3│
└──────────────────────────────────────┘
```

This is particularly useful for navigation bars and headers.

---

## 3. Supports Flexible Sizing

Flexbox allows items to grow or shrink based on the available space.

For example:

```css
.item {
    flex-grow: 1;
}
```

Items can use available space instead of requiring fixed dimensions.

This makes layouts more flexible when the container changes size.

---

## 4. Makes Responsive Layouts Easier

Flexbox can adapt to different container sizes.

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

When there is not enough horizontal space, items can move onto another line.

```text
Large screen:

┌────┐ ┌────┐ ┌────┐ ┌────┐
│ 1  │ │ 2  │ │ 3  │ │ 4  │
└────┘ └────┘ └────┘ └────┘


Smaller screen:

┌────┐ ┌────┐
│ 1  │ │ 2  │
└────┘ └────┘

┌────┐ ┌────┐
│ 3  │ │ 4  │
└────┘ └────┘
```

This behavior is useful for responsive components.

---

## 5. Reduces the Need for Positioning

Many layouts that might otherwise be created using:

```css
position
top
left
right
bottom
```

can be handled more naturally using Flexbox.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This is generally more appropriate for normal layout alignment than manually positioning elements.

---

## 6. Provides Clear Layout Control

Flexbox separates layout responsibilities into meaningful properties.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}
```

Each property has a specific purpose:

```text
flex-direction
→ Direction of the layout

justify-content
→ Distribution along the main axis

align-items
→ Alignment along the cross axis

gap
→ Space between items
```

This makes the layout easier to understand and maintain.

---

## 7. Useful for Common UI Components

Many everyday UI components can be built naturally with Flexbox.

### Navigation Bar

```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

### Button Group

```css
.buttons {
    display: flex;
    gap: 10px;
}
```

### Card Row

```css
.cards {
    display: flex;
    gap: 20px;
}
```

### Header

```css
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

---

## 8. Works Well with Different Content Sizes

Flexbox does not require every item to have exactly the same size.

For example:

```html
<div class="container">
    <div>Short</div>
    <div>This is a longer item</div>
    <div>Medium content</div>
</div>
```

Flexbox can arrange these items while taking their different sizes into account.

This is useful for real-world content where text and element sizes are not always predictable.

---

## 9. Makes Spacing More Consistent

The `gap` property provides a simple way to create consistent spacing between flex items.

```css
.container {
    display: flex;
    gap: 20px;
}
```

Instead of manually adding margins to individual children, the container can define the spacing.

```text
Item 1    20px    Item 2    20px    Item 3
```

---

## 10. Improves Maintainability

Flexbox layouts can often be expressed with a small number of clear properties.

For example:

```css
.container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
```

The intent of the layout is easy to understand.

This can make CSS easier to read, modify, and maintain.

---

## Flexbox Compared with Older Layout Techniques

Before Flexbox, developers commonly used techniques such as:

```text
Floats
Inline-block
Tables
Absolute positioning
```

These approaches still have valid uses, but Flexbox provides a layout system specifically designed for flexible alignment and distribution.

A simplified comparison:

| Technique | Common Purpose |
|-----------|----------------|
| Float | Older page/content layouts |
| Inline-block | Inline element layouts |
| Positioning | Precise positioning |
| Flexbox | One-dimensional layouts |
| Grid | Two-dimensional layouts |

---

## Flexbox Is Not a Replacement for Everything

Flexbox is powerful, but it is not the best solution for every layout.

Use Flexbox when the layout is primarily:

```text
One direction
    ↓
Row or Column
```

For layouts requiring simultaneous control over:

```text
Rows
+
Columns
```

CSS Grid may be more appropriate.

---

> 💡 **Pro Tip:** Don't use Flexbox simply because it is available. First identify the layout problem. If you need to arrange and align items along one main direction, Flexbox is usually a strong choice.

---

> 💡 **Remember:** Flexbox is important because it turns common layout problems—**alignment, spacing, distribution, sizing, and responsive arrangement**—into problems that can be handled directly with dedicated CSS properties.

---

# Flex Container and Flex Items

Every Flexbox layout is based on two fundamental concepts:

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

The **flex container** is the parent element on which Flexbox is enabled.

The **flex items** are its direct children.

---

## Flex Container

A **flex container** is an element whose `display` property is set to:

```css
display: flex;
```

Example:

```css
.container {
    display: flex;
}
```

The element now establishes a Flexbox formatting context for its direct children.

---

## Flex Items

The direct children of a flex container become **flex items** automatically.

Example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

The result is:

```text
.container
     ↓
Flex Container
     │
     ├── Item 1 → Flex Item
     ├── Item 2 → Flex Item
     └── Item 3 → Flex Item
```

No `display: flex` declaration is required on the children.

---

## Direct Children Only

An important rule is that **only direct children** become flex items.

Consider:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

```css
.container {
    display: flex;
}
```

Here:

```text
.container
    ↓
Flex Container

.item
    ↓
Flex Item

span
    ↓
Not a flex item of .container
```

The `<span>` can become a flex item if `.item` itself becomes a flex container:

```css
.item {
    display: flex;
}
```

Now there are two Flexbox contexts:

```text
.container
    ↓
Flex Container
    │
    └── .item
          ↓
       Flex Container
          │
          └── span
                ↓
             Flex Item
```

---

## A Flex Container Can Also Be a Flex Item

An element can be both:

- A flex item of its parent
- A flex container for its own children

Example:

```html
<div class="outer">
    <div class="inner">
        <span>Content</span>
    </div>
</div>
```

```css
.outer {
    display: flex;
}

.inner {
    display: flex;
}
```

The relationship is:

```text
.outer
  ↓
Flex Container
  │
  └── .inner
        ↓
     Flex Item
     +
     Flex Container
        │
        └── span
              ↓
           Flex Item
```

This is useful for creating **nested Flexbox layouts**.

---

## Default Arrangement

When a flex container is created:

```css
.container {
    display: flex;
}
```

its direct children are arranged in a row by default.

```text
┌─────────────────────────────────────┐
│                                     │
│  ┌─────┐  ┌─────┐  ┌─────┐          │
│  │  1  │  │  2  │  │  3  │          │
│  └─────┘  └─────┘  └─────┘          │
│                                     │
└─────────────────────────────────────┘
```

This happens because the default value of:

```css
flex-direction
```

is:

```css
row
```

---

## Container Controls the Layout

Many Flexbox properties are applied to the container.

Example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

These properties control how the flex items are arranged.

The items themselves can also have Flexbox-specific properties.

For example:

```css
.item {
    flex-grow: 1;
}
```

This gives Flexbox two levels of control:

```text
Container
   ↓
Controls overall arrangement

Items
   ↓
Controls individual behavior
```

---

## Normal CSS Properties Still Work

Flex items are still normal CSS elements.

You can apply properties such as:

```css
.item {
    width: 100px;
    padding: 20px;
    margin: 10px;
    background-color: lightblue;
}
```

Flexbox adds additional layout behavior on top of normal CSS.

---

## Flex Container vs Flex Item

| Concept | Flex Container | Flex Item |
|---------|----------------|------------|
| Created by | `display: flex` | Automatically |
| Usually represents | Parent | Direct child |
| Controls children | Yes | No, not its siblings |
| Can use container properties | Yes | No |
| Can use item properties | It can also be an item if nested | Yes |
| Main purpose | Controls layout | Participates in layout |

---

## Example

```html
<div class="container">
    <div class="item">One</div>
    <div class="item">Two</div>
    <div class="item">Three</div>
</div>
```

```css
.container {
    display: flex;
}

.item {
    padding: 20px;
}
```

The parent creates the Flexbox layout:

```text
┌─────────────────────────────────────┐
│ Container                           │
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐   │
│  │ One   │  │ Two   │  │ Three │   │
│  └───────┘  └───────┘  └───────┘   │
│                                     │
└─────────────────────────────────────┘
```

---

> 💡 **Pro Tip:** When debugging a Flexbox layout, first identify **which element is the flex container**. Then identify its **direct children**. Most Flexbox properties make sense once you know exactly which container they belong to.

---

> 💡 **Remember:** `display: flex` creates the **flex container**, while its **direct children automatically become flex items**. A flex container can also be a flex item if it is itself a child of another flex container.

---

# Creating a Flex Container

To use Flexbox, an element must first be turned into a **flex container**.

This is done using:

```css
display: flex;
```

---

## Basic Syntax

```css
.container {
    display: flex;
}
```

Once `display: flex` is applied, the element becomes a flex container.

Its direct children automatically become flex items.

```text
.container
     ↓
Flex Container
     │
     ├── Item 1 → Flex Item
     ├── Item 2 → Flex Item
     └── Item 3 → Flex Item
```

---

## Basic Example

```html
<div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
</div>
```

```css
.container {
    display: flex;
}
```

By default, the items are arranged in a row:

```text
┌─────────────────────────────────────┐
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐   │
│  │ Item 1│  │ Item 2│  │ Item 3│   │
│  └───────┘  └───────┘  └───────┘   │
│                                     │
└─────────────────────────────────────┘
```

---

## What Changes When `display: flex` Is Applied?

Before Flexbox, block-level elements normally stack vertically.

```text
┌─────────┐
│ Item 1  │
└─────────┘

┌─────────┐
│ Item 2  │
└─────────┘

┌─────────┐
│ Item 3  │
└─────────┘
```

After:

```css
.container {
    display: flex;
}
```

the direct children are laid out according to Flexbox.

By default:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│ Item 1  │  │ Item 2  │  │ Item 3  │
└─────────┘  └─────────┘  └─────────┘
```

This happens because the default `flex-direction` is:

```css
row
```

---

## `display: flex` vs `display: block`

Consider:

```html
<div class="container">
    <div>One</div>
    <div>Two</div>
    <div>Three</div>
</div>
```

Without Flexbox:

```css
.container {
    display: block;
}
```

The children follow the normal block layout.

With:

```css
.container {
    display: flex;
}
```

the children become flex items and participate in the Flexbox layout.

```text
display: block
→ Normal block layout

display: flex
→ Flexbox layout
```

---

## Flex Container Is Still a Normal Element

Making an element a flex container does not remove its normal CSS properties.

You can still use:

```css
.container {
    width: 500px;
    height: 300px;
    padding: 20px;
    border: 1px solid black;
    background-color: lightgray;
    display: flex;
}
```

Flexbox controls how the children are laid out inside the container.

---

## Adding a Gap

A common pattern is to combine Flexbox with `gap`.

```css
.container {
    display: flex;
    gap: 20px;
}
```

This creates space between the flex items.

```text
Item 1
   ↓
  20px
   ↓
Item 2
   ↓
  20px
   ↓
Item 3
```

The `gap` property will be covered in more detail later.

---

## Creating a Column Layout

Although the default direction is a row, the container can be changed to a column.

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Result:

```text
┌─────────┐
│ Item 1  │
└─────────┘
     ↓
┌─────────┐
│ Item 2  │
└─────────┘
     ↓
┌─────────┐
│ Item 3  │
└─────────┘
```

The `flex-direction` property will be covered separately.

---

## Flex Container Establishes a Flex Formatting Context

When:

```css
display: flex;
```

is applied, the element establishes a **flex formatting context** for its contents.

Its direct children are laid out as flex items instead of following the normal layout behavior of the parent.

This is what enables Flexbox properties such as:

```css
justify-content
align-items
flex-wrap
gap
```

to control the layout.

---

## Inline Flex Container

CSS also provides:

```css
display: inline-flex;
```

This creates an **inline-level flex container**.

Example:

```css
.container {
    display: inline-flex;
}
```

The element itself participates in the surrounding inline layout, while its children are still laid out using Flexbox.

Compare:

```text
display: flex
→ Block-level flex container

display: inline-flex
→ Inline-level flex container
```

Both create Flexbox layouts for their children.

---

## `flex` vs `inline-flex`

Example:

```css
.block-container {
    display: flex;
}
```

and:

```css
.inline-container {
    display: inline-flex;
}
```

The main difference is how the **container itself participates in the surrounding layout**.

The children of both containers are still flex items.

---

## Example with `inline-flex`

```html
<div class="container">
    <span>One</span>
    <span>Two</span>
</div>

<div class="container">
    <span>Three</span>
    <span>Four</span>
</div>
```

```css
.container {
    display: inline-flex;
}
```

The containers can participate alongside other inline-level content.

---

## Common Pattern

A very common Flexbox setup is:

```css
.container {
    display: flex;
    gap: 20px;
    align-items: center;
}
```

This means:

```text
display: flex
→ Enable Flexbox

gap
→ Add space between items

align-items
→ Control cross-axis alignment
```

Additional properties can then be added depending on the layout requirements.

---

> 💡 **Pro Tip:** When starting a Flexbox layout, begin with the smallest useful declaration:

```css
.container {
    display: flex;
}
```

Then add properties such as `flex-direction`, `justify-content`, `align-items`, and `gap` only when the layout actually requires them. This keeps the CSS easier to understand and debug.

---

> 💡 **Remember:** `display: flex` is the declaration that creates a **flex container**. Its direct children become **flex items**, and the container can then control their direction, alignment, spacing, and distribution.

---

# Flex Direction

The `flex-direction` property controls the **direction in which flex items are placed** inside a flex container.

```css
.container {
    display: flex;
    flex-direction: row;
}
```

The default value is:

```css
row
```

---

## Syntax

```css
.container {
    display: flex;
    flex-direction: value;
}
```

The `flex-direction` property accepts four values:

```text
row
row-reverse
column
column-reverse
```

---

## `row`

The default value is:

```css
flex-direction: row;
```

Items are arranged from left to right in a left-to-right writing mode.

```text
┌────────┐  ┌────────┐  ┌────────┐
│ Item 1 │  │ Item 2 │  │ Item 3 │
└────────┘  └────────┘  └────────┘
      ────────────────────────→
            Main Axis
```

Example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

This is the same as:

```css
.container {
    display: flex;
}
```

because `row` is the default value.

---

## `row-reverse`

The `row-reverse` value reverses the direction of the row.

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

The items are placed in the opposite direction of `row`.

```text
┌────────┐  ┌────────┐  ┌────────┐
│ Item 3 │  │ Item 2 │  │ Item 1 │
└────────┘  └────────┘  └────────┘
←────────────────────────
        Main Axis
```

The visual order is reversed.

---

## `column`

The `column` value arranges items vertically.

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Result:

```text
┌────────┐
│ Item 1 │
└────────┘
     ↓
┌────────┐
│ Item 2 │
└────────┘
     ↓
┌────────┐
│ Item 3 │
└────────┘
```

The main axis is now vertical.

```text
Main Axis
    ↓
    ↓
    ↓
```

---

## `column-reverse`

The `column-reverse` value reverses the vertical direction.

```css
.container {
    display: flex;
    flex-direction: column-reverse;
}
```

Result:

```text
┌────────┐
│ Item 3 │
└────────┘
     ↑
┌────────┐
│ Item 2 │
└────────┘
     ↑
┌────────┐
│ Item 1 │
└────────┘
```

The items are arranged in the reverse direction of `column`.

---

## Comparing the Four Values

| Value | Direction | Main Axis |
|-------|-----------|-----------|
| `row` | Horizontal | Left → Right |
| `row-reverse` | Horizontal reversed | Right → Left |
| `column` | Vertical | Top → Bottom |
| `column-reverse` | Vertical reversed | Bottom → Top |

The exact visual direction can also be affected by the document's writing mode and direction.

---

## `row` Example

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>
```

```css
.container {
    display: flex;
    flex-direction: row;
}
```

Result:

```text
1 → 2 → 3
```

---

## `row-reverse` Example

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

Result:

```text
3 → 2 → 1
```

The items are visually arranged in the reverse direction.

---

## `column` Example

```css
.container {
    display: flex;
    flex-direction: column;
}
```

Result:

```text
1
↓
2
↓
3
```

---

## `column-reverse` Example

```css
.container {
    display: flex;
    flex-direction: column-reverse;
}
```

Result:

```text
3
↑
2
↑
1
```

---

## Flex Direction Changes the Main Axis

The `flex-direction` property is important because it determines the **main axis**.

With:

```css
flex-direction: row;
```

the main axis is horizontal.

```text
────────────────────→
     Main Axis
```

With:

```css
flex-direction: column;
```

the main axis is vertical.

```text
     Main Axis
          ↓
          ↓
          ↓
```

This is important when using properties such as:

```css
justify-content
align-items
```

because their behavior is based on the flex container's axes.

---

## `flex-direction` and `justify-content`

`justify-content` operates along the **main axis**.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
}
```

The items are centered horizontally.

```text
┌──────────────────────────────┐
│       1   2   3              │
└──────────────────────────────┘
```

If the direction changes:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```

the same `justify-content: center` centers the items along the vertical main axis.

```text
┌──────────────────────────────┐
│                              │
│          1                   │
│          2                   │
│          3                   │
│                              │
└──────────────────────────────┘
```

This is why understanding the main axis is essential when working with Flexbox.

---

## `flex-direction` and `align-items`

`align-items` operates along the **cross axis**.

For:

```css
flex-direction: row;
```

the cross axis is vertical.

For:

```css
flex-direction: column;
```

the cross axis is horizontal.

Therefore, changing `flex-direction` changes how these alignment properties behave.

---

## Reversing Direction vs Changing HTML Order

Consider:

```html
<div>1</div>
<div>2</div>
<div>3</div>
```

Using:

```css
flex-direction: row-reverse;
```

changes the visual direction without changing the HTML source order.

```text
HTML order:

1 → 2 → 3

Visual arrangement:

3 → 2 → 1
```

This distinction can be important for accessibility and logical document structure.

For many layouts, it is preferable to keep meaningful content in a logical HTML order and use CSS for presentation.

---

## Common Use Cases

### Horizontal Navigation

```css
.nav {
    display: flex;
    flex-direction: row;
}
```

### Vertical Menu

```css
.menu {
    display: flex;
    flex-direction: column;
}
```

### Reversing a Layout

```css
.container {
    display: flex;
    flex-direction: row-reverse;
}
```

### Reversing a Vertical Layout

```css
.container {
    display: flex;
    flex-direction: column-reverse;
}
```

---

## Important Difference

`flex-direction` does **not** determine whether an element is a flex container.

This:

```css
.container {
    display: flex;
}
```

creates the Flexbox layout.

This:

```css
.container {
    flex-direction: column;
}
```

controls the direction of that layout.

Therefore, a common combination is:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

---

> 💡 **Pro Tip:** When a Flexbox alignment property seems to behave unexpectedly, check `flex-direction` first. The main axis and cross axis depend on the direction of the flex container.

---

> 💡 **Remember:** `flex-direction` controls the direction of the flex items and determines the **main axis**. Its four values are `row`, `row-reverse`, `column`, and `column-reverse`.

---

# Main Axis and Cross Axis

Flexbox layouts are based on two axes:

```text
Main Axis
Cross Axis
```

Understanding these axes is essential because Flexbox alignment properties work relative to them.

The direction of these axes depends on the value of:

```css
flex-direction
```

---

## Main Axis

The **main axis** is the primary direction in which flex items are laid out.

For example, with:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

the main axis is horizontal.

```text
Item 1 → Item 2 → Item 3
────────────────────────→
        Main Axis
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

the main axis becomes vertical.

```text
        Main Axis
             ↓
             ↓
             ↓
```

---

## Cross Axis

The **cross axis** is perpendicular to the main axis.

When:

```css
flex-direction: row;
```

the main axis is horizontal and the cross axis is vertical.

```text
             Cross Axis
                  ↓
                  ↓
                  ↓

Item 1    Item 2    Item 3
────────────────────────────→
          Main Axis
```

When:

```css
flex-direction: column;
```

the main axis is vertical and the cross axis is horizontal.

```text
        Cross Axis
    ←────────────────→

         Item 1
            ↓
         Item 2
            ↓
         Item 3

        Main Axis
```

---

## Axes Depend on `flex-direction`

The relationship between the axes changes depending on the flex direction.

### `row`

```css
flex-direction: row;
```

```text
Main Axis   → Horizontal
Cross Axis  ↓ Vertical
```

### `row-reverse`

```css
flex-direction: row-reverse;
```

```text
Main Axis   ← Horizontal
Cross Axis  ↓ Vertical
```

### `column`

```css
flex-direction: column;
```

```text
Main Axis   ↓ Vertical
Cross Axis  → Horizontal
```

### `column-reverse`

```css
flex-direction: column-reverse;
```

```text
Main Axis   ↑ Vertical
Cross Axis  → Horizontal
```

---

## Visual Comparison

```text
flex-direction: row

Cross Axis
    ↓
    ↓
    ↓
┌──────────────────────────────┐
│  1    2    3                 │
└──────────────────────────────┘
──────────────────────────────→
          Main Axis
```

```text
flex-direction: column

       Cross Axis
←────────────────────→

┌─────────┐
│    1    │
└─────────┘
     ↓
┌─────────┐
│    2    │
└─────────┘
     ↓
┌─────────┐
│    3    │
└─────────┘

     Main Axis
```

---

## Why Are the Axes Important?

Flexbox properties such as:

```css
justify-content
align-items
align-content
```

use the flex container's axes to determine how items are positioned.

For example:

```css
.container {
    display: flex;
    justify-content: center;
}
```

`justify-content` aligns items along the **main axis**.

Therefore, changing:

```css
flex-direction: row;
```

to:

```css
flex-direction: column;
```

changes the direction in which `justify-content` operates.

---

## `justify-content` and the Main Axis

With:

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
}
```

the items are centered horizontally.

```text
┌──────────────────────────────┐
│                              │
│        1   2   3             │
│                              │
└──────────────────────────────┘
```

The main axis is horizontal, so `justify-content` works horizontally.

Now change the direction:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```

The main axis becomes vertical.

Therefore, `justify-content` now centers the items vertically.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

---

## `align-items` and the Cross Axis

`align-items` operates along the **cross axis**.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    align-items: center;
}
```

Since the cross axis is vertical, the items are centered vertically.

```text
┌──────────────────────────────┐
│                              │
│      1    2    3             │
│                              │
└──────────────────────────────┘
```

If the direction changes:

```css
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

the cross axis becomes horizontal.

The items are therefore centered horizontally.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

---

## The Most Important Rule

A useful way to remember Flexbox axes is:

```text
justify-content
        ↓
Main Axis

align-items
        ↓
Cross Axis
```

And:

```text
flex-direction
        ↓
Determines the Main Axis
        ↓
Cross Axis is perpendicular to it
```

---

## Complete Example

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
```

Here:

```text
display: flex
    ↓
Creates Flexbox

flex-direction: row
    ↓
Main Axis = Horizontal
Cross Axis = Vertical

justify-content: center
    ↓
Centers items on Main Axis

align-items: center
    ↓
Centers items on Cross Axis
```

Result:

```text
┌──────────────────────────────┐
│                              │
│          1   2   3           │
│                              │
└──────────────────────────────┘
```

---

## Common Mistake

A common mistake is memorizing:

```text
justify-content = horizontal
align-items = vertical
```

This is **not always true**.

These properties are based on the **main and cross axes**, not permanently on horizontal and vertical directions.

For example:

```css
flex-direction: column;
```

changes the main axis to vertical.

Therefore:

```css
justify-content
```

also operates vertically.

---

## Quick Reference

| `flex-direction` | Main Axis | Cross Axis |
|-------------------|-----------|------------|
| `row` | Horizontal | Vertical |
| `row-reverse` | Horizontal | Vertical |
| `column` | Vertical | Horizontal |
| `column-reverse` | Vertical | Horizontal |

---

> 💡 **Pro Tip:** Never memorize `justify-content` as "horizontal" and `align-items` as "vertical." Instead, remember **`justify-content` follows the main axis** and **`align-items` follows the cross axis**.

---

> 💡 **Remember:** `flex-direction` determines the **main axis**, while the **cross axis** is perpendicular to it. Flexbox alignment properties work according to these axes.

---

# Flex Wrap

By default, Flexbox tries to place all flex items on a **single line**.

The `flex-wrap` property controls whether flex items are allowed to move onto multiple lines when there is not enough available space.

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

---

## Default Behavior

The default value of `flex-wrap` is:

```css
nowrap
```

This means flex items remain on a single line.

```css
.container {
    display: flex;
    flex-wrap: nowrap;
}
```

Result:

```text
┌──────────────────────────────────────────┐
│  1    2    3    4    5    6    7       │
└──────────────────────────────────────────┘
```

If the container becomes too small, the items can become compressed or overflow depending on their sizing and the available space.

---

## `nowrap`

```css
flex-wrap: nowrap;
```

This is the default value.

All flex items remain on one flex line.

```text
Container

┌───────────────────────────────┐
│  1   2   3   4   5   6        │
└───────────────────────────────┘
```

The items do not automatically move onto another line.

---

## `wrap`

The `wrap` value allows flex items to move onto additional lines when necessary.

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

Example:

```text
┌───────────────────────────────┐
│  1    2    3                  │
│                               │
│  4    5    6                  │
└───────────────────────────────┘
```

The items remain flex items, but they can now form multiple flex lines.

---

## Basic Example

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
</div>
```

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

.item {
    width: 100px;
    padding: 20px;
}
```

If the container is not wide enough to hold all the items on one line, the items can wrap:

```text
┌──────────────────────────────────┐
│  ┌─────┐  ┌─────┐  ┌─────┐      │
│  │  1  │  │  2  │  │  3  │      │
│  └─────┘  └─────┘  └─────┘      │
│                                  │
│  ┌─────┐  ┌─────┐  ┌─────┐      │
│  │  4  │  │  5  │  │  6  │      │
│  └─────┘  └─────┘  └─────┘      │
└──────────────────────────────────┘
```

---

## `wrap-reverse`

The third value is:

```css
flex-wrap: wrap-reverse;
```

This also allows multiple flex lines, but the cross-axis direction of the lines is reversed.

```css
.container {
    display: flex;
    flex-wrap: wrap-reverse;
}
```

Conceptually:

```text
Normal wrap:

Line 1
Line 2
Line 3
   ↓


Wrap reverse:

Line 3
Line 2
Line 1
```

The exact visual direction depends on the flex direction and writing mode.

---

## Comparing the Values

| Value | Behavior |
|-------|----------|
| `nowrap` | Keeps items on one line |
| `wrap` | Allows items to move onto multiple lines |
| `wrap-reverse` | Allows multiple lines and reverses their cross-axis direction |

---

## `flex-wrap` and Container Size

Wrapping becomes useful when the container has limited available space.

For example:

```css
.container {
    width: 400px;
    display: flex;
    flex-wrap: wrap;
}
```

If the items cannot all fit on one line, additional items can move to another line.

```text
┌──────────────────────────────┐
│  1     2     3               │
│                              │
│  4     5     6               │
└──────────────────────────────┘
```

Without wrapping:

```css
.container {
    width: 400px;
    display: flex;
    flex-wrap: nowrap;
}
```

the items are kept on one line.

---

## Wrapping Is Based on Available Space

Flexbox does not wrap simply because a certain number of items exists.

Wrapping depends on whether the items can fit within the available space.

For example:

```text
Wide container:

┌─────────────────────────────────────┐
│  1   2   3   4   5   6             │
└─────────────────────────────────────┘
```

The same items in a smaller container:

```text
┌──────────────────────┐
│  1   2   3           │
│                      │
│  4   5   6           │
└──────────────────────┘
```

This makes `flex-wrap` particularly useful for responsive layouts.

---

## `flex-wrap` With `flex-direction`

`flex-wrap` works together with `flex-direction`.

For example:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```

The items are laid out in rows and can create additional rows.

```text
1   2   3
4   5   6
```

With:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

the main direction is vertical, so additional flex lines can form horizontally.

```text
1   4
2   5
3   6
```

The exact result depends on the available container dimensions.

---

## `flex-wrap` With `gap`

`flex-wrap` is commonly used together with `gap`.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

This provides consistent spacing between items and between flex lines.

```text
┌───────────────────────────────┐
│  1     2     3                │
│                               │
│  4     5     6                │
└───────────────────────────────┘
```

---

## Common Use Cases

`flex-wrap` is commonly useful for:

- Card layouts
- Product lists
- Button groups
- Tags
- Navigation elements
- Image galleries
- Responsive components

### Card Example

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

Cards can move to additional lines when the available width becomes smaller.

---

## Responsive Layout Example

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

This allows the cards to grow and shrink while also wrapping when necessary.

The `flex` property will be covered later in this chapter.

---

## `flex-wrap` Does Not Change Item Order

When normal wrapping occurs:

```css
flex-wrap: wrap;
```

items continue following their normal order.

For example:

```text
1   2   3
4   5   6
```

The order remains:

```text
1 → 2 → 3 → 4 → 5 → 6
```

Wrapping changes the layout into multiple lines; it does not by itself reorder the items.

---

## Single Line vs Multiple Lines

A useful way to think about `flex-wrap` is:

```text
nowrap
   ↓
One flex line

wrap
   ↓
Multiple flex lines allowed

wrap-reverse
   ↓
Multiple flex lines allowed
+
Cross-axis direction reversed
```

---

> 💡 **Pro Tip:** For responsive card or button layouts, `flex-wrap: wrap` is often a good starting point. Combine it with flexible item sizing and `gap` to create layouts that adapt naturally to available space.

---

> 💡 **Remember:** `flex-wrap` controls whether flex items stay on one line or are allowed to form multiple flex lines. Its three values are `nowrap`, `wrap`, and `wrap-reverse`.

---

# Flex Flow

The `flex-flow` property is a **shorthand property** that combines:

```css
flex-direction
flex-wrap
```

Instead of writing both properties separately:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```

you can write:

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

Both produce the same Flexbox configuration.

---

## Syntax

```css
.container {
    display: flex;
    flex-flow: <flex-direction> <flex-wrap>;
}
```

The two values are:

```text
flex-direction
+
flex-wrap
```

For example:

```css
flex-flow: row wrap;
```

means:

```css
flex-direction: row;
flex-wrap: wrap;
```

---

## Basic Example

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

This means:

```text
Direction → row
Wrapping  → wrap
```

The items are arranged horizontally and can move onto additional lines when necessary.

```text
┌───────────────────────────────┐
│  1     2     3                │
│                               │
│  4     5     6                │
└───────────────────────────────┘
```

---

## `flex-flow: row nowrap`

```css
.container {
    display: flex;
    flex-flow: row nowrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
}
```

Items are arranged in a row and remain on one flex line.

---

## `flex-flow: row wrap`

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```

Items are arranged in a row and can wrap onto additional lines.

---

## `flex-flow: row-reverse wrap`

```css
.container {
    display: flex;
    flex-flow: row-reverse wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: row-reverse;
    flex-wrap: wrap;
}
```

The items are arranged in the reverse row direction and can wrap.

---

## `flex-flow: column wrap`

```css
.container {
    display: flex;
    flex-flow: column wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

The main direction is vertical, and items can form additional flex lines.

```text
1    4
2    5
3    6
```

---

## `flex-flow: column-reverse wrap`

```css
.container {
    display: flex;
    flex-flow: column-reverse wrap;
}
```

Equivalent to:

```css
.container {
    display: flex;
    flex-direction: column-reverse;
    flex-wrap: wrap;
}
```

The items use a reversed column direction and are allowed to wrap.

---

## Order of Values

The values are normally written as:

```css
flex-flow: flex-direction flex-wrap;
```

For example:

```css
flex-flow: row wrap;
```

However, the two values can be provided in either order because the values have different allowed keywords.

For clarity and readability, the conventional order is:

```css
flex-flow: row wrap;
```

---

## Default Value

The initial value of `flex-flow` is equivalent to:

```css
flex-flow: row nowrap;
```

This means:

```css
flex-direction: row;
flex-wrap: nowrap;
```

Therefore:

```css
.container {
    display: flex;
}
```

uses the default Flexbox flow of:

```text
row
+
nowrap
```

---

## Common Combinations

### Row Without Wrapping

```css
flex-flow: row nowrap;
```

### Row With Wrapping

```css
flex-flow: row wrap;
```

### Reversed Row With Wrapping

```css
flex-flow: row-reverse wrap;
```

### Column Without Wrapping

```css
flex-flow: column nowrap;
```

### Column With Wrapping

```css
flex-flow: column wrap;
```

### Reversed Column With Wrapping

```css
flex-flow: column-reverse wrap;
```

---

## `flex-flow` vs Individual Properties

Using separate properties:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

Using the shorthand:

```css
.container {
    display: flex;
    flex-flow: column wrap;
}
```

The result is equivalent.

The shorthand simply provides a more compact way to specify both properties.

---

## When to Use `flex-flow`

`flex-flow` can be useful when:

- You need both `flex-direction` and `flex-wrap`.
- You want to keep related Flexbox settings together.
- You prefer concise CSS.
- The direction and wrapping behavior are clear from one declaration.

For example:

```css
.cards {
    display: flex;
    flex-flow: row wrap;
    gap: 20px;
}
```

This clearly communicates that the cards should flow horizontally and wrap when necessary.

---

## Important Difference

`flex-flow` does not replace:

```css
display: flex;
```

You still need to create the flex container.

For example:

```css
.container {
    display: flex;
    flex-flow: row wrap;
}
```

Here:

```text
display: flex
    ↓
Creates the Flexbox container

flex-flow
    ↓
Controls direction + wrapping
```

---

> 💡 **Pro Tip:** Use `flex-flow` when you want to configure direction and wrapping together. If you are learning or debugging Flexbox, writing `flex-direction` and `flex-wrap` separately can sometimes make the CSS easier to understand.

---

> 💡 **Remember:** `flex-flow` is shorthand for **`flex-direction` + `flex-wrap`**.

```css
flex-flow: row wrap;
```

is equivalent to:

```css
flex-direction: row;
flex-wrap: wrap;
```

---

# Justify Content

The `justify-content` property controls how flex items are **aligned and distributed along the main axis** of a flex container.

```css
.container {
    display: flex;
    justify-content: center;
}
```

The effect of `justify-content` depends on the value of:

```css
flex-direction
```

because `flex-direction` determines the main axis.

---

## Syntax

```css
.container {
    display: flex;
    justify-content: value;
}
```

Common values include:

```text
flex-start
flex-end
center
space-between
space-around
space-evenly
```

---

## `flex-start`

The default value is:

```css
justify-content: flex-start;
```

Items are placed at the beginning of the main axis.

For a normal left-to-right `row`:

```text
┌──────────────────────────────────────┐
│  1    2    3                         │
└──────────────────────────────────────┘
→ Main Axis
```

Example:

```css
.container {
    display: flex;
    justify-content: flex-start;
}
```

---

## `flex-end`

The `flex-end` value places the items at the end of the main axis.

```css
.container {
    display: flex;
    justify-content: flex-end;
}
```

Result for a normal `row`:

```text
┌──────────────────────────────────────┐
│                         1    2    3  │
└──────────────────────────────────────┘
```

---

## `center`

The `center` value places the items together in the center of the main axis.

```css
.container {
    display: flex;
    justify-content: center;
}
```

Result:

```text
┌──────────────────────────────────────┐
│             1    2    3              │
└──────────────────────────────────────┘
```

This is one of the most commonly used values.

---

## `space-between`

The `space-between` value distributes the available space **between the items**.

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

Result:

```text
┌──────────────────────────────────────┐
│  1             2              3      │
└──────────────────────────────────────┘
```

The first item is placed at the beginning and the last item at the end.

There is no extra distributed space before the first item or after the last item.

---

## `space-around`

The `space-around` value distributes space around each item.

```css
.container {
    display: flex;
    justify-content: space-around;
}
```

Conceptually:

```text
┌──────────────────────────────────────┐
│    1        2        3               │
└──────────────────────────────────────┘
```

Each item receives space around it.

The space between two neighboring items is effectively twice the space at either outer edge.

---

## `space-evenly`

The `space-evenly` value distributes the available space so that the spaces between items and the container edges are equal.

```css
.container {
    display: flex;
    justify-content: space-evenly;
}
```

Result:

```text
┌──────────────────────────────────────┐
│     1        2        3              │
└──────────────────────────────────────┘
```

The spacing is equal:

```text
Edge
 ↓
[space] 1 [space] 2 [space] 3 [space]
                                             ↑
                                            Edge
```

---

## Comparing the Values

Consider three items:

```text
1   2   3
```

### `flex-start`

```text
1   2   3
```

Items start at the beginning.

### `flex-end`

```text
                    1   2   3
```

Items move to the end.

### `center`

```text
            1   2   3
```

Items are grouped in the center.

### `space-between`

```text
1              2              3
```

Space is placed between the items.

### `space-around`

```text
   1        2        3
```

Space is distributed around each item.

### `space-evenly`

```text
    1       2       3
```

All available spaces are equal.

---

## `justify-content` Uses the Main Axis

A very important concept is:

```text
justify-content
        ↓
Main Axis
```

For:

```css
flex-direction: row;
```

the main axis is horizontal.

Therefore:

```css
justify-content: center;
```

centers the items horizontally.

```text
┌──────────────────────────────┐
│        1   2   3             │
└──────────────────────────────┘
```

---

## With `flex-direction: column`

Now consider:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```

The main axis is now vertical.

Therefore, `justify-content` centers the items vertically.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

This is why `justify-content` should not simply be remembered as "horizontal alignment."

It always works along the **main axis**.

---

## `justify-content` With `row`

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}
```

Result:

```text
┌──────────────────────────────────────┐
│  1              2              3     │
└──────────────────────────────────────┘
```

The main axis is horizontal.

---

## `justify-content` With `column`

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
```

Result:

```text
┌──────────────────────┐
│ 1                    │
│                      │
│ 2                    │
│                      │
│ 3                    │
└──────────────────────┘
```

The main axis is vertical, so the available space is distributed vertically.

---

## Free Space

`justify-content` becomes especially useful when there is **extra free space** along the main axis.

For example:

```css
.container {
    width: 600px;
    display: flex;
    justify-content: center;
}
```

If the items occupy less space than the container, the remaining space can be distributed according to the chosen `justify-content` value.

```text
Container width
────────────────────────────────────────

Items width
──────────────

Remaining space
────────────────────
```

`justify-content` determines how that remaining space is handled.

---

## Common Navigation Example

A navigation bar can use:

```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

This can position one group at the beginning and another at the end.

```text
┌──────────────────────────────────────┐
│ Logo                 Home About Login│
└──────────────────────────────────────┘
```

---

## Common Centering Example

To center items along the main axis:

```css
.container {
    display: flex;
    justify-content: center;
}
```

For complete horizontal and vertical centering in a row-based container, it is common to combine:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Here:

```text
justify-content
→ Main axis

align-items
→ Cross axis
```

---

## Important Difference

Do not confuse:

```css
justify-content
```

with:

```css
align-items
```

`justify-content` controls distribution along the **main axis**.

`align-items` controls alignment along the **cross axis**.

```text
Main Axis
    ↓
justify-content

Cross Axis
    ↓
align-items
```

---

## Quick Reference

| Value | Behavior |
|-------|----------|
| `flex-start` | Items at the start |
| `flex-end` | Items at the end |
| `center` | Items centered |
| `space-between` | Equal space between items |
| `space-around` | Space around each item |
| `space-evenly` | Equal space everywhere |

---

> 💡 **Pro Tip:** If `justify-content` appears to do nothing, check whether there is any free space along the main axis. If the flex items already consume all available space, there may be no extra space for the property to distribute.

---

> 💡 **Remember:** `justify-content` controls how flex items are positioned and distributed along the **main axis**. The main axis is determined by `flex-direction`.

---

# Align Items

The `align-items` property controls how flex items are **aligned along the cross axis** of a flex container.

```css
.container {
    display: flex;
    align-items: center;
}
```

The cross axis depends on the value of:

```css
flex-direction
```

---

## Syntax

```css
.container {
    display: flex;
    align-items: value;
}
```

Common values include:

```text
stretch
flex-start
flex-end
center
baseline
```

---

## `stretch`

The default value is:

```css
align-items: stretch;
```

Flex items stretch along the cross axis when their cross-axis size is `auto`.

Example:

```css
.container {
    display: flex;
    align-items: stretch;
}
```

For a row-based container:

```text
┌──────────────────────────────────────┐
│  ┌────┐  ┌────┐  ┌────┐              │
│  │    │  │    │  │    │              │
│  │  1 │  │  2 │  │  3 │              │
│  │    │  │    │  │    │              │
│  └────┘  └────┘  └────┘              │
└──────────────────────────────────────┘
```

The items can stretch to fill the available cross-axis space.

---

## `flex-start`

The `flex-start` value places items at the beginning of the cross axis.

```css
.container {
    display: flex;
    align-items: flex-start;
}
```

For a normal row:

```text
┌──────────────────────────────────────┐
│  1      2      3                     │
│                                      │
│                                      │
│                                      │
└──────────────────────────────────────┘
```

The items are aligned toward the start of the cross axis.

---

## `flex-end`

The `flex-end` value places items at the end of the cross axis.

```css
.container {
    display: flex;
    align-items: flex-end;
}
```

For a normal row:

```text
┌──────────────────────────────────────┐
│                                      │
│                                      │
│                                      │
│  1      2      3                     │
└──────────────────────────────────────┘
```

---

## `center`

The `center` value centers the flex items along the cross axis.

```css
.container {
    display: flex;
    align-items: center;
}
```

For a row-based container:

```text
┌──────────────────────────────────────┐
│                                      │
│       1      2      3                │
│                                      │
└──────────────────────────────────────┘
```

This is one of the most commonly used values.

---

## `baseline`

The `baseline` value aligns flex items according to their text baselines.

```css
.container {
    display: flex;
    align-items: baseline;
}
```

This is particularly useful when items contain text with different font sizes.

Example:

```text
┌──────────────────────────────────────┐
│  Small     LARGE     Medium          │
│     ────────────────                 │
│          Common Baseline             │
└──────────────────────────────────────┘
```

The text baselines are aligned rather than simply aligning the top or bottom edges of the items.

---

## Comparing the Values

For a row-based container:

### `flex-start`

```text
1   2   3
```

Items align at the top.

### `flex-end`

```text
        1   2   3
```

Items align at the bottom.

### `center`

```text
    1   2   3
```

Items align in the center.

### `stretch`

```text
┌───┐ ┌───┐ ┌───┐
│ 1 │ │ 2 │ │ 3 │
│   │ │   │ │   │
│   │ │   │ │   │
└───┘ └───┘ └───┘
```

Items stretch across the available cross-axis space when applicable.

### `baseline`

```text
1       LARGE       3
───────────────
   Common Baseline
```

Text baselines are aligned.

---

## `align-items` Uses the Cross Axis

The most important rule is:

```text
align-items
     ↓
Cross Axis
```

For:

```css
flex-direction: row;
```

the cross axis is vertical.

Therefore:

```css
align-items: center;
```

centers items vertically.

```text
┌──────────────────────────────┐
│                              │
│       1   2   3              │
│                              │
└──────────────────────────────┘
```

---

## With `flex-direction: column`

Consider:

```css
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

Now the main axis is vertical and the cross axis is horizontal.

Therefore, `align-items: center` centers the items horizontally.

```text
┌──────────────────────────────┐
│                              │
│            1                 │
│            2                 │
│            3                 │
│                              │
└──────────────────────────────┘
```

This is why `align-items` should not simply be remembered as "vertical alignment."

It always operates along the **cross axis**.

---

## `justify-content` vs `align-items`

These two properties are often used together.

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Their responsibilities are:

```text
justify-content
      ↓
Main Axis

align-items
      ↓
Cross Axis
```

For a normal row:

```text
Main Axis
────────────────────────→

Cross Axis
      ↓
      ↓
      ↓
```

Therefore:

```css
justify-content: center;
```

centers items along the horizontal main axis.

And:

```css
align-items: center;
```

centers them along the vertical cross axis.

Together, they can center items in both directions.

---

## Complete Centering Example

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 300px;
}
```

Result:

```text
┌──────────────────────────────┐
│                              │
│                              │
│          1   2   3           │
│                              │
│                              │
└──────────────────────────────┘
```

Here:

```text
justify-content
→ Centers on the main axis

align-items
→ Centers on the cross axis
```

---

## `align-items` and Item Height

The effect of `align-items` is easiest to see when the flex container has extra space along its cross axis.

For example:

```css
.container {
    height: 300px;
    display: flex;
    align-items: center;
}
```

The items can then be positioned within the available vertical space.

Without enough cross-axis space, there may be little or no visible difference between some alignment values.

---

## `align-items` With Different Item Sizes

Flex items do not have to be the same size.

Example:

```html
<div class="container">
    <div class="item small">Small</div>
    <div class="item large">Large</div>
    <div class="item medium">Medium</div>
</div>
```

```css
.container {
    display: flex;
    align-items: center;
}
```

The different-sized items are aligned according to the selected cross-axis alignment.

```text
┌──────────────────────────────────────┐
│                                      │
│   Small     Large     Medium         │
│                                      │
└──────────────────────────────────────┘
```

---

## Common Use Cases

### Vertically Centering a Row

```css
.container {
    display: flex;
    align-items: center;
}
```

### Centering Items in a Column

```css
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
```

### Aligning Header Content

```css
.header {
    display: flex;
    align-items: center;
}
```

This is commonly used to vertically align a logo, navigation, and buttons.

### Aligning Different Text Sizes

```css
.container {
    display: flex;
    align-items: baseline;
}
```

This can keep text baselines visually aligned.

---

## Important Difference From `align-content`

Do not confuse:

```css
align-items
```

with:

```css
align-content
```

`align-items` controls the alignment of **items within a flex line**.

`align-content` controls the distribution of **multiple flex lines** when wrapping creates extra cross-axis space.

```text
align-items
     ↓
Items

align-content
     ↓
Flex Lines
```

`align-content` becomes relevant when there are multiple flex lines, such as when:

```css
flex-wrap: wrap;
```

is being used.

---

## Quick Reference

| Value | Behavior |
|-------|----------|
| `stretch` | Stretches items along the cross axis when applicable |
| `flex-start` | Aligns items at the start of the cross axis |
| `flex-end` | Aligns items at the end of the cross axis |
| `center` | Centers items along the cross axis |
| `baseline` | Aligns items according to their baselines |

---

> 💡 **Pro Tip:** If you want to understand what `align-items` is doing, first identify the cross axis. Ask: **"Which direction is perpendicular to my `flex-direction`?"** That is the direction in which `align-items` works.

---

> 💡 **Remember:** `align-items` controls the alignment of flex items along the **cross axis**. It is commonly used with `justify-content` to control alignment in both axes.

---

# Align Content

The `align-content` property controls how **multiple flex lines** are aligned and distributed along the **cross axis** of a flex container.

It becomes relevant when:

```css
flex-wrap: wrap;
```

creates multiple flex lines and there is extra space available along the cross axis.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}
```

---

## Syntax

```css
.container {
    display: flex;
    align-content: value;
}
```

Common values include:

```text
normal
flex-start
flex-end
center
space-between
space-around
space-evenly
stretch
```

---

## Why `align-content` Is Different

A common source of confusion is the difference between:

```css
align-items
```

and:

```css
align-content
```

They control different things.

```text
align-items
     ↓
Items inside a flex line

align-content
     ↓
Multiple flex lines
```

For example:

```text
Line 1 → 1   2   3

Line 2 → 4   5   6

Line 3 → 7   8   9
```

`align-items` controls the items within each line.

`align-content` controls the positioning of the lines themselves.

---

## `align-content` Requires Multiple Lines

Consider:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

If all items fit on one line:

```text
1   2   3   4   5
```

there is only one flex line.

In that situation, `align-content` generally has no visible effect.

When items wrap:

```text
1   2   3
4   5   6
7   8   9
```

there are multiple flex lines, so `align-content` can control their distribution.

---

## `normal`

The default value is:

```css
align-content: normal;
```

For flex containers, this behaves like:

```css
stretch;
```

when there is extra cross-axis space.

---

## `flex-start`

The `flex-start` value places the flex lines at the beginning of the cross axis.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;
}
```

For a row-based container:

```text
┌──────────────────────────────┐
│ 1   2   3                    │
│ 4   5   6                    │
│ 7   8   9                    │
│                              │
│                              │
└──────────────────────────────┘
```

The lines are grouped toward the start.

---

## `flex-end`

The `flex-end` value places the flex lines at the end of the cross axis.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: flex-end;
}
```

Result:

```text
┌──────────────────────────────┐
│                              │
│                              │
│ 1   2   3                    │
│ 4   5   6                    │
│ 7   8   9                    │
└──────────────────────────────┘
```

---

## `center`

The `center` value groups the flex lines in the center of the cross axis.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}
```

Result:

```text
┌──────────────────────────────┐
│                              │
│ 1   2   3                    │
│ 4   5   6                    │
│ 7   8   9                    │
│                              │
└──────────────────────────────┘
```

---

## `space-between`

The `space-between` value distributes the available space **between the flex lines**.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
}
```

Conceptually:

```text
┌──────────────────────────────┐
│ 1   2   3                    │
│                              │
│ 4   5   6                    │
│                              │
│ 7   8   9                    │
└──────────────────────────────┘
```

The first line is at the beginning and the last line is at the end, with extra space distributed between the lines.

---

## `space-around`

The `space-around` value distributes space around each flex line.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: space-around;
}
```

Conceptually:

```text
┌──────────────────────────────┐
│                              │
│ 1   2   3                    │
│                              │
│ 4   5   6                    │
│                              │
│ 7   8   9                    │
│                              │
└──────────────────────────────┘
```

Each flex line receives space around it.

---

## `space-evenly`

The `space-evenly` value distributes the available space equally between:

- The container's start edge and first line
- Each pair of lines
- The last line and the container's end edge

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: space-evenly;
}
```

Conceptually:

```text
┌──────────────────────────────┐
│                              │
│ 1   2   3                    │
│                              │
│ 4   5   6                    │
│                              │
│ 7   8   9                    │
│                              │
└──────────────────────────────┘
```

The available spaces are equal.

---

## `stretch`

The `stretch` value allows flex lines to stretch to use available cross-axis space.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: stretch;
}
```

This is the default behavior for flex containers through the `normal` initial value.

The flex lines can grow to fill available cross-axis space.

---

## Comparing `align-content` Values

Suppose a container has three flex lines:

```text
1  2  3
4  5  6
7  8  9
```

### `flex-start`

```text
1  2  3
4  5  6
7  8  9
```

Lines are grouped at the start.

### `flex-end`

```text
7  8  9
```

The group is positioned toward the end of the cross axis.

### `center`

```text
   1  2  3
   4  5  6
   7  8  9
```

Lines are grouped in the center.

### `space-between`

```text
1  2  3

4  5  6

7  8  9
```

Extra space is placed between lines.

### `space-around`

```text
  1  2  3

  4  5  6

  7  8  9
```

Space is distributed around lines.

### `space-evenly`

```text
  1  2  3

  4  5  6

  7  8  9
```

The spaces between the container edges and the lines, as well as between the lines, are equal.

---

## `align-content` Uses the Cross Axis

The property works along the:

```text
Cross Axis
```

For:

```css
flex-direction: row;
```

the cross axis is vertical.

Therefore, `align-content` distributes flex lines vertically.

```text
Cross Axis
    ↓

Line 1
Line 2
Line 3

    ↑
Cross Axis
```

For:

```css
flex-direction: column;
```

the cross axis becomes horizontal.

Therefore, `align-content` distributes the flex lines horizontally.

---

## Example With Row Direction

```css
.container {
    height: 400px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: center;
}
```

The items wrap into multiple rows, and those rows are centered vertically.

```text
┌──────────────────────────────┐
│                              │
│  1   2   3                   │
│  4   5   6                   │
│  7   8   9                   │
│                              │
└──────────────────────────────┘
```

Here:

```text
flex-direction: row
        ↓
Cross Axis = Vertical

align-content: center
        ↓
Centers the flex lines vertically
```

---

## Example With Column Direction

```css
.container {
    width: 500px;
    height: 300px;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-content: center;
}
```

The flex lines are distributed along the horizontal cross axis.

```text
┌──────────────────────────────────┐
│                                  │
│       1    4                     │
│       2    5                     │
│       3    6                     │
│                                  │
└──────────────────────────────────┘
```

---

## `align-items` vs `align-content`

This distinction is extremely important.

### `align-items`

Controls the alignment of items within a flex line.

```text
Line
────────────────────
  1     2     3
```

### `align-content`

Controls the distribution of multiple flex lines.

```text
Line 1
Line 2
Line 3
```

A simple way to remember:

```text
align-items
→ Items

align-content
→ Content of multiple lines
```

---

## Example

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    align-content: space-between;
}
```

Here:

```text
align-items
    ↓
Controls items inside each line

align-content
    ↓
Controls spacing between the lines
```

Both properties can therefore be used together.

---

## Why `align-content` Sometimes Appears Not to Work

A common reason is that the container does not have enough extra cross-axis space.

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

If the flex lines already occupy the entire cross-axis space:

```text
Available space
────────────────────

Flex lines
────────────────────
```

there may be no extra space for `align-content` to distribute.

A larger container can make the effect visible:

```css
.container {
    height: 500px;
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}
```

---

## Important Requirement

For `align-content` to have a meaningful effect, you generally need:

```text
1. Multiple flex lines
2. Extra space along the cross axis
```

Multiple lines are commonly created using:

```css
flex-wrap: wrap;
```

---

## Quick Reference

| Value | Behavior |
|-------|----------|
| `normal` | Default behavior; equivalent to stretching in Flexbox |
| `flex-start` | Lines at the start |
| `flex-end` | Lines at the end |
| `center` | Lines centered |
| `space-between` | Space between lines |
| `space-around` | Space around lines |
| `space-evenly` | Equal space around and between lines |
| `stretch` | Lines stretch across available space |

---

> 💡 **Pro Tip:** If `align-content` appears to have no effect, check two things first: **Are there multiple flex lines?** and **Is there extra space along the cross axis?** Without those conditions, there may be nothing for `align-content` to distribute.

---

> 💡 **Remember:** `align-items` aligns **items within a flex line**, while `align-content` controls the distribution of **multiple flex lines** along the cross axis.

---

# Gap

The `gap` property controls the **space between flex items**.

It is especially useful when multiple flex items need consistent spacing.

```css
.container {
    display: flex;
    gap: 20px;
}
```

This creates `20px` of space between the flex items.

```text
┌──────────────────────────────────────┐
│                                      │
│  ┌─────┐    ┌─────┐    ┌─────┐      │
│  │  1  │    │  2  │    │  3  │      │
│  └─────┘    └─────┘    └─────┘      │
│      ↑          ↑          ↑         │
│    20px       20px       20px        │
└──────────────────────────────────────┘
```

---

## Syntax

```css
.container {
    display: flex;
    gap: value;
}
```

Example:

```css
.container {
    display: flex;
    gap: 16px;
}
```

The `gap` property can accept lengths such as:

```css
gap: 10px;
gap: 1rem;
gap: 5%;
```

---

## Basic Example

```html
<div class="container">
    <div>One</div>
    <div>Two</div>
    <div>Three</div>
</div>
```

```css
.container {
    display: flex;
    gap: 20px;
}
```

The items are separated by consistent spacing:

```text
One    20px    Two    20px    Three
```

---

## Why Use `gap`?

Before `gap`, developers often used margins to create spacing between flex items.

For example:

```css
.item {
    margin-right: 20px;
}
```

This can create unwanted spacing at the end of the row.

```text
1    2    3    20px
```

With `gap`:

```css
.container {
    display: flex;
    gap: 20px;
}
```

the spacing is applied **between the items**.

```text
1    2    3
```

There is no extra gap added after the last item just because it is the last item.

---

## `gap` vs Margin

Consider:

```css
.container {
    display: flex;
    gap: 20px;
}
```

The container controls the spacing between its flex items.

With margins:

```css
.item {
    margin-right: 20px;
}
```

each item is responsible for creating its own spacing.

A simple comparison:

| `gap` | Margin |
|-------|--------|
| Controlled by container | Controlled by items |
| Designed for spacing between layout items | General-purpose spacing |
| Avoids special handling for the last item | Can require last-item adjustments |
| Works naturally with Flexbox | Works in many layout contexts |

---

## Gap With `flex-direction: row`

For:

```css
.container {
    display: flex;
    flex-direction: row;
    gap: 20px;
}
```

the gap creates spacing between items horizontally.

```text
1    20px    2    20px    3
```

---

## Gap With `flex-direction: column`

For:

```css
.container {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
```

the gap creates spacing between items vertically.

```text
1
↓
20px
↓
2
↓
20px
↓
3
```

Therefore, `gap` follows the layout direction.

---

## Gap With Wrapping

`gap` also works when flex items wrap onto multiple lines.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

Example:

```text
┌────────────────────────────────┐
│  1      2      3               │
│                                │
│  4      5      6               │
└────────────────────────────────┘
```

The spacing is applied between items and between flex lines.

---

## Gap With Different Item Sizes

Flex items can have different dimensions.

```css
.container {
    display: flex;
    gap: 20px;
}
```

The same gap is maintained between neighboring flex items even when their sizes differ.

```text
┌──────┐    ┌──────────┐    ┌─────┐
│  1   │    │    2     │    │  3  │
└──────┘    └──────────┘    └─────┘
     ↑            ↑
   20px         20px
```

---

## Gap and Free Space

`gap` reserves space **between flex items**.

For example:

```css
.container {
    display: flex;
    justify-content: space-between;
    gap: 20px;
}
```

Here both properties can influence the spacing:

```text
gap
→ Minimum specified spacing between items

justify-content
→ Distribution of remaining free space
```

The final spacing depends on the available space and the other Flexbox properties.

---

## Gap With `justify-content`

Consider:

```css
.container {
    display: flex;
    justify-content: center;
    gap: 20px;
}
```

The items are grouped in the center while maintaining `20px` between neighboring items.

```text
┌──────────────────────────────────────┐
│                                      │
│        1    20px    2    20px    3  │
│                                      │
└──────────────────────────────────────┘
```

This combination is very common.

---

## Gap With `align-items`

`gap` can also be used alongside:

```css
align-items
```

For example:

```css
.container {
    display: flex;
    align-items: center;
    gap: 20px;
}
```

Here:

```text
align-items
→ Controls cross-axis alignment

gap
→ Controls spacing between items
```

Each property has a separate responsibility.

---

## Gap With Wrapped Rows

When a flex container wraps:

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

the same gap value is used for both:

```text
Horizontal spacing
+
Vertical spacing
```

For example:

```text
┌────────────────────────────────┐
│  1      2      3               │
│                                │
│       20px                     │
│                                │
│  4      5      6               │
└────────────────────────────────┘
```

For more precise control over row and column spacing, CSS also provides:

```css
row-gap
column-gap
```

These will be covered separately.

---

## Zero Gap

You can explicitly remove the spacing:

```css
.container {
    display: flex;
    gap: 0;
}
```

The items will have no gap created by the container.

```text
1  2  3
```

---

## Responsive Values

The gap can use relative units.

For example:

```css
.container {
    display: flex;
    gap: 1rem;
}
```

or:

```css
.container {
    display: flex;
    gap: 2vw;
}
```

The appropriate unit depends on the design requirements.

---

## Common Use Cases

`gap` is useful for:

- Navigation links
- Button groups
- Card layouts
- Form controls
- Tags
- Lists
- Toolbars
- Responsive components

### Navigation

```css
.nav {
    display: flex;
    gap: 24px;
}
```

### Buttons

```css
.buttons {
    display: flex;
    gap: 12px;
}
```

### Cards

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}
```

---

## Important Difference

`gap` does not control alignment.

For example:

```css
gap: 20px;
```

does not center items.

It only controls the spacing between them.

For alignment, use properties such as:

```css
justify-content
align-items
```

Therefore:

```text
gap
→ Spacing

justify-content
→ Main-axis distribution

align-items
→ Cross-axis alignment
```

---

## `gap` Does Not Replace All Margins

`gap` is useful for spacing between layout items, but margins still have important uses.

For example, margin can be useful when an element needs spacing from:

- Its parent
- Other unrelated elements
- A specific side
- The surrounding layout

Use `gap` when the spacing is fundamentally part of the relationship between items in the flex container.

---

> 💡 **Pro Tip:** When you need consistent spacing between Flexbox items, prefer `gap` instead of adding margins to every child. It keeps the spacing responsibility in the container and usually makes the CSS easier to maintain.

---

> 💡 **Remember:** `gap` controls the spacing between flex items. With wrapped layouts, it can also create spacing between flex lines. For separate control over horizontal and vertical gaps, use `column-gap` and `row-gap`.

---

# Row Gap and Column Gap

CSS provides two properties for controlling spacing separately:

```css
row-gap
column-gap
```

They are useful when a flex container contains multiple flex lines and you need different spacing between rows and columns.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    row-gap: 20px;
    column-gap: 30px;
}
```

Here:

```text
row-gap
→ Space between flex rows

column-gap
→ Space between flex columns
```

---

## `row-gap`

The `row-gap` property controls the space between rows.

```css
.container {
    row-gap: 20px;
}
```

With a wrapped row-based flex container:

```text
┌──────────────────────────────────┐
│  1      2      3                 │
│                                  │
│          20px                    │
│                                  │
│  4      5      6                 │
└──────────────────────────────────┘
```

The vertical space between the flex lines is controlled by `row-gap`.

---

## `column-gap`

The `column-gap` property controls the space between columns.

```css
.container {
    column-gap: 30px;
}
```

Example:

```text
┌──────────────────────────────────┐
│  1     30px     2     30px     3 │
└──────────────────────────────────┘
```

The horizontal space between neighboring items is controlled by `column-gap`.

---

## Using Both Together

You can specify both properties:

```css
.container {
    display: flex;
    flex-wrap: wrap;
    row-gap: 20px;
    column-gap: 30px;
}
```

This means:

```text
Vertical spacing   → 20px
Horizontal spacing → 30px
```

Conceptually:

```text
┌──────────────────────────────────┐
│  1      2      3                 │
│                                  │
│          20px                    │
│                                  │
│  4      5      6                 │
└──────────────────────────────────┘

Horizontal gaps → 30px
```

---

## `gap` vs `row-gap` and `column-gap`

The `gap` property is shorthand for:

```css
row-gap
column-gap
```

For example:

```css
.container {
    gap: 20px;
}
```

is equivalent to:

```css
.container {
    row-gap: 20px;
    column-gap: 20px;
}
```

Both directions use the same value.

---

## Different Values

If you need different spacing in each direction:

```css
.container {
    row-gap: 20px;
    column-gap: 40px;
}
```

You can think of it as:

```text
row-gap
   ↓
20px

column-gap
   ↓
40px
```

This cannot be expressed with a single-value `gap` declaration without using the two-value syntax.

---

## Two-Value `gap` Syntax

The `gap` shorthand can accept two values:

```css
.container {
    gap: 20px 40px;
}
```

The order is:

```text
gap: row-gap column-gap;
```

Therefore:

```css
gap: 20px 40px;
```

means:

```css
row-gap: 20px;
column-gap: 40px;
```

This is equivalent to:

```css
.container {
    row-gap: 20px;
    column-gap: 40px;
}
```

---

## Common Patterns

### Same Gap in Both Directions

```css
.container {
    gap: 20px;
}
```

Equivalent to:

```css
.container {
    row-gap: 20px;
    column-gap: 20px;
}
```

### Different Row and Column Gaps

```css
.container {
    gap: 20px 40px;
}
```

Equivalent to:

```css
.container {
    row-gap: 20px;
    column-gap: 40px;
}
```

### Using Individual Properties

```css
.container {
    row-gap: 20px;
    column-gap: 40px;
}
```

This is useful when the two directions need to be clearly specified.

---

## Flexbox Example

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
    <div class="item">5</div>
    <div class="item">6</div>
</div>
```

```css
.container {
    display: flex;
    flex-wrap: wrap;
    row-gap: 20px;
    column-gap: 30px;
}
```

If the items wrap:

```text
┌──────────────────────────────────┐
│  1      2      3                 │
│                                  │
│          20px                    │
│                                  │
│  4      5      6                 │
└──────────────────────────────────┘
```

The horizontal spacing between items is `30px`, while the vertical spacing between flex lines is `20px`.

---

## With `flex-direction: row`

For:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    row-gap: 20px;
    column-gap: 30px;
}
```

the layout generally appears as:

```text
1     2     3

4     5     6
```

Here:

```text
row-gap
→ Vertical spacing between rows

column-gap
→ Horizontal spacing between items
```

---

## With `flex-direction: column`

When using:

```css
.container {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
}
```

the meaning of the properties is still based on **rows and columns**, not simply "main axis" and "cross axis."

Therefore, always consider the actual layout direction when determining where the visual space will appear.

---

## `gap` With `justify-content`

You can combine gap properties with alignment properties.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    row-gap: 20px;
    column-gap: 30px;
}
```

Here:

```text
justify-content
→ Distributes items along the main axis

row-gap
→ Controls spacing between rows

column-gap
→ Controls spacing between columns
```

Each property has a different responsibility.

---

## `gap` With `align-content`

You can also combine them with:

```css
align-content
```

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
    row-gap: 20px;
    column-gap: 30px;
}
```

Here:

```text
align-content
→ Controls distribution of flex lines

row-gap
→ Controls space between rows

column-gap
→ Controls space between columns
```

---

## Zero Values

You can remove one direction's gap independently.

```css
.container {
    row-gap: 0;
    column-gap: 20px;
}
```

This creates horizontal spacing but no row spacing.

Or:

```css
.container {
    row-gap: 20px;
    column-gap: 0;
}
```

This creates row spacing but no column spacing.

---

## Practical Card Layout

A common use case is a responsive card layout:

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    row-gap: 24px;
    column-gap: 16px;
}
```

This allows you to use different spacing vertically and horizontally.

For example:

```text
┌───────┐   ┌───────┐   ┌───────┐
│ Card  │   │ Card  │   │ Card  │
└───────┘   └───────┘   └───────┘

          24px

┌───────┐   ┌───────┐   ┌───────┐
│ Card  │   │ Card  │   │ Card  │
└───────┘   └───────┘   └───────┘
```

---

## Quick Reference

| Property | Controls |
|----------|----------|
| `gap` | Row and column spacing |
| `row-gap` | Space between rows |
| `column-gap` | Space between columns |

### Shorthand

```css
gap: 20px;
```

means:

```css
row-gap: 20px;
column-gap: 20px;
```

### Two Values

```css
gap: 20px 40px;
```

means:

```css
row-gap: 20px;
column-gap: 40px;
```

---

> 💡 **Pro Tip:** Use `gap` when the same spacing works in both directions. Use `row-gap` and `column-gap` when your design needs different vertical and horizontal spacing.

---

> 💡 **Remember:** `row-gap` controls the space between rows, while `column-gap` controls the space between columns. The `gap` shorthand lets you control both together.

---

# Flex Item Properties

Flexbox properties can be divided into two broad groups:

```text
Flex Container Properties
        ↓
Control the layout

Flex Item Properties
        ↓
Control individual items
```

The container properties discussed so far include:

```css
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
gap
```

Flex items also have their own properties.

The main flex item properties are:

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

These properties are applied directly to individual flex items.

---

## Flex Container vs Flex Item

Consider this HTML:

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
</div>
```

The parent is the flex container:

```css
.container {
    display: flex;
}
```

The children are flex items:

```text
.container
    │
    ├── .item
    ├── .item
    └── .item
```

Container properties are applied to:

```css
.container
```

Item properties are applied to:

```css
.item
```

---

## `order`

The `order` property controls the visual order of a flex item.

```css
.item {
    order: 2;
}
```

The default value is:

```css
order: 0;
```

Flex items are arranged according to their `order` value.

For example:

```css
.item:nth-child(1) {
    order: 3;
}

.item:nth-child(2) {
    order: 1;
}

.item:nth-child(3) {
    order: 2;
}
```

The visual order becomes:

```text
2 → 3 → 1
```

The `order` property will be covered in detail in the next section.

---

## `flex-grow`

The `flex-grow` property controls how a flex item can grow when there is extra space available along the main axis.

```css
.item {
    flex-grow: 1;
}
```

For example:

```css
.item:nth-child(1) {
    flex-grow: 1;
}

.item:nth-child(2) {
    flex-grow: 2;
}
```

The second item is given a larger share of the available positive free space.

Conceptually:

```text
┌──────────────────────────────────────┐
│   Item 1   │       Item 2            │
│            │                          │
└──────────────────────────────────────┘
     1 part          2 parts
```

The `flex-grow` property will be covered in detail later.

---

## `flex-shrink`

The `flex-shrink` property controls how a flex item can shrink when there is not enough space along the main axis.

```css
.item {
    flex-shrink: 1;
}
```

The default value is:

```css
flex-shrink: 1;
```

When the items require more space than the container provides, Flexbox can shrink them according to their shrink factors.

The `flex-shrink` property will be covered in detail later.

---

## `flex-basis`

The `flex-basis` property defines the initial size of a flex item along the main axis before the remaining available space is distributed.

```css
.item {
    flex-basis: 200px;
}
```

For a row-based flex container, this generally corresponds to the item's initial main size in the horizontal direction.

For a column-based flex container, it generally corresponds to the vertical direction.

The `flex-basis` property will be covered in detail later.

---

## `flex`

The `flex` property is a shorthand for:

```css
flex-grow
flex-shrink
flex-basis
```

For example:

```css
.item {
    flex: 1;
}
```

The `flex` shorthand will be covered separately after its individual components are understood.

---

## `align-self`

The `align-self` property allows an individual flex item to override the container's:

```css
align-items
```

value.

For example:

```css
.container {
    display: flex;
    align-items: center;
}

.item {
    align-self: flex-start;
}
```

The other items follow:

```css
align-items: center;
```

while this particular item uses:

```css
align-self: flex-start;
```

The `align-self` property will be covered later.

---

## Main Flex Item Properties

| Property | Purpose |
|----------|---------|
| `order` | Changes the visual order of an item |
| `flex-grow` | Controls how an item grows |
| `flex-shrink` | Controls how an item shrinks |
| `flex-basis` | Defines the initial main-axis size |
| `flex` | Shorthand for grow, shrink, and basis |
| `align-self` | Overrides the item's cross-axis alignment |

---

## Container Properties vs Item Properties

### Container Properties

Applied to the flex container:

```css
.container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    align-content: center;
    gap: 20px;
}
```

They control the overall layout.

### Item Properties

Applied to individual flex items:

```css
.item {
    order: 1;
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 200px;
    align-self: center;
}
```

They control the behavior of individual items.

---

## A Simple Mental Model

Think of Flexbox as having two levels.

```text
                 Flex Container
                       │
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
     Item 1          Item 2         Item 3
```

The container decides:

```text
How should the items be arranged?
```

The items decide:

```text
How should I behave within that arrangement?
```

---

## Example

```css
.container {
    display: flex;
    gap: 20px;
    align-items: center;
}

.item {
    flex-grow: 1;
}
```

Here:

```text
.container
    ↓
Creates the Flexbox layout
Controls spacing and alignment

.item
    ↓
Controls how each individual item grows
```

This separation is important when learning Flexbox.

---

## Important Note

The properties introduced in this section are not all equally simple.

The following properties involve more detailed Flexbox sizing behavior:

```css
flex-grow
flex-shrink
flex-basis
flex
```

They will therefore be explained individually in the upcoming sections.

This section serves as an overview of the **flex item property group**.

---

> 💡 **Pro Tip:** When debugging a Flexbox layout, first determine whether the problem belongs to the **container** or to an **individual item**. This makes it much easier to choose the correct property.

---

> 💡 **Remember:** Container properties control the overall Flexbox layout, while flex item properties control the behavior of individual flex items.

---

---

# Order

The `order` property controls the **visual order of flex items** inside a flex container.

```css
.item {
    order: 2;
}
```

By default, all flex items have:

```css
order: 0;
```

Flex items are displayed according to their `order` values.

---

## Basic Example

HTML:

```html
<div class="container">
    <div class="item one">1</div>
    <div class="item two">2</div>
    <div class="item three">3</div>
</div>
```

By default:

```text
1 → 2 → 3
```

The HTML order and visual order are the same.

Now change the order:

```css
.one {
    order: 3;
}

.two {
    order: 1;
}

.three {
    order: 2;
}
```

The visual order becomes:

```text
2 → 3 → 1
```

The HTML itself has not changed.

---

## Default Value

The default value of `order` is:

```css
order: 0;
```

Therefore:

```html
<div>1</div>
<div>2</div>
<div>3</div>
```

behaves as though each item has:

```css
order: 0;
```

When all items have the same `order` value, their original source order is preserved.

---

## How Ordering Works

Flexbox sorts items according to their `order` values.

For example:

```css
.item-1 {
    order: 3;
}

.item-2 {
    order: 1;
}

.item-3 {
    order: 2;
}
```

The browser effectively arranges them as:

```text
order: 1
    ↓
Item 2

order: 2
    ↓
Item 3

order: 3
    ↓
Item 1
```

Result:

```text
2 → 3 → 1
```

---

## Smaller Values Come First

Consider:

```css
.one {
    order: 5;
}

.two {
    order: 2;
}

.three {
    order: 4;
}

.four {
    order: 1;
}
```

The visual order becomes:

```text
4 → 2 → 3 → 1
```

because:

```text
1 → Item 4
2 → Item 2
4 → Item 3
5 → Item 1
```

The lowest `order` value appears first.

---

## Negative Values

The `order` property also accepts negative values.

```css
.item {
    order: -1;
}
```

For example:

```css
.one {
    order: 0;
}

.two {
    order: -1;
}

.three {
    order: 1;
}
```

The visual order becomes:

```text
2 → 1 → 3
```

because:

```text
-1 → Item 2
 0 → Item 1
 1 → Item 3
```

Negative values can be useful when an item needs to move before items using the default value of `0`.

---

## Same `order` Values

Multiple items can have the same `order` value.

```css
.one {
    order: 1;
}

.two {
    order: 1;
}

.three {
    order: 2;
}
```

The result is:

```text
1 → 2 → 3
```

Items with the same `order` value maintain their original source order.

Therefore, if two items both have:

```css
order: 1;
```

their relative order follows the HTML order.

---

## Changing One Item

You do not need to assign an `order` value to every item.

For example:

```css
.special {
    order: -1;
}
```

If the other items use the default:

```css
order: 0;
```

the special item moves before them.

```text
Before:

1 → 2 → 3

After:

special → 1 → 2 → 3
```

---

## Example: Move an Item to the End

HTML:

```html
<div class="container">
    <div class="item">A</div>
    <div class="item">B</div>
    <div class="item last">C</div>
</div>
```

CSS:

```css
.last {
    order: 1;
}
```

If the other items have the default:

```css
order: 0;
```

the result becomes:

```text
A → B → C
```

However, if the original item was in the middle:

```text
A → C → B
```

and:

```css
.c {
    order: 1;
}
```

while the others remain at `0`, it moves after them:

```text
A → B → C
```

---

## `order` Works on Flex Items

The `order` property applies to **flex items**.

For example:

```css
.container {
    display: flex;
}

.item {
    order: 2;
}
```

The `.item` elements are flex items because their parent is a flex container.

If the parent is not a flex or grid container, `order` does not provide this Flexbox ordering behavior.

---

## `order` Does Not Change the HTML

This is an important concept.

Suppose the HTML is:

```html
<div>One</div>
<div>Two</div>
<div>Three</div>
```

and CSS changes the visual order to:

```text
Three → One → Two
```

The HTML source is still:

```text
One
Two
Three
```

The `order` property changes the **visual layout order**, not the source code.

---

## Visual Order vs Source Order

Think of it as two different orders:

```text
HTML Source Order
        ↓
1 → 2 → 3


Visual Flexbox Order
        ↓
3 → 1 → 2
```

This distinction is important for accessibility and keyboard navigation.

---

## Accessibility Consideration

Using `order` to rearrange content visually does not necessarily change the logical order of the document.

For important content, the HTML source should generally be arranged in a meaningful and logical order first.

Avoid using `order` simply to make a poorly structured document appear correct visually.

For example, if the intended reading order is:

```text
Heading
Content
Image
```

it is better for the HTML structure to reflect that order rather than relying entirely on CSS to rearrange it.

---

## Responsive Design Example

`order` can be useful when a layout needs to change at different screen sizes.

For example:

```css
.container {
    display: flex;
}

.sidebar {
    order: 1;
}

.content {
    order: 2;
}
```

A media query can change the visual arrangement on smaller screens:

```css
@media (max-width: 600px) {
    .content {
        order: 1;
    }

    .sidebar {
        order: 2;
    }
}
```

This allows the visual arrangement to change without changing the HTML structure.

---

## Order With Negative Values

A common pattern is:

```css
.item {
    order: -1;
}
```

Since the default is:

```css
order: 0;
```

the item moves before the default-ordered items.

```text
Default:

1 → 2 → 3

Special item with order: -1:

Special → 1 → 2 → 3
```

---

## Order and Flex Direction

The `order` property determines the sequence of flex items along the flex layout.

It works with different values of:

```css
flex-direction
```

For example:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

The reordered items appear along the row.

With:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

the reordered items appear along the column.

The `order` values still determine the sequence.

---

## Common Use Cases

The `order` property can be useful for:

- Responsive layouts
- Rearranging sidebar and content sections
- Changing the visual position of buttons
- Mobile layout adjustments
- Reordering cards
- Creating alternate visual arrangements

---

## Common Mistake

Do not confuse:

```css
order
```

with:

```css
z-index
```

They control different things.

```text
order
→ Controls the sequence of flex items

z-index
→ Controls stacking order
```

For example:

```text
order:

1 → 2 → 3
```

does not mean:

```text
z-index:

1 → behind
2 → middle
3 → front
```

They solve different layout problems.

---

## Quick Reference

| Value | Meaning |
|-------|---------|
| `order: 0` | Default order |
| Negative value | Appears before higher order values |
| Smaller value | Appears earlier |
| Larger value | Appears later |
| Same value | Source order is preserved |

Example:

```css
.item-a {
    order: 2;
}

.item-b {
    order: -1;
}

.item-c {
    order: 1;
}
```

Visual order:

```text
B → C → A
```

---

> 💡 **Pro Tip:** Use `order` when the visual arrangement genuinely needs to differ from the source order, especially for responsive layouts. Keep the HTML source in a sensible logical order whenever possible.

---

> 💡 **Remember:** `order` changes the **visual sequence of flex items**. The default is `0`, smaller values appear first, and items with equal values retain their source order.

---

# Flex Grow

The `flex-grow` property controls how much a flex item can **grow relative to the other flex items** when there is extra available space in the flex container.

```css
.item {
    flex-grow: 1;
}
```

It applies to **flex items**, not the flex container.

---

## Syntax

```css
.item {
    flex-grow: value;
}
```

The value is a non-negative number.

For example:

```css
.item {
    flex-grow: 1;
}
```

or:

```css
.item {
    flex-grow: 2;
}
```

---

## Default Value

The default value is:

```css
flex-grow: 0;
```

This means a flex item does not grow to consume extra free space by default.

For example:

```css
.container {
    display: flex;
}
```

The items keep their normal sizes rather than automatically expanding to fill all available space.

---

## Basic Example

HTML:

```html
<div class="container">
    <div class="item one">One</div>
    <div class="item two">Two</div>
</div>
```

CSS:

```css
.container {
    display: flex;
}

.one {
    flex-grow: 1;
}
```

The first item can grow into available extra space.

```text
Before:

┌──────────────────────────────────────┐
│ One │ Two                            │
└──────────────────────────────────────┘

After:

┌──────────────────────────────────────┐
│ One grows │ Two                      │
└──────────────────────────────────────┘
```

The second item remains at its normal size because its default is:

```css
flex-grow: 0;
```

---

## Two Items With Equal Growth

Consider:

```css
.one {
    flex-grow: 1;
}

.two {
    flex-grow: 1;
}
```

Both items have the same growth factor.

```text
1 part → One
1 part → Two
```

The available positive free space is distributed equally between them.

Conceptually:

```text
┌──────────────────────────────────────┐
│          One          │      Two     │
└──────────────────────────────────────┘
```

---

## Different Growth Values

Consider:

```css
.one {
    flex-grow: 1;
}

.two {
    flex-grow: 2;
}
```

The growth factors are:

```text
One → 1
Two → 2
```

So the extra available space is distributed in a:

```text
1 : 2
```

ratio.

The second item receives twice the share of the positive free space received by the first item.

Conceptually:

```text
┌──────────────────────────────────────┐
│    One    │          Two             │
│  1 part   │         2 parts          │
└──────────────────────────────────────┘
```

---

## Three Items

Consider:

```css
.one {
    flex-grow: 1;
}

.two {
    flex-grow: 2;
}

.three {
    flex-grow: 1;
}
```

The total growth factor is:

```text
1 + 2 + 1 = 4
```

Therefore, the available positive free space is divided proportionally:

```text
One   → 1/4
Two   → 2/4
Three → 1/4
```

Conceptually:

```text
┌────────────────────────────────────────┐
│ One │       Two       │ Three │
│ 1   │        2        │  1    │
└────────────────────────────────────────┘
```

---

## `flex-grow: 0`

The default behavior is:

```css
.item {
    flex-grow: 0;
}
```

The item does not grow to consume positive free space.

For example:

```css
.one {
    flex-grow: 0;
}

.two {
    flex-grow: 1;
}
```

Only the second item participates in distributing the available positive free space.

---

## `flex-grow: 1`

A value of:

```css
flex-grow: 1;
```

means the item participates in distributing positive free space.

It does **not** mean:

```text
Make the item exactly twice as wide
```

Instead, it means:

```text
Give this item one share of the available positive free space.
```

This distinction is important.

---

## `flex-grow: 2`

A value of:

```css
flex-grow: 2;
```

means the item receives two growth shares relative to an item with:

```css
flex-grow: 1;
```

For example:

```css
.one {
    flex-grow: 1;
}

.two {
    flex-grow: 2;
}
```

The ratio is:

```text
One : Two
 1  :  2
```

This applies to the **extra free space**, not necessarily to the final widths themselves.

---

## Flex Grow Works Along the Main Axis

`flex-grow` operates along the **main axis**.

If:

```css
flex-direction: row;
```

the main axis is horizontal.

```text
Main Axis →
```

Therefore, growth generally affects the horizontal size.

If:

```css
flex-direction: column;
```

the main axis is vertical.

```text
Main Axis
   ↓
```

Therefore, growth generally affects the vertical size.

---

## Example With Row Direction

```css
.container {
    display: flex;
    flex-direction: row;
}

.item {
    flex-grow: 1;
}
```

The items can grow horizontally:

```text
←──────── Main Axis ────────→
```

---

## Example With Column Direction

```css
.container {
    display: flex;
    flex-direction: column;
}

.item {
    flex-grow: 1;
}
```

The items can grow vertically:

```text
Main Axis
   ↓
   ↓
   ↓
```

---

## `flex-grow` and Available Space

`flex-grow` matters when there is **positive free space**.

For example:

```text
Container width = 600px

Items' base sizes = 400px

Remaining space = 200px
```

There is:

```text
200px
```

of positive free space.

If the items have growth factors:

```text
Item A → 1
Item B → 1
```

that extra space is distributed between them according to their growth factors.

---

## Growth Is Relative

Suppose:

```css
.one {
    flex-grow: 1;
}

.two {
    flex-grow: 3;
}
```

The values do not mean:

```text
One = 25% of container
Two = 75% of container
```

They describe the **relative distribution of positive free space**.

The existing base sizes of the items also matter.

Therefore, `flex-grow` should be understood as a growth factor rather than a direct width percentage.

---

## `flex-grow` Does Not Set the Initial Size

Consider:

```css
.item {
    flex-grow: 1;
}
```

This does not define the initial size of the item.

The initial size can be influenced by factors such as:

```css
width
flex-basis
content size
```

`flex-grow` determines how the item participates in distributing positive free space after the initial sizing stage.

---

## `flex-grow` vs `width`

These properties have different purposes.

```css
.item {
    width: 200px;
}
```

defines a width.

Whereas:

```css
.item {
    flex-grow: 1;
}
```

defines how the item participates in growing when extra main-axis space is available.

They can also be used together, although the final size is determined by the Flexbox sizing algorithm.

---

## Common Layout Pattern

A common pattern is:

```css
.container {
    display: flex;
}

.sidebar {
    width: 200px;
}

.content {
    flex-grow: 1;
}
```

The sidebar keeps its intended size while the content item can consume the remaining available space.

Conceptually:

```text
┌──────────┬─────────────────────────────┐
│ Sidebar  │           Content           │
│  200px   │       grows as needed       │
└──────────┴─────────────────────────────┘
```

This is a very common Flexbox layout pattern.

---

## Multiple Growing Items

You can have multiple growing items:

```css
.item-a {
    flex-grow: 1;
}

.item-b {
    flex-grow: 2;
}

.item-c {
    flex-grow: 1;
}
```

The positive free space is distributed according to:

```text
1 : 2 : 1
```

The middle item receives twice the growth share of each of the other items.

---

## `flex-grow` and `gap`

`flex-grow` can be combined with:

```css
gap
```

For example:

```css
.container {
    display: flex;
    gap: 20px;
}

.item {
    flex-grow: 1;
}
```

The gap remains between the items, while the available positive free space is distributed among the growing items.

Conceptually:

```text
┌──────────────────────────────────────┐
│      Item 1    20px    Item 2       │
│       grows             grows       │
└──────────────────────────────────────┘
```

---

## `flex-grow` and `justify-content`

Both properties can affect the use of available space, but they do different jobs.

```text
flex-grow
→ Allows flex items to grow into positive free space

justify-content
→ Distributes remaining free space along the main axis
```

When flex items grow and consume the available positive free space, there may be little or no free space left for `justify-content` to distribute.

---

## Common Mistake

Do not think:

```css
flex-grow: 1;
```

means:

```text
width: 100%;
```

It does not.

It means the item is allowed to receive a proportional share of available positive free space.

---

## Quick Reference

| Value | Meaning |
|-------|---------|
| `0` | Item does not grow |
| `1` | One growth share |
| `2` | Two growth shares |
| `3` | Three growth shares |
| Higher value | Larger share relative to lower values |

Example:

```css
.one {
    flex-grow: 1;
}

.two {
    flex-grow: 2;
}

.three {
    flex-grow: 1;
}
```

Growth ratio:

```text
One   → 1
Two   → 2
Three → 1
```

Therefore:

```text
1 : 2 : 1
```

---

> 💡 **Pro Tip:** Think of `flex-grow` as a **share of extra space**, not as a direct width. If two items have `flex-grow: 1`, they share the available positive free space equally; if one has `2`, it receives twice the share of an item with `1`.

---

> 💡 **Remember:** `flex-grow` controls how flex items use **positive free space along the main axis**. Its default value is `0`, and larger values receive proportionally larger shares of the available extra space.

---

# Flex Shrink

The `flex-shrink` property controls how much a flex item can **shrink relative to other flex items** when there is not enough available space in the flex container.

```css
.item {
    flex-shrink: 1;
}
```

It applies to **flex items**, not the flex container.

---

## Syntax

```css
.item {
    flex-shrink: value;
}
```

The value is a non-negative number.

For example:

```css
.item {
    flex-shrink: 1;
}
```

or:

```css
.item {
    flex-shrink: 2;
}
```

---

## Default Value

The default value is:

```css
flex-shrink: 1;
```

This means flex items are allowed to shrink when there is insufficient space along the main axis.

```text
Not enough space
        ↓
Flex items can shrink
```

---

## Basic Example

HTML:

```html
<div class="container">
    <div class="item one">One</div>
    <div class="item two">Two</div>
</div>
```

CSS:

```css
.container {
    display: flex;
    width: 300px;
}

.one,
.two {
    width: 200px;
}
```

The items would require:

```text
200px + 200px = 400px
```

but the container only has:

```text
300px
```

There is not enough space.

Because the default is:

```css
flex-shrink: 1;
```

the items are allowed to shrink.

---

## `flex-shrink: 0`

You can prevent an item from shrinking:

```css
.item {
    flex-shrink: 0;
}
```

For example:

```css
.sidebar {
    width: 200px;
    flex-shrink: 0;
}
```

The sidebar will not shrink because of Flexbox's negative free-space distribution.

This is useful when an element needs to maintain its intended size.

---

## `flex-shrink: 1`

The default behavior is:

```css
.item {
    flex-shrink: 1;
}
```

The item participates in distributing negative free space.

For example:

```text
Available space < Required space
        ↓
Negative free space
        ↓
Items shrink
```

---

## `flex-shrink: 2`

A value of:

```css
.item {
    flex-shrink: 2;
}
```

gives the item a larger shrink factor relative to an item with:

```css
flex-shrink: 1;
```

For example:

```css
.one {
    flex-shrink: 1;
}

.two {
    flex-shrink: 2;
}
```

The second item has a greater shrink factor.

However, the final sizes are **not determined by the shrink values alone**. Flexbox also considers the items' base sizes when distributing negative free space.

---

## `flex-shrink` Is Not a Percentage

Do not interpret:

```css
flex-shrink: 2;
```

as:

```text
Shrink the item by 200%
```

It is a **factor used by the Flexbox sizing algorithm**.

For example:

```text
Item A → shrink factor 1
Item B → shrink factor 2
```

means Item B has twice the shrink factor of Item A, subject to the other sizing constraints involved in Flexbox.

---

## Flex Shrink Works Along the Main Axis

Like `flex-grow`, `flex-shrink` works along the **main axis**.

With:

```css
flex-direction: row;
```

the main axis is horizontal.

```text
←──────── Main Axis ────────→
```

Therefore, shrinking generally affects horizontal sizing.

With:

```css
flex-direction: column;
```

the main axis is vertical.

```text
Main Axis
   ↓
   ↓
   ↓
```

Therefore, shrinking generally affects vertical sizing.

---

## Example With Row Direction

```css
.container {
    display: flex;
    flex-direction: row;
}

.item {
    flex-shrink: 1;
}
```

The items can shrink along the horizontal main axis when required.

---

## Example With Column Direction

```css
.container {
    display: flex;
    flex-direction: column;
}

.item {
    flex-shrink: 1;
}
```

The items can shrink along the vertical main axis when required.

---

## Negative Free Space

`flex-shrink` becomes relevant when the flex items require more space than the container provides.

For example:

```text
Container = 500px

Required item size = 700px
```

Then:

```text
500px - 700px = -200px
```

There is:

```text
200px of negative free space
```

Flexbox can distribute this negative free space among shrinkable items.

---

## Positive vs Negative Free Space

This is an important distinction.

```text
Extra space available
        ↓
Positive free space
        ↓
flex-grow
```

Whereas:

```text
Not enough space
        ↓
Negative free space
        ↓
flex-shrink
```

So:

```text
flex-grow
→ Handles available extra space

flex-shrink
→ Handles insufficient space
```

---

## `flex-grow` vs `flex-shrink`

| Property | Used When | Default |
|----------|-----------|---------|
| `flex-grow` | Positive free space exists | `0` |
| `flex-shrink` | Negative free space exists | `1` |

A useful mental model:

```text
Too much space
    ↓
Grow

Too little space
    ↓
Shrink
```

---

## Preventing a Sidebar From Shrinking

A common practical example is a sidebar.

```css
.container {
    display: flex;
}

.sidebar {
    width: 240px;
    flex-shrink: 0;
}

.content {
    flex-grow: 1;
}
```

Conceptually:

```text
┌────────────┬──────────────────────────┐
│  Sidebar   │         Content          │
│   240px    │       flexible           │
└────────────┴──────────────────────────┘
```

The sidebar is prevented from shrinking while the content takes the remaining space.

---

## `flex-shrink` With Width

Consider:

```css
.item {
    width: 300px;
    flex-shrink: 1;
}
```

The `width` contributes to the item's sizing, while:

```css
flex-shrink: 1;
```

allows the item to shrink if the Flexbox layout requires it.

Therefore:

```text
width
→ Influences the item's size

flex-shrink
→ Controls whether/how it participates in negative free-space distribution
```

---

## `flex-shrink: 0` Does Not Mean "Never Change Size"

This distinction is important.

```css
.item {
    flex-shrink: 0;
}
```

means the item does not shrink due to Flexbox's negative free-space distribution.

It does not mean the item's size can never change for every possible reason.

Other CSS properties and layout constraints can still affect the final rendered size.

---

## Multiple Shrinking Items

Consider:

```css
.one {
    flex-shrink: 1;
}

.two {
    flex-shrink: 1;
}

.three {
    flex-shrink: 1;
}
```

All three items participate in shrinking according to the Flexbox algorithm.

If one item has:

```css
flex-shrink: 0;
```

that item does not participate in the shrink distribution.

---

## Different Shrink Factors

For example:

```css
.one {
    flex-shrink: 1;
}

.two {
    flex-shrink: 2;
}
```

The values establish a relative shrink factor:

```text
One → 1
Two → 2
```

But the final amount each item shrinks is also influenced by its flex base size.

Therefore, avoid thinking of the values as simple percentages.

---

## Shrinking Can Be Limited

Flex items can have minimum-size constraints.

For example:

```css
.item {
    flex-shrink: 1;
    min-width: 150px;
}
```

The item may shrink until its minimum-size constraints prevent further shrinking.

This is one reason why setting:

```css
flex-shrink: 1;
```

does not guarantee that an item will become arbitrarily small.

---

## `flex-shrink` and `flex-wrap`

When wrapping is enabled:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

items can move onto another flex line instead of remaining on the same line and shrinking indefinitely.

Conceptually:

```text
Without wrapping:

1  2  3  4
← items may shrink →


With wrapping:

1  2  3
4
```

Whether items shrink or wrap depends on the complete Flexbox configuration and available space.

---

## Common Use Cases

`flex-shrink` is useful for:

- Preventing important elements from becoming smaller
- Creating flexible sidebars
- Building responsive layouts
- Controlling how cards react to limited space
- Managing fixed-size controls inside flexible containers

---

## Common Mistake

Do not assume:

```css
flex-shrink: 0;
```

automatically makes an item completely fixed-size.

It only prevents that item from participating in Flexbox's shrinking behavior.

If you need a fixed-size component, consider all relevant sizing properties and constraints together.

---

## Quick Reference

| Value | Meaning |
|-------|---------|
| `0` | Item does not shrink through Flexbox negative free-space distribution |
| `1` | Default shrink factor |
| `2` | Larger shrink factor relative to `1` |
| Higher value | Greater relative shrink factor |

Example:

```css
.sidebar {
    flex-shrink: 0;
}

.content {
    flex-shrink: 1;
}
```

Conceptually:

```text
Sidebar
   ↓
Does not shrink

Content
   ↓
Can shrink
```

---

> 💡 **Pro Tip:** If an important sidebar, logo, button, or control keeps becoming smaller when the container gets tight, check its `flex-shrink` value. Setting `flex-shrink: 0` can prevent Flexbox from shrinking it.

---

> 💡 **Remember:** `flex-shrink` controls how flex items respond to **negative free space** along the main axis. Its default is `1`, while `0` prevents the item from participating in Flexbox's shrinking behavior.

---

# Flex Basis

The `flex-basis` property defines the **initial size of a flex item along the main axis** before Flexbox distributes positive or negative free space.

```css
.item {
    flex-basis: 200px;
}
```

It is one of the three properties represented by the `flex` shorthand:

```css
flex-grow
flex-shrink
flex-basis
```

---

## Syntax

```css
.item {
    flex-basis: value;
}
```

Example:

```css
.item {
    flex-basis: 200px;
}
```

Common values include:

```css
flex-basis: 200px;
flex-basis: 20%;
flex-basis: 10rem;
flex-basis: auto;
flex-basis: 0;
```

---

## Default Value

The default value is:

```css
flex-basis: auto;
```

With `auto`, Flexbox uses the item's main-size property, such as:

```css
width
```

when the main axis is horizontal, or:

```css
height
```

when the main axis is vertical.

The item's content and other sizing rules can also affect its final size.

---

## Main Axis

`flex-basis` is based on the **main axis**, not necessarily the horizontal width.

For:

```css
flex-direction: row;
```

the main axis is horizontal.

```text
←──────── Main Axis ────────→
```

Therefore:

```css
flex-basis: 200px;
```

generally establishes an initial horizontal size.

For:

```css
flex-direction: column;
```

the main axis is vertical.

```text
Main Axis
   ↓
   ↓
   ↓
```

Therefore, `flex-basis` generally establishes an initial vertical size.

---

## Basic Example

```css
.container {
    display: flex;
}

.item {
    flex-basis: 200px;
}
```

Each item starts with a flex basis of:

```text
200px
```

before Flexbox distributes any remaining free space.

Conceptually:

```text
Item 1 → 200px
Item 2 → 200px
Item 3 → 200px
```

The final sizes can change depending on:

```css
flex-grow
flex-shrink
```

and other layout constraints.

---

## `flex-basis` vs `width`

A common question is:

```text
What is the difference between flex-basis and width?
```

They are not exactly the same.

```css
width: 200px;
```

sets the element's width.

Whereas:

```css
flex-basis: 200px;
```

sets the item's initial size along the **main axis** for Flexbox sizing.

Therefore:

```text
width
→ Physical horizontal size property

flex-basis
→ Initial Flexbox main-axis size
```

---

## Row Direction

Consider:

```css
.container {
    display: flex;
    flex-direction: row;
}

.item {
    flex-basis: 200px;
}
```

The main axis is horizontal:

```text
←────────────────────────────→
        Main Axis
```

Therefore, the basis generally corresponds to the initial horizontal size.

---

## Column Direction

Now consider:

```css
.container {
    display: flex;
    flex-direction: column;
}

.item {
    flex-basis: 200px;
}
```

The main axis is vertical:

```text
Main Axis
   ↓
   ↓
   ↓
```

Therefore, the basis generally corresponds to the initial vertical size.

This is why `flex-basis` is more flexible than simply using `width`.

---

## `flex-basis: auto`

The default is:

```css
flex-basis: auto;
```

This tells Flexbox to use the item's main-size property as the basis when appropriate.

For example:

```css
.item {
    width: 200px;
    flex-basis: auto;
}
```

In a row-based flex container, the `width` can provide the initial main size.

---

## `flex-basis: 0`

You can explicitly set:

```css
.item {
    flex-basis: 0;
}
```

This means the item's flex base size starts from zero, subject to the Flexbox sizing algorithm and other constraints.

This is commonly seen with:

```css
.item {
    flex: 1;
}
```

which is frequently used to create equally flexible items.

---

## Percentage Values

`flex-basis` can use percentages:

```css
.item {
    flex-basis: 50%;
}
```

The percentage is resolved relative to the flex container's inner main size when that size is definite.

For example:

```css
.container {
    display: flex;
}

.item {
    flex-basis: 50%;
}
```

Two items with:

```css
flex-basis: 50%;
```

can initially occupy approximately half of the container's main size each, before other Flexbox calculations.

---

## Fixed Length Values

You can use fixed lengths:

```css
.item {
    flex-basis: 250px;
}
```

Other CSS length units can also be used:

```css
flex-basis: 20rem;
flex-basis: 30vw;
```

Choose the unit based on the layout requirements.

---

## `flex-basis` and `flex-grow`

These properties work together.

For example:

```css
.item {
    flex-basis: 200px;
    flex-grow: 1;
}
```

The process can be understood conceptually as:

```text
1. Establish the initial flex size
           ↓
     flex-basis: 200px

2. Check available free space
           ↓
3. Distribute positive free space
           ↓
     flex-grow: 1
```

Therefore, `flex-basis` does not necessarily represent the final size.

---

## `flex-basis` and `flex-shrink`

The same applies when there is not enough space.

```css
.item {
    flex-basis: 300px;
    flex-shrink: 1;
}
```

Conceptually:

```text
Initial flex size
       ↓
300px

Not enough space?
       ↓
flex-shrink
       ↓
Item may become smaller
```

So:

```text
flex-basis
→ Starting point

flex-shrink
→ Handles negative free space
```

---

## `flex-basis` Does Not Guarantee Final Size

This is one of the most important points.

If you write:

```css
.item {
    flex-basis: 200px;
}
```

it does **not** necessarily mean the final rendered size will always be exactly `200px`.

The final size can be affected by:

```css
flex-grow
flex-shrink
min-width
max-width
min-height
max-height
content size
```

and other Flexbox constraints.

Think of `flex-basis` as the **starting point for Flexbox sizing**.

---

## Example With Extra Space

```css
.container {
    display: flex;
}

.one,
.two {
    flex-basis: 200px;
}

.one,
.two {
    flex-grow: 1;
}
```

Suppose the container provides more space than the two 200px bases require.

The extra space can be distributed because:

```css
flex-grow: 1;
```

is enabled.

Conceptually:

```text
flex-basis
   ↓
200px + 200px

Extra space
   ↓
Distributed by flex-grow
```

---

## Example With Insufficient Space

```css
.container {
    display: flex;
    width: 300px;
}

.one,
.two {
    flex-basis: 200px;
    flex-shrink: 1;
}
```

The initial bases require:

```text
200px + 200px = 400px
```

but the container has only:

```text
300px
```

There is negative free space.

Because:

```css
flex-shrink: 1;
```

is enabled, the items can shrink.

Conceptually:

```text
flex-basis
   ↓
400px total

Available
   ↓
300px

Negative free space
   ↓
flex-shrink
```

---

## `flex-basis` and `width` in a Row

Consider:

```css
.container {
    display: flex;
    flex-direction: row;
}

.item {
    width: 300px;
    flex-basis: 200px;
}
```

When `flex-basis` is not `auto`, it generally takes precedence as the flex item's basis for the main-axis sizing calculation.

Therefore, do not assume:

```text
width = final flex size
```

when an explicit `flex-basis` is being used.

---

## `flex-basis` and `height` in a Column

For:

```css
.container {
    display: flex;
    flex-direction: column;
}

.item {
    height: 300px;
    flex-basis: 200px;
}
```

the main axis is vertical, so the flex basis is relevant to the initial vertical sizing.

This demonstrates why `flex-basis` should be understood as a **main-axis property** rather than simply a width property.

---

## Common Use Cases

`flex-basis` is useful for:

- Setting initial card sizes
- Creating flexible columns
- Building responsive layouts
- Defining sidebar starting sizes
- Combining with `flex-grow`
- Combining with `flex-shrink`
- Creating equal-width flexible items

---

## Example: Sidebar and Content

```css
.container {
    display: flex;
}

.sidebar {
    flex-basis: 250px;
    flex-shrink: 0;
}

.content {
    flex-grow: 1;
}
```

Conceptually:

```text
┌──────────────┬─────────────────────────┐
│   Sidebar    │         Content         │
│   250px      │        flexible         │
└──────────────┴─────────────────────────┘
```

The sidebar starts from a basis of `250px`, while the content can use the remaining space.

---

## Example: Equal Flexible Items

A common pattern is:

```css
.item {
    flex-basis: 0;
    flex-grow: 1;
}
```

All items start from the same basis and then share available positive free space according to the same growth factor.

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│    1     │    2     │    3     │
└──────────┴──────────┴──────────┘
```

This pattern is often written more conveniently using:

```css
flex: 1;
```

The shorthand will be covered separately.

---

## `flex-basis` vs `flex-grow` vs `flex-shrink`

These three properties have different responsibilities:

```text
flex-basis
     ↓
Initial main-axis size

flex-grow
     ↓
Uses positive free space

flex-shrink
     ↓
Handles negative free space
```

A useful mental model is:

```text
Start
 ↓
flex-basis
 ↓
Is there extra space?
 ├── Yes → flex-grow
 │
 └── No → Is space insufficient?
             ↓
         flex-shrink
```

This is a simplified mental model; the actual Flexbox sizing algorithm also considers constraints and other factors.

---

## Quick Reference

| Property | Purpose |
|----------|---------|
| `flex-basis` | Defines the initial main-axis size |
| `flex-grow` | Controls growth into positive free space |
| `flex-shrink` | Controls shrinking when space is insufficient |

Common values:

```css
flex-basis: auto;
flex-basis: 0;
flex-basis: 200px;
flex-basis: 50%;
```

Default:

```css
flex-basis: auto;
```

---

> 💡 **Pro Tip:** Think of `flex-basis` as the **starting size** of a flex item along the main axis. Then `flex-grow` and `flex-shrink` determine how that starting size can change when the available space differs from what the items need.

---

> 💡 **Remember:** `flex-basis` defines an item's initial main-axis size. It is not necessarily the final size because Flexbox can grow or shrink the item afterward.

---

# Flex Shorthand

The `flex` property is a shorthand for three flex item properties:

```css
flex-grow
flex-shrink
flex-basis
```

Instead of writing:

```css
.item {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 200px;
}
```

you can write:

```css
.item {
    flex: 1 1 200px;
}
```

---

## Syntax

The general syntax is:

```css
.item {
    flex: grow shrink basis;
}
```

For example:

```css
.item {
    flex: 1 1 200px;
}
```

This corresponds to:

```css
.item {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 200px;
}
```

---

## The Three Components

The shorthand follows this order:

```text
flex: grow shrink basis;
       │     │     │
       │     │     └── flex-basis
       │     └──────── flex-shrink
       └────────────── flex-grow
```

For example:

```css
.item {
    flex: 2 1 250px;
}
```

means:

```css
flex-grow: 2;
flex-shrink: 1;
flex-basis: 250px;
```

---

## Why Use the Shorthand?

The shorthand makes Flexbox CSS shorter and easier to read.

Instead of:

```css
.item {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 0;
}
```

you can write:

```css
.item {
    flex: 1 1 0;
}
```

This is especially useful when working with multiple flex items.

---

## `flex: 1`

One of the most common Flexbox declarations is:

```css
.item {
    flex: 1;
}
```

This is a special shorthand form.

It is commonly used when you want multiple flex items to share available space.

For example:

```css
.container {
    display: flex;
}

.item {
    flex: 1;
}
```

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│  Item 1  │  Item 2  │  Item 3  │
└──────────┴──────────┴──────────┘
```

If the items have the same relevant sizing conditions, they can share the available space equally.

---

## `flex: 1 1 0`

You can explicitly write:

```css
.item {
    flex: 1 1 0;
}
```

This means:

```css
flex-grow: 1;
flex-shrink: 1;
flex-basis: 0;
```

This pattern is commonly used when creating equally flexible items.

---

## `flex: 0 1 auto`

The initial value of the `flex` shorthand is:

```css
flex: 0 1 auto;
```

This corresponds conceptually to:

```css
flex-grow: 0;
flex-shrink: 1;
flex-basis: auto;
```

Therefore:

```text
Grow → No
Shrink → Yes
Basis → auto
```

This is the default flex item behavior.

---

## `flex: none`

The keyword:

```css
flex: none;
```

is equivalent to:

```css
flex: 0 0 auto;
```

Conceptually:

```text
Do not grow
Do not shrink
Use auto basis
```

This can be useful for an item that should not participate in flexible growth or shrinking.

---

## `flex: auto`

The keyword:

```css
flex: auto;
```

is equivalent to:

```css
flex: 1 1 auto;
```

Conceptually:

```text
Grow → Yes
Shrink → Yes
Basis → auto
```

---

## `flex: initial`

The keyword:

```css
flex: initial;
```

represents the initial flex behavior:

```css
flex: 0 1 auto;
```

Conceptually:

```text
Grow → No
Shrink → Yes
Basis → auto
```

---

## Comparing Common Shorthand Values

| Declaration | Grow | Shrink | Basis |
|-------------|------|--------|-------|
| `flex: initial` | `0` | `1` | `auto` |
| `flex: auto` | `1` | `1` | `auto` |
| `flex: none` | `0` | `0` | `auto` |
| `flex: 1 1 0` | `1` | `1` | `0` |

These values have different layout behaviors.

---

## `flex: 1` vs `flex: 1 1 0`

For learning and practical Flexbox work, it is useful to understand the difference between the shorthand form and the explicit three-value form.

```css
flex: 1;
```

is commonly used as a convenient way to make an item flexible.

When you need to communicate the exact intended values, you can write:

```css
flex: 1 1 0;
```

The explicit form makes the three components visible:

```text
grow  shrink  basis
 1      1       0
```

---

## Example: Equal Columns

HTML:

```html
<div class="container">
    <div class="item">One</div>
    <div class="item">Two</div>
    <div class="item">Three</div>
</div>
```

CSS:

```css
.container {
    display: flex;
    gap: 20px;
}

.item {
    flex: 1;
}
```

The items can share the available space.

```text
┌──────────┬──────────┬──────────┐
│   One    │   Two    │  Three   │
└──────────┴──────────┴──────────┘
```

The `gap` remains between the items.

---

## Example: Sidebar and Content

A common layout is:

```css
.sidebar {
    flex: 0 0 250px;
}

.content {
    flex: 1;
}
```

The sidebar uses:

```text
grow   = 0
shrink = 0
basis  = 250px
```

while the content is flexible.

Conceptually:

```text
┌──────────────┬─────────────────────────┐
│   Sidebar    │         Content         │
│    250px     │        flexible         │
└──────────────┴─────────────────────────┘
```

This is a useful real-world Flexbox pattern.

---

## Example: Different Flexible Items

```css
.one {
    flex: 1;
}

.two {
    flex: 2;
}

.three {
    flex: 1;
}
```

Conceptually, the flexible growth ratio is:

```text
1 : 2 : 1
```

The second item receives a larger share of available positive free space.

---

## Explicit Three-Value Syntax

You can specify all three components:

```css
.item {
    flex: 2 1 300px;
}
```

This means:

```css
flex-grow: 2;
flex-shrink: 1;
flex-basis: 300px;
```

The mental model is:

```text
Starting size
     ↓
300px

Extra space?
     ↓
Grow using factor 2

Not enough space?
     ↓
Shrink using factor 1
```

---

## Two-Value Syntax

The `flex` shorthand also supports two-value forms.

For example:

```css
.item {
    flex: 2 1;
}
```

The first value is interpreted as:

```text
flex-grow
```

and the second as:

```text
flex-shrink
```

with the basis using its appropriate default behavior for the shorthand form.

Another common form is:

```css
.item {
    flex: 1 200px;
}
```

where the values represent:

```text
flex-grow
flex-basis
```

The exact interpretation depends on the value types.

For clarity, when learning Flexbox it is often useful to use the explicit three-value form:

```css
flex: 1 1 200px;
```

---

## One-Value Syntax

A single number can be used:

```css
.item {
    flex: 1;
}
```

A single basis value can also be used:

```css
.item {
    flex: 200px;
}
```

The browser interprets these according to the `flex` shorthand syntax.

When you need predictable and explicit behavior, writing all three values can make the intention clearer:

```css
flex: 1 1 200px;
```

---

## `flex` and `width`

Consider:

```css
.item {
    width: 200px;
    flex: 1;
}
```

The `flex` shorthand changes the flex item's flexible sizing behavior.

Therefore, do not assume that:

```css
width: 200px;
```

will always remain the final width when the item is participating in a flexible layout.

The Flexbox sizing algorithm determines the final size.

---

## `flex` and `gap`

The shorthand works normally with container spacing:

```css
.container {
    display: flex;
    gap: 20px;
}

.item {
    flex: 1;
}
```

The items share the available space while:

```css
gap: 20px;
```

maintains the space between them.

---

## `flex` and `flex-direction`

The `flex` property operates on the item's main-axis sizing.

For:

```css
flex-direction: row;
```

the main axis is horizontal.

For:

```css
flex-direction: column;
```

the main axis is vertical.

Therefore, the same:

```css
flex: 1;
```

can make an item flexible along different physical directions depending on the container's `flex-direction`.

---

## Common Use Cases

The `flex` shorthand is commonly used for:

- Equal-width columns
- Flexible content areas
- Sidebar layouts
- Responsive cards
- Navigation layouts
- Flexible buttons
- Space distribution between items

---

## Common Mistake

Do not confuse:

```css
flex: 1;
```

with:

```css
width: 1px;
```

They are completely different.

```text
flex: 1
→ Flex shorthand

width: 1px
→ Explicit width
```

Similarly, do not assume that the first value of:

```css
flex: 1 2 200px;
```

is the basis.

The order is:

```text
grow → shrink → basis
```

---

## Quick Reference

### Three Values

```css
flex: 1 1 200px;
```

means:

```css
flex-grow: 1;
flex-shrink: 1;
flex-basis: 200px;
```

### Common Keywords

```css
flex: initial;
flex: auto;
flex: none;
```

Conceptually:

```text
initial → 0 1 auto
auto    → 1 1 auto
none    → 0 0 auto
```

### Common Flexible Pattern

```css
.item {
    flex: 1;
}
```

### Explicit Flexible Pattern

```css
.item {
    flex: 1 1 0;
}
```

---

## Flexbox Item Properties Recap

At this point, the three main sizing properties have been covered:

```css
flex-grow
flex-shrink
flex-basis
```

They can be written individually:

```css
.item {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 200px;
}
```

or using the shorthand:

```css
.item {
    flex: 1 1 200px;
}
```

This is why understanding the individual properties first is important before relying heavily on the shorthand.

---

> 💡 **Pro Tip:** Learn `flex-grow`, `flex-shrink`, and `flex-basis` individually first. Then use `flex` for cleaner CSS once you understand what each value controls.

---

> 💡 **Remember:** The `flex` shorthand combines **grow, shrink, and basis** in that order:

```text
flex: grow shrink basis;
```

For example:

```css
flex: 1 1 200px;
```

means:

```css
flex-grow: 1;
flex-shrink: 1;
flex-basis: 200px;
```

---

# Align Self

The `align-self` property controls the alignment of an **individual flex item** along the cross axis.

It allows one flex item to override the alignment defined by the flex container's:

```css
align-items
```

property.

---

## Syntax

```css
.item {
    align-self: value;
}
```

Common values include:

```css
align-self: auto;
align-self: flex-start;
align-self: flex-end;
align-self: center;
align-self: stretch;
align-self: baseline;
```

---

## Default Value

The default value is:

```css
align-self: auto;
```

With `auto`, the item uses the value of the parent's:

```css
align-items
```

property.

For example:

```css
.container {
    display: flex;
    align-items: center;
}
```

An item with:

```css
.item {
    align-self: auto;
}
```

follows:

```css
align-items: center;
```

---

## Basic Example

HTML:

```html
<div class="container">
    <div class="item">One</div>
    <div class="item special">Two</div>
    <div class="item">Three</div>
</div>
```

CSS:

```css
.container {
    display: flex;
    align-items: center;
}

.special {
    align-self: flex-start;
}
```

The normal items are centered:

```text
        One
        Three
```

while the special item is aligned at the start of the cross axis.

---

## Why Use `align-self`?

Suppose the container has:

```css
.container {
    display: flex;
    align-items: center;
}
```

This affects all flex items.

But perhaps one particular item needs different alignment.

Instead of changing:

```css
align-items
```

for the entire container, use:

```css
align-self
```

on that individual item.

```text
Container
    │
    ├── Item 1 → center
    ├── Item 2 → start
    └── Item 3 → center
```

This is the main purpose of `align-self`.

---

## `align-self: auto`

```css
.item {
    align-self: auto;
}
```

The item follows the parent's:

```css
align-items
```

value.

For example:

```css
.container {
    display: flex;
    align-items: flex-end;
}

.item {
    align-self: auto;
}
```

The item behaves as if it were using:

```css
align-items: flex-end;
```

---

## `align-self: flex-start`

```css
.item {
    align-self: flex-start;
}
```

The item is positioned at the start of the cross axis.

For a typical row layout:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

the cross axis is vertical.

Conceptually:

```text
Cross Axis

Start
  ↓
┌──────────────────────┐
│ Item                 │
│                      │
│                      │
└──────────────────────┘
  ↑
End
```

---

## `align-self: flex-end`

```css
.item {
    align-self: flex-end;
}
```

The item is positioned at the end of the cross axis.

In a typical row layout:

```text
┌──────────────────────┐
│                      │
│                      │
│ Item                 │
└──────────────────────┘
```

---

## `align-self: center`

```css
.item {
    align-self: center;
}
```

The item is centered along the cross axis.

```text
┌──────────────────────┐
│                      │
│        Item          │
│                      │
└──────────────────────┘
```

---

## `align-self: stretch`

```css
.item {
    align-self: stretch;
}
```

The item can stretch to fill the available cross-axis space, subject to its size constraints.

For example:

```css
.container {
    display: flex;
    align-items: flex-start;
}

.item {
    align-self: stretch;
}
```

The individual item can stretch even though the other items use the container's:

```css
align-items: flex-start;
```

---

## `align-self: baseline`

```css
.item {
    align-self: baseline;
}
```

The item is aligned according to the flex line's baseline.

This is useful when aligning content based on text or other baseline-aligned content.

---

## `align-self` vs `align-items`

These properties are closely related but operate at different levels.

### `align-items`

Applied to the **flex container**:

```css
.container {
    align-items: center;
}
```

It controls the default cross-axis alignment of the flex items.

### `align-self`

Applied to an **individual flex item**:

```css
.item {
    align-self: flex-end;
}
```

It allows that item to override the container's default.

---

## Mental Model

Think of:

```css
align-items
```

as:

```text
"What should all my children do?"
```

and:

```css
align-self
```

as:

```text
"What should this particular child do?"
```

For example:

```text
Container:
align-items: center

       ↓

Item 1 → center
Item 2 → center
Item 3 → center
```

Now:

```css
.item-2 {
    align-self: flex-start;
}
```

Result:

```text
Item 1 → center
Item 2 → flex-start
Item 3 → center
```

---

## Example: One Item at the Top

```css
.container {
    display: flex;
    align-items: center;
}

.top {
    align-self: flex-start;
}
```

Conceptually:

```text
┌────────────────────────────┐
│ Top                        │
│                            │
│       Other items          │
│                            │
└────────────────────────────┘
```

Only the `.top` item changes its cross-axis alignment.

---

## Example: One Item at the Bottom

```css
.container {
    display: flex;
    align-items: center;
}

.bottom {
    align-self: flex-end;
}
```

The other items remain centered while the selected item moves toward the cross-axis end.

---

## Example: Different Items, Different Alignment

```css
.container {
    display: flex;
    align-items: center;
}

.start {
    align-self: flex-start;
}

.center {
    align-self: center;
}

.end {
    align-self: flex-end;
}
```

Conceptually:

```text
┌────────────────────────────────┐
│ Start                          │
│                                │
│             Center             │
│                                │
│                          End   │
└────────────────────────────────┘
```

Each item can have its own cross-axis alignment.

---

## `align-self` and `flex-direction`

`align-self` works along the **cross axis**.

With:

```css
flex-direction: row;
```

the cross axis is generally vertical.

```text
Main Axis →
Cross Axis
    ↓
```

With:

```css
flex-direction: column;
```

the cross axis is generally horizontal.

```text
Cross Axis →
Main Axis
    ↓
```

Therefore, the physical direction affected by `align-self` depends on the container's `flex-direction`.

---

## `align-self` Does Not Control the Main Axis

Do not confuse:

```css
align-self
```

with:

```css
justify-content
```

In a typical row-based flex container:

```text
justify-content
→ Main axis

align-self
→ Individual item's cross-axis alignment
```

For example:

```css
.container {
    display: flex;
}

.item {
    align-self: flex-end;
}
```

This does not move the item toward the end of the main axis.

It changes its position along the cross axis.

---

## `align-self` vs `justify-self`

Flexbox does not use:

```css
justify-self
```

for positioning individual flex items along the main axis in the same way CSS Grid does.

For Flexbox, individual cross-axis alignment is handled by:

```css
align-self
```

while main-axis distribution is generally controlled by the container's:

```css
justify-content
```

---

## `align-self` and `align-items`

A useful comparison:

```text
align-items
     ↓
Container
     ↓
Controls default alignment of all items


align-self
     ↓
Individual item
     ↓
Overrides the container's default
```

Example:

```css
.container {
    display: flex;
    align-items: center;
}

.special {
    align-self: flex-end;
}
```

Result:

```text
Normal items → center
Special item → flex-end
```

---

## Common Use Cases

`align-self` is useful for:

- Positioning one special item differently
- Responsive layouts
- Aligning buttons independently
- Creating card layouts
- Adjusting individual navigation items
- Fine-tuning cross-axis alignment

---

## Common Mistake

Do not apply:

```css
align-self
```

to the flex container expecting it to control all children.

It is an **item property**.

Correct:

```css
.container {
    display: flex;
}

.item {
    align-self: center;
}
```

For controlling all items, use:

```css
.container {
    align-items: center;
}
```

---

## Quick Reference

| Value | Purpose |
|-------|---------|
| `auto` | Uses the parent's `align-items` value |
| `flex-start` | Aligns item at cross-axis start |
| `flex-end` | Aligns item at cross-axis end |
| `center` | Centers item on the cross axis |
| `stretch` | Stretches item across the cross axis when possible |
| `baseline` | Aligns item according to the baseline |

---

## Flex Item Properties Recap

The main flex item properties covered so far are:

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

Their responsibilities can be summarized as:

```text
order
  ↓
Visual sequence

flex-grow
  ↓
Growth into positive free space

flex-shrink
  ↓
Response to negative free space

flex-basis
  ↓
Initial main-axis size

flex
  ↓
Shorthand for grow, shrink, basis

align-self
  ↓
Individual cross-axis alignment
```

---

> 💡 **Pro Tip:** If most flex items need the same cross-axis alignment, use `align-items` on the container. Use `align-self` only when individual items need to behave differently.

---

> 💡 **Remember:** `align-items` controls the default cross-axis alignment for flex items, while `align-self` lets an individual flex item override that default.

---

# Nested Flex Containers

A flex container can also be a flex item of another flex container.

This allows Flexbox layouts to be **nested**.

For example:

```html
<div class="outer">
    <div class="item">One</div>

    <div class="inner">
        <div>Two</div>
        <div>Three</div>
    </div>
</div>
```

The `.outer` element can be a flex container:

```css
.outer {
    display: flex;
}
```

The `.inner` element can also be a flex container:

```css
.inner {
    display: flex;
}
```

This creates two levels of Flexbox:

```text
Outer Flex Container
│
├── Item
│
└── Inner Flex Container
    ├── Item
    └── Item
```

---

## A Flex Item Can Also Be a Flex Container

This is an important Flexbox concept.

An element can simultaneously be:

```text
Flex Item
    +
Flex Container
```

For example:

```css
.outer {
    display: flex;
}

.inner {
    display: flex;
}
```

If `.inner` is a child of `.outer`, then:

```text
.outer
→ Flex Container

.inner
→ Flex Item of .outer
→ Flex Container for its own children
```

---

## Basic Example

HTML:

```html
<div class="container">
    <div class="item">A</div>

    <div class="nested">
        <div class="item">B</div>
        <div class="item">C</div>
    </div>

    <div class="item">D</div>
</div>
```

CSS:

```css
.container {
    display: flex;
}

.nested {
    display: flex;
}
```

The outer container controls:

```text
A
Nested
D
```

The nested container controls:

```text
B
C
```

Conceptually:

```text
Outer Flexbox
┌──────┬──────────────┬──────┐
│  A   │    Nested    │  D   │
│      │              │      │
│      │   B   C      │      │
└──────┴──────────────┴──────┘
```

---

## Two Independent Flex Layouts

The outer and inner containers have their own Flexbox properties.

For example:

```css
.outer {
    display: flex;
    gap: 20px;
}

.inner {
    display: flex;
    gap: 10px;
}
```

The outer container controls:

```text
Spacing between A, Inner, and D
```

The inner container controls:

```text
Spacing between B and C
```

The two `gap` properties operate at different levels.

---

## Different Flex Directions

Nested containers do not have to use the same direction.

For example:

```css
.outer {
    display: flex;
    flex-direction: row;
}

.inner {
    display: flex;
    flex-direction: column;
}
```

The outer layout is horizontal:

```text
A → Inner → D
```

while the inner layout is vertical:

```text
B
↓
C
```

Conceptually:

```text
┌─────┬───────────┬─────┐
│  A  │     B     │  D  │
│     │     ↓     │     │
│     │     C     │     │
└─────┴───────────┴─────┘
```

This is one of the most useful patterns with nested Flexbox.

---

## Different Alignment Rules

Each flex container can have its own alignment rules.

For example:

```css
.outer {
    display: flex;
    align-items: center;
}

.inner {
    display: flex;
    align-items: flex-start;
}
```

The outer container controls how the nested container itself is aligned.

The inner container controls how its own children are aligned.

Think of the levels separately:

```text
Outer Flexbox
    ↓
Positions the inner container

Inner Flexbox
    ↓
Positions the inner container's children
```

---

## Container Properties Do Not Automatically Pass Down

Suppose:

```css
.outer {
    display: flex;
    justify-content: center;
}
```

This controls the direct children of `.outer`.

It does not automatically center the grandchildren inside `.inner`.

For example:

```text
.outer
│
└── .inner
    ├── Item A
    └── Item B
```

`justify-content` on `.outer` affects:

```text
.inner
```

as an outer flex item.

It does not directly control:

```text
Item A
Item B
```

Those items are controlled by `.inner` if `.inner` is a flex container.

---

## Nested Flexbox Mental Model

Consider:

```html
<div class="outer">
    <div class="inner">
        <div class="child">A</div>
        <div class="child">B</div>
    </div>
</div>
```

Think about the layout in two steps.

### Level 1

```css
.outer {
    display: flex;
}
```

This creates:

```text
Outer Flexbox
    ↓
Inner
```

### Level 2

```css
.inner {
    display: flex;
}
```

This creates:

```text
Inner Flexbox
    ↓
A
B
```

Therefore:

```text
Outer Flexbox
     ↓
  Inner
     ↓
Inner Flexbox
   ↓     ↓
  A       B
```

---

## Nested Navigation Example

Nested Flexbox is common in navigation layouts.

HTML:

```html
<nav class="navbar">
    <div class="logo">Logo</div>

    <div class="links">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </div>
</nav>
```

CSS:

```css
.navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.links {
    display: flex;
    gap: 20px;
}
```

The outer container controls:

```text
Logo       Links
```

The nested container controls:

```text
Home → About → Contact
```

Conceptually:

```text
┌────────────────────────────────────────┐
│ Logo             Home About Contact   │
└────────────────────────────────────────┘
```

---

## Nested Card Example

Nested Flexbox is also useful for cards.

HTML:

```html
<div class="card">
    <div class="card-content">
        <h2>Title</h2>
        <p>Description</p>
    </div>

    <button>Read More</button>
</div>
```

CSS:

```css
.card {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.card-content {
    display: flex;
    flex-direction: column;
}
```

The card uses Flexbox to position:

```text
Content + Button
```

while the nested content uses another Flexbox layout for:

```text
Title
   ↓
Description
```

---

## Nested Flexbox and `flex-grow`

A nested flex container can also be a flex item that grows.

For example:

```css
.outer {
    display: flex;
}

.inner {
    display: flex;
    flex-grow: 1;
}
```

Here `.inner` has two roles:

```text
As a child of .outer:
→ Flex item

For its own children:
→ Flex container
```

Therefore:

```text
Outer
│
├── Other Item
│
└── Inner
      ↑
      Can grow

      ↓
   Inner children
```

---

## Nested Flexbox and `align-self`

The nested container can also use item properties.

For example:

```css
.outer {
    display: flex;
    align-items: center;
}

.inner {
    display: flex;
    align-self: flex-start;
}
```

Here:

```text
.outer
→ Controls .inner as a flex item

.inner
→ Controls its own children as a flex container
```

This demonstrates how Flexbox properties can apply at different levels.

---

## Three Levels of Flexbox

Flexbox can be nested more than once.

For example:

```html
<div class="level-one">
    <div class="level-two">
        <div class="level-three">
            <div>Content</div>
        </div>
    </div>
</div>
```

Each level can become a flex container:

```css
.level-one {
    display: flex;
}

.level-two {
    display: flex;
}

.level-three {
    display: flex;
}
```

Conceptually:

```text
Level 1 Flex Container
        ↓
Level 2 Flex Container
        ↓
Level 3 Flex Container
        ↓
Content
```

Each level controls its own direct children.

---

## Important Rule

Flexbox properties generally affect the **direct children** of a flex container.

For example:

```css
.parent {
    display: flex;
    justify-content: center;
}
```

The direct children of `.parent` are flex items.

But grandchildren are not directly controlled by `.parent`'s Flexbox layout.

```text
Parent
│
├── Child        ← Flex Item
│
└── Child        ← Flex Item
     │
     └── Grandchild ← Not a direct flex item of Parent
```

If the child also has:

```css
display: flex;
```

then it creates a new Flexbox context for its own children.

---

## Common Use Cases

Nested Flexbox is useful for:

- Navigation bars
- Cards
- Headers
- Footers
- Sidebars
- Form layouts
- Dashboard layouts
- Button groups
- Responsive components
- Complex page sections

---

## Common Mistake

Do not assume that applying:

```css
display: flex;
```

to a parent automatically makes every descendant a flex item.

Only the **direct children** become flex items.

For example:

```text
Parent
│
├── Child A ← Flex Item
│
└── Child B ← Flex Item
     │
     └── Grandchild ← Not a flex item of Parent
```

If you want the grandchildren to participate in another Flexbox layout, their direct parent can also become a flex container.

---

## Nested Flexbox vs One Large Flexbox

Instead of trying to control every element from one container:

```text
One huge Flexbox
    ↓
Many unrelated elements
```

it is often cleaner to divide the layout into logical groups:

```text
Main Flexbox
    │
    ├── Header Group
    │      ↓
    │   Nested Flexbox
    │
    ├── Content Group
    │      ↓
    │   Nested Flexbox
    │
    └── Footer Group
           ↓
        Nested Flexbox
```

This makes each layout responsibility easier to understand.

---

## Quick Reference

A nested flex container can be:

```text
Flex Item
    +
Flex Container
```

Example:

```css
.outer {
    display: flex;
}

.inner {
    display: flex;
}
```

Therefore:

```text
.outer
→ Flex container

.inner
→ Flex item of .outer
→ Flex container for its children
```

The key rule is:

```text
Flexbox properties apply to direct children.
```

A nested flex container creates another independent Flexbox layout for its own children.

---

> 💡 **Pro Tip:** When a component becomes complicated, break its layout into smaller Flexbox containers. Let the parent control the component's position and let nested containers control the internal arrangement.

---

> 💡 **Remember:** A flex item can also be a flex container. This allows Flexbox layouts to be nested, with each container controlling the arrangement of its own direct children.

---

# Centering with Flexbox

One of the most common uses of Flexbox is centering content.

By combining:

```css
justify-content
```

and:

```css
align-items
```

you can easily center an element along both axes.

---

## Horizontal Centering

For a typical row-based flex container:

```css
.container {
    display: flex;
    justify-content: center;
}
```

`justify-content` controls the main axis.

With the default:

```css
flex-direction: row;
```

the main axis is horizontal.

Conceptually:

```text
┌──────────────────────────────┐
│                              │
│          Content             │
│                              │
└──────────────────────────────┘
```

The content is centered horizontally.

---

## Vertical Centering

To center an item vertically in a typical row-based flex container:

```css
.container {
    display: flex;
    align-items: center;
}
```

`align-items` controls the cross axis.

With:

```css
flex-direction: row;
```

the cross axis is vertical.

Conceptually:

```text
┌──────────────────────────────┐
│                              │
│          Content             │
│                              │
└──────────────────────────────┘
```

The item is centered vertically.

---

## Centering Both Horizontally and Vertically

The most common Flexbox centering pattern is:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This centers the content along both axes.

Conceptually:

```text
┌──────────────────────────────┐
│                              │
│                              │
│          Content             │
│                              │
│                              │
└──────────────────────────────┘
```

This works because:

```text
justify-content
→ Main-axis centering

align-items
→ Cross-axis centering
```

---

## Complete Example

HTML:

```html
<div class="container">
    <div class="box">
        Centered Content
    </div>
</div>
```

CSS:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 300px;
}

.box {
    padding: 20px;
}
```

The `.box` is centered inside the `.container`.

---

## Full-Page Centering

Flexbox can also center content within the viewport.

```css
body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
```

The content can be centered both horizontally and vertically within the viewport.

A common pattern is:

```css
body {
    margin: 0;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

---

## Why `min-height: 100vh`?

Consider:

```css
body {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

The body may not have enough height for vertical centering to have the expected effect.

Using:

```css
min-height: 100vh;
```

makes the body at least as tall as the viewport.

```text
Viewport
┌────────────────────────────┐
│                            │
│                            │
│         Content            │
│                            │
│                            │
└────────────────────────────┘
```

---

## Centering a Button

HTML:

```html
<div class="container">
    <button>Click Me</button>
</div>
```

CSS:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

The button is centered along both axes within the available container.

---

## Centering an Image

HTML:

```html
<div class="container">
    <img src="image.jpg" alt="Example">
</div>
```

CSS:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

The image is centered along the main and cross axes.

---

## Centering Multiple Items

Suppose:

```html
<div class="container">
    <div>One</div>
    <div>Two</div>
    <div>Three</div>
</div>
```

CSS:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

The group is centered, while `gap` controls the spacing between the items.

Conceptually:

```text
┌────────────────────────────────┐
│                                │
│       One   Two   Three        │
│                                │
└────────────────────────────────┘
```

---

## Centering With `flex-direction: column`

When using:

```css
flex-direction: column;
```

the axes change.

```text
Main Axis
   ↓
   ↓
   ↓

Cross Axis →
```

Therefore:

```css
justify-content: center;
```

centers along the vertical main axis.

And:

```css
align-items: center;
```

centers along the horizontal cross axis.

So this still centers content in both directions:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
```

The important concept is that Flexbox properties work according to the **main axis and cross axis**, not fixed physical directions.

---

## `justify-content` vs `align-items` for Centering

For the default row direction:

```css
flex-direction: row;
```

use:

```text
justify-content: center
        ↓
Horizontal centering

align-items: center
        ↓
Vertical centering
```

For column direction:

```css
flex-direction: column;
```

use:

```text
justify-content: center
        ↓
Vertical centering

align-items: center
        ↓
Horizontal centering
```

This is why understanding the axes is important.

---

## Centering a Card

A common UI pattern is a centered card:

```html
<div class="page">
    <div class="card">
        <h2>Welcome</h2>
        <p>Hello!</p>
    </div>
</div>
```

CSS:

```css
.page {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.card {
    padding: 30px;
}
```

The card is centered within the page.

---

## Centering With `margin: auto`

Flexbox also supports another useful technique.

For example:

```css
.container {
    display: flex;
}

.item {
    margin: auto;
}
```

Auto margins can absorb available free space.

However, for straightforward two-axis centering, the following is usually easier to understand:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

---

## Centering One Item Among Others

Suppose a container has multiple items:

```css
.container {
    display: flex;
}
```

You can use:

```css
.item {
    margin-left: auto;
    margin-right: auto;
}
```

in appropriate layouts to consume available horizontal free space.

However, this is different from:

```css
justify-content: center;
```

because auto margins participate directly in free-space distribution.

Choose the technique based on the desired layout behavior.

---

## Common Centering Pattern

For a single element that needs to be centered inside a container:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

For a full viewport:

```css
.container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

These are two patterns worth remembering.

---

## Centering With a Gap

You can combine centering with spacing:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 16px;
}
```

The group is centered while the items maintain a `16px` gap.

---

## Centering Does Not Mean Fixed Positioning

Flexbox centering is part of the layout system.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

The item remains part of the normal Flexbox layout.

This is different from using:

```css
position: absolute;
```

and manually calculating offsets.

Flexbox is therefore often a cleaner choice for responsive alignment.

---

## Responsive Centering

Because Flexbox distributes available space dynamically, centered layouts can naturally adapt to different container sizes.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}
```

The content remains centered as the viewport size changes, subject to the normal layout constraints.

---

## Common Mistakes

### Forgetting `display: flex`

This will not work as Flexbox centering:

```css
.container {
    justify-content: center;
    align-items: center;
}
```

The container must first be a flex container:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

---

### Confusing the Axes

Do not always think:

```text
justify-content = horizontal
align-items = vertical
```

Instead remember:

```text
justify-content
→ Main axis

align-items
→ Cross axis
```

The physical direction depends on:

```css
flex-direction
```

---

### Forgetting Container Size

Vertical centering is difficult to see when the container has no meaningful height.

For example:

```css
.container {
    display: flex;
    align-items: center;
}
```

If the container's height is only determined by its content, there may be little or no extra vertical space to distribute.

A defined or minimum height can make the effect clear:

```css
.container {
    min-height: 300px;
    display: flex;
    align-items: center;
}
```

---

## Quick Reference

### Horizontal Centering in a Row

```css
.container {
    display: flex;
    justify-content: center;
}
```

### Vertical Centering in a Row

```css
.container {
    display: flex;
    align-items: center;
}
```

### Both Directions

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### Full Viewport

```css
.container {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

---

## Centering Mental Model

Remember:

```text
             Main Axis
                ↓
        justify-content
                ↓
           CENTER

             Cross Axis
                ↓
          align-items
                ↓
           CENTER
```

For a row:

```text
justify-content → horizontal
align-items     → vertical
```

For a column:

```text
justify-content → vertical
align-items     → horizontal
```

---

> 💡 **Pro Tip:** When you need to center something with Flexbox, first identify the main and cross axes. Then use `justify-content` for the main axis and `align-items` for the cross axis.

---

> 💡 **Remember:** The classic Flexbox centering pattern is:

```css
display: flex;
justify-content: center;
align-items: center;
```

It centers the flex items along both axes.

---

# Common Flexbox Layouts

Flexbox is useful for creating many common web layouts without relying on complicated positioning.

The same core properties can be combined in different ways depending on the layout requirement.

Common patterns include:

- Navigation bars
- Headers
- Footers
- Sidebars
- Card layouts
- Button groups
- Centered layouts
- Split layouts
- Responsive sections

---

## Navigation Bar

A navigation bar is a common Flexbox use case.

HTML:

```html
<nav class="navbar">
    <div class="logo">Logo</div>

    <div class="nav-links">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Services</a>
        <a href="#">Contact</a>
    </div>
</nav>
```

CSS:

```css
.navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.nav-links {
    display: flex;
    gap: 20px;
}
```

Conceptually:

```text
┌────────────────────────────────────────────┐
│ Logo          Home About Services Contact  │
└────────────────────────────────────────────┘
```

The outer container positions the logo and navigation links.

The nested container arranges the links.

---

## Header Layout

A header can contain multiple groups:

```text
┌─────────────────────────────────────────────┐
│ Logo        Navigation          User        │
└─────────────────────────────────────────────┘
```

Example:

```css
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
```

If the navigation itself contains multiple items:

```css
.navigation {
    display: flex;
    gap: 24px;
}
```

This creates a simple nested Flexbox layout.

---

## Footer Layout

Flexbox can also arrange footer sections.

HTML:

```html
<footer class="footer">
    <div>Company</div>
    <div>Resources</div>
    <div>Social</div>
</footer>
```

CSS:

```css
.footer {
    display: flex;
    justify-content: space-between;
    gap: 30px;
}
```

Conceptually:

```text
┌────────────┬────────────┬────────────┐
│  Company   │ Resources  │   Social   │
└────────────┴────────────┴────────────┘
```

---

## Sidebar Layout

A common page layout consists of a sidebar and a content area.

```text
┌──────────────┬────────────────────────────┐
│   Sidebar    │          Content           │
│              │                            │
│              │                            │
└──────────────┴────────────────────────────┘
```

Example:

```css
.page {
    display: flex;
}

.sidebar {
    flex: 0 0 240px;
}

.content {
    flex: 1;
}
```

The sidebar starts at `240px` while the content uses the remaining available space.

---

## Sidebar With a Non-Shrinking Width

A sidebar often should not become smaller than intended.

```css
.sidebar {
    width: 240px;
    flex-shrink: 0;
}
```

This prevents Flexbox from shrinking the sidebar through negative free-space distribution.

The content can remain flexible:

```css
.content {
    flex: 1;
}
```

---

## Two-Column Layout

A simple two-column layout can be created with:

```css
.container {
    display: flex;
    gap: 20px;
}

.column {
    flex: 1;
}
```

Conceptually:

```text
┌────────────────────┬────────────────────┐
│      Column 1      │      Column 2      │
└────────────────────┴────────────────────┘
```

Both columns can share the available space.

---

## Three-Column Layout

The same pattern can be extended:

```css
.container {
    display: flex;
    gap: 20px;
}

.column {
    flex: 1;
}
```

HTML:

```html
<div class="container">
    <div class="column">One</div>
    <div class="column">Two</div>
    <div class="column">Three</div>
</div>
```

Conceptually:

```text
┌────────────┬────────────┬────────────┐
│    One     │    Two     │   Three    │
└────────────┴────────────┴────────────┘
```

Because the items have the same flexible sizing, they can share the available space.

---

## Unequal Columns

Not every layout needs equal columns.

For example:

```css
.main {
    flex: 2;
}

.side {
    flex: 1;
}
```

Conceptually:

```text
┌────────────────────────┬──────────────┐
│          Main          │     Side     │
│                        │              │
└────────────────────────┴──────────────┘
```

The main section has a larger growth factor than the side section.

---

## Card Layout

Flexbox can arrange cards in a row.

```html
<div class="cards">
    <div class="card">Card 1</div>
    <div class="card">Card 2</div>
    <div class="card">Card 3</div>
</div>
```

CSS:

```css
.cards {
    display: flex;
    gap: 20px;
}

.card {
    flex: 1;
}
```

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│  Card 1  │  Card 2  │  Card 3  │
└──────────┴──────────┴──────────┘
```

---

## Responsive Card Layout

Cards can wrap when the container becomes too narrow.

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

The basis provides an initial size:

```css
flex-basis: 250px;
```

while:

```css
flex-wrap: wrap;
```

allows items to move to another line when necessary.

Conceptually:

```text
Wide screen:

┌────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │
└────────┴────────┴────────┘


Narrower screen:

┌────────┬────────┐
│ Card 1 │ Card 2 │
├────────┼────────┤
│ Card 3 │        │
└────────┴────────┘
```

The exact arrangement depends on the available space and item sizing.

---

## Button Group

Flexbox is useful for arranging buttons.

```css
.buttons {
    display: flex;
    gap: 10px;
}
```

Conceptually:

```text
┌──────────┐  ┌──────────┐  ┌──────────┐
│  Cancel  │  │   Save   │  │  Delete  │
└──────────┘  └──────────┘  └──────────┘
```

You can also center the group:

```css
.buttons {
    display: flex;
    justify-content: center;
    gap: 10px;
}
```

---

## Vertically Stacked Content

Flexbox can arrange content vertically.

```css
.container {
    display: flex;
    flex-direction: column;
    gap: 16px;
}
```

Conceptually:

```text
Item 1
  ↓
Item 2
  ↓
Item 3
```

This is useful for:

- Forms
- Menus
- Card content
- Sidebars
- Sections

---

## Card With Content and Button

A card can use a column-based Flexbox layout:

```css
.card {
    display: flex;
    flex-direction: column;
    gap: 12px;
}
```

For example:

```text
┌────────────────────┐
│ Title              │
│                    │
│ Description        │
│                    │
│ Button             │
└────────────────────┘
```

Each direct child is arranged along the column's main axis.

---

## Card With Button at the Bottom

Flexbox can also help keep a button at the bottom of a card.

```css
.card {
    display: flex;
    flex-direction: column;
}

.button {
    margin-top: auto;
}
```

The auto margin consumes available free space.

Conceptually:

```text
┌────────────────────┐
│ Title              │
│                    │
│ Description        │
│                    │
│                    │
│       Button       │
└────────────────────┘
```

This is useful when cards have different amounts of content but need their actions aligned toward the bottom.

---

## Centered Content Section

A section can center its content in both directions:

```css
.section {
    min-height: 400px;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Conceptually:

```text
┌──────────────────────────────┐
│                              │
│                              │
│          Content             │
│                              │
│                              │
└──────────────────────────────┘
```

This is useful for:

- Hero sections
- Empty states
- Login screens
- Welcome messages
- Loading screens

---

## Split Layout

A common layout divides a section into two parts:

```text
┌───────────────────┬───────────────────┐
│                   │                   │
│      Image        │      Content      │
│                   │                   │
└───────────────────┴───────────────────┘
```

Example:

```css
.section {
    display: flex;
    gap: 40px;
}

.image {
    flex: 1;
}

.content {
    flex: 1;
}
```

Both sections can share the available space.

---

## Image and Content With Different Sizes

You can give the content a larger share:

```css
.image {
    flex: 1;
}

.content {
    flex: 2;
}
```

Conceptually:

```text
┌──────────────┬──────────────────────────┐
│    Image     │         Content          │
│              │                          │
└──────────────┴──────────────────────────┘
```

The content has a larger growth factor.

---

## Navigation With a Flexible Middle Section

A header can contain:

```text
Logo | Navigation | Actions
```

Example:

```css
.header {
    display: flex;
    align-items: center;
    gap: 20px;
}

.navigation {
    flex: 1;
}
```

The navigation can use the available space between the other sections.

A nested Flexbox can then arrange the navigation items:

```css
.navigation {
    display: flex;
    justify-content: center;
    gap: 20px;
}
```

---

## Full Page Layout

A page can use a column-based Flexbox layout:

```css
.page {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}
```

The structure can be:

```text
┌────────────────────────────┐
│           Header           │
├────────────────────────────┤
│                            │
│          Content           │
│                            │
├────────────────────────────┤
│           Footer           │
└────────────────────────────┘
```

If the content should consume the remaining space:

```css
.content {
    flex: 1;
}
```

This allows the content section to grow and push the footer toward the bottom of the page.

---

## Header, Content, and Footer

A practical example:

```css
.page {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.header {
    flex-shrink: 0;
}

.content {
    flex: 1;
}

.footer {
    flex-shrink: 0;
}
```

Conceptually:

```text
┌──────────────────────────┐
│          Header          │
├──────────────────────────┤
│                          │
│                          │
│         Content          │
│                          │
│                          │
├──────────────────────────┤
│          Footer          │
└──────────────────────────┘
```

The content area uses the flexible remaining space.

---

## Wrapping Navigation Items

A navigation group can wrap:

```css
.navigation {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}
```

This allows items to move to additional flex lines when the available width becomes insufficient.

Conceptually:

```text
Wide:

Home  About  Services  Contact


Narrow:

Home  About
Services  Contact
```

The exact wrapping depends on the available space and item sizes.

---

## Form Layout

Flexbox can be used to arrange form controls vertically.

```css
.form {
    display: flex;
    flex-direction: column;
    gap: 16px;
}
```

Conceptually:

```text
Name
  ↓
Email
  ↓
Password
  ↓
Submit
```

This provides a simple and predictable structure for form controls.

---

## Form Row

Multiple controls can be placed in a row:

```css
.form-row {
    display: flex;
    gap: 16px;
}

.form-field {
    flex: 1;
}
```

Conceptually:

```text
┌──────────────────┬──────────────────┐
│      First       │       Last       │
└──────────────────┴──────────────────┘
```

The fields can share the available space.

---

## Common Layout Pattern

Many real-world layouts can be understood using a combination of:

```css
display: flex;
flex-direction;
justify-content;
align-items;
gap;
flex;
flex-wrap;
```

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: stretch;
    gap: 20px;
}
```

The exact combination depends on the design requirement.

---

## Choosing the Right Flexbox Properties

A useful way to approach a layout is:

### Step 1 — Create the Flex Container

```css
.container {
    display: flex;
}
```

### Step 2 — Choose the Direction

```css
flex-direction: row;
```

or:

```css
flex-direction: column;
```

### Step 3 — Control Main-Axis Distribution

```css
justify-content: center;
```

### Step 4 — Control Cross-Axis Alignment

```css
align-items: center;
```

### Step 5 — Add Spacing

```css
gap: 20px;
```

### Step 6 — Control Item Sizing

```css
flex: 1;
```

### Step 7 — Handle Wrapping When Needed

```css
flex-wrap: wrap;
```

This step-by-step approach makes complex layouts easier to build.

---

## Common Mistakes

### Using Too Much Positioning

Avoid using:

```css
position: absolute;
left: ...;
top: ...;
```

for layouts that can naturally be handled by Flexbox.

Flexbox is designed for distributing and aligning elements within a layout.

---

### Forgetting the Main Axis

Before using:

```css
justify-content
```

identify the main axis.

The main axis depends on:

```css
flex-direction;
```

---

### Making Every Element a Flex Container

Not every element needs:

```css
display: flex;
```

Use Flexbox where it provides a layout benefit.

Nested Flexbox is useful, but unnecessary nesting can make a stylesheet harder to understand.

---

### Using Flexbox for Every Layout

Flexbox is primarily designed for **one-dimensional layouts**.

If the layout needs simultaneous control of rows and columns, CSS Grid may be a better choice.

---

## Quick Reference

### Navigation

```css
.navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
```

### Equal Columns

```css
.container {
    display: flex;
    gap: 20px;
}

.column {
    flex: 1;
}
```

### Sidebar + Content

```css
.container {
    display: flex;
}

.sidebar {
    flex: 0 0 240px;
}

.content {
    flex: 1;
}
```

### Centering

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### Vertical Stack

```css
.container {
    display: flex;
    flex-direction: column;
    gap: 16px;
}
```

### Responsive Cards

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

### Full Page Layout

```css
.page {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.content {
    flex: 1;
}
```

---

> 💡 **Pro Tip:** When creating a Flexbox layout, first identify the layout direction, then decide how space should be distributed, how items should align, and finally how individual items should size themselves.

---

> 💡 **Remember:** Most practical Flexbox layouts are combinations of a few core properties: `flex-direction`, `justify-content`, `align-items`, `gap`, `flex`, and `flex-wrap`.

---

# Flexbox vs Grid

Both **Flexbox** and **CSS Grid** are modern CSS layout systems.

They can solve many of the same layout problems, but they are designed with different strengths.

The simplest distinction is:

```text
Flexbox
→ One-dimensional layout

Grid
→ Two-dimensional layout
```

---

## Flexbox

Flexbox is designed primarily for arranging items along **one axis at a time**.

The layout can be:

```css
flex-direction: row;
```

or:

```css
flex-direction: column;
```

Conceptually:

```text
Row:

Item → Item → Item → Item
```

or:

```text
Column:

Item
  ↓
Item
  ↓
Item
```

Flexbox is especially useful when the relationship between items is mainly along one direction.

---

## CSS Grid

CSS Grid is designed for **two-dimensional layouts**.

It can control:

```text
Rows
  +
Columns
```

at the same time.

Conceptually:

```text
┌───────┬───────┬───────┐
│       │       │       │
│   A   │   B   │   C   │
│       │       │       │
├───────┼───────┼───────┤
│       │       │       │
│   D   │   E   │   F   │
│       │       │       │
└───────┴───────┴───────┘
```

Grid is therefore well suited to layouts where both rows and columns matter.

---

## One-Dimensional vs Two-Dimensional

This is the most important difference.

### Flexbox

```text
One dimension

──────────────→
Main Axis
```

Flexbox primarily works along the main axis, while also providing cross-axis alignment.

### Grid

```text
Two dimensions

Rows
 ↓
┌───┬───┬───┐
│   │   │   │
├───┼───┼───┤
│   │   │   │
└───┴───┴───┘
      →
   Columns
```

Grid manages rows and columns together.

---

## Flexbox Is Content-Oriented

Flexbox is often useful when the size and arrangement of the content should influence the layout.

For example:

```css
.navbar {
    display: flex;
    align-items: center;
    gap: 20px;
}
```

This is a natural Flexbox use case because navigation items are arranged along one primary direction.

---

## Grid Is Layout-Oriented

Grid is often useful when you have a defined two-dimensional structure.

For example:

```text
┌────────────┬────────────┐
│   Header   │   Header   │
├────────────┼────────────┤
│  Sidebar   │   Main     │
├────────────┼────────────┤
│   Footer   │   Footer   │
└────────────┴────────────┘
```

This kind of row-and-column relationship is a natural Grid use case.

---

## Simple Comparison

| Feature | Flexbox | Grid |
|---------|---------|------|
| Primary dimension | One-dimensional | Two-dimensional |
| Main focus | Items along an axis | Rows and columns |
| Direction | Row or column | Rows and columns together |
| Alignment | Strong | Strong |
| Navigation | Excellent | Possible |
| Simple component layouts | Excellent | Excellent |
| Complex page layouts | Possible | Excellent |
| Card rows | Excellent | Excellent |
| Two-dimensional structure | Limited | Excellent |

---

## Flexbox Example

Suppose you want three buttons in a row:

```html
<div class="buttons">
    <button>Save</button>
    <button>Cancel</button>
    <button>Reset</button>
</div>
```

Flexbox is a natural choice:

```css
.buttons {
    display: flex;
    gap: 10px;
}
```

Conceptually:

```text
Save   Cancel   Reset
```

The primary concern is the horizontal arrangement.

---

## Grid Example

Suppose you want a dashboard:

```text
┌──────────┬──────────┬──────────┐
│          │          │          │
│    A     │    B     │    C     │
│          │          │          │
├──────────┼──────────┼──────────┤
│          │          │          │
│    D     │    E     │    F     │
│          │          │          │
└──────────┴──────────┴──────────┘
```

Both rows and columns are important.

This is a natural Grid use case.

---

## Flexbox for Navigation

Navigation is commonly one-dimensional:

```text
Home → About → Services → Contact
```

Therefore:

```css
.nav {
    display: flex;
    gap: 20px;
}
```

is a simple and readable solution.

---

## Grid for a Page Layout

A page can have:

```text
Header
────────────────────
Sidebar | Main
────────────────────
Footer
```

This involves relationships between both rows and columns.

Grid is often a better fit for this type of overall page structure.

---

## Flexbox for Component Layout

Flexbox is excellent for arranging the internal parts of a component.

For example:

```text
┌──────────────────────────┐
│ Icon   Title              │
│        Description        │
│                          │
│        Button             │
└──────────────────────────┘
```

You can use nested Flexbox containers to arrange these elements.

---

## Grid for Component Layout

Grid can also be used inside components.

For example, a dashboard card might have:

```text
┌────────────┬────────────┐
│    Icon    │   Status   │
├────────────┴────────────┤
│       Statistics        │
├─────────────────────────┤
│         Actions         │
└─────────────────────────┘
```

Because the design has multiple rows and columns, Grid may be more convenient.

---

## Flexbox and Grid Can Be Used Together

You do not have to choose only one layout system for an entire website.

They can be combined.

For example:

```text
Page
│
├── Header
│     ↓
│   Flexbox
│
├── Main
│     ↓
│    Grid
│
└── Footer
      ↓
    Flexbox
```

This is a common and practical approach.

---

## Example: Grid Page + Flexbox Navigation

HTML:

```html
<div class="page">
    <header class="header">
        <div class="logo">Logo</div>

        <nav class="nav">
            <a href="#">Home</a>
            <a href="#">About</a>
            <a href="#">Contact</a>
        </nav>
    </header>

    <main class="main">
        <aside class="sidebar">Sidebar</aside>
        <section class="content">Content</section>
    </main>
</div>
```

The header can use Flexbox:

```css
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
```

The navigation can use another Flexbox:

```css
.nav {
    display: flex;
    gap: 20px;
}
```

The main page structure could use Grid:

```text
Header
──────────────────────

Sidebar | Content

──────────────────────
```

This demonstrates that Flexbox and Grid can complement each other.

---

## Which One Should You Choose?

A useful decision process is:

### Use Flexbox When:

The layout is primarily along one direction.

Examples:

```text
Navigation
Button group
Toolbar
Form row
Horizontal card content
Vertical content stack
```

---

### Use Grid When:

The layout requires simultaneous row and column control.

Examples:

```text
Dashboard
Gallery
Page structure
Complex card grid
Two-dimensional application layout
```

---

## Flexbox Is Not "Better" Than Grid

It is incorrect to think:

```text
Flexbox > Grid
```

or:

```text
Grid > Flexbox
```

They solve different layout problems.

A better way to think about them is:

```text
Flexbox
→ Best tool for many one-dimensional layouts

Grid
→ Best tool for many two-dimensional layouts
```

---

## Can Flexbox Create a Grid?

Flexbox can create layouts that look like grids.

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}

.item {
    flex: 1 1 250px;
}
```

This can produce multiple rows of items.

However, Flexbox is still fundamentally managing **flex lines**, rather than providing the same explicit row-and-column model as Grid.

If precise row and column relationships are important, Grid is generally the more natural choice.

---

## Can Grid Create a One-Dimensional Layout?

Yes.

Grid can be used for simple layouts too.

However, just because something can be done with Grid does not mean Grid is always the simplest choice.

For example:

```css
.nav {
    display: flex;
    gap: 20px;
}
```

may be more straightforward than creating a Grid layout for a simple navigation row.

Choose the system that best matches the layout problem.

---

## Flexbox Alignment

Flexbox provides useful alignment properties such as:

```css
justify-content
align-items
align-content
align-self
```

These make it particularly convenient for aligning items along the main and cross axes.

---

## Grid Alignment

Grid also provides alignment capabilities, including:

```css
justify-items
align-items
justify-content
align-content
```

The exact property depends on whether you are aligning the grid items themselves or the grid tracks within the container.

---

## Flexbox vs Grid Mental Model

A useful mental model is:

```text
Flexbox:

"How should these items be arranged
along this axis?"
```

Grid:

```text
"Where should these items go
within this row-and-column structure?"
```

This is not a strict technical definition, but it is a useful starting point when choosing a layout system.

---

## Common Mistake

Do not choose Grid simply because the layout contains multiple elements.

The important question is:

```text
Is the layout primarily one-dimensional
or two-dimensional?
```

For example:

```text
A row of buttons
→ Flexbox

A dashboard with rows and columns
→ Grid
```

---

## Another Common Mistake

Do not force Flexbox to handle a complex two-dimensional layout when Grid provides a clearer structure.

For example, if you need specific relationships between:

```text
Rows
+
Columns
```

Grid may make the CSS easier to understand and maintain.

---

## Practical Rule

A useful starting rule is:

```text
One dimension
     ↓
Flexbox

Two dimensions
     ↓
Grid
```

Then consider the actual design requirements before making the final choice.

---

## Quick Reference

### Flexbox

```css
.container {
    display: flex;
}
```

Best suited for:

```text
One-dimensional layouts
Navigation
Toolbars
Button groups
Component internals
Simple rows and columns
```

### Grid

```css
.container {
    display: grid;
}
```

Best suited for:

```text
Two-dimensional layouts
Dashboards
Page structures
Galleries
Complex card layouts
```

### Both

You can combine them:

```text
Page
 ↓
Grid

Component
 ↓
Flexbox
```

or:

```text
Page
 ↓
Flexbox

Component
 ↓
Grid
```

Choose based on the layout requirements.

---

> 💡 **Pro Tip:** Don't memorize "Flexbox for rows, Grid for columns." That rule is too simplistic. Think in terms of **one-dimensional vs two-dimensional layout**.

---

> 💡 **Remember:** Flexbox is primarily a one-dimensional layout system, while Grid is a two-dimensional layout system. They can also be combined within the same page or component.

---

# Common Use Cases

Flexbox is widely used for arranging and aligning elements in web interfaces.

Its one-dimensional layout model makes it especially useful for components where elements need to be positioned in a row or column.

Common use cases include:

- Navigation bars
- Headers
- Footers
- Sidebars
- Button groups
- Forms
- Cards
- Toolbars
- Media objects
- Centered content
- Page sections
- Responsive components

---

## Navigation Bars

Navigation bars are one of the most common uses of Flexbox.

```css
.navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
```

A nested navigation group can also use Flexbox:

```css
.nav-links {
    display: flex;
    gap: 20px;
}
```

Conceptually:

```text
Logo          Home  About  Contact
```

Flexbox makes it easy to align the logo and navigation items.

---

## Website Headers

Headers often contain multiple groups of content:

```text
Logo | Navigation | Actions
```

Flexbox can arrange these groups:

```css
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
```

The header can then contain nested flex containers for individual groups.

---

## Footers

A footer may contain several sections:

```text
Company     Resources     Social
```

Flexbox can distribute them across the available space:

```css
.footer {
    display: flex;
    justify-content: space-between;
}
```

For smaller layouts, the direction can be changed:

```css
.footer {
    display: flex;
    flex-direction: column;
}
```

---

## Sidebars

A common page structure is:

```text
┌─────────────┬──────────────────────┐
│   Sidebar   │       Content        │
│             │                      │
│             │                      │
└─────────────┴──────────────────────┘
```

Flexbox can create this structure:

```css
.page {
    display: flex;
}

.sidebar {
    flex: 0 0 240px;
}

.content {
    flex: 1;
}
```

The sidebar has a fixed basis while the content uses the remaining space.

---

## Button Groups

Flexbox is useful for arranging related buttons.

```css
.button-group {
    display: flex;
    gap: 10px;
}
```

Example:

```text
[Cancel] [Save] [Delete]
```

The group can also be centered:

```css
.button-group {
    display: flex;
    justify-content: center;
    gap: 10px;
}
```

---

## Toolbars

Toolbars often contain several controls in a row.

```text
[Undo] [Redo] [Search] [Settings]
```

Flexbox can arrange these controls:

```css
.toolbar {
    display: flex;
    align-items: center;
    gap: 12px;
}
```

This keeps the controls aligned while maintaining consistent spacing.

---

## Forms

Flexbox can organize form controls vertically.

```css
.form {
    display: flex;
    flex-direction: column;
    gap: 16px;
}
```

Conceptually:

```text
Name
  ↓
Email
  ↓
Password
  ↓
Submit
```

This is useful for login forms, registration forms, search forms, and other vertical form layouts.

---

## Form Rows

Related form fields can be placed beside each other.

```css
.form-row {
    display: flex;
    gap: 16px;
}

.form-field {
    flex: 1;
}
```

Conceptually:

```text
┌───────────────┬───────────────┐
│ First Name    │ Last Name     │
└───────────────┴───────────────┘
```

The fields can share the available width.

---

## Cards

Flexbox can arrange cards horizontally:

```css
.cards {
    display: flex;
    gap: 20px;
}
```

Individual cards can share available space:

```css
.card {
    flex: 1;
}
```

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│ Card 1   │ Card 2   │ Card 3   │
└──────────┴──────────┴──────────┘
```

---

## Card Content

Flexbox can also organize the internal content of a card.

```css
.card {
    display: flex;
    flex-direction: column;
    gap: 12px;
}
```

This can create:

```text
Title
  ↓
Description
  ↓
Button
```

Nested Flexbox can therefore be useful at the component level.

---

## Keeping Actions at the Bottom

A card can use an auto margin to push an action toward the bottom.

```css
.card {
    display: flex;
    flex-direction: column;
}

.card-action {
    margin-top: auto;
}
```

Conceptually:

```text
┌────────────────────┐
│ Title              │
│                    │
│ Description        │
│                    │
│                    │
│       Button       │
└────────────────────┘
```

This is particularly useful when cards have different amounts of content.

---

## Media Objects

A common component contains an image next to text:

```text
┌──────┬─────────────────────┐
│Image │ Title               │
│      │ Description         │
└──────┴─────────────────────┘
```

Flexbox can create this layout:

```css
.media {
    display: flex;
    gap: 16px;
    align-items: center;
}
```

This pattern is useful for:

- User profiles
- Comments
- Notifications
- Articles
- Product previews

---

## Profile Components

A profile section might contain:

```text
[Avatar]  Name
          Role
```

Flexbox can align the avatar and information:

```css
.profile {
    display: flex;
    align-items: center;
    gap: 12px;
}
```

The text itself can use another Flexbox container:

```css
.profile-info {
    display: flex;
    flex-direction: column;
}
```

---

## Centered Login Screens

Flexbox is useful for centering a login form.

```css
.login-page {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Conceptually:

```text
┌────────────────────────────┐
│                            │
│       ┌───────────┐        │
│       │ Login     │        │
│       │           │        │
│       └───────────┘        │
│                            │
└────────────────────────────┘
```

---

## Hero Sections

A hero section often needs centered or split content.

For centered content:

```css
.hero {
    min-height: 500px;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

For image and text:

```css
.hero {
    display: flex;
    align-items: center;
    gap: 40px;
}
```

---

## Responsive Navigation

Flexbox can also help navigation adapt to smaller widths.

For example:

```css
.nav {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}
```

When there is not enough horizontal space, items can move onto additional flex lines.

A different layout can also be applied at a smaller screen size:

```css
.nav {
    display: flex;
}

@media (max-width: 600px) {
    .nav {
        flex-direction: column;
    }
}
```

---

## Responsive Card Groups

Card groups can use wrapping:

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

This allows cards to move onto additional lines when necessary.

---

## Search Bars

A search area can contain an input and button:

```text
┌────────────────────────────┬──────────┐
│ Search...                  │ Search   │
└────────────────────────────┴──────────┘
```

Flexbox can arrange them:

```css
.search {
    display: flex;
}

.search input {
    flex: 1;
}

.search button {
    flex-shrink: 0;
}
```

The input can grow while the button maintains its required size.

---

## Status Indicators

A small icon and text can be aligned with Flexbox.

```css
.status {
    display: flex;
    align-items: center;
    gap: 8px;
}
```

Conceptually:

```text
● Online
```

This pattern can be used for:

- Online status
- Notifications
- Labels
- Badges
- Metadata

---

## Breadcrumbs

Breadcrumb navigation is another simple one-dimensional layout.

```text
Home → Products → Details
```

Example:

```css
.breadcrumbs {
    display: flex;
    align-items: center;
    gap: 8px;
}
```

Each item is arranged along the main axis.

---

## Pagination

Pagination controls can be arranged using Flexbox:

```text
[Previous] [1] [2] [3] [Next]
```

Example:

```css
.pagination {
    display: flex;
    justify-content: center;
    gap: 8px;
}
```

---

## Loading Indicators

Flexbox can center a loading indicator inside a container:

```css
.loading {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 200px;
}
```

This is useful for loading states and empty states.

---

## Empty States

An empty state often contains an icon, message, and action.

```text
      Icon

   No Results

   [Try Again]
```

Flexbox can arrange the content vertically:

```css
.empty-state {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 16px;
}
```

---

## Dashboard Components

Flexbox is useful inside dashboard components even when the overall dashboard uses Grid.

For example:

```text
Dashboard
│
├── Grid
│
└── Card
     │
     └── Flexbox
```

The dashboard may use Grid for its two-dimensional structure while individual cards use Flexbox internally.

This combination is common in real-world interfaces.

---

## Responsive Component Layouts

Flexbox can change direction depending on available space.

For example:

```css
.component {
    display: flex;
    gap: 20px;
}
```

On smaller screens:

```css
@media (max-width: 600px) {
    .component {
        flex-direction: column;
    }
}
```

The same component can therefore have:

```text
Large screen:

Image | Content


Small screen:

Image
  ↓
Content
```

---

## Page Layouts

Flexbox can be used for larger page structures.

A common example is:

```css
.page {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.content {
    flex: 1;
}
```

This creates:

```text
Header
   ↓
Content
   ↓
Footer
```

with the content area taking the available remaining space.

---

## When Flexbox Is a Good Choice

Flexbox is a good choice when:

- Elements are primarily arranged in one direction.
- Content needs simple alignment.
- Items need to grow or shrink.
- Space needs to be distributed between items.
- Elements need to wrap when necessary.
- Components need flexible internal layouts.
- Items need easy horizontal or vertical centering.

---

## When Flexbox May Not Be the Best Choice

Flexbox may not be the best choice when the layout requires precise control over both rows and columns.

For example:

```text
┌─────┬─────┬─────┐
│     │     │     │
├─────┼─────┼─────┤
│     │     │     │
├─────┼─────┼─────┤
│     │     │     │
└─────┴─────┴─────┘
```

For this kind of two-dimensional structure, CSS Grid may provide a clearer solution.

---

## Practical Decision Guide

Use this mental checklist:

```text
Need one-dimensional alignment?
        ↓
      Flexbox
```

```text
Need two-dimensional row + column control?
        ↓
       Grid
```

```text
Need both?
        ↓
Combine Flexbox and Grid
```

---

## Quick Reference

| Use Case | Typical Flexbox Approach |
|----------|---------------------------|
| Navigation | `display: flex` |
| Header | `align-items` + `justify-content` |
| Footer | `display: flex` |
| Sidebar | Fixed basis + flexible content |
| Buttons | `gap` |
| Forms | `flex-direction: column` |
| Form rows | `flex: 1` |
| Cards | `flex` + `gap` |
| Media object | `align-items` + `gap` |
| Centered content | `justify-content` + `align-items` |
| Search bar | `flex: 1` |
| Pagination | `justify-content` + `gap` |
| Responsive cards | `flex-wrap` |
| Responsive components | `flex-direction` |
| Page structure | `flex-direction: column` |

---

> 💡 **Pro Tip:** Think of Flexbox as a tool for building flexible relationships between elements. Instead of manually positioning every element, describe how the elements should align, grow, shrink, wrap, and distribute available space.

---

> 💡 **Remember:** Flexbox is especially powerful for component-level layouts. A page can use Grid for its overall structure while individual components use Flexbox for their internal arrangement.

---

# Key Takeaways

- Flexbox is a **one-dimensional CSS layout system** used to arrange elements along a main axis.
- A flex container is created with:

```css
display: flex;
```

- The direct children of a flex container become **flex items**.
- `flex-direction` determines the main axis:

```css
flex-direction: row;
flex-direction: column;
```

- `justify-content` controls the distribution of flex items along the **main axis**.
- `align-items` controls alignment along the **cross axis**.
- `align-content` controls the distribution of **multiple flex lines**.
- `gap` creates consistent spacing between flex items.
- `flex-wrap` allows flex items to move onto additional lines.
- `flex-flow` is a shorthand for:

```css
flex-direction
flex-wrap
```

- Flex items can be individually controlled using:

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

- `flex-grow` controls how an item can receive available positive free space.
- `flex-shrink` controls how an item can shrink when there is insufficient space.
- `flex-basis` defines the initial main-size contribution of a flex item before remaining free space is distributed.
- `flex` is a shorthand for:

```css
flex-grow
flex-shrink
flex-basis
```

- A flex item can also become a **flex container**, allowing nested Flexbox layouts.
- The common two-axis centering pattern is:

```css
display: flex;
justify-content: center;
align-items: center;
```

- Flexbox is commonly used for:

```text
Navigation
Headers
Footers
Cards
Forms
Button groups
Toolbars
Sidebars
Media objects
Responsive components
```

- Flexbox works especially well for **component-level layouts** and other one-dimensional relationships.
- CSS Grid is generally better suited to layouts where **rows and columns need to be controlled together**.
- Flexbox and Grid can be combined in the same page or component.
- Flexbox properties should be understood in terms of the **main axis and cross axis**, rather than assuming that `justify-content` always means horizontal and `align-items` always means vertical.

---

## Flexbox Mental Model

A simple way to remember Flexbox is:

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

The container controls the arrangement of its direct children.

---

## Main Axis and Cross Axis

Remember:

```text
justify-content
        ↓
   Main Axis

align-items
        ↓
   Cross Axis
```

The physical direction depends on:

```css
flex-direction
```

For example:

```text
row
→ Main axis is horizontal

column
→ Main axis is vertical
```

---

## Flex Container vs Flex Item

A useful distinction is:

```text
Parent
  ↓
Flex Container
  ↓
Direct Children
  ↓
Flex Items
```

A flex item can also become another flex container:

```text
Outer Flex Container
        ↓
   Inner Flex Item
        ↓
 Inner Flex Container
        ↓
   Its Flex Items
```

This is the basis of nested Flexbox layouts.

---

## Most Important Properties

### Container Properties

```css
display
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
gap
```

### Item Properties

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

---

## Essential Flexbox Pattern

For a basic flexible row:

```css
.container {
    display: flex;
    gap: 20px;
}
```

For centered content:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

For a vertical layout:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

For wrapping items:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

---

## Flexbox vs Grid

Remember the basic distinction:

```text
Flexbox
→ One-dimensional

Grid
→ Two-dimensional
```

This is a useful starting point when deciding which CSS layout system to use.

---

> 💡 **Remember:** The most important Flexbox concepts are the flex container, flex items, main axis, cross axis, alignment, distribution, wrapping, and flexible sizing.

---

# References

- [MDN — CSS Flexible Box Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Flexible_box_layout)
  - Comprehensive reference for CSS Flexbox concepts and properties.

- [MDN — Basic Concepts of Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Flexible_box_layout/Basic_concepts_of_flexbox)
  - Covers flex containers, flex items, axes, and the basic Flexbox model.

- [MDN — Aligning Items in a Flex Container](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Flexible_box_layout/Mastering_wrapping_of_flex_items)
  - Useful for understanding alignment and wrapping behavior.

- [MDN — `flex` CSS Property](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/flex)
  - Reference for the `flex` shorthand property.

- [MDN — `justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/justify-content)
  - Reference for distributing items along the main axis.

- [MDN — `align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/align-items)
  - Reference for cross-axis alignment.

- [MDN — `gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/gap)
  - Reference for spacing between flex and grid items.

---

> 💡 **Note:** These references are provided for further learning and for verifying Flexbox behavior and property details.

---

# Quick Revision

## What Is Flexbox?

Flexbox is a **one-dimensional CSS layout system** used to arrange and align elements inside a container.

```css
.container {
    display: flex;
}
```

---

## Flex Container

An element becomes a flex container when:

```css
display: flex;
```

Its direct children become flex items.

```text
Flex Container
      │
      ├── Flex Item
      ├── Flex Item
      └── Flex Item
```

---

## Flex Direction

Controls the direction of the main axis.

```css
flex-direction: row;
```

```text
Item → Item → Item
```

```css
flex-direction: column;
```

```text
Item
  ↓
Item
  ↓
Item
```

Other values:

```css
row-reverse;
column-reverse;
```

---

## Main Axis and Cross Axis

The main axis depends on `flex-direction`.

```text
flex-direction: row

Main Axis   → → →
Cross Axis  ↓
```

```text
flex-direction: column

Main Axis   ↓
            ↓
            ↓

Cross Axis  →
```

---

## Flex Wrap

Controls whether flex items can move onto multiple lines.

```css
flex-wrap: nowrap;
```

Default behavior.

```css
flex-wrap: wrap;
```

Allows wrapping.

```css
flex-wrap: wrap-reverse;
```

Allows wrapping in the reverse cross-axis direction.

---

## Flex Flow

Shorthand for:

```css
flex-direction
flex-wrap
```

Example:

```css
flex-flow: row wrap;
```

---

## Justify Content

Controls how flex items are distributed along the **main axis**.

Common values:

```css
justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

---

## Align Items

Controls alignment along the **cross axis**.

Common values:

```css
align-items: stretch;
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

---

## Align Content

Controls the distribution of **multiple flex lines**.

It becomes useful when:

```css
flex-wrap: wrap;
```

is being used.

Common values include:

```css
align-content: flex-start;
align-content: center;
align-content: flex-end;
align-content: space-between;
align-content: space-around;
align-content: space-evenly;
align-content: stretch;
```

---

## Gap

Creates consistent spacing between flex items.

```css
gap: 20px;
```

Separate row and column gaps can be defined:

```css
row-gap: 20px;
column-gap: 30px;
```

Or together:

```css
gap: 20px 30px;
```

---

# Flex Item Properties

Flex item properties control individual flex items.

```css
order;
flex-grow;
flex-shrink;
flex-basis;
flex;
align-self;
```

---

## Order

Changes the visual order of flex items.

```css
.item {
    order: 2;
}
```

The default value is:

```css
order: 0;
```

Items are arranged according to their order value, with lower values appearing first.

---

## Flex Grow

Controls how an item can grow when extra space is available.

```css
.item {
    flex-grow: 1;
}
```

A larger grow factor means the item can receive a larger share of available free space.

---

## Flex Shrink

Controls how an item can shrink when there is insufficient space.

```css
.item {
    flex-shrink: 1;
}
```

The default value is:

```css
flex-shrink: 1;
```

---

## Flex Basis

Defines the initial main-size contribution of a flex item before remaining free space is distributed.

```css
.item {
    flex-basis: 200px;
}
```

---

## Flex Shorthand

Combines:

```css
flex-grow
flex-shrink
flex-basis
```

Example:

```css
.item {
    flex: 1 1 200px;
}
```

---

## Align Self

Overrides the container's `align-items` value for an individual flex item.

```css
.item {
    align-self: center;
}
```

---

# Centering With Flexbox

A common pattern for horizontal and vertical centering is:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

This is one of the most commonly used Flexbox patterns.

---

# Common Flexbox Patterns

### Horizontal Layout

```css
.container {
    display: flex;
}
```

### Vertical Layout

```css
.container {
    display: flex;
    flex-direction: column;
}
```

### Centering

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### Space Between

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

### Wrapping

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

### Flexible Items

```css
.item {
    flex: 1;
}
```

### Consistent Spacing

```css
.container {
    display: flex;
    gap: 20px;
}
```

---

# Common Use Cases

Flexbox is commonly used for:

```text
Navigation bars
Headers
Footers
Sidebars
Button groups
Toolbars
Forms
Cards
Media objects
Search bars
Pagination
Centered content
Responsive components
```

---

# Flexbox vs Grid

The basic distinction:

```text
Flexbox
→ One-dimensional layout

Grid
→ Two-dimensional layout
```

Use Flexbox when the primary relationship is along one axis.

Use Grid when both rows and columns need to be controlled together.

They can also be combined.

---

# Important Mental Model

When working with Flexbox, think in this order:

```text
1. Flex Container
       ↓
2. Flex Direction
       ↓
3. Main Axis / Cross Axis
       ↓
4. Item Distribution
       ↓
5. Item Alignment
       ↓
6. Item Sizing
       ↓
7. Wrapping if needed
```

---

# Most Important Properties

### Container

```css
display
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
gap
```

### Items

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

---

> 💡 **Remember:** If you understand the **main axis, cross axis, container properties, and item properties**, most Flexbox layouts become much easier to reason about.

---

# Best Practices

Following good practices when using Flexbox makes layouts easier to understand, maintain, maintain, and debug.

---

## Use Flexbox for One-Dimensional Layouts

Use Flexbox when elements primarily need to be arranged along one direction.

For example:

```text
Logo → Navigation → Actions
```

or:

```text
Title
  ↓
Description
  ↓
Button
```

For layouts that require explicit control over both rows and columns, consider CSS Grid.

---

## Start With the Container

When creating a Flexbox layout, first identify the element that should control the arrangement.

Then apply:

```css
display: flex;
```

For example:

```css
.navbar {
    display: flex;
}
```

After that, decide the direction, alignment, spacing, and item sizing.

---

## Choose the Direction Intentionally

Do not rely on the default direction without considering the layout requirement.

For a horizontal layout:

```css
.container {
    display: flex;
    flex-direction: row;
}
```

For a vertical layout:

```css
.container {
    display: flex;
    flex-direction: column;
}
```

This makes the intended layout easier to understand.

---

## Think in Terms of Axes

Always consider:

```text
Main Axis
Cross Axis
```

Then choose properties accordingly.

```css
justify-content
```

works along the main axis.

```css
align-items
```

works along the cross axis.

This prevents confusion when changing:

```css
flex-direction
```

---

## Prefer `gap` for Spacing

Use:

```css
gap: 20px;
```

when you need consistent spacing between flex items.

For example:

```css
.container {
    display: flex;
    gap: 20px;
}
```

This is usually clearer than adding margins to individual items.

---

## Avoid Unnecessary Margins for Layout Spacing

Instead of:

```css
.item {
    margin-right: 20px;
}
```

consider:

```css
.container {
    display: flex;
    gap: 20px;
}
```

Using `gap` keeps the spacing responsibility on the container.

It also avoids special handling for the final item.

---

## Use `flex` When Items Need to Share Space

When several items should share available space, `flex` can provide a simple solution.

```css
.column {
    flex: 1;
}
```

For example:

```text
┌──────────┬──────────┬──────────┐
│ Column 1 │ Column 2 │ Column 3 │
└──────────┴──────────┴──────────┘
```

---

## Use `flex-basis` When an Initial Size Matters

If an item should start from a particular main size:

```css
.item {
    flex-basis: 250px;
}
```

This can be useful for flexible cards, sidebars, and responsive components.

---

## Use `flex-shrink: 0` Carefully

If an item should not shrink:

```css
.sidebar {
    flex-shrink: 0;
}
```

This can be useful for fixed-width controls or sidebars.

However, preventing shrinking can also create overflow on smaller containers.

Use it only when the design requires that behavior.

---

## Use Wrapping for Flexible Rows

When items may not fit on one line:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

This is useful for:

- Card groups
- Navigation links
- Tags
- Buttons
- Responsive components

---

## Give Wrapped Items a Sensible Basis

For responsive cards:

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

The basis provides an initial size while allowing the item to grow or shrink.

---

## Avoid Excessive Fixed Widths

Avoid building a flexible layout around many rigid widths such as:

```css
.item {
    width: 300px;
}
```

when the design needs to adapt to different container sizes.

Flex properties can often provide a more flexible solution:

```css
.item {
    flex: 1 1 250px;
}
```

---

## Use `min-width` When Content Can Cause Overflow

Flex items can sometimes become narrower than expected.

For content that should be allowed to shrink properly, this pattern can be useful:

```css
.item {
    min-width: 0;
}
```

This is particularly relevant when a flex item contains long text or other content that can create overflow.

---

## Avoid Using Flexbox for Every Layout

Flexbox is powerful, but it should not automatically be used for every layout.

Use it when the layout relationship is primarily one-dimensional.

For example:

```text
Navigation
→ Flexbox
```

For a complex row-and-column structure:

```text
Dashboard
→ Grid may be more appropriate
```

Choose the layout system that matches the problem.

---

## Combine Flexbox and Grid When Appropriate

Flexbox and Grid work well together.

For example:

```text
Page
 ↓
Grid
 ↓
Cards
 ↓
Flexbox
```

Grid can manage the overall page structure while Flexbox manages the internal layout of individual components.

---

## Keep Nested Flexbox Meaningful

Nested Flexbox containers are useful when different groups need different layout rules.

For example:

```text
Header
│
├── Logo
│
└── Navigation
     │
     ├── Home
     ├── About
     └── Contact
```

The header and navigation can each have their own Flexbox behavior.

Avoid adding `display: flex` to elements when it does not provide a meaningful layout benefit.

---

## Use `align-items` Instead of Manual Positioning

If items need to be aligned along the cross axis, prefer:

```css
align-items: center;
```

instead of manually adjusting their position with:

```css
position: relative;
top: ...;
```

Flexbox alignment is generally more predictable for this type of layout.

---

## Use `justify-content` for Main-Axis Distribution

When items need to be distributed along the main axis, use:

```css
justify-content
```

For example:

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

This is clearer than manually positioning each item.

---

## Avoid Absolute Positioning for Normal Layout

Do not use absolute positioning simply to create a layout that Flexbox can naturally handle.

For example, avoid using:

```css
position: absolute;
left: 100px;
```

to manually position navigation items.

Prefer:

```css
display: flex;
gap: 20px;
```

when the elements belong to a normal flexible layout.

Absolute positioning still has legitimate uses, but it should not replace normal layout systems unnecessarily.

---

## Keep Alignment Rules on the Correct Element

Remember that container properties and item properties have different responsibilities.

### Container

```css
justify-content
align-items
align-content
gap
```

### Item

```css
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```

Putting a property on the wrong element can make the layout difficult to debug.

---

## Prefer Simple Flex Shorthand When Appropriate

When the intended behavior is simply:

```css
flex: 1;
```

use it instead of unnecessarily specifying multiple properties.

For example:

```css
.item {
    flex: 1;
}
```

is often easier to read than:

```css
.item {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 0%;
}
```

When you need precise control, however, the individual properties can be specified explicitly.

---

## Make Responsive Behavior Intentional

Do not assume that a desktop Flexbox layout will automatically produce the desired mobile layout.

Consider whether the layout should:

```text
Stay in a row
       ↓
Wrap
       ↓
Change to a column
```

For example:

```css
.component {
    display: flex;
    gap: 20px;
}

@media (max-width: 600px) {
    .component {
        flex-direction: column;
    }
}
```

---

## Test Different Content Sizes

A Flexbox layout should not only work with ideal content.

Test with:

- Short text
- Long text
- Different button labels
- Different image sizes
- Narrow containers
- Wide containers
- Multiple flex items

This helps reveal unexpected shrinking, wrapping, or overflow.

---

## Test Different Screen Sizes

Responsive layouts should be tested at different viewport sizes.

Pay particular attention to:

```text
Navigation
Cards
Forms
Sidebars
Buttons
Long text
Wrapped content
```

A layout that works at one width may need additional rules at another width.

---

## Use Meaningful Class Names

Prefer descriptive class names such as:

```css
.navbar
.card-list
.button-group
.sidebar
.content
```

rather than names based only on visual appearance:

```css
.left-box
.blue-row
.big-container
```

Meaningful names make the layout easier to maintain.

---

## Avoid Overusing `order`

The `order` property can visually rearrange flex items:

```css
.item {
    order: 2;
}
```

Use it intentionally.

If the visual order differs significantly from the document order, consider whether the HTML structure itself should be improved.

This is especially important for accessibility and logical navigation.

---

## Consider Accessibility

CSS Flexbox changes visual layout, but it does not automatically change the semantic or logical order of the HTML.

For example:

```css
.item {
    order: -1;
}
```

changes visual placement, but the underlying document structure remains important.

Keep semantic HTML and logical content order in mind.

---

## Do Not Depend on Visual Order for Meaning

If content must be understood in a specific sequence, the HTML should normally reflect that sequence.

Use Flexbox for presentation rather than relying on `order` to completely redefine the meaning of the content.

---

## Use Auto Margins When They Solve the Layout Clearly

An auto margin can consume available free space in a flex layout.

For example:

```css
.button {
    margin-left: auto;
}
```

This can push an item toward the opposite side of a row.

Conceptually:

```text
Content                 Button
──────────────────────────────→
```

This can be a simple alternative to more complicated alignment rules in certain layouts.

---

## Keep Flexbox Rules Close to Their Purpose

A useful organization is:

```text
Container
├── Direction
├── Wrapping
├── Alignment
├── Spacing
└── Item sizing
```

This makes the layout easier to reason about and maintain.

---

## Use Developer Tools

Browser developer tools are extremely useful for debugging Flexbox.

They can help you inspect:

- Flex containers
- Flex items
- Main axis
- Cross axis
- Item sizes
- Alignment
- Wrapping
- Free space

When a Flexbox layout behaves unexpectedly, inspect the container and its direct children first.

---

## Start Simple

Do not immediately add many Flexbox properties.

Start with:

```css
.container {
    display: flex;
}
```

Then add only what is required:

```css
flex-direction
justify-content
align-items
gap
flex-wrap
```

Finally, add item-specific properties if needed.

This makes debugging much easier.

---

## A Practical Workflow

When building a Flexbox layout:

```text
1. Identify the container
        ↓
2. Add display: flex
        ↓
3. Choose the direction
        ↓
4. Identify the main axis
        ↓
5. Set alignment
        ↓
6. Add spacing
        ↓
7. Control item sizing
        ↓
8. Add wrapping if required
        ↓
9. Test responsive behavior
        ↓
10. Test different content sizes
```

---

## Recommended Pattern

A clean starting point for many layouts is:

```css
.container {
    display: flex;
    align-items: center;
    gap: 20px;
}
```

Then add only the properties required by the design.

For example:

```css
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
}
```

---

## Best Practice Checklist

Before considering a Flexbox layout complete, ask:

```text
☑ Is Flexbox appropriate for this layout?
☑ Is the correct flex container selected?
☑ Is the direction intentional?
☑ Do I understand the main and cross axes?
☑ Is spacing handled consistently?
☑ Do items need to grow or shrink?
☑ Do items need to wrap?
☑ Could Grid be more appropriate?
☑ Does the layout work with different content sizes?
☑ Does it work at different viewport sizes?
☑ Is the HTML order logical?
☑ Have unnecessary positioning rules been avoided?
```

---

> 💡 **Pro Tip:** Start with the simplest Flexbox solution possible. Add direction, alignment, spacing, sizing, and wrapping only when the layout actually needs them.

---

> 💡 **Remember:** Good Flexbox code is not about using many Flexbox properties. It is about choosing the right properties for the layout problem and keeping the resulting CSS simple and predictable.

---

# Common Mistakes

Flexbox is powerful, but some common mistakes can lead to unexpected layout behavior.

Understanding these mistakes makes Flexbox easier to debug and use correctly.

---

## Forgetting `display: flex`

Flexbox properties only work when the parent is actually a flex container.

Incorrect:

```css
.container {
    justify-content: center;
}
```

Correct:

```css
.container {
    display: flex;
    justify-content: center;
}
```

Without:

```css
display: flex;
```

the element does not establish a flex formatting context.

---

## Confusing the Main Axis and Cross Axis

A common mistake is assuming:

```text
justify-content → horizontal
align-items     → vertical
```

This is not always true.

The direction depends on:

```css
flex-direction;
```

With:

```css
flex-direction: row;
```

the main axis is horizontal.

With:

```css
flex-direction: column;
```

the main axis is vertical.

Remember:

```text
justify-content
→ Main Axis

align-items
→ Cross Axis
```

---

## Using `align-content` Instead of `align-items`

These properties have different purposes.

`align-items` controls the alignment of flex items along the cross axis.

```css
.container {
    display: flex;
    align-items: center;
}
```

`align-content` controls the distribution of multiple flex lines.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: center;
}
```

If there is only one flex line, `align-content` generally does not provide the effect people expect.

---

## Forgetting That `flex-wrap` Is Needed

Flex items do not automatically wrap onto multiple lines.

The default is:

```css
flex-wrap: nowrap;
```

If wrapping is required:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

Without wrapping, items may shrink or overflow depending on the layout.

---

## Using `width` When Flexible Sizing Is Needed

A rigid width can make a layout less flexible.

For example:

```css
.card {
    width: 300px;
}
```

may not behave as desired in a flexible responsive layout.

Depending on the requirement, a flexible basis can be more appropriate:

```css
.card {
    flex: 1 1 250px;
}
```

The correct choice depends on the design.

---

## Using `flex: 1` Without Understanding It

This pattern is common:

```css
.item {
    flex: 1;
}
```

But it should not be treated as a magic "make equal width" rule without understanding what it does.

The `flex` shorthand controls:

```text
flex-grow
flex-shrink
flex-basis
```

Understanding these properties helps explain the resulting sizes.

---

## Setting `flex-shrink: 0` Everywhere

Preventing an item from shrinking can be useful:

```css
.sidebar {
    flex-shrink: 0;
}
```

But using it unnecessarily can cause overflow.

For example, a row of fixed-size items may become wider than its container.

Use:

```css
flex-shrink: 0;
```

only when the item genuinely should not shrink.

---

## Using Too Many Fixed Sizes

A layout such as:

```css
.item {
    width: 300px;
    height: 200px;
}
```

can become difficult to adapt to different container sizes.

Flexbox is intended to help distribute available space.

Consider whether flexible sizing is more appropriate.

---

## Forgetting `min-width: 0`

A flex item containing long content can sometimes refuse to shrink as expected.

For example:

```css
.content {
    min-width: 0;
}
```

can allow the flex item to shrink within its container.

This is particularly useful when the item contains:

- Long text
- Long URLs
- Code
- Wide content

---

## Expecting `margin: auto` to Behave Like Normal Margins

In a flex container, an auto margin can absorb available free space.

For example:

```css
.button {
    margin-left: auto;
}
```

can push the button toward the opposite side of a row.

This is useful, but it should be understood as a Flexbox free-space mechanism rather than ordinary fixed spacing.

---

## Using Too Many Alignment Properties

Adding every available alignment property does not automatically improve a layout.

For example:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    align-content: space-between;
    gap: 20px;
}
```

Some of these properties may not be relevant to the actual layout.

Start with the minimum required properties.

---

## Using Absolute Positioning Instead of Flexbox

A common mistake is manually positioning elements that could naturally be arranged with Flexbox.

For example:

```css
.item {
    position: absolute;
    left: 100px;
}
```

If the elements are part of a normal layout, consider:

```css
.container {
    display: flex;
    gap: 20px;
}
```

Absolute positioning still has valid use cases, but it should not replace Flexbox unnecessarily.

---

## Changing `flex-direction` Without Reconsidering Alignment

Changing:

```css
flex-direction: row;
```

to:

```css
flex-direction: column;
```

changes the main axis.

Therefore, existing alignment rules may produce a different visual result.

For example:

```css
justify-content: center;
```

will operate along the new main axis.

Always reconsider the axes when changing the direction.

---

## Confusing `align-items` and `align-self`

`align-items` is a container property:

```css
.container {
    display: flex;
    align-items: center;
}
```

`align-self` is an item property:

```css
.item {
    align-self: flex-end;
}
```

Use `align-self` when one particular item needs different cross-axis alignment.

---

## Forgetting That Flex Properties Apply to Direct Children

Flex container properties arrange the container's direct children.

For example:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

The `.item` is the flex item.

The `<span>` is not a flex item of `.container`.

If the span needs Flexbox behavior, its own parent must become a flex container.

---

## Making Every Nested Element a Flex Container

Nested Flexbox is useful, but unnecessary nesting can make CSS harder to understand.

Avoid:

```css
div {
    display: flex;
}
```

just because Flexbox is available.

Instead, apply Flexbox to elements that actually need to control the layout of their children.

---

## Ignoring Content Size

A Flexbox layout may appear correct with short text but fail with longer content.

For example:

```text
Short title
```

may fit perfectly, while:

```text
A very long title that requires significantly more space
```

may cause unexpected shrinking or overflow.

Test realistic content.

---

## Ignoring Responsive Behavior

A layout that works on a wide screen may not work on a narrow screen.

For example:

```text
Desktop:

Image | Content
```

may need to become:

```text
Mobile:

Image
  ↓
Content
```

Use wrapping or responsive rules when necessary.

---

## Overusing `order`

The `order` property changes visual ordering:

```css
.item {
    order: -1;
}
```

However, it does not replace the logical order of the HTML.

Avoid using `order` excessively to compensate for poorly structured markup.

Keep the document structure logical whenever possible.

---

## Depending on Visual Order for Meaning

If the content has a meaningful sequence, the HTML should generally reflect that sequence.

Flexbox is primarily a layout and presentation tool.

Do not rely on CSS ordering to completely redefine the logical structure of content.

---

## Using Flexbox for a Two-Dimensional Problem

Flexbox can create wrapped layouts:

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

But if the design requires precise relationships between rows and columns, CSS Grid may be a better choice.

For example:

```text
┌─────┬─────┬─────┐
│  A  │  B  │  C  │
├─────┼─────┼─────┤
│  D  │  E  │  F  │
└─────┴─────┴─────┘
```

If both dimensions are important, consider Grid.

---

## Assuming Flexbox Automatically Makes Everything Responsive

Flexbox provides flexible layout behavior, but it does not automatically solve every responsive design problem.

You may still need:

```css
flex-wrap
```

or:

```css
@media
```

or:

```css
min-width
max-width
```

depending on the layout.

---

## Forgetting `gap` Is Not the Same as Margins

`gap` creates spacing between flex items.

For example:

```css
.container {
    gap: 20px;
}
```

It does not create the same kind of outer spacing around the container.

If the container itself needs space from surrounding elements, use appropriate container margins or padding.

---

## Relying on `space-between` for All Spacing

This:

```css
justify-content: space-between;
```

distributes available free space between items.

It is not always a replacement for:

```css
gap
```

If you simply need consistent spacing between items:

```css
.container {
    display: flex;
    gap: 20px;
}
```

may communicate the intent more clearly.

---

## Forgetting to Inspect the Parent

When a Flexbox item behaves unexpectedly, developers sometimes modify the item immediately.

First inspect the parent.

Ask:

```text
Is the parent a flex container?
What is its flex-direction?
Is wrapping enabled?
What is its available size?
How are items being aligned?
```

Many Flexbox problems originate from the container rather than the item.

---

## Debugging Only the Child

If an item appears in the wrong position, check:

```text
Parent
 ↓
display
 ↓
flex-direction
 ↓
justify-content
 ↓
align-items
 ↓
gap
 ↓
child sizing
```

Do not immediately add random margins or positioning rules to the child.

---

## Adding Random Margins to Fix Alignment

A common temporary fix is:

```css
.item {
    margin-left: 13px;
    margin-top: 7px;
}
```

This may visually fix one situation but create problems when the container size changes.

Prefer solving the actual layout problem with Flexbox properties when appropriate.

---

## Ignoring Overflow

If items cannot shrink or wrap correctly, they may overflow the container.

Check:

```css
flex-wrap
flex-shrink
min-width
max-width
```

and inspect the content that is causing the overflow.

---

## Common Debugging Checklist

When a Flexbox layout does not behave as expected, check:

```text
☑ Is display: flex applied?
☑ Is the correct parent selected?
☑ What is flex-direction?
☑ What is the main axis?
☑ What is the cross axis?
☑ Is flex-wrap enabled if needed?
☑ Is justify-content being applied on the expected axis?
☑ Is align-items being applied on the expected axis?
☑ Is align-content actually relevant?
☑ Is gap being used correctly?
☑ Are flex items growing or shrinking?
☑ Is flex-basis affecting the initial size?
☑ Is min-width causing overflow?
☑ Is the content itself too large?
☑ Would Grid be more appropriate?
```

---

> 💡 **Pro Tip:** When Flexbox behaves unexpectedly, don't immediately add margins, offsets, or absolute positioning. First check the container, axes, alignment, wrapping, and item sizing.

---

> 💡 **Remember:** Most Flexbox problems become easier to diagnose when you work from the **parent container → axes → alignment → spacing → item sizing → content**.