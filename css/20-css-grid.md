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

---

## Grid Container

A **grid container** is an element whose `display` property is set to `grid` or `inline-grid`.

Example:

```css
.container {
    display: grid;
}
```

The element with `display: grid` becomes the grid container, and its direct children become grid items.

### Basic Example

HTML:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

CSS:

```css
.container {
    display: grid;
}
```

The structure is:

```text
.container
     ↓
Grid Container
     │
     ├── Item 1 → Grid Item
     ├── Item 2 → Grid Item
     └── Item 3 → Grid Item
```

### `display: grid`

The most common way to create a grid container is:

```css
.container {
    display: grid;
}
```

This creates a block-level grid container.

For example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
</div>
```

```css
.container {
    display: grid;
}
```

The `.container` participates in normal block layout, while its direct children participate in grid layout.

### `display: inline-grid`

CSS also provides:

```css
.container {
    display: inline-grid;
}
```

`inline-grid` creates an inline-level grid container.

For example:

```css
.container {
    display: inline-grid;
}
```

The grid itself behaves like an inline-level element, while its direct children are still laid out using CSS Grid.

### Grid Container vs Grid Items

Consider:

```html
<div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
</div>
```

```css
.container {
    display: grid;
}
```

Here:

```text
.container
     ↓
Grid Container

.item
.item
     ↓
Grid Items
```

Only the **direct children** automatically become grid items.

### Defining Columns on the Container

The grid structure is normally defined on the grid container.

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
}
```

This creates two columns.

```text
┌────────────┬────────────┐
│   Item     │   Item     │
├────────────┼────────────┤
│   Item     │   Item     │
└────────────┴────────────┘
```

### Defining Rows on the Container

Rows can also be defined:

```css
.container {
    display: grid;
    grid-template-columns: 200px 200px;
    grid-template-rows: 100px 100px;
}
```

The container now has two explicitly defined columns and two explicitly defined rows.

### Grid Container Controls the Layout

Many Grid properties are applied to the grid container.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
}
```

Here:

```text
display
    ↓
Creates the grid

grid-template-columns
    ↓
Defines the columns

gap
    ↓
Controls spacing between grid items
```

### Container With Four Items

HTML:

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
</div>
```

CSS:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The browser can place the items into the available columns:

```text
┌──────────┬──────────┐
│    1     │    2     │
├──────────┼──────────┤
│    3     │    4     │
└──────────┴──────────┘
```

### Grid Container With Three Columns

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

This creates three flexible columns:

```text
┌────────┬────────┬────────┐
│ Item 1 │ Item 2 │ Item 3 │
├────────┼────────┼────────┤
│ Item 4 │ Item 5 │ Item 6 │
└────────┴────────┴────────┘
```

### Grid Container and Available Space

The grid container provides the available space in which the grid tracks are created.

For example:

```css
.container {
    width: 600px;
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The two `1fr` columns can divide the available grid space equally.

Conceptually:

```text
600px
  ↓
┌──────────────────────────────┐
│       300px      │   300px   │
└──────────────────────────────┘
```

### Grid Container Can Be Responsive

A grid container can use media queries:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

The same container can therefore use three columns on larger screens and one column on smaller screens.

### Important Point

The grid container is where the overall grid structure is established.

Common container properties include:

```css
.container {
    display: grid;
    grid-template-columns: ...;
    grid-template-rows: ...;
    gap: ...;
}
```

Later sections will cover these properties individually.

> 💡 **Remember:** A grid container is the element that establishes a CSS Grid formatting context. Its direct children become grid items and can then be arranged into rows and columns.

---

## Grid Items

A **grid item** is an element that is a direct child of a grid container.

A grid item participates in the CSS Grid layout created by its parent.

### Basic Example

HTML:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

CSS:

```css
.container {
    display: grid;
}
```

The structure is:

```text
.container
     ↓
Grid Container
     │
     ├── Item 1 → Grid Item
     ├── Item 2 → Grid Item
     └── Item 3 → Grid Item
```

### Direct Children Become Grid Items

Only the **direct children** of a grid container automatically become grid items.

For example:

```html
<div class="container">
    <div class="item">
        <span>Text</span>
    </div>
</div>
```

Here:

```text
.container
    ↓
Grid Container
    ↓
.item
    ↓
Grid Item
    ↓
<span>
    ↓
Not a grid item
```

The `<span>` is a descendant of the grid container, but it is not a direct child.

### Basic Grid Items

Consider:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

HTML:

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
</div>
```

The four direct children become grid items:

```text
┌──────────┬──────────┐
│    1     │    2     │
├──────────┼──────────┤
│    3     │    4     │
└──────────┴──────────┘
```

### Grid Items Can Contain Other Elements

A grid item can contain its own content.

```html
<div class="container">
    <article class="card">
        <h2>Title</h2>
        <p>Description</p>
    </article>
</div>
```

Here:

```text
.container
    ↓
Grid Container

.card
    ↓
Grid Item

<h2>
<p>
    ↓
Content inside the grid item
```

The internal elements do not automatically become items of the outer grid.

### Grid Item Placement

By default, Grid automatically places items into available grid cells.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

With four items:

```text
Item 1 → Cell 1
Item 2 → Cell 2
Item 3 → Cell 3
Item 4 → Cell 4
```

Result:

```text
┌──────────┬──────────┐
│ Item 1   │ Item 2   │
├──────────┼──────────┤
│ Item 3   │ Item 4   │
└──────────┴──────────┘
```

This automatic behavior is called **auto-placement** and will be covered later.

### Styling Individual Grid Items

Grid items can have their own styles.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}

.item {
    padding: 20px;
    background-color: lightblue;
}
```

The container controls the grid layout, while the item can control its own appearance.

### Placing an Item Across Columns

A grid item can span multiple columns.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.item:first-child {
    grid-column: span 2;
}
```

The first item occupies two columns:

```text
┌──────────────────────┬──────────┐
│       Item 1         │  Item 2  │
│      2 columns       │          │
├──────────┬───────────┴──────────┤
│ Item 3   │ Item 4                │
└──────────┴───────────────────────┘
```

The `grid-column` property will be covered in detail later.

### Placing an Item Across Rows

Grid items can also span multiple rows.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}

.item:first-child {
    grid-row: span 2;
}
```

The first item occupies two rows.

```text
┌──────────┬──────────┐
│          │  Item 2  │
│  Item 1  ├──────────┤
│          │  Item 3  │
└──────────┴──────────┘
```

### Grid Items Can Be Repositioned

Grid items can be explicitly positioned using properties such as:

```css
grid-column
grid-row
```

For example:

```css
.item {
    grid-column: 1 / 3;
}
```

This tells the item to occupy the space between grid column lines 1 and 3.

### Grid Items and Alignment

Grid items can also be aligned within their grid areas.

For example:

```css
.item {
    justify-self: center;
    align-self: center;
}
```

These properties control the individual item's position within its grid area.

### Grid Item Size

A grid item's size is influenced by the grid tracks it occupies.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 300px;
}
```

The first column is:

```text
200px
```

and the second is:

```text
300px
```

An item placed in the first column is therefore positioned within that 200px track.

### Grid Items and `gap`

The spacing between grid items is controlled by the grid container.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

The grid items are separated by the specified gap.

```text
┌──────────┐ 20px ┌──────────┐
│  Item 1  │      │  Item 2  │
└──────────┘      └──────────┘
```

### Important Point

A grid item is specifically a **direct child** of a grid container.

```text
Grid Container
      │
      ├── Direct Child → Grid Item
      ├── Direct Child → Grid Item
      └── Direct Child → Grid Item
```

A nested descendant does not automatically become an item of the outer grid.

> 💡 **Remember:** A grid item is a direct child of a grid container. The grid container establishes the layout, while individual grid items can be styled, positioned, aligned, or made to span multiple rows and columns.

---

## Grid Columns

Grid columns are the **vertical tracks** of a CSS Grid.

They divide the grid container from left to right and determine how much horizontal space is available for grid items.

### Basic Example

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

Each column has a width of:

```text
200px
```

### Creating Multiple Columns

You can define several columns in `grid-template-columns`.

```css
.container {
    display: grid;
    grid-template-columns: 100px 200px 300px;
}
```

This creates:

```text
┌───────┬──────────────┬────────────────────┐
│ 100px │    200px     │       300px        │
└───────┴──────────────┴────────────────────┘
```

Each value represents one column.

### Equal-Width Columns

The `fr` unit can be used to create flexible columns.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The available space is divided equally:

```text
┌────────────────┬────────────────┐
│    Column 1     │    Column 2    │
│      1fr        │      1fr       │
└────────────────┴────────────────┘
```

### Three Equal Columns

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Result:

```text
┌──────────┬──────────┬──────────┐
│    1fr   │    1fr   │    1fr   │
└──────────┴──────────┴──────────┘
```

Each column receives an equal share of the available space.

### Unequal Flexible Columns

Different `fr` values create different proportions.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

The available space is divided into three fractional parts:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second column is twice the flexible size of the first.

### Fixed and Flexible Columns

You can combine fixed lengths with flexible columns.

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

This is useful for layouts such as a sidebar and main content:

```text
┌──────────────┬──────────────────────────┐
│   Sidebar    │       Main Content       │
│    200px     │           1fr            │
└──────────────┴──────────────────────────┘
```

### Three Columns With Different Sizes

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 300px;
}
```

The layout contains:

```text
200px       flexible        300px
   ↓            ↓              ↓
┌───────┬────────────────┬─────────┐
│ Left  │     Center     │  Right  │
└───────┴────────────────┴─────────┘
```

### Using Percentages

Columns can also be defined using percentages.

```css
.container {
    grid-template-columns: 50% 50%;
}
```

This creates two columns, each taking 50% of the grid container's relevant size.

However, when using percentages together with gaps, the total layout can require additional consideration.

### Using `auto`

The `auto` keyword can also be used.

```css
.container {
    grid-template-columns: auto 1fr;
}
```

The first column can size itself based on its contents and available space, while the second column uses the remaining flexible space.

### Combining Different Units

Grid columns can use different CSS units together.

```css
.container {
    grid-template-columns: 150px 20% 1fr;
}
```

You can combine:

```text
px
%
fr
auto
```

and other appropriate CSS length values.

### Using `repeat()`

When several columns follow the same pattern, `repeat()` makes the declaration shorter.

Instead of:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

you can write:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

Both create three equal flexible columns.

### Four Equal Columns

```css
.container {
    grid-template-columns: repeat(4, 1fr);
}
```

Result:

```text
┌──────┬──────┬──────┬──────┐
│ 1fr  │ 1fr  │ 1fr  │ 1fr  │
└──────┴──────┴──────┴──────┘
```

The `repeat()` function will be covered in more detail later.

### Columns With a Gap

The `gap` property can add space between columns.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
}
```

The result is conceptually:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│ Column 1 │      │ Column 2 │      │ Column 3 │
└──────────┘      └──────────┘      └──────────┘
```

The gap is separate from the column track sizes.

### Responsive Columns

Grid columns can be changed using media queries.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

Large screens:

```text
┌────────┬────────┬────────┐
│        │        │        │
└────────┴────────┴────────┘
```

Small screens:

```text
┌──────────────────────────┐
│                          │
├──────────────────────────┤
│                          │
├──────────────────────────┤
│                          │
└──────────────────────────┘
```

### Practical Card Grid

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

HTML:

```html
<div class="cards">
    <article>Card 1</article>
    <article>Card 2</article>
    <article>Card 3</article>
    <article>Card 4</article>
    <article>Card 5</article>
    <article>Card 6</article>
</div>
```

The cards are automatically arranged into three columns:

```text
┌────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │
├────────┼────────┼────────┤
│ Card 4 │ Card 5 │ Card 6 │
└────────┴────────┴────────┘
```

### Important Property

The main property for defining grid columns is:

```css
grid-template-columns
```

Its value defines the size of the column tracks.

Examples:

```css
grid-template-columns: 200px 300px;
```

```css
grid-template-columns: 1fr 1fr;
```

```css
grid-template-columns: repeat(3, 1fr);
```

```css
grid-template-columns: 200px 1fr;
```

> 💡 **Remember:** `grid-template-columns` defines the columns of a grid. Each value represents a column track, and you can combine fixed sizes, flexible `fr` units, percentages, `auto`, and other supported sizing values.

---

## Grid Rows

Grid rows are the **horizontal tracks** of a CSS Grid.

They determine how the grid is divided vertically and control the available space for grid items from top to bottom.

### Basic Example

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px;
}
```

This creates two rows:

```text
┌────────────────────────────┐
│          Row 1             │ 100px
├────────────────────────────┤
│          Row 2             │ 100px
└────────────────────────────┘
```

Each value in `grid-template-rows` defines one row track.

### Creating Multiple Rows

You can define several rows:

```css
.container {
    display: grid;
    grid-template-rows: 100px 150px 200px;
}
```

This creates three rows:

```text
┌────────────────────────────┐
│          Row 1             │
├────────────────────────────┤
│          Row 2             │
├────────────────────────────┤
│          Row 3             │
└────────────────────────────┘
```

The rows have heights of:

```text
100px
150px
200px
```

### Equal-Height Rows

The `fr` unit can be used to divide available space between rows.

```css
.container {
    display: grid;
    grid-template-rows: 1fr 1fr;
}
```

The available grid height is divided equally:

```text
┌────────────────────────────┐
│           1fr              │
├────────────────────────────┤
│           1fr              │
└────────────────────────────┘
```

### Three Equal Rows

```css
.container {
    display: grid;
    grid-template-rows: repeat(3, 1fr);
}
```

This creates three equal flexible rows.

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

### Fixed and Flexible Rows

You can combine fixed and flexible values.

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr;
}
```

This is useful for layouts such as a header and main content area.

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│        Main Content        │ 1fr
│                            │
└────────────────────────────┘
```

### Header, Main, and Footer

A common page layout can use:

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr 60px;
}
```

Conceptually:

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│           Main             │ 1fr
│                            │
├────────────────────────────┤
│           Footer           │ 60px
└────────────────────────────┘
```

### Using `auto`

Rows can also use `auto`.

```css
.container {
    display: grid;
    grid-template-rows: auto 1fr;
}
```

The first row can size itself based on its content and available space, while the second row uses flexible space.

### Combining Different Units

Grid rows can use different sizing values.

```css
.container {
    grid-template-rows: 80px 30% 1fr;
}
```

You can combine values such as:

```text
px
%
fr
auto
```

and other supported CSS sizing values.

### Rows and Columns Together

Rows are usually defined together with columns.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 200px;
}
```

This creates:

```text
             Column 1       Column 2
          ┌──────────────┬──────────────┐
Row 1     │              │              │ 100px
          ├──────────────┼──────────────┤
Row 2     │              │              │ 200px
          └──────────────┴──────────────┘
```

### Rows With Gaps

The `gap` property can add spacing between rows.

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px 100px;
    gap: 20px;
}
```

The rows are separated by `20px`.

```text
┌────────────────────────────┐
│           Row 1            │
└────────────────────────────┘
             20px
┌────────────────────────────┐
│           Row 2            │
└────────────────────────────┘
             20px
┌────────────────────────────┐
│           Row 3            │
└────────────────────────────┘
```

### Responsive Rows

Rows can be changed using media queries.

```css
.container {
    display: grid;
    grid-template-rows: 100px 1fr;
}

@media (max-width: 600px) {
    .container {
        grid-template-rows: 60px 1fr;
    }
}
```

The header row becomes smaller on narrow screens.

### `grid-template-rows`

The main property for explicitly defining rows is:

```css
grid-template-rows
```

For example:

```css
grid-template-rows: 100px 200px;
```

creates two row tracks.

Another example:

```css
grid-template-rows: repeat(3, 1fr);
```

creates three equal flexible row tracks.

### Important Point

Columns describe the horizontal structure:

```css
grid-template-columns
```

Rows describe the vertical structure:

```css
grid-template-rows
```

Together they define the main grid structure:

```text
        Columns →
     ┌──────┬──────┬──────┐
Rows │      │      │      │
  ↓  ├──────┼──────┼──────┤
     │      │      │      │
     ├──────┼──────┼──────┤
     │      │      │      │
     └──────┴──────┴──────┘
```

> 💡 **Remember:** `grid-template-rows` defines the size of grid row tracks. It can be combined with `grid-template-columns` to create a complete two-dimensional grid structure.

---

## Grid Tracks

A **grid track** is the space between two adjacent grid lines.

A grid track can be either:

- A **column track**
- A **row track**

In simple terms:

```text
Grid
│
├── Column tracks → vertical
└── Row tracks    → horizontal
```

### Column Tracks

When you define columns:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 2fr;
}
```

you create three column tracks:

```text
┌──────────┬──────────┬────────────────┐
│ Track 1  │ Track 2  │    Track 3     │
│  200px   │   1fr    │      2fr       │
└──────────┴──────────┴────────────────┘
```

Each value in `grid-template-columns` defines the size of a column track.

### Row Tracks

Similarly, when you define rows:

```css
.container {
    display: grid;
    grid-template-rows: 100px 1fr 200px;
}
```

you create three row tracks:

```text
┌──────────────────────────────┐
│          Track 1             │ 100px
├──────────────────────────────┤
│          Track 2             │ 1fr
├──────────────────────────────┤
│          Track 3             │ 200px
└──────────────────────────────┘
```

Each value in `grid-template-rows` defines the size of a row track.

### Grid Lines Define Tracks

Grid lines surround grid tracks.

For example, two columns have three vertical grid lines:

```text
Line 1       Line 2       Line 3
   ↓            ↓            ↓
   │            │            │
   ├────────────┼────────────┤
   │  Column 1  │  Column 2  │
   ├────────────┼────────────┤
   │            │            │
```

The space between:

```text
Line 1 → Line 2
```

is the first column track.

The space between:

```text
Line 2 → Line 3
```

is the second column track.

### Tracks and Grid Cells

A **grid cell** is created where a row track and a column track intersect.

For example:

```text
             Column Tracks
          ┌────────┬────────┐
Row       │        │        │
Track 1   │ Cell 1 │ Cell 2 │
          ├────────┼────────┤
Row       │        │        │
Track 2   │ Cell 3 │ Cell 4 │
          └────────┴────────┘
```

So:

```text
Column Track + Row Track
          ↓
      Grid Cell
```

### Fixed-Size Tracks

A track can have a fixed size.

```css
.container {
    grid-template-columns: 200px 300px;
}
```

This creates:

```text
Track 1 → 200px
Track 2 → 300px
```

### Flexible Tracks

Tracks can use the `fr` unit.

```css
.container {
    grid-template-columns: 1fr 2fr;
}
```

The available flexible space is divided into three parts:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second track receives twice the flexible share of the first.

The `fr` unit will be covered in detail later.

### `auto` Tracks

Tracks can also use `auto`.

```css
.container {
    grid-template-columns: auto 1fr;
}
```

An `auto` track can size itself based on its contents and available space.

### Track Sizing With `minmax()`

Grid tracks can use `minmax()` to specify a minimum and maximum size.

```css
.container {
    grid-template-columns: minmax(200px, 1fr) 1fr;
}
```

The first track can grow flexibly while respecting the specified minimum.

The `minmax()` function will be covered in detail later.

### Repeating Tracks

The `repeat()` function can create multiple tracks with the same pattern.

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

This creates:

```text
1fr | 1fr | 1fr
```

or three equal column tracks.

### Explicit Tracks

Tracks directly defined using:

```css
grid-template-columns
grid-template-rows
```

are called **explicit grid tracks**.

Example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}
```

This explicitly defines:

```text
2 column tracks
2 row tracks
```

### Implicit Tracks

Grid can also create additional tracks automatically when there are more items than the explicitly defined grid can accommodate.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

If there are five items:

```text
┌────────┬────────┐
│ Item 1 │ Item 2 │
├────────┼────────┤
│ Item 3 │ Item 4 │
├────────┼────────┤
│ Item 5 │        │
└────────┴────────┘
```

The additional row is created automatically.

These automatically generated tracks are called **implicit tracks**.

### Track Size vs Item Size

A grid track is part of the grid structure.

A grid item is placed inside one or more tracks.

For example:

```text
Grid Track
┌─────────────────────┐
│                     │
│      Grid Item      │
│                     │
└─────────────────────┘
```

The track determines the available grid space, while the item's own size and alignment determine how its content occupies that space.

### Grid Tracks and `gap`

A gap creates space between tracks.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

Conceptually:

```text
┌────────────┐  20px  ┌────────────┐
│ Track 1    │        │ Track 2    │
│            │        │            │
└────────────┘        └────────────┘
```

The gap is not itself a grid track.

### Important Grid Track Properties

Grid tracks are commonly created and sized using:

```css
grid-template-columns
grid-template-rows
```

and can use sizing techniques such as:

```css
fr
repeat()
minmax()
auto
px
%
```

### Track Mental Model

```text
Grid Lines
    ↓
┌────────┬────────┐
│ Track  │ Track  │
│   1    │   2    │
├────────┼────────┤
│ Track  │ Track  │
│   3    │   4    │
└────────┴────────┘
    ↑
Grid Cells
```

A more accurate conceptual model is:

```text
Grid Line
    ↓
┌──────────────┐
│ Grid Track   │
└──────────────┘
    ↑
Grid Line
```

> 💡 **Remember:** A grid track is a row or column of the grid. `grid-template-columns` creates column tracks, while `grid-template-rows` creates row tracks. Grid lines define the boundaries of those tracks.

---

## Grid Lines

**Grid lines** are the horizontal and vertical dividing lines that form the structure of a CSS Grid.

They define the boundaries of grid tracks and are used to position grid items.

### Basic Grid

Consider a grid with two columns and two rows:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}
```

Conceptually:

```text
        Column Line
        1       2       3
        ↓       ↓       ↓
        │       │       │
     ┌──┼───────┼───────┐
  1  │  │       │       │
     ├──┼───────┼───────┤
  2  │  │       │       │
     └──┼───────┼───────┘
        ↑       ↑       ↑
        1       2       3
```

There are:

- **3 vertical grid lines** for 2 columns
- **3 horizontal grid lines** for 2 rows

### Grid Lines and Columns

If a grid has:

```css
grid-template-columns: 1fr 1fr;
```

there are two column tracks.

Two tracks require three vertical grid lines:

```text
Line 1       Line 2       Line 3
   │            │            │
   │  Track 1   │  Track 2   │
   │            │            │
```

The first column is between:

```text
Grid Line 1 → Grid Line 2
```

The second column is between:

```text
Grid Line 2 → Grid Line 3
```

### Grid Lines and Rows

If a grid has:

```css
grid-template-rows: 100px 100px;
```

there are two row tracks.

Two row tracks require three horizontal grid lines:

```text
Grid Line 1
───────────────

    Row Track 1

Grid Line 2
───────────────

    Row Track 2

Grid Line 3
───────────────
```

### Grid Line Numbering

Grid lines are automatically numbered.

For a grid with three columns:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

there are four vertical grid lines:

```text
Line 1     Line 2     Line 3     Line 4
   │          │          │          │
   │  1fr     │  1fr     │  1fr     │
   │          │          │          │
```

The columns are therefore:

```text
Column 1 → Line 1 to Line 2
Column 2 → Line 2 to Line 3
Column 3 → Line 3 to Line 4
```

### Grid Lines Are Used to Position Items

Grid items can be positioned using grid line numbers.

For example:

```css
.item {
    grid-column: 1 / 3;
}
```

This means the item starts at column line `1` and ends at column line `3`.

```text
Line 1       Line 2       Line 3
   ↓            ↓            ↓
   │            │            │
   ├────────────┼────────────┤
   │                         │
   │         Item            │
   │                         │
   └─────────────────────────┘
```

The item therefore spans two column tracks.

### Grid Row Lines

Rows can also be referenced by their line numbers.

```css
.item {
    grid-row: 1 / 3;
}
```

This starts the item at row line `1` and ends it at row line `3`.

```text
Row Line 1
───────────────
       │
       │ Item
       │
Row Line 2
───────────────
       │
       │ Item
       │
Row Line 3
───────────────
```

The item spans two row tracks.

### Grid Line Names

Grid lines can also have custom names.

For example:

```css
.container {
    display: grid;
    grid-template-columns:
        [sidebar-start] 200px
        [sidebar-end content-start] 1fr
        [content-end] 200px;
}
```

The lines now have names such as:

```text
sidebar-start
sidebar-end
content-start
content-end
```

These names can be used when positioning items.

For example:

```css
.sidebar {
    grid-column: sidebar-start / sidebar-end;
}
```

Named lines can make complex layouts easier to understand.

### Negative Grid Line Numbers

Grid lines can also be referenced using negative numbers.

The last grid line is:

```text
-1
```

For example, in a four-column grid:

```text
Line:    1    2    3    4    5
         │    │    │    │    │
         │    │    │    │    │
Negative -5   -4   -3   -2   -1
```

This can be useful when you want to reference the end of the grid without knowing its exact positive line number.

Example:

```css
.item {
    grid-column: 1 / -1;
}
```

This makes the item span from the first grid line to the last grid line.

Conceptually:

```text
┌────────────────────────────────┐
│             Item               │
└────────────────────────────────┘
```

### Grid Lines vs Grid Tracks

These terms are related but different.

**Grid line:**

```text
Boundary
```

**Grid track:**

```text
Space between two adjacent grid lines
```

For example:

```text
Line 1        Line 2        Line 3
  │             │             │
  │   Track 1   │   Track 2   │
  │             │             │
```

So:

```text
Grid Lines
    ↓
Define boundaries
    ↓
Grid Tracks
    ↓
Contain grid cells
```

### Grid Lines vs Grid Cells

A grid cell is the space created by the intersection of one row track and one column track.

```text
          Column Lines
       1       2       3
       ↓       ↓       ↓
       │       │       │
  1 ───┼───────┼───────┤
       │ Cell  │ Cell  │
  2 ───┼───────┼───────┤
       │ Cell  │ Cell  │
  3 ───┴───────┴───────┘
```

The lines create the boundaries, while the cells occupy the spaces between those boundaries.

### Important Rule

If a grid contains:

```text
N columns
```

it normally has:

```text
N + 1 vertical grid lines
```

Similarly, if it contains:

```text
N rows
```

it normally has:

```text
N + 1 horizontal grid lines
```

For example:

```text
2 columns → 3 column lines
3 columns → 4 column lines
4 columns → 5 column lines
```

And:

```text
2 rows → 3 row lines
3 rows → 4 row lines
4 rows → 5 row lines
```

### Basic Mental Model

```text
Grid Lines
    ↓
┌───────┬───────┐
│       │       │
│ Cell  │ Cell  │
│       │       │
├───────┼───────┤
│       │       │
│ Cell  │ Cell  │
│       │       │
└───────┴───────┘
    ↑
Grid Lines
```

> 💡 **Remember:** Grid lines are the boundaries of a CSS Grid. They are automatically numbered, can optionally be named, and are commonly used with `grid-column` and `grid-row` to precisely position and span grid items.

---

## Grid Cells

A **grid cell** is the smallest unit of space in a CSS Grid.

A grid cell is created where **one row track and one column track intersect**.

### Basic Example

Consider a grid with two columns and two rows:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 100px;
}
```

This creates four grid cells:

```text
┌────────────┬────────────┐
│   Cell 1   │   Cell 2   │
├────────────┼────────────┤
│   Cell 3   │   Cell 4   │
└────────────┴────────────┘
```

Each cell is the intersection of:

```text
One column track
       +
One row track
       ↓
Grid Cell
```

### Grid Cell vs Grid Track

A **grid track** is an entire row or column.

A **grid cell** is one individual area inside the grid.

For example:

```text
Column Track 1     Column Track 2
      ↓                  ↓
┌───────────────┬───────────────┐
│    Cell 1     │    Cell 2     │ ← Row Track 1
├───────────────┼───────────────┤
│    Cell 3     │    Cell 4     │ ← Row Track 2
└───────────────┴───────────────┘
```

Here:

```text
Column Track 1 → Cells 1 and 3
Column Track 2 → Cells 2 and 4

Row Track 1 → Cells 1 and 2
Row Track 2 → Cells 3 and 4
```

### Grid Cell vs Grid Item

A grid cell is a **location in the grid**.

A grid item is an **element placed into that location**.

For example:

```html
<div class="container">
    <div>Item 1</div>
    <div>Item 2</div>
</div>
```

With:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

The browser can place the items into cells:

```text
┌────────────┬────────────┐
│   Item 1   │   Item 2   │
│   Cell 1   │   Cell 2   │
└────────────┴────────────┘
```

So:

```text
Grid Cell
   ↓
Available location

Grid Item
   ↓
Element placed in that location
```

### Number of Grid Cells

If a grid has:

```text
3 columns
2 rows
```

the grid contains:

```text
3 × 2 = 6 cells
```

Example:

```text
┌────────┬────────┬────────┐
│ Cell 1 │ Cell 2 │ Cell 3 │
├────────┼────────┼────────┤
│ Cell 4 │ Cell 5 │ Cell 6 │
└────────┴────────┴────────┘
```

Similarly:

```text
4 columns × 3 rows = 12 cells
```

### Grid Cells and Grid Lines

Grid lines form the boundaries of grid cells.

For a two-column, two-row grid:

```text
        Line 1     Line 2     Line 3
           ↓          ↓          ↓
           │          │          │
Line 1 ────┼──────────┼──────────┤
           │  Cell 1  │  Cell 2  │
Line 2 ────┼──────────┼──────────┤
           │  Cell 3  │  Cell 4  │
Line 3 ────┴──────────┴──────────┘
```

Each cell is bounded by:

- Two vertical grid lines
- Two horizontal grid lines

### Positioning Items Using Cells

Grid items are normally placed into cells automatically.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

With three items:

```text
┌──────────┬──────────┬──────────┐
│  Item 1  │  Item 2  │  Item 3  │
│  Cell 1  │  Cell 2  │  Cell 3  │
└──────────┴──────────┴──────────┘
```

The first item occupies the first available cell, the second item occupies the next available cell, and so on.

This automatic behavior is called **auto-placement**.

### An Item Can Span Multiple Cells

A grid item does not have to remain inside a single cell.

It can span multiple columns or rows.

For example:

```css
.item {
    grid-column: span 2;
}
```

An item can occupy two adjacent column tracks:

```text
┌────────────────────────────┬──────────┐
│          Item 1            │  Item 2  │
│        spans 2 cells       │          │
└────────────────────────────┴──────────┘
```

The item covers the space that would otherwise contain two cells.

### Spanning Rows

An item can also span multiple rows:

```css
.item {
    grid-row: span 2;
}
```

Example:

```text
┌────────────┬────────────┐
│            │   Item 2   │
│   Item 1   ├────────────┤
│            │   Item 3   │
└────────────┴────────────┘
```

Here, `Item 1` spans two row tracks.

### Grid Area

When an item spans multiple cells, the combined space occupied by that item can be considered its **grid area**.

For example:

```css
.item {
    grid-column: span 2;
    grid-row: span 2;
}
```

Conceptually:

```text
┌───────────────────────┬──────────┐
│                       │          │
│        Item 1         │  Item 2  │
│                       ├──────────┤
│                       │  Item 3  │
└───────────────────────┴──────────┘
```

The item's grid area covers multiple cells.

### Empty Grid Cells

A grid can contain cells that do not currently contain a grid item.

For example:

```text
┌──────────┬──────────┐
│  Item 1  │          │
├──────────┼──────────┤
│  Item 2  │  Item 3  │
└──────────┴──────────┘
```

The top-right cell is still part of the grid even though no item occupies it.

### Grid Cells and `gap`

When `gap` is used:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

the cells remain part of the grid, while the gap creates space between the tracks.

Conceptually:

```text
┌────────────┐      ┌────────────┐
│   Cell 1   │ 20px │   Cell 2   │
└────────────┘      └────────────┘
```

The gap itself is not a grid cell or grid track.

### Grid Cell Mental Model

```text
Grid
 │
 ├── Grid Lines
 │      ↓
 │   Boundaries
 │
 ├── Grid Tracks
 │      ↓
 │   Rows / Columns
 │
 └── Grid Cells
        ↓
     Individual
     grid spaces
```

A useful way to remember the relationship is:

```text
Grid Lines
    ↓
define
    ↓
Grid Tracks
    ↓
intersect
    ↓
Grid Cells
    ↓
contain
    ↓
Grid Items
```

> 💡 **Remember:** A grid cell is the smallest individual space in a CSS Grid, created by the intersection of one row track and one column track. Grid items are placed into these cells and can span multiple cells.

---

## Grid Template Columns

The `grid-template-columns` property defines the **number and size of column tracks** in a CSS Grid.

It is one of the main properties used to create the column structure of a grid.

### Basic Syntax

```css
.container {
    display: grid;
    grid-template-columns: value;
}
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 300px;
}
```

This creates two columns:

```text
┌────────────┬────────────────┐
│   200px    │     300px      │
└────────────┴────────────────┘
```

### Multiple Column Values

Each value represents a column track.

```css
.container {
    grid-template-columns: 100px 200px 300px;
}
```

This creates three columns:

```text
┌───────┬──────────────┬────────────────────┐
│ 100px │    200px     │       300px        │
└───────┴──────────────┴────────────────────┘
```

So:

```text
1st value → Column 1
2nd value → Column 2
3rd value → Column 3
```

### Equal Columns

You can create equal-width columns using the `fr` unit:

```css
.container {
    grid-template-columns: 1fr 1fr;
}
```

The available space is divided equally:

```text
┌────────────────┬────────────────┐
│      1fr       │      1fr       │
└────────────────┴────────────────┘
```

Three equal columns:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

Or:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

### Fixed-Width Columns

You can use fixed lengths:

```css
.container {
    grid-template-columns: 200px 300px;
}
```

The first column is `200px` and the second is `300px`.

This is useful when a specific column width is required.

### Fixed and Flexible Columns

Fixed and flexible tracks can be combined:

```css
.container {
    grid-template-columns: 200px 1fr;
}
```

Conceptually:

```text
┌──────────────┬──────────────────────────┐
│   Sidebar    │       Main Content       │
│    200px     │           1fr            │
└──────────────┴──────────────────────────┘
```

The `200px` column keeps its defined size, while `1fr` uses the remaining flexible space.

### Different Flexible Sizes

Different `fr` values create proportional columns:

```css
.container {
    grid-template-columns: 1fr 2fr;
}
```

The available flexible space is divided into three parts:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second column receives twice the flexible share of the first.

### Three Different Flexible Columns

```css
.container {
    grid-template-columns: 1fr 2fr 1fr;
}
```

The ratio is:

```text
1 : 2 : 1
```

Conceptually:

```text
┌──────────┬─────────────────────┬──────────┐
│   1fr    │        2fr          │   1fr    │
└──────────┴─────────────────────┴──────────┘
```

### Using `auto`

The `auto` keyword can be used as a track size:

```css
.container {
    grid-template-columns: auto 1fr;
}
```

The `auto` track can size itself based on its content and available space.

This can be useful for layouts where one column should adapt to its contents.

### Using Percentages

Percentages can also define columns:

```css
.container {
    grid-template-columns: 50% 50%;
}
```

This creates two columns based on the grid container's relevant size.

When using percentages together with gaps, remember that the percentage track sizes and the gaps both contribute to the overall layout.

### Combining Different Units

Different sizing values can be combined:

```css
.container {
    grid-template-columns: 150px 20% 1fr;
}
```

A grid can therefore contain:

```text
Fixed column
      +
Percentage column
      +
Flexible column
```

### Using `repeat()`

The `repeat()` function is useful when multiple columns use the same pattern.

Instead of:

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

you can write:

```css
.container {
    grid-template-columns: repeat(3, 1fr);
}
```

Both create three equal columns.

Another example:

```css
.container {
    grid-template-columns: repeat(4, 200px);
}
```

This creates four `200px` columns.

### Repeating Mixed Patterns

`repeat()` can also repeat a more complex pattern.

```css
.container {
    grid-template-columns: repeat(2, 100px 1fr);
}
```

This repeats:

```text
100px 1fr
```

twice.

Conceptually:

```text
100px | 1fr | 100px | 1fr
```

### Using `minmax()`

`minmax()` can define a minimum and maximum size for a column.

```css
.container {
    grid-template-columns: minmax(200px, 1fr) 1fr;
}
```

The first column can grow as flexible space becomes available while respecting the specified minimum.

`minmax()` is especially useful for responsive layouts.

### Responsive Column Pattern

A common responsive pattern is:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

Large screens:

```text
┌────────┬────────┬────────┐
│        │        │        │
└────────┴────────┴────────┘
```

Small screens:

```text
┌──────────────────────────┐
│                          │
├──────────────────────────┤
│                          │
├──────────────────────────┤
│                          │
└──────────────────────────┘
```

### Grid Columns With `gap`

The `gap` property adds space between the columns:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Conceptually:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│ Column 1 │      │ Column 2 │      │ Column 3 │
└──────────┘      └──────────┘      └──────────┘
```

The `gap` is separate from the column track sizes.

### Common Examples

Two equal columns:

```css
grid-template-columns: 1fr 1fr;
```

Three equal columns:

```css
grid-template-columns: repeat(3, 1fr);
```

Sidebar and content:

```css
grid-template-columns: 250px 1fr;
```

Three-column layout:

```css
grid-template-columns: 1fr 2fr 1fr;
```

Four fixed columns:

```css
grid-template-columns: repeat(4, 200px);
```

Responsive minimum-width columns:

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

### Important Point

`grid-template-columns` controls the **explicit column tracks** of the grid.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 2fr;
}
```

This explicitly defines three column tracks.

```text
200px | 1fr | 2fr
```

> 💡 **Remember:** `grid-template-columns` defines the column structure of a grid. Each value represents a column track, and values such as `px`, `%`, `auto`, `fr`, `repeat()`, and `minmax()` can be used to create flexible and responsive layouts.

---

## Grid Template Rows

The `grid-template-rows` property defines the **number and size of row tracks** in a CSS Grid.

It is the row equivalent of `grid-template-columns`.

### Basic Syntax

```css
.container {
    display: grid;
    grid-template-rows: value;
}
```

For example:

```css
.container {
    display: grid;
    grid-template-rows: 100px 200px;
}
```

This creates two rows:

```text
┌────────────────────────────┐
│          Row 1             │ 100px
├────────────────────────────┤
│          Row 2             │ 200px
└────────────────────────────┘
```

### Multiple Row Values

Each value represents one row track.

```css
.container {
    grid-template-rows: 100px 150px 200px;
}
```

This creates three rows:

```text
┌────────────────────────────┐
│          Row 1             │ 100px
├────────────────────────────┤
│          Row 2             │ 150px
├────────────────────────────┤
│          Row 3             │ 200px
└────────────────────────────┘
```

### Equal-Height Rows

The `fr` unit can be used to divide available space equally.

```css
.container {
    grid-template-rows: 1fr 1fr;
}
```

The available flexible space is divided equally:

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

Three equal rows:

```css
.container {
    grid-template-rows: repeat(3, 1fr);
}
```

### Fixed and Flexible Rows

You can combine fixed and flexible row sizes.

```css
.container {
    grid-template-rows: 80px 1fr;
}
```

This is useful for layouts such as a header and main content:

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│        Main Content        │ 1fr
│                            │
└────────────────────────────┘
```

### Header, Main, and Footer

A common page structure can be created with:

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr 60px;
}
```

Result:

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│           Main             │ 1fr
│                            │
├────────────────────────────┤
│           Footer           │ 60px
└────────────────────────────┘
```

### Different Flexible Sizes

Different `fr` values can create proportional row sizes.

```css
.container {
    grid-template-rows: 1fr 2fr;
}
```

The available flexible space is divided into three parts:

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│                            │
│            2fr             │
│                            │
└────────────────────────────┘
```

The second row receives twice the flexible share of the first.

### Using `auto`

Rows can use the `auto` keyword:

```css
.container {
    grid-template-rows: auto 1fr;
}
```

The `auto` track can size itself based on its contents and available space.

This can be useful for content-dependent rows.

### Using Percentages

Percentage values can also define row tracks.

```css
.container {
    grid-template-rows: 30% 70%;
}
```

The row sizes are calculated relative to the relevant size of the grid container.

When percentages are combined with gaps, the total layout should be considered carefully.

### Combining Different Units

Different sizing values can be combined:

```css
.container {
    grid-template-rows: 80px 30% 1fr;
}
```

For example:

```text
80px
  +
30%
  +
1fr
```

This allows different rows to use different sizing strategies.

### Using `repeat()`

The `repeat()` function can create multiple rows with the same size.

Instead of:

```css
.container {
    grid-template-rows: 100px 100px 100px;
}
```

you can write:

```css
.container {
    grid-template-rows: repeat(3, 100px);
}
```

Both create three `100px` rows.

### Repeating Flexible Rows

```css
.container {
    grid-template-rows: repeat(3, 1fr);
}
```

This creates three equal flexible row tracks.

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

### Using `minmax()`

`minmax()` can define a minimum and maximum row size.

```css
.container {
    grid-template-rows: minmax(100px, 1fr) 1fr;
}
```

The first row can grow flexibly while respecting its minimum size.

This is useful when row content needs a minimum amount of space.

### Rows With `gap`

The `gap` property creates space between rows.

```css
.container {
    display: grid;
    grid-template-rows: 100px 100px 100px;
    gap: 20px;
}
```

Conceptually:

```text
┌────────────────────────────┐
│           Row 1            │
└────────────────────────────┘
             20px
┌────────────────────────────┐
│           Row 2            │
└────────────────────────────┘
             20px
┌────────────────────────────┐
│           Row 3            │
└────────────────────────────┘
```

The gap is space between the tracks, not another row.

### Rows and Columns Together

`grid-template-rows` is commonly used together with `grid-template-columns`.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 200px;
}
```

This creates:

```text
              Columns
          1fr          1fr
       ┌────────────┬────────────┐
100px  │            │            │
       ├────────────┼────────────┤
200px  │            │            │
       └────────────┴────────────┘
          ↑
         Rows
```

### Practical Page Layout

A complete page structure can use:

```css
.page {
    display: grid;
    grid-template-rows: 70px 1fr 50px;
}
```

HTML:

```html
<div class="page">
    <header>Header</header>
    <main>Main Content</main>
    <footer>Footer</footer>
</div>
```

The layout becomes:

```text
┌────────────────────────────┐
│           Header           │
├────────────────────────────┤
│                            │
│        Main Content        │
│                            │
├────────────────────────────┤
│           Footer           │
└────────────────────────────┘
```

### Important Property

The main property for defining explicit row tracks is:

```css
grid-template-rows
```

Examples:

```css
grid-template-rows: 100px 200px;
```

```css
grid-template-rows: 1fr 1fr;
```

```css
grid-template-rows: repeat(3, 1fr);
```

```css
grid-template-rows: 80px 1fr 60px;
```

### Columns vs Rows

```text
grid-template-columns
        ↓
Defines column tracks
        ↓
Horizontal structure

grid-template-rows
        ↓
Defines row tracks
        ↓
Vertical structure
```

Together:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 100px 1fr;
}
```

create the two-dimensional grid structure.

> 💡 **Remember:** `grid-template-rows` defines the size of explicit row tracks. It can use fixed values, flexible `fr` units, `auto`, percentages, `repeat()`, `minmax()`, and other supported sizing values.

---

## The `fr` Unit

The `fr` unit stands for **fraction**.

It represents a **fraction of the available space** in a CSS Grid container.

The `fr` unit is one of the most useful sizing units in CSS Grid because it allows grid tracks to share available space proportionally.

### Basic Syntax

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

This creates two columns that share the available flexible space equally.

```text
┌────────────────┬────────────────┐
│      1fr       │      1fr       │
└────────────────┴────────────────┘
```

Each column receives one fraction of the available space.

### Two Equal Fractions

```css
grid-template-columns: 1fr 1fr;
```

The available space is divided into:

```text
1 + 1 = 2 fractions
```

Each column receives:

```text
1 / 2
```

of the available flexible space.

### Three Equal Fractions

```css
grid-template-columns: 1fr 1fr 1fr;
```

The available flexible space is divided into:

```text
1 + 1 + 1 = 3 fractions
```

Result:

```text
┌──────────┬──────────┬──────────┐
│   1fr    │   1fr    │   1fr    │
└──────────┴──────────┴──────────┘
```

Each column receives an equal share.

### Unequal Fractions

Different `fr` values create proportional tracks.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr;
}
```

The total number of fractions is:

```text
1 + 2 = 3
```

Therefore:

```text
First column  → 1/3
Second column → 2/3
```

Conceptually:

```text
┌──────────┬─────────────────────┐
│   1fr    │        2fr          │
└──────────┴─────────────────────┘
```

The second column receives twice the flexible share of the first.

### Three Different Fractions

```css
.container {
    display: grid;
    grid-template-columns: 1fr 2fr 3fr;
}
```

The total is:

```text
1 + 2 + 3 = 6
```

Therefore:

```text
Column 1 → 1/6
Column 2 → 2/6
Column 3 → 3/6
```

Conceptually:

```text
┌─────┬──────────┬───────────────┐
│ 1fr │   2fr    │      3fr      │
└─────┴──────────┴───────────────┘
```

### `fr` With Fixed Columns

The `fr` unit is especially useful when combined with fixed sizes.

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr;
}
```

The `200px` track gets its defined size first.

The `1fr` track uses the remaining available space.

```text
┌──────────────┬──────────────────────────┐
│   200px      │           1fr            │
│              │                          │
└──────────────┴──────────────────────────┘
```

This pattern is commonly used for sidebars.

### Multiple Flexible Tracks With a Fixed Track

```css
.container {
    display: grid;
    grid-template-columns: 200px 1fr 2fr;
}
```

Conceptually:

```text
┌──────────────┬──────────┬────────────────┐
│    200px     │   1fr    │      2fr       │
└──────────────┴──────────┴────────────────┘
```

The fixed track is allocated separately, and the remaining flexible space is distributed according to the `fr` values.

### `fr` and `gap`

Consider:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

The gap occupies space between the tracks.

Conceptually:

```text
┌──────────────┐ 20px ┌──────────────┐
│     1fr      │      │     1fr      │
└──────────────┘      └──────────────┘
```

The `fr` tracks share the space available after accounting for the gap.

### `fr` Can Be Used for Rows

The `fr` unit is not limited to columns.

It can also be used with rows:

```css
.container {
    display: grid;
    grid-template-rows: 1fr 1fr;
}
```

This divides the available grid height into two flexible portions.

```text
┌────────────────────────────┐
│            1fr             │
├────────────────────────────┤
│            1fr             │
└────────────────────────────┘
```

### Header and Main Content

A common layout is:

```css
.container {
    display: grid;
    grid-template-rows: 80px 1fr;
}
```

The first row is fixed:

```text
80px
```

The second row takes the remaining flexible space:

```text
1fr
```

```text
┌────────────────────────────┐
│           Header           │ 80px
├────────────────────────────┤
│                            │
│        Main Content        │ 1fr
│                            │
└────────────────────────────┘
```

### `fr` Is Different From `%`

These two approaches are not always equivalent.

For example:

```css
grid-template-columns: 50% 50%;
```

uses percentages based on the grid container's relevant size.

While:

```css
grid-template-columns: 1fr 1fr;
```

divides the available flexible space between the tracks.

This distinction becomes especially important when gaps or other fixed-sized tracks are present.

### `fr` With `auto`

You can combine `fr` with `auto`:

```css
.container {
    display: grid;
    grid-template-columns: auto 1fr;
}
```

The first column can size itself based on its content, while the second flexible column receives the remaining available space.

### `fr` and Content

The exact final size of an `fr` track can also depend on the grid's sizing rules and the minimum size requirements of its contents.

For example:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

does not simply mean that every possible piece of space is always split blindly in half.

Grid's track-sizing algorithm also considers factors such as:

- Available space
- Track sizing functions
- Minimum contributions from grid items
- Gaps
- Other fixed or intrinsic sizes

For straightforward layouts, however, `1fr 1fr` can be understood as two equal flexible portions.

### Common `fr` Patterns

Two equal columns:

```css
grid-template-columns: 1fr 1fr;
```

Three equal columns:

```css
grid-template-columns: repeat(3, 1fr);
```

Sidebar and content:

```css
grid-template-columns: 250px 1fr;
```

Main content with a larger secondary area:

```css
grid-template-columns: 1fr 2fr;
```

Header and flexible content:

```css
grid-template-rows: 70px 1fr;
```

### Practical Example

HTML:

```html
<div class="layout">
    <aside>Sidebar</aside>
    <main>Main Content</main>
</div>
```

CSS:

```css
.layout {
    display: grid;
    grid-template-columns: 200px 1fr;
    gap: 20px;
}
```

Result:

```text
┌──────────────┐ 20px ┌──────────────────────────┐
│   Sidebar    │      │       Main Content       │
│    200px     │      │           1fr            │
└──────────────┘      └──────────────────────────┘
```

The sidebar keeps its fixed width while the main content expands into the remaining space.

### Important Points

```text
fr
│
├── Means fraction
├── Represents flexible space
├── Can be used for columns
├── Can be used for rows
├── Multiple fr values create proportions
├── Works with fixed-size tracks
├── Works with gaps
└── Is useful for responsive layouts
```

> 💡 **Remember:** The `fr` unit represents a flexible fraction of the available grid space. Values such as `1fr 2fr` distribute flexible space proportionally, while fixed tracks such as `200px` can be combined with `fr` tracks to create practical layouts.

---

## `repeat()` Function

The `repeat()` function is a CSS Grid function used to **repeat a pattern of grid tracks**.

It is commonly used with `grid-template-columns` and `grid-template-rows` to avoid writing the same track size multiple times.

### Basic Syntax

```css
repeat(count, track-size)
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

This is equivalent to:

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Both create three equal columns.

### Repeating Equal Columns

```css
.container {
    grid-template-columns: repeat(4, 1fr);
}
```

Result:

```text
┌────────┬────────┬────────┬────────┐
│  1fr   │  1fr   │  1fr   │  1fr   │
└────────┴────────┴────────┴────────┘
```

The first argument specifies how many times the track should be repeated.

The second argument specifies the track size.

```text
repeat(4, 1fr)
       │   │
       │   └── Track size
       └────── Number of repetitions
```

### Repeating Fixed-Size Columns

`repeat()` is not limited to `fr`.

```css
.container {
    grid-template-columns: repeat(3, 200px);
}
```

This creates:

```text
200px | 200px | 200px
```

Equivalent to:

```css
grid-template-columns: 200px 200px 200px;
```

### Repeating Rows

`repeat()` can also be used with rows.

```css
.container {
    grid-template-rows: repeat(3, 100px);
}
```

This creates three `100px` rows:

```text
┌──────────────────────┐
│       100px           │
├──────────────────────┤
│       100px           │
├──────────────────────┤
│       100px           │
└──────────────────────┘
```

### Repeating Different Flexible Sizes

You can repeat a pattern containing different track sizes.

```css
.container {
    grid-template-columns: repeat(2, 1fr 2fr);
}
```

This produces:

```text
1fr | 2fr | 1fr | 2fr
```

Equivalent to:

```css
grid-template-columns: 1fr 2fr 1fr 2fr;
```

### Repeating Multiple Values

The second argument can contain multiple track sizes.

```css
.container {
    grid-template-columns: repeat(3, 100px 1fr);
}
```

This produces:

```text
100px | 1fr | 100px | 1fr | 100px | 1fr
```

The pattern:

```text
100px 1fr
```

is repeated three times.

### Combining `repeat()` With Other Tracks

You can combine `repeat()` with tracks outside the function.

```css
.container {
    grid-template-columns: 200px repeat(3, 1fr) 150px;
}
```

This creates:

```text
200px | 1fr | 1fr | 1fr | 150px
```

This is useful when the beginning and end of a layout have fixed columns while the middle contains repeated flexible columns.

### `repeat()` With `minmax()`

`repeat()` can be combined with `minmax()`.

```css
.container {
    grid-template-columns: repeat(3, minmax(200px, 1fr));
}
```

This creates three columns where each track has:

```text
Minimum → 200px
Maximum → 1fr
```

This is particularly useful for responsive card layouts.

### Responsive Card Layout

A common Grid pattern is:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, minmax(200px, 1fr));
    gap: 20px;
}
```

This creates three columns while giving each column a minimum size.

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│  Card 1  │  Card 2  │  Card 3  │
└──────────┴──────────┴──────────┘
```

If the available space becomes insufficient for the minimum track sizes, the layout may need another responsive strategy, such as media queries or the auto-repeat forms discussed later.

### `repeat()` With `auto-fit`

`repeat()` can use the `auto-fit` keyword:

```css
.container {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(200px, 1fr)
    );
}
```

The browser determines how many tracks can fit based on the available space and the minimum track size.

This can create responsive grids without specifying a fixed number of columns.

### `repeat()` With `auto-fill`

Similarly:

```css
.container {
    display: grid;
    grid-template-columns: repeat(
        auto-fill,
        minmax(200px, 1fr)
    );
}
```

`auto-fill` and `auto-fit` are useful for responsive Grid layouts.

Their behavior differs when there is extra space and when empty tracks can be created, so they should not be treated as identical.

### `repeat()` With Rows and Columns

You can use `repeat()` independently for both dimensions.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 100px);
}
```

This creates:

```text
Columns → 3 equal tracks
Rows    → 2 tracks of 100px
```

Result:

```text
┌────────┬────────┬────────┐
│        │        │        │ 100px
├────────┼────────┼────────┤
│        │        │        │ 100px
└────────┴────────┴────────┘
```

### `repeat()` vs Writing Values Manually

Without `repeat()`:

```css
grid-template-columns:
    1fr 1fr 1fr 1fr 1fr;
```

With `repeat()`:

```css
grid-template-columns: repeat(5, 1fr);
```

The second version is shorter and makes the repetition pattern more obvious.

### Common Examples

Three equal columns:

```css
grid-template-columns: repeat(3, 1fr);
```

Four fixed columns:

```css
grid-template-columns: repeat(4, 200px);
```

Three equal rows:

```css
grid-template-rows: repeat(3, 1fr);
```

Repeated mixed pattern:

```css
grid-template-columns: repeat(2, 1fr 2fr);
```

Responsive columns:

```css
grid-template-columns: repeat(
    auto-fit,
    minmax(200px, 1fr)
);
```

### Important Points

```text
repeat()
│
├── Repeats grid tracks
├── Used with columns and rows
├── First argument → repetition count
├── Second argument → track pattern
├── Can repeat one track size
├── Can repeat multiple track sizes
├── Can be combined with minmax()
├── Can be combined with auto-fit
└── Can be combined with auto-fill
```

> 💡 **Remember:** `repeat()` makes Grid declarations shorter by repeating a track size or pattern. For example, `repeat(3, 1fr)` creates three equal flexible tracks.

---

## `minmax()` Function

The `minmax()` function is a CSS Grid function used to define a **minimum and maximum size for a grid track**.

It is useful when you want a grid track to be flexible while preventing it from becoming too small or too large.

### Basic Syntax

```css
minmax(minimum, maximum)
```

For example:

```css
.container {
    display: grid;
    grid-template-columns: minmax(200px, 1fr);
}
```

This means:

```text
Minimum size → 200px
Maximum size → 1fr
```

The track can grow as needed, but it should not become smaller than its minimum size.

### Basic Example

```css
.container {
    display: grid;
    grid-template-columns: minmax(200px, 400px);
}
```

The column can have a size between:

```text
200px → 400px
```

Conceptually:

```text
Minimum                 Maximum
  200px                    400px
    │                        │
    ├────────────────────────┤
             Track
```

### `minmax()` With `fr`

A common pattern is:

```css
.container {
    display: grid;
    grid-template-columns: minmax(200px, 1fr);
}
```

Here:

```text
Minimum → 200px
Maximum → 1fr
```

The column can grow to use available flexible space while maintaining a minimum size.

### Multiple Columns

You can use `minmax()` with multiple columns:

```css
.container {
    display: grid;
    grid-template-columns:
        minmax(200px, 1fr)
        minmax(200px, 1fr);
}
```

This creates two flexible columns, each with a minimum size of `200px`.

```text
┌────────────────┬────────────────┐
│     1fr        │      1fr       │
│ min 200px      │  min 200px     │
└────────────────┴────────────────┘
```

### `minmax()` With `repeat()`

`minmax()` becomes especially useful when combined with `repeat()`.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, minmax(200px, 1fr));
}
```

This creates three columns.

Each column has:

```text
Minimum → 200px
Maximum → 1fr
```

Conceptually:

```text
┌──────────┬──────────┬──────────┐
│  Column  │  Column  │  Column  │
│ min 200  │ min 200  │ min 200  │
└──────────┴──────────┴──────────┘
```

### Responsive Card Layout

A common use of `minmax()` is a card grid:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
    gap: 20px;
}
```

The columns can grow when more space is available while maintaining their minimum size.

### `auto-fit` With `minmax()`

For responsive layouts, `auto-fit` can be combined with `minmax()`:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
}
```

This allows the browser to determine how many columns can fit while using:

```text
Minimum column size → 200px
Maximum column size → 1fr
```

For example, a wide screen might produce:

```text
┌────────┬────────┬────────┬────────┐
│ Card 1 │ Card 2 │ Card 3 │ Card 4 │
└────────┴────────┴────────┴────────┘
```

A narrower screen might produce:

```text
┌────────┬────────┐
│ Card 1 │ Card 2 │
├────────┼────────┤
│ Card 3 │ Card 4 │
└────────┴────────┘
```

### `auto-fill` With `minmax()`

Another common pattern is:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fill, minmax(200px, 1fr));
}
```

`auto-fill` allows the grid to create as many tracks as can fit according to the minimum track size.

### `auto-fit` vs `auto-fill`

Both are commonly used with:

```css
repeat()
```

and:

```css
minmax()
```

For example:

```css
repeat(auto-fit, minmax(200px, 1fr))
```

and:

```css
repeat(auto-fill, minmax(200px, 1fr))
```

They are similar when the grid is filled with enough items, but they can behave differently when there is extra space and fewer items than available tracks.

A useful simplified distinction is:

```text
auto-fill
    ↓
Keeps fitting tracks into the available space

auto-fit
    ↓
Fits tracks and can collapse empty tracks
    allowing existing items to expand
```

### `minmax()` With Fixed Maximum

You can use fixed values for both arguments:

```css
grid-template-columns: minmax(200px, 400px);
```

The track is constrained between:

```text
200px minimum
400px maximum
```

### `minmax()` With `auto`

`auto` can also be used in supported track-sizing combinations.

For example:

```css
grid-template-columns: minmax(200px, auto);
```

This allows the track to have a minimum of `200px` while its maximum sizing behavior is based on `auto`.

### `minmax()` With Rows

`minmax()` is not limited to columns.

It can also be used for rows:

```css
.container {
    display: grid;
    grid-template-rows: minmax(100px, 1fr);
}
```

The row has:

```text
Minimum → 100px
Maximum → 1fr
```

### Preventing Very Small Columns

Consider a responsive card layout:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

Depending on the available space, the columns can become too narrow for the intended design.

Using:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(3, minmax(200px, 1fr));
}
```

provides a minimum track size.

### `minmax()` and `gap`

`minmax()` can be combined with `gap`:

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

The grid must account for both:

```text
Minimum track sizes
        +
Gaps
        +
Available container space
```

This makes the pattern useful for responsive card layouts.

### Common Examples

Minimum `200px`, flexible maximum:

```css
grid-template-columns: minmax(200px, 1fr);
```

Three flexible columns:

```css
grid-template-columns:
    repeat(3, minmax(200px, 1fr));
```

Responsive columns:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));
```

Fixed range:

```css
grid-template-columns:
    minmax(200px, 400px);
```

Flexible rows:

```css
grid-template-rows:
    minmax(100px, 1fr);
```

### Important Points

```text
minmax()
│
├── Defines a minimum size
├── Defines a maximum size
├── Used for grid tracks
├── Works with columns
├── Works with rows
├── Commonly used with fr
├── Commonly used with repeat()
├── Useful for responsive layouts
├── Works with auto-fit
└── Works with auto-fill
```

> 💡 **Remember:** `minmax(minimum, maximum)` gives a grid track a size range. It is especially useful for responsive layouts where a track should remain usable at smaller sizes but still expand when more space is available.

---

## `gap`

The `gap` property controls the **space between rows and columns** in a CSS Grid.

It is useful for creating consistent spacing between grid tracks without adding margins to individual grid items.

### Basic Syntax

```css
.container {
    display: grid;
    gap: 20px;
}
```

This creates a `20px` gap between both rows and columns.

### Basic Example

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

The result is conceptually:

```text
┌────────────┐  20px  ┌────────────┐
│   Item 1   │        │   Item 2   │
└────────────┘        └────────────┘

             20px

┌────────────┐  20px  ┌────────────┐
│   Item 3   │        │   Item 4   │
└────────────┘        └────────────┘
```

The `20px` spacing is applied between the grid tracks.

### `gap` Between Columns and Rows

When a single value is used:

```css
gap: 20px;
```

the same gap is applied to:

```text
Rows    → 20px
Columns → 20px
```

### Different Row and Column Gaps

You can specify separate values:

```css
.container {
    gap: 10px 20px;
}
```

The order is:

```text
gap: row-gap column-gap;
```

Therefore:

```text
Row gap    → 10px
Column gap → 20px
```

Conceptually:

```text
┌────────────┐ 20px ┌────────────┐
│            │      │            │
└────────────┘      └────────────┘
       ↑
      10px
       ↓
┌────────────┐ 20px ┌────────────┐
│            │      │            │
└────────────┘      └────────────┘
```

### `row-gap`

The `row-gap` property controls the spacing **between rows**.

```css
.container {
    row-gap: 30px;
}
```

Only the vertical spacing between row tracks is affected.

Example:

```text
┌────────────┐
│    Row 1   │
└────────────┘
      ↑
    30px
      ↓
┌────────────┐
│    Row 2   │
└────────────┘
```

### `column-gap`

The `column-gap` property controls the spacing **between columns**.

```css
.container {
    column-gap: 20px;
}
```

Only the horizontal spacing between column tracks is affected.

Example:

```text
┌──────────┐ 20px ┌──────────┐
│ Column 1 │      │ Column 2 │
└──────────┘      └──────────┘
```

### `gap` vs `row-gap` and `column-gap`

These are related properties:

```css
gap: 20px;
```

sets both row and column gaps.

```css
row-gap: 20px;
column-gap: 30px;
```

sets them independently.

The shorthand:

```css
gap: 20px 30px;
```

is equivalent to:

```css
row-gap: 20px;
column-gap: 30px;
```

### `gap` With Multiple Columns

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Result:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│  Item 1  │      │  Item 2  │      │  Item 3  │
└──────────┘      └──────────┘      └──────────┘
```

The same `20px` spacing is used between the columns.

### `gap` With Rows

```css
.container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    row-gap: 30px;
}
```

This creates `30px` of vertical spacing between the rows.

```text
┌──────────┬──────────┐
│  Item 1  │  Item 2  │
└──────────┴──────────┘

          30px

┌──────────┬──────────┐
│  Item 3  │  Item 4  │
└──────────┴──────────┘
```

### `gap` With `fr`

The `gap` is separate from flexible `fr` tracks.

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

Conceptually:

```text
┌──────────────┐ 20px ┌──────────────┐
│     1fr      │      │     1fr      │
└──────────────┘      └──────────────┘
```

The available space is distributed to the flexible tracks after the fixed gap is accounted for.

### `gap` With `minmax()`

`gap` is commonly combined with responsive `minmax()` layouts.

```css
.cards {
    display: grid;
    grid-template-columns:
        repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
}
```

This creates:

```text
Responsive columns
        +
Consistent spacing
```

For example:

```text
┌──────────┐ 20px ┌──────────┐ 20px ┌──────────┐
│  Card 1  │      │  Card 2  │      │  Card 3  │
└──────────┘      └──────────┘      └──────────┘
```

### `gap` vs Margins

Without `gap`, you might add margins to individual items:

```css
.item {
    margin: 10px;
}
```

With Grid, you can instead use:

```css
.container {
    gap: 20px;
}
```

This allows the container to control the spacing between grid tracks.

### Why `gap` Is Useful

Using `gap` provides several advantages:

- Consistent spacing
- Simpler CSS
- No need to add margins to every grid item
- Works for both rows and columns
- Easy to change responsively
- Useful for reusable components

### Responsive Gap

The gap can be changed using a media query.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
        gap: 12px;
    }
}
```

Large screens:

```text
Gap → 24px
```

Small screens:

```text
Gap → 12px
```

### Practical Card Layout

HTML:

```html
<div class="cards">
    <article>Card 1</article>
    <article>Card 2</article>
    <article>Card 3</article>
    <article>Card 4</article>
</div>
```

CSS:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}
```

Result:

```text
┌────────────┐ 20px ┌────────────┐
│   Card 1   │      │   Card 2   │
└────────────┘      └────────────┘

             20px

┌────────────┐ 20px ┌────────────┐
│   Card 3   │      │   Card 4   │
└────────────┘      └────────────┘
```

### Important Points

```text
gap
│
├── Controls spacing between grid tracks
├── Can control rows and columns
├── One value → same row and column gap
├── Two values → row gap and column gap
├── row-gap → spacing between rows
├── column-gap → spacing between columns
└── Does not create an additional grid track
```

### Common Examples

Same gap everywhere:

```css
gap: 20px;
```

Different row and column gaps:

```css
gap: 10px 20px;
```

Only row spacing:

```css
row-gap: 20px;
```

Only column spacing:

```css
column-gap: 30px;
```

Responsive card grid:

```css
grid-template-columns:
    repeat(auto-fit, minmax(200px, 1fr));

gap: 20px;
```

> 💡 **Remember:** `gap` controls the space between grid rows and columns. It is the preferred way to create consistent spacing between Grid tracks instead of adding margins to individual grid items.