## Table of Contents

- [Introduction](#introduction)
- [Grid Container](#grid-container)
- [Grid Items](#grid-items)
- [Grid Columns](#grid-columns)
- [Grid Rows](#grid-rows)
- [Grid Tracks](#grid-tracks)
- [Grid Lines](#grid-lines)
- [Grid Cells](#grid-cells)
- [Grid Template Columns](#grid-template-columns)
- [Grid Template Rows](#grid-template-rows)
- [The `fr` Unit](#the-fr-unit)
- [`repeat()` Function](#repeat-function)
- [`minmax()` Function](#minmax-function)
- [`gap`](#gap)
- [Grid Column](#grid-column)
- [Grid Row](#grid-row)
- [Grid Areas](#grid-areas)
- [Grid Alignment](#grid-alignment)
- [Auto Placement](#auto-placement)
- [Explicit vs Implicit Grid](#explicit-vs-implicit-grid)
- [Responsive Grid](#responsive-grid)
- [Practical Examples](#practical-examples)
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

CSS Grid is a **two-dimensional layout system** in CSS that allows elements to be arranged into rows and columns.

It is designed for layouts where you need control over both:

- Horizontal placement
- Vertical placement

### Basic Example

A Grid layout starts by making an element a grid container:

```css
.container {
    display: grid;
}
```

For example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
    <div>Item 4</div>
</div>
```

Once:

```css
.container {
    display: grid;
}
```

is applied, the `.container` becomes a **grid container** and its direct children become **grid items**.

### Two-Dimensional Layout

CSS Grid works with two dimensions:

```text
              Columns
        ↓        ↓        ↓
      ┌────────┬────────┐
Rows  │ Item 1 │ Item 2 │
  ↓   ├────────┼────────┤
      │ Item 3 │ Item 4 │
      └────────┴────────┘
```

The columns control the horizontal structure, while the rows control the vertical structure.

### Grid Compared With Flexbox

Flexbox is primarily a **one-dimensional** layout system.

It generally works along one main direction:

```text
Flexbox

Item 1 → Item 2 → Item 3 → Item 4
```

CSS Grid is designed for two-dimensional layouts:

```text
Grid

┌────────┬────────┐
│ Item 1 │ Item 2 │
├────────┼────────┤
│ Item 3 │ Item 4 │
└────────┴────────┘
```

This makes Grid particularly useful for layouts involving both rows and columns.

### Common Uses of CSS Grid

CSS Grid can be used for:

- Website page layouts
- Card layouts
- Image galleries
- Dashboard layouts
- Product grids
- Application interfaces
- Responsive layouts

For example, a simple card layout can be created with:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

This creates three columns of equal flexible width.

### Grid Terminology

CSS Grid introduces several important terms:

```text
Grid Container
      ↓
Grid Items
      ↓
Grid Lines
      ↓
Grid Tracks
      ↓
Grid Cells
      ↓
Grid Areas
```

These concepts describe different parts of a grid.

### Grid Container

The element with:

```css
display: grid;
```

is called the **grid container**.

Example:

```css
.container {
    display: grid;
}
```

### Grid Items

The direct children of a grid container are called **grid items**.

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
</div>
```

Here:

```text
.container
    ↓
Grid Container

<div>Item 1</div>
    ↓
Grid Item

<div>Item 2</div>
    ↓
Grid Item
```

### Defining Columns

A grid becomes more useful when columns are explicitly defined.

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
}
```

This creates two columns:

```text
┌────────────┬────────────┐
│            │            │
│  Column 1  │  Column 2  │
│            │            │
└────────────┴────────────┘
```

### Defining Rows

Rows can also be defined:

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
    grid-template-rows: 100px 100px;
}
```

This creates a two-column and two-row grid.

```text
┌────────────┬────────────┐
│            │            │  100px
├────────────┼────────────┤
│            │            │  100px
└────────────┴────────────┘
   200px        200px
```

### Why Grid Is Powerful

CSS Grid separates the layout structure from the individual content items.

Instead of manually positioning every element, you can define the grid structure:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

The browser then places the grid items according to the defined grid.

### Basic Mental Model

Think of CSS Grid as creating a framework:

```text
Define Grid
    ↓
Create Columns and Rows
    ↓
Place Grid Items
    ↓
Control Spacing
    ↓
Control Alignment
    ↓
Create Responsive Layout
```

> 💡 **Remember:** CSS Grid is a two-dimensional CSS layout system designed to control both rows and columns. It is especially useful for structured layouts where horizontal and vertical placement need to work together.