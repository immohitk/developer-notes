## Table of Contents

- [Introduction](#introduction)
- [What is the `display` Property?](#what-is-the-display-property)
- [Block Elements](#block-elements)
- [Inline Elements](#inline-elements)
- [Inline-Block Elements](#inline-block-elements)
- [`display: none`](#display-none)
- [`display: contents`](#display-contents)
- [`display: flex`](#display-flex)
- [`display: grid`](#display-grid)
- [Other Common Display Values](#other-common-display-values)
- [Display Comparison Table](#display-comparison-table)
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


## Introduction

Every HTML element has a **display type** that determines **how it appears and behaves within a webpage layout**.

Some elements naturally occupy an entire line, while others only take up as much space as their content requires. Some elements can be completely hidden, while others become flexible containers for advanced layouts.

The CSS **`display`** property allows you to control this behavior.

By changing an element's display type, you can completely alter how it interacts with surrounding elements without changing the HTML itself.

For example, you can:

- Make an inline element behave like a block element.
- Place multiple block elements on the same line.
- Hide elements from the page.
- Create flexible layouts with Flexbox.
- Build two-dimensional layouts with Grid.

Because of its versatility, the `display` property is one of the most frequently used properties in modern CSS.

In this chapter, you'll learn the most common display values, when to use them, how they affect layout, and how they serve as the foundation for advanced layout systems.

> 💡 **Pro Tip:** Before reaching for Flexbox or Grid, first ask yourself: *"How should this element behave?"* The answer often begins with choosing the correct `display` value.


---


## What is the `display` Property?

The **`display`** property determines **how an HTML element is displayed and participates in the page layout**.

Every HTML element has a default display type assigned by the browser.

For example:

- `<div>` is a **block** element.
- `<span>` is an **inline** element.
- `<img>` is an **inline** element (often treated as a replaced inline element).
- `<button>` commonly behaves as an **inline-block** element in browsers.

By changing the `display` property, you can completely change how an element behaves without modifying the HTML structure.

---

## Syntax

```css
selector {
    display: value;
}
```

---

## Common Values

| Value | Purpose |
|--------|---------|
| `block` | Displays the element as a block-level element. |
| `inline` | Displays the element inline with surrounding content. |
| `inline-block` | Combines features of inline and block elements. |
| `none` | Removes the element from the layout. |
| `flex` | Creates a Flexbox container. |
| `grid` | Creates a Grid container. |
| `contents` | Removes the element's own box while keeping its children. |

---

## Why is `display` Important?

The `display` property controls:

- Whether an element starts on a new line.
- Whether width and height can be applied.
- How much horizontal space an element occupies.
- How child elements are laid out.
- Whether an element participates in the document layout.

Changing `display` often changes the entire behavior of an element.

---

## Example

### HTML

```html
<div class="box">
    Hello CSS
</div>
```

### CSS

```css
.box {
    display: inline;
}
```

Although `<div>` is normally a block element, it now behaves like an inline element.

---

## Default Behavior

Different HTML elements have different default display values.

Examples:

| Element | Default Display |
|----------|-----------------|
| `<div>` | `block` |
| `<p>` | `block` |
| `<h1>`–`<h6>` | `block` |
| `<span>` | `inline` |
| `<a>` | `inline` |
| `<strong>` | `inline` |
| `<img>` | `inline` |
| `<button>` | Usually `inline-block` |

These defaults can be changed using CSS.

---

## Layout Behavior

Think of `display` as answering one question:

> **How should this element behave inside the layout?**

Possible answers include:

```text
Take the whole row?

↓

display: block
```

```text
Stay within surrounding text?

↓

display: inline
```

```text
Stay inline but allow width and height?

↓

display: inline-block
```

```text
Become a flexible layout container?

↓

display: flex
```

```text
Become a two-dimensional layout?

↓

display: grid
```

---

## Advantages

- Controls element layout behavior.
- Makes layouts flexible without changing HTML.
- Enables modern layout systems.
- Works with every HTML element.

---

## Limitations

- Some display values affect which CSS properties have an effect (for example, `width` and `height` on inline elements).
- Choosing the wrong display type can produce unexpected layouts.
- Advanced values such as `contents` have specific use cases and should be used carefully.

> 💡 **Pro Tip:** Before changing margins, widths, or positioning, first verify that the element has the correct `display` value. Many layout issues are caused by using the wrong display type.

### 🌍 Real-World Usage

The `display` property is used on virtually every website to:

- Build navigation menus
- Create cards
- Align buttons
- Hide and show content
- Build dashboards
- Create responsive layouts
- Enable Flexbox and Grid

### 📌 Did You Know?

Modern CSS layout begins with one property:

```css
display
```

Both **Flexbox** and **Grid** are enabled simply by changing the `display` value.

### ⚠️ Important

The `display` property changes **how an element behaves**, not what the element is.

For example:

```html
<div></div>
```

will always remain a `<div>` element, even if you apply:

```css
display: inline;
```

Only its layout behavior changes.


---


## Block Elements

A **block element** starts on a **new line** and, by default, expands to occupy the **full available width** of its parent container.

Block elements are primarily used to structure the layout of a webpage.

### Default Behavior

When multiple block elements appear one after another, each starts on its own line.

```text
+-----------------------------+
|         Header              |
+-----------------------------+

+-----------------------------+
|        Paragraph            |
+-----------------------------+

+-----------------------------+
|         Footer              |
+-----------------------------+
```

Each element occupies its own row.

---

## Syntax

```css
selector {
    display: block;
}
```

---

## Common Block Elements

The following HTML elements are block-level by default:

| Element | Purpose |
|----------|---------|
| `<div>` | Generic container |
| `<p>` | Paragraph |
| `<h1>`–`<h6>` | Headings |
| `<section>` | Content section |
| `<article>` | Independent content |
| `<header>` | Header section |
| `<footer>` | Footer section |
| `<main>` | Main page content |
| `<nav>` | Navigation |
| `<aside>` | Sidebar |

---

## Characteristics

Block elements:

- Start on a new line.
- Expand to the available width by default.
- Respect `width` and `height`.
- Support `margin` and `padding` on all sides.
- Can contain both block and inline elements (subject to HTML content rules).

---

## Example

### HTML

```html
<div>First Box</div>
<div>Second Box</div>
<div>Third Box</div>
```

### CSS

```css
div {
    border: 2px solid royalblue;
    padding: 10px;
}
```

Result:

```text
+---------------------+
| First Box           |
+---------------------+

+---------------------+
| Second Box          |
+---------------------+

+---------------------+
| Third Box           |
+---------------------+
```

Each `<div>` automatically begins on a new line.

---

## Changing an Inline Element to Block

Even inline elements can become block elements.

```html
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
```

```css
span {
    display: block;
}
```

Result:

```text
HTML

CSS

JavaScript
```

Each `<span>` now occupies its own line.

---

## Width Behavior

Without specifying a width:

```css
div {
    display: block;
}
```

The element stretches across the available horizontal space.

To limit its width:

```css
div {
    width: 300px;
}
```

---

## Advantages

- Easy to build page layouts.
- Supports explicit width and height.
- Ideal for sections, containers, and structural elements.
- Works naturally with the Box Model.

---

## Limitations

- Always starts on a new line.
- Cannot sit beside another block element without additional layout techniques (such as Flexbox, Grid, or other positioning methods).
- May occupy more horizontal space than necessary if no width is specified.

> 💡 **Pro Tip:** Use block elements for the main structure of your webpage—headers, sections, articles, sidebars, and containers are all natural candidates.

### 🌍 Real-World Usage

Block elements are commonly used for:

- Page headers
- Navigation sections
- Hero banners
- Content containers
- Blog posts
- Cards
- Footers

Almost every webpage begins with a hierarchy of block elements.

### 📌 Did You Know?

Even though block elements usually occupy the full available width, you can control their size using properties such as:

```css
width
max-width
min-width
```

This makes them highly flexible for responsive layouts.

### ⚠️ Important

A block element's default width is typically **`auto`**, which means it expands to fill the available horizontal space in its containing block.

It does **not** automatically become `100%`; instead, the browser calculates the width based on the available space.

### 🎯 Interview Insight

A common interview question is:

> **What are the characteristics of a block element?**

A strong answer is:

- Starts on a new line.
- Occupies the available width by default.
- Supports width and height.
- Supports margins and padding.
- Commonly used for page structure and layout.


---


## Inline Elements

An **inline element** flows **within a line of text** and occupies **only the space required by its content**.

Unlike block elements, inline elements do **not** start on a new line.

They are commonly used to style or mark up small portions of text within a larger block of content.

---

## Default Behavior

Multiple inline elements appear on the same line if there is enough horizontal space.

```text
HTML   CSS   JavaScript
```

Instead of:

```text
HTML

CSS

JavaScript
```

---

## Syntax

```css
selector {
    display: inline;
}
```

---

## Common Inline Elements

The following HTML elements are inline by default:

| Element | Purpose |
|----------|---------|
| `<span>` | Generic inline container |
| `<a>` | Hyperlink |
| `<strong>` | Strong importance |
| `<em>` | Emphasized text |
| `<b>` | Bold text |
| `<i>` | Italic text |
| `<code>` | Inline code |
| `<small>` | Smaller text |
| `<mark>` | Highlighted text |
| `<label>` | Form label |

---

## Characteristics

Inline elements:

- Stay on the same line whenever possible.
- Occupy only the space required by their content.
- Do **not** start on a new line.
- Ignore `width` and `height` in normal layout.
- Support horizontal padding and margins.
- Can have vertical padding and borders, but they generally do not affect line placement the way block elements do.

---

## Example

### HTML

```html
<span>HTML</span>
<span>CSS</span>
<span>JavaScript</span>
```

### CSS

```css
span {
    border: 1px solid royalblue;
    padding: 5px;
}
```

Result:

```text
+----+  +---+  +-----------+
|HTML|  |CSS|  |JavaScript |
+----+  +---+  +-----------+
```

All three elements remain on the same line.

---

## Width and Height

Consider:

```css
span {
    width: 300px;
    height: 100px;
}
```

These properties generally have **no effect** on a normal inline element's layout.

This is one of the biggest differences between **block** and **inline** elements.

---

## Converting a Block Element to Inline

Even block elements can become inline.

```html
<div>HTML</div>
<div>CSS</div>
<div>JavaScript</div>
```

```css
div {
    display: inline;
}
```

Result:

```text
HTML CSS JavaScript
```

The `<div>` elements now flow on the same line.

---

## Advantages

- Ideal for styling text within paragraphs.
- Occupies only the required space.
- Flows naturally with surrounding content.
- Useful for links, labels, and inline formatting.

---

## Limitations

- Does not start on a new line.
- `width` and `height` generally do not affect normal inline layout.
- Not suitable for building larger page structures.

> 💡 **Pro Tip:** Use inline elements for **content inside a sentence**, not for creating page sections or containers.

### 🌍 Real-World Usage

Inline elements are commonly used for:

- Hyperlinks
- Highlighted words
- Bold and italic text
- Inline code snippets
- Form labels
- Icons placed within text

They enhance or annotate content without interrupting the flow of the document.

### 📌 Did You Know?

Many interactive elements, such as links (`<a>`), are inline by default. Developers often change them to `inline-block` or `block` when they need additional layout control, such as setting dimensions or creating larger clickable areas.

### ⚠️ Important

Although inline elements can have padding and borders, using large vertical values may affect the appearance of surrounding text because they remain part of the same line formatting context.

### 🎯 Interview Insight

A common interview question is:

> **What are the characteristics of an inline element?**

A strong answer is:

- Does not start on a new line.
- Occupies only the space required by its content.
- Flows with surrounding text.
- Generally ignores `width` and `height`.
- Commonly used for styling or marking up text within larger content.


---


## Inline-Block Elements

An **inline-block element** combines the characteristics of both **inline** and **block** elements.

Like an inline element, it **does not start on a new line**.

Like a block element, it **supports explicit width and height**.

This makes `inline-block` useful when you want multiple elements to appear on the same line while still controlling their dimensions.

---

## Syntax

```css
selector {
    display: inline-block;
}
```

---

## Behavior

An inline-block element:

- Stays on the same line when there is enough space.
- Occupies only the required horizontal space by default.
- Supports `width` and `height`.
- Supports margins and padding on all sides.
- Behaves like a block element internally while participating in inline layout.

---

## Visual Representation

```text
+---------+  +---------+  +---------+
| Card 1  |  | Card 2  |  | Card 3  |
+---------+  +---------+  +---------+
```

Unlike block elements, these boxes remain on the same line.

Unlike inline elements, each box can have its own width and height.

---

## Example

### HTML

```html
<div class="box">HTML</div>
<div class="box">CSS</div>
<div class="box">JavaScript</div>
```

### CSS

```css
.box {
    display: inline-block;
    width: 120px;
    height: 80px;
    border: 2px solid royalblue;
    padding: 10px;
    margin: 10px;
}
```

Result:

```text
+-----------+  +-----------+  +-----------+
|   HTML    |  |    CSS    |  | JavaScript|
+-----------+  +-----------+  +-----------+
```

All three boxes appear on the same line while maintaining their own dimensions.

---

## Width and Height

Unlike normal inline elements:

```css
.box {
    display: inline-block;
    width: 200px;
    height: 100px;
}
```

Both properties are fully respected.

This is one of the biggest advantages of `inline-block`.

---

## Comparison

| Feature | Inline | Inline-Block |
|---------|--------|--------------|
| Starts on a new line | ❌ No | ❌ No |
| Supports width | ❌ Generally No | ✅ Yes |
| Supports height | ❌ Generally No | ✅ Yes |
| Flows with surrounding elements | ✅ Yes | ✅ Yes |

---

## Advantages

- Allows elements to appear on the same line.
- Supports explicit width and height.
- Supports margins and padding.
- Useful for small reusable UI components.

---

## Limitations

- Whitespace between inline-block elements in HTML can create small gaps.
- Aligning multiple inline-block elements can become cumbersome compared to Flexbox.
- Modern layouts typically favor Flexbox or Grid for complex alignment.

> 💡 **Pro Tip:** Although `inline-block` is still useful, many modern layouts that previously relied on it are now implemented using **Flexbox**, which provides more powerful alignment and spacing controls.

### 🌍 Real-World Usage

`inline-block` has traditionally been used for:

- Navigation menus
- Buttons
- Badges
- Small cards
- Icon groups
- Tags and labels

While still valid, many of these use cases are now handled more conveniently with Flexbox.

### 📌 Did You Know?

Before Flexbox became widely supported, `inline-block` was one of the primary techniques for placing multiple elements side by side while retaining control over their dimensions.

### ⚠️ Important

If you place multiple `inline-block` elements on separate lines in your HTML, the whitespace between them may create visible gaps.

Example:

```html
<div class="box"></div>
<div class="box"></div>
```

The space or line break between the elements can affect the rendered layout. Flexbox and Grid do not have this specific whitespace behavior.

### 🎯 Interview Insight

A common interview question is:

> **When would you use `inline-block` instead of `inline`?**

A strong answer is:

> Use `inline-block` when you want elements to remain on the same line while still being able to set their width and height. Unlike `inline`, `inline-block` fully supports sizing and behaves more like a block element internally.


---


## `display: none`

The value:

```css
display: none;
```

completely removes an element from the webpage layout.

The browser behaves as if the element **does not exist**.

Unlike other display values, the element:

- Is not rendered.
- Does not occupy any space.
- Does not affect the layout of surrounding elements.

---

## Syntax

```css
selector {
    display: none;
}
```

---

## Example

### HTML

```html
<div>First</div>

<div class="hidden">
    Hidden Element
</div>

<div>Third</div>
```

### CSS

```css
.hidden {
    display: none;
}
```

Result:

```text
First

Third
```

The hidden element disappears completely.

---

## Layout Behavior

Without `display: none`:

```text
+---------+
| First   |
+---------+

+---------+
| Hidden  |
+---------+

+---------+
| Third   |
+---------+
```

With `display: none`:

```text
+---------+
| First   |
+---------+

+---------+
| Third   |
+---------+
```

The surrounding elements move together because the hidden element no longer occupies space.

---

## Common Use Cases

`display: none` is commonly used for:

- Hiding menus
- Mobile navigation
- Pop-up dialogs before opening
- Tabs
- Accordions
- Loading screens
- Conditional UI components

JavaScript often changes:

```css
display: none;
```

to:

```css
display: block;
```

or

```css
display: flex;
```

to show an element dynamically.

---

## Example with JavaScript

```html
<button onclick="showBox()">
    Show
</button>

<div id="box">
    Hello!
</div>
```

```css
#box {
    display: none;
}
```

```javascript
function showBox() {
    document.getElementById("box").style.display = "block";
}
```

Initially:

```text
Button
```

After clicking:

```text
Button

Hello!
```

---

## Advantages

- Completely removes elements from the layout.
- Prevents hidden elements from occupying space.
- Ideal for interactive interfaces.
- Simple to toggle with JavaScript.

---

## Limitations

- Hidden elements cannot be interacted with while `display: none` is applied.
- Showing and hiding elements may affect the surrounding layout because other elements shift to fill the available space.

> 💡 **Pro Tip:** Use `display: none` when an element should not participate in the layout at all. If you only want to make an element invisible while keeping its space reserved, a different property such as `visibility` is more appropriate (covered in a later chapter).

### 🌍 Real-World Usage

`display: none` is frequently used in:

- Dropdown menus
- Mobile navigation drawers
- Search panels
- Modal dialogs
- Expandable FAQ sections
- Shopping cart sidebars
- Responsive layouts

Many interactive web applications rely on this property to show and hide interface elements.

### 📌 Did You Know?

Many CSS frameworks include utility classes similar to:

```css
.hidden {
    display: none;
}
```

These classes make it easy to hide or reveal elements without writing additional CSS.

### ⚠️ Important

Applying:

```css
display: none;
```

removes the element from the normal document flow.

When the element becomes visible again, the browser recalculates the layout to accommodate it.

### 🎯 Interview Insight

A common interview question is:

> **What does `display: none` do?**

A strong answer is:

> `display: none` removes an element from the document layout. The element is not rendered, occupies no space, and surrounding elements behave as though it does not exist.


---


## `display: contents`

The value:

```css
display: contents;
```

removes an element's **own box** from the layout while **keeping its child elements** in the document flow.

Unlike:

```css
display: none;
```

the children are still rendered and displayed normally.

Think of it as making the **container disappear**, but leaving everything inside it visible.

---

## Syntax

```css
selector {
    display: contents;
}
```

---

## Example

### HTML

```html
<div class="wrapper">
    <p>HTML</p>
    <p>CSS</p>
    <p>JavaScript</p>
</div>
```

### Default Layout

```text
Wrapper

+----------------------+
| HTML                 |
| CSS                  |
| JavaScript           |
+----------------------+
```

---

### CSS

```css
.wrapper {
    display: contents;
}
```

Result:

```text
HTML

CSS

JavaScript
```

The wrapper no longer creates its own box.

The child paragraphs remain visible.

---

## How It Works

Normally:

```text
Wrapper
   │
   ├── HTML
   ├── CSS
   └── JavaScript
```

With:

```css
display: contents;
```

the browser behaves as though the wrapper's box doesn't exist.

```text
HTML

CSS

JavaScript
```

The children participate directly in the surrounding layout.

---

## Common Use Cases

`display: contents` can be useful when:

- Removing unnecessary wrapper elements.
- Simplifying layouts.
- Working with Grid and Flexbox while preserving child placement.
- Reducing extra layout boxes created by container elements.

---

## Advantages

- Removes unnecessary layout boxes.
- Keeps child elements visible.
- Allows children to participate directly in the parent layout.
- Can simplify certain Flexbox and Grid structures.

---

## Limitations

- The element itself no longer generates a box, so properties such as background, border, padding, and margin on that element have no visible effect.
- Browser behavior and accessibility support have historically varied, so testing is recommended before relying on it in production.

> 💡 **Pro Tip:** Use `display: contents` only when the wrapper element has no visual styling of its own and exists primarily for document structure.

### 🌍 Real-World Usage

`display: contents` is occasionally used in:

- Advanced Grid layouts
- Advanced Flexbox layouts
- Component-based UI libraries
- Layout refactoring where extra wrapper boxes interfere with positioning

It is much less common than `block`, `inline`, `flex`, or `grid`.

### 📌 Did You Know?

If an element uses:

```css
display: contents;
```

properties such as:

```css
background
border
padding
margin
```

applied to that element will generally have no visible effect because the element no longer generates a box.

Its child elements continue to render normally.

### ⚠️ Important

Do **not** confuse:

```css
display: none;
```

with:

```css
display: contents;
```

| `display: none` | `display: contents` |
|-----------------|---------------------|
| Removes the element | Removes only the element's box |
| Removes child elements from rendering | Child elements remain visible |
| Occupies no layout space | Children still participate in layout |

### 🎯 Interview Insight

A common interview question is:

> **What is the difference between `display: none` and `display: contents`?**

A strong answer is:

> `display: none` removes both the element and its children from rendering. `display: contents` removes only the element's own box while leaving its child elements visible and participating in the layout.