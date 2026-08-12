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

---

# What Are Media Queries?

**Media Queries** are a CSS feature that allows styles to be applied conditionally based on the characteristics of the device, viewport, or browsing environment.

They are mainly used to create **responsive layouts** that can adapt to different screen sizes and device conditions.

A basic media query looks like this:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
    }
}
```

In this example, the CSS rule inside the media query is applied when the viewport width is `600px` or less.

---

## Basic Concept

A media query allows CSS to check whether a particular condition is true.

The basic structure is:

```css
@media (condition) {
    /* CSS rules */
}
```

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

Here, the browser checks the following condition:

```text
Is the viewport width 768px or less?
```

If the condition is true, the CSS rules inside the media query are applied.

If the condition is false, those rules are not applied.

---

## Media Queries Are Conditional CSS

A normal CSS rule is applied whenever its selector matches an element.

For example:

```css
.container {
    width: 80%;
}
```

A media query adds an additional condition:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

The `.container` will have a width of `100%` only when the viewport width is `768px` or less.

This can be visualized as:

```text
CSS Rule
   │
   ▼
Condition Checked
   │
   ├── True  → Apply CSS
   │
   └── False → Do Not Apply CSS
```

---

## Media Queries and Responsive Design

Media queries are one of the fundamental tools used to create responsive websites.

A responsive website can change its layout depending on the available screen space.

For example, a desktop layout may display items horizontally:

```text
┌──────────┐  ┌──────────┐  ┌──────────┐
│  Item 1  │  │  Item 2  │  │  Item 3  │
└──────────┘  └──────────┘  └──────────┘
```

On a smaller screen, the same items can be arranged vertically:

```text
┌──────────┐
│  Item 1  │
└──────────┘
      ↓
┌──────────┐
│  Item 2  │
└──────────┘
      ↓
┌──────────┐
│  Item 3  │
└──────────┘
```

This can be achieved using a media query:

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

The HTML structure can remain unchanged while the CSS layout adapts to the viewport.

---

## Common Characteristics Checked by Media Queries

Media queries can be used to check different characteristics of the browsing environment.

Common examples include:

- Viewport width
- Viewport height
- Device orientation
- Display characteristics
- User preferences

For example:

```css
@media (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This rule is applied when the viewport is in landscape orientation.

---

## Media Queries Do Not Require Separate HTML Pages

A media query allows the same webpage to adapt to different conditions.

For example, the same HTML can be used for both desktop and mobile layouts:

```html
<div class="container">
    <div class="box">One</div>
    <div class="box">Two</div>
    <div class="box">Three</div>
</div>
```

The layout can then be changed with CSS:

```css
.container {
    display: flex;
}

@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

The HTML remains the same.

Only the CSS presentation changes according to the viewport condition.

---

## Media Query Example

Consider a navigation menu:

```css
.nav {
    display: flex;
    gap: 20px;
}
```

On a smaller screen, the navigation can be changed to a vertical layout:

```css
@media (max-width: 600px) {
    .nav {
        flex-direction: column;
    }
}
```

The result can be visualized as:

```text
Large Screen:

Home    About    Services    Contact


Small Screen:

Home
About
Services
Contact
```

This is one of the common ways media queries are used in responsive web development.

---

> 💡 **Pro Tip:** Think of a media query as a condition that tells CSS when a particular set of styles should be used.

---

> 💡 **Remember:** A media query is a conditional CSS feature that allows different styles to be applied when specific conditions of the viewing environment are satisfied.

---

## Why Are Media Queries Important?

Media queries are important because they allow CSS to adapt a webpage's layout and appearance to different screen sizes and viewing conditions.

Modern websites are accessed from many different devices, including:

- Mobile phones
- Tablets
- Laptops
- Desktop computers
- Large displays

Each device can have a different viewport size. A layout that works well on a large desktop screen may not work well on a smaller mobile screen.

Media queries allow CSS to respond to these differences and create responsive layouts.

---

## Responsive Design

One of the main reasons media queries are important is that they help create responsive websites.

A responsive website can change its layout according to the available screen space.

For example, a desktop layout may display three columns:

```text
┌────────────┬────────────┬────────────┐
│   Column 1 │   Column 2 │   Column 3 │
└────────────┴────────────┴────────────┘
```

On a smaller screen, the same columns can be arranged vertically:

```text
┌────────────┐
│   Column 1 │
├────────────┤
│   Column 2 │
├────────────┤
│   Column 3 │
└────────────┘
```

This can be achieved using a media query:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

The HTML structure can remain the same while the CSS layout changes according to the viewport size.

---

## Better User Experience

Media queries help improve the user experience by making websites easier to use on different devices.

For example, a navigation menu that fits comfortably on a desktop screen may not fit properly on a mobile screen.

```css
.navigation {
    display: flex;
    gap: 20px;
}

@media (max-width: 600px) {
    .navigation {
        flex-direction: column;
        gap: 10px;
    }
}
```

The navigation can therefore change its layout when the available screen width becomes smaller.

---

## Better Readability

Media queries can be used to adjust typography for different screen sizes.

For example:

```css
h1 {
    font-size: 40px;
}

@media (max-width: 600px) {
    h1 {
        font-size: 28px;
    }
}
```

On larger screens, the heading can use a larger font size.

On smaller screens, the font size can be reduced to make better use of the available space.

---

## Better Use of Available Space

Different devices provide different amounts of available screen space.

Media queries allow elements to use that space more effectively.

For example:

```css
.container {
    width: 80%;
}

@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}
```

The container can use a larger portion of the available viewport width on smaller screens.

---

## Adapting Components

Media queries can also be used to change individual components.

For example, cards may appear in a row on a larger screen:

```text
┌─────────┐  ┌─────────┐  ┌─────────┐
│  Card 1 │  │  Card 2 │  │  Card 3 │
└─────────┘  └─────────┘  └─────────┘
```

On a smaller screen, the cards can be displayed vertically:

```text
┌─────────┐
│  Card 1 │
└─────────┘

┌─────────┐
│  Card 2 │
└─────────┘

┌─────────┐
│  Card 3 │
└─────────┘
```

This allows components to remain usable across different screen sizes.

---

## Working With Flexbox and Grid

Media queries are commonly used together with CSS layout systems such as Flexbox and Grid.

For example, Flexbox can change from a horizontal layout to a vertical layout:

```css
.container {
    display: flex;
    gap: 20px;
}

@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }
}
```

Grid can also change the number of columns:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

This makes it easier to create layouts that work across different screen sizes.

---

## Supporting Different Orientations

Media queries can also respond to the orientation of the viewport.

For example:

```css
@media (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This allows the design to respond differently when the viewport is in landscape orientation.

---

## One Website for Different Devices

Media queries make it possible to maintain one website while adapting its presentation for different devices.

```text
                 Same HTML
                     ↓
                    CSS
                     ↓
              Media Queries
                     ↓
          ┌──────────┼──────────┐
          ↓          ↓          ↓
       Mobile      Tablet     Desktop
```

The same HTML structure can therefore be styled differently depending on the conditions of the viewing environment.

This makes responsive development easier to maintain than creating completely separate layouts for every device.

---

## Common Areas Where Media Queries Are Useful

Media queries can be used to adapt many parts of a webpage, including:

- Layouts
- Navigation
- Typography
- Spacing
- Images
- Components
- Columns
- Flexbox layouts
- Grid layouts

For example, a webpage may use:

```text
Large screens
     ↓
Multiple columns

Medium screens
     ↓
Fewer columns

Small screens
     ↓
Single column
```

This allows the layout to respond naturally to the available space.

---

## Media Queries and Maintainability

Media queries can make responsive CSS easier to organize because different responsive changes can be grouped together.

For example:

```css
.card {
    width: 300px;
    padding: 20px;
}

@media (max-width: 768px) {
    .card {
        width: 100%;
        padding: 15px;
    }
}
```

The base styles define the normal appearance, while the media query contains the changes required for smaller screens.

This approach helps keep responsive behavior close to the CSS that controls the design.

---

> 💡 **Pro Tip:** Use media queries when the layout or presentation needs to change because of the available space or viewing conditions, rather than targeting specific device names.

---

> 💡 **Remember:** Media queries are important because they allow websites to adapt their layouts, typography, navigation, components, spacing, and other styles to different screen sizes and viewing conditions.

---

## Media Query Syntax

A media query uses the `@media` rule to apply CSS styles only when a specified condition is satisfied.

The basic syntax is:

```css
@media (condition) {
    /* CSS rules */
}
```

The browser evaluates the condition.

If the condition is true, the CSS rules inside the media query are applied.

If the condition is false, those rules are not applied.

Conceptually:

```text
@media
   ↓
Condition
   ↓
Is the condition true?
   ├── Yes → Apply the CSS rules
   │
   └── No  → Do not apply the CSS rules
```

---

## Basic Media Query

A simple media query can check the width of the viewport.

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

In this example, the style inside the media query is applied when the viewport width is `600px` or less.

The media query can be understood as:

```text
Viewport width
      ↓
Is it 600px or less?
      ↓
     Yes
      ↓
Apply the CSS rules
```

If the viewport is wider than `600px`, the condition is not satisfied and the styles inside the media query are not applied.

---

## Understanding the `@media` Rule

The `@media` rule starts a media query.

It tells the browser that the following CSS rules should be applied only when a specified condition is satisfied.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

The structure can be understood as:

```text
@media
   ↓
Start media query

(max-width: 600px)
   ↓
Condition

{
    CSS rules
}
   ↓
Rules applied when the condition is true
```

---

## Understanding the Condition

The condition determines when the CSS rules inside the media query should be applied.

For example:

```css
(max-width: 600px)
```

checks the viewport width.

It can be understood as:

```text
Viewport width
      ↓
600px or less?
      ├── Yes → Apply styles
      │
      └── No  → Do not apply styles
```

The condition can use different media features such as:

- `max-width`
- `min-width`
- `orientation`
- `height`

These media features will be covered in more detail later in the chapter.

---

## Understanding the CSS Block

The curly braces contain the CSS rules that should be applied when the condition is satisfied.

For example:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
    }

    h1 {
        font-size: 28px;
    }
}
```

When the condition is true, both CSS rules are applied.

Conceptually:

```text
max-width: 600px
       ↓
Condition is true
       ↓
┌──────────────────────┐
│ body → 14px          │
│ h1   → 28px          │
└──────────────────────┘
```

A single media query can therefore contain multiple CSS rules.

---

## Media Queries With Normal CSS

Media queries are normally written together with regular CSS rules.

For example:

```css
.container {
    width: 80%;
    margin: auto;
}

@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}
```

The normal CSS rule provides the default styling.

When the viewport becomes `600px` or smaller, the media query changes the width.

The process can be represented as:

```text
Default CSS
    ↓
width: 80%

Smaller viewport
    ↓
Media Query
    ↓
width: 95%
```

This pattern is commonly used when creating responsive layouts.

---

## Using `min-width`

The `min-width` media feature checks whether the viewport width is at least the specified value.

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition means:

```text
Viewport width >= 768px
        ↓
       True
        ↓
Apply the styles
```

Therefore, the styles are applied when the viewport is `768px` or wider.

---

## Using `max-width`

The `max-width` media feature checks whether the viewport width is at most the specified value.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

The condition means:

```text
Viewport width <= 768px
        ↓
       True
        ↓
Apply the styles
```

Therefore, the styles are applied when the viewport is `768px` or narrower.

---

## `min-width` vs `max-width`

These two media features work in opposite directions.

```text
min-width
    ↓
At or above the specified width
```

```text
max-width
    ↓
At or below the specified width
```

For example:

```css
@media (min-width: 768px) {
    /* 768px and wider */
}
```

```css
@media (max-width: 768px) {
    /* 768px and narrower */
}
```

A simple mental model is:

```text
min-width
    ↓
Minimum viewport width

max-width
    ↓
Maximum viewport width
```

---

## Media Queries With Multiple CSS Rules

A media query can contain multiple CSS declarations and multiple selectors.

For example:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
        margin: 10px;
    }

    h1 {
        font-size: 28px;
    }

    .container {
        width: 95%;
    }
}
```

When the condition is satisfied, all of these rules can be applied.

Conceptually:

```text
Media Query
     ↓
┌─────────────────────────┐
│ Typography              │
│ Spacing                 │
│ Container width         │
└─────────────────────────┘
```

This makes media queries useful when several parts of a layout need to change together.

---

## Media Query With a Media Type

A media query can also include a media type.

For example:

```css
@media screen and (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

Here:

```text
screen
   ↓
Media Type

and
   ↓
Logical Operator

(max-width: 600px)
   ↓
Condition
```

The media type and logical operator will be covered in more detail in later sections.

---

## Media Query Without a Media Type

The media type can be omitted.

For example:

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

This is a common form of media query syntax.

The browser evaluates the condition and applies the styles when the condition matches.

---

## Multiple Media Queries

A stylesheet can contain multiple media queries.

For example:

```css
.container {
    width: 95%;
}

@media (min-width: 600px) {
    .container {
        width: 85%;
    }
}

@media (min-width: 1000px) {
    .container {
        width: 75%;
    }
}
```

The layout can therefore change as the viewport becomes wider.

```text
Small viewport
     ↓
width: 95%

Medium viewport
     ↓
width: 85%

Large viewport
     ↓
width: 75%
```

This allows different responsive styles to be applied at different viewport sizes.

---

## Media Queries and Responsive Layouts

Media queries are especially useful when a layout needs to change its structure.

For example, a navigation layout may use a horizontal arrangement on larger screens:

```text
┌────────┬────────┬────────┬────────┐
│  Home  │ About  │Contact │ Login  │
└────────┴────────┴────────┴────────┘
```

On a smaller screen, the same navigation can become vertical:

```text
┌──────────┐
│   Home   │
├──────────┤
│  About   │
├──────────┤
│ Contact  │
├──────────┤
│  Login   │
└──────────┘
```

The HTML structure can remain the same while the CSS changes through a media query.

---

## Media Queries With Flexbox

Media queries are commonly used together with Flexbox.

For example:

```css
.container {
    display: flex;
    gap: 20px;
}

@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

On a larger screen:

```text
┌──────────┐  ┌──────────┐
│  Item 1  │  │  Item 2  │
└──────────┘  └──────────┘
```

On a smaller screen:

```text
┌──────────┐
│  Item 1  │
└──────────┘
      ↓
┌──────────┐
│  Item 2  │
└──────────┘
```

The media query changes the Flexbox direction when the viewport becomes smaller.

---

## Media Queries With Grid

Media queries can also change the number of Grid columns.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 768px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

On a larger screen:

```text
┌───────┬───────┬───────┐
│   1   │   2   │   3   │
└───────┴───────┴───────┘
```

On a smaller screen:

```text
┌───────┐
│   1   │
├───────┤
│   2   │
├───────┤
│   3   │
└───────┘
```

The media query allows the Grid layout to adapt to the available space.

---

## Media Query Syntax and the CSS Cascade

Media queries are part of CSS, so normal CSS cascade rules still apply.

For example:

```css
.box {
    width: 300px;
}

@media (max-width: 600px) {
    .box {
        width: 100%;
    }
}
```

When the viewport is `600px` or smaller, the media query matches and its declaration can change the width.

The basic flow is:

```text
Normal CSS
    ↓
width: 300px
    ↓
Viewport becomes 600px or smaller
    ↓
Media query matches
    ↓
width: 100%
```

Specificity and source order still matter when multiple CSS declarations apply to the same element.

---

## Common Mistake: Confusing `min-width` and `max-width`

A common mistake is confusing the direction of `min-width` and `max-width`.

For example:

```css
@media (max-width: 600px) {
    /* Smaller viewport */
}
```

means:

```text
600px or smaller
```

Whereas:

```css
@media (min-width: 600px) {
    /* Larger viewport */
}
```

means:

```text
600px or larger
```

Remember:

```text
max-width
    ↓
At or below

min-width
    ↓
At or above
```

---

## Practical Mental Model

A useful way to understand media query syntax is to think of it as a decision.

```text
                Media Query
                     ↓
              Check condition
                     ↓
             Is it satisfied?
               ↙          ↘
             Yes           No
              ↓             ↓
        Apply CSS       Ignore CSS
```

For example:

```css
@media (max-width: 600px) {
    .card {
        width: 100%;
    }
}
```

The browser effectively checks:

```text
Is viewport width <= 600px?
          ↓
      ┌───┴───┐
     Yes      No
      ↓        ↓
Apply CSS   Ignore CSS
```

This mental model becomes especially useful when working with multiple conditions and logical operators.

---

> 💡 **Pro Tip:** Read a media query as a condition. Instead of memorizing the syntax, ask yourself: **"Under what condition should these CSS rules be applied?"**

---

> 💡 **Remember:** A media query starts with `@media`, contains a condition, and includes CSS rules that are applied when that condition is satisfied.

---

## Media Types

Media types describe the general category of media for which a CSS style is intended.

A media query can use a media type together with media features to determine when CSS rules should be applied.

The basic structure is:

```css
@media media-type {
    /* CSS rules */
}
```

For example:

```css
@media screen {
    body {
        font-size: 16px;
    }
}
```

Here, `screen` is the media type.

---

## Common Media Types

CSS media queries provide several media types, including:

- `all`
- `screen`
- `print`

These media types can be used to target different output environments.

Conceptually:

```text
Media Types
     ↓
┌─────────┬──────────┬─────────┐
│   all   │  screen  │  print  │
└─────────┴──────────┴─────────┘
```

---

## `all`

The `all` media type matches all devices.

For example:

```css
@media all {
    body {
        font-family: Arial, sans-serif;
    }
}
```

This media type is useful when the styles are intended to apply across all media types.

In many situations, the media type can simply be omitted because `all` is the default media type.

For example:

```css
@media (max-width: 600px) {
    body {
        font-size: 14px;
    }
}
```

This is effectively targeting the default `all` media type together with the specified condition.

---

## `screen`

The `screen` media type is used for devices with screens.

For example:

```css
@media screen {
    body {
        background-color: white;
    }
}
```

A screen can include devices such as:

- Mobile phones
- Tablets
- Laptops
- Desktop computers

The `screen` media type is commonly seen when a stylesheet also contains styles specifically intended for printed documents.

---

## `print`

The `print` media type is used when a document is printed or prepared for print output.

For example:

```css
@media print {
    body {
        color: black;
        background: white;
    }
}
```

Print styles can be used to create a more suitable version of a webpage for printing.

For example, a navigation menu may not be useful on a printed page.

```css
@media print {
    .navigation {
        display: none;
    }
}
```

This hides the navigation when the document is printed.

---

## Screen vs Print

A webpage may need different styles for screen viewing and printing.

For example:

```text
                 Webpage
                    ↓
          ┌─────────┴─────────┐
          ↓                   ↓
       Screen                Print
          ↓                   ↓
   Interactive layout     Printable layout
```

The CSS can therefore provide different presentations for the same document.

For example:

```css
body {
    font-family: Arial, sans-serif;
}

@media print {
    body {
        font-family: serif;
    }
}
```

The normal style is used for the webpage, while the print media query provides a different style for printed output.

---

## Combining Media Types With Media Features

A media type can be combined with a media feature.

For example:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

This contains two parts:

```text
screen
   ↓
Media Type

and
   ↓
Logical Operator

(max-width: 600px)
   ↓
Media Feature
```

The CSS is applied when the query matches the screen media type and the viewport width is `600px` or less.

---

## `screen` With `min-width`

Media types can also be combined with `min-width`.

For example:

```css
@media screen and (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition can be understood as:

```text
Is the output a screen?
        ↓
      Yes
        ↓
Is the viewport at least 768px?
        ↓
      Yes
        ↓
Apply the styles
```

---

## `print` With Media Features

Print styles can also use media features.

For example:

```css
@media print and (orientation: landscape) {
    .report {
        width: 100%;
    }
}
```

This allows print styles to be adjusted according to additional conditions.

Media features such as orientation will be discussed in more detail later.

---

## Using Separate Screen and Print Styles

A stylesheet can contain separate rules for screens and printing.

For example:

```css
.navigation {
    display: flex;
}

@media print {
    .navigation {
        display: none;
    }
}
```

On a screen:

```text
Navigation
    ↓
Visible
```

When printing:

```text
Navigation
    ↓
Hidden
```

This allows the same webpage to provide an appropriate presentation for different output environments.

---

## Practical Example: Printable Article

Consider an article page with navigation, content, and a footer.

```text
Screen
┌──────────────────────────────┐
│          Navigation          │
├──────────────────────────────┤
│                              │
│          Article             │
│                              │
├──────────────────────────────┤
│           Footer             │
└──────────────────────────────┘
```

For printing, some elements may not be necessary.

```css
@media print {
    .navigation,
    .footer {
        display: none;
    }
}
```

The printed version can therefore focus on the article content.

```text
Print
┌──────────────────────────────┐
│                              │
│          Article             │
│                              │
└──────────────────────────────┘
```

This is a practical use of the `print` media type.

---

## Why Media Types Matter

Media types allow CSS to distinguish between different output environments.

For example:

```text
Same HTML
    ↓
Different Media Types
    ↓
┌──────────────┬──────────────┐
│    Screen    │    Print     │
└──────────────┴──────────────┘
       ↓               ↓
Interactive        Printable
  design             design
```

This allows a single document to have different presentations without requiring separate HTML pages.

---

## Media Type vs Media Feature

A media type describes the general type of output.

A media feature describes a characteristic or condition of that output.

For example:

```css
@media screen and (max-width: 600px) {
    /* CSS rules */
}
```

Here:

```text
screen
   ↓
Media Type

max-width
   ↓
Media Feature
```

A useful mental model is:

```text
Media Type
    ↓
"What kind of output?"

Media Feature
    ↓
"What condition does it have?"
```

This distinction becomes important when writing more advanced media queries.

---

## Omitting the Media Type

The media type is optional in many common media queries.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

This is often preferred when the styles are intended for the normal screen-based presentation and no explicit media type is required.

Compared with:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

both forms can be useful, but the shorter form is common in responsive CSS.

---

## Quick Comparison

| Media Type | Purpose |
|------------|---------|
| `all` | Matches all media types |
| `screen` | Targets screen-based output |
| `print` | Targets printed output |

Example:

```css
@media screen {
    /* Screen styles */
}
```

```css
@media print {
    /* Print styles */
}
```

```css
@media all {
    /* Styles for all media types */
}
```

---

## Common Mistake

Do not confuse a media type with a media feature.

For example:

```css
@media screen and (max-width: 600px) {
    /* CSS rules */
}
```

Here:

```text
screen
    ↓
Media Type

max-width: 600px
    ↓
Media Feature
```

`screen` does not describe the viewport width.

`max-width` describes the viewport width condition.

---

> 💡 **Pro Tip:** Use a media type when you actually need to distinguish the output environment, such as screen and print. For many responsive layouts, a media feature such as `max-width` or `min-width` is enough.

---

> 💡 **Remember:** Media types describe the general output environment, such as `screen`, `print`, or `all`. Media features describe characteristics or conditions such as width, height, or orientation.

---

## Media Features

Media features describe specific characteristics of the device, browser, or viewing environment.

While a media type describes the general type of output, such as `screen` or `print`, a media feature describes a particular characteristic or condition.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

Here, `max-width` is a media feature.

It checks the available viewport width and determines whether the condition is satisfied.

Conceptually:

```text
Media Query
     ↓
Media Feature
     ↓
Check a characteristic
     ↓
Condition satisfied?
     ├── Yes → Apply CSS
     │
     └── No  → Do not apply CSS
```

---

## Media Type vs Media Feature

A media type describes the general type of output.

A media feature describes a specific characteristic of that output.

For example:

```css
@media screen and (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

The query can be divided into:

```text
screen
   ↓
Media Type

max-width: 600px
   ↓
Media Feature
```

A simple way to remember the difference is:

```text
Media Type
    ↓
"What kind of output is this?"

Media Feature
    ↓
"What characteristics or conditions does it have?"
```

---

## Common Media Features

CSS provides many media features that can be used to describe characteristics of the viewing environment.

Common examples include:

- `width`
- `min-width`
- `max-width`
- `height`
- `min-height`
- `max-height`
- `orientation`
- `aspect-ratio`
- `resolution`

Some media features describe viewport dimensions, while others describe characteristics such as orientation or display resolution.

---

## Width

The `width` media feature checks the width of the viewport.

For example:

```css
@media (width: 600px) {
    .container {
        width: 100%;
    }
}
```

The condition checks whether the viewport width is exactly `600px`.

Conceptually:

```text
Viewport width
      ↓
Exactly 600px?
      ↓
   ┌───┴───┐
  Yes      No
   ↓        ↓
Apply    Ignore
 CSS       CSS
```

Exact-value queries are less common in responsive design than range-based queries such as `min-width` and `max-width`.

---

## `min-width`

The `min-width` media feature checks whether the viewport width is at least a specified value.

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition means:

```text
Viewport width >= 768px
```

Therefore, the styles apply at `768px` and wider.

---

## `max-width`

The `max-width` media feature checks whether the viewport width is at most a specified value.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

The condition means:

```text
Viewport width <= 768px
```

Therefore, the styles apply at `768px` and narrower.

---

## Width Range

Media features can be combined to target a range of viewport widths.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

The condition can be understood as:

```text
Viewport width
      ↓
At least 600px?
      ↓
     Yes
      ↓
At most 1000px?
      ↓
     Yes
      ↓
Apply the styles
```

This allows a design to target a specific range rather than only a single minimum or maximum size.

---

## Height

The `height` media feature checks the height of the viewport.

For example:

```css
@media (height: 800px) {
    .container {
        min-height: 400px;
    }
}
```

This checks whether the viewport height is exactly `800px`.

As with exact width queries, exact height queries are less common than range-based conditions.

---

## `min-height`

The `min-height` media feature checks whether the viewport height is at least a specified value.

For example:

```css
@media (min-height: 700px) {
    .hero {
        min-height: 500px;
    }
}
```

The condition means:

```text
Viewport height >= 700px
        ↓
Apply the styles
```

This can be useful when a design needs to respond to available vertical space.

---

## `max-height`

The `max-height` media feature checks whether the viewport height is at most a specified value.

For example:

```css
@media (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The condition means:

```text
Viewport height <= 600px
        ↓
Apply the styles
```

This can be useful when the available vertical space becomes limited.

---

## Width and Height Together

Width and height conditions can be combined.

For example:

```css
@media (max-width: 768px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The styles are applied when both conditions are satisfied.

Conceptually:

```text
Viewport
   ↓
Width <= 768px?
   ↓
 Yes
   ↓
Height <= 600px?
   ↓
 Yes
   ↓
Apply CSS
```

This allows responsive styles to consider both horizontal and vertical space.

---

## Orientation

The `orientation` media feature checks whether the viewport is in portrait or landscape orientation.

There are two commonly used values:

```text
portrait
landscape
```

For example:

```css
@media (orientation: portrait) {
    .container {
        width: 95%;
    }
}
```

This applies when the viewport is in portrait orientation.

For landscape:

```css
@media (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

The basic relationship is:

```text
Orientation
     ↓
┌─────────────┬─────────────┐
│  portrait   │  landscape  │
└─────────────┴─────────────┘
```

---

## Portrait Orientation

Portrait orientation means the viewport is taller than it is wide.

Conceptually:

```text
┌──────────┐
│          │
│          │
│          │
│          │
│          │
└──────────┘
```

A media query can target portrait orientation:

```css
@media (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

This can be useful when the available horizontal space is limited.

---

## Landscape Orientation

Landscape orientation means the viewport is wider than it is tall.

Conceptually:

```text
┌────────────────────┐
│                    │
│                    │
└────────────────────┘
```

A media query can target landscape orientation:

```css
@media (orientation: landscape) {
    .navigation {
        flex-direction: row;
    }
}
```

This can be useful when more horizontal space is available.

---

## Aspect Ratio

The `aspect-ratio` media feature describes the ratio between the viewport's width and height.

For example:

```css
@media (aspect-ratio: 16 / 9) {
    .video {
        width: 100%;
    }
}
```

An aspect ratio can be represented as:

```text
Width : Height
   ↓
16 : 9
```

The `aspect-ratio` feature can be useful when a design needs to respond to the shape of the viewport rather than only its width or height.

---

## Minimum and Maximum Aspect Ratio

Aspect ratio can also be used with range conditions.

For example:

```css
@media (min-aspect-ratio: 16 / 9) {
    .container {
        width: 90%;
    }
}
```

And:

```css
@media (max-aspect-ratio: 4 / 3) {
    .container {
        width: 95%;
    }
}
```

These conditions allow CSS to respond to different viewport proportions.

---

## Resolution

The `resolution` media feature describes the resolution of the output device.

For example:

```css
@media (min-resolution: 2dppx) {
    .logo {
        background-image: url("logo-high-resolution.png");
    }
}
```

This can be useful when different assets or styles are needed for displays with different pixel densities.

The `resolution` feature is more specialized than common responsive features such as `min-width` and `max-width`.

---

## Combining Different Media Features

Multiple media features can be combined using logical operators.

For example:

```css
@media screen and (min-width: 768px) and (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

The query contains:

```text
screen
   ↓
Media Type

min-width: 768px
   ↓
Width Condition

orientation: landscape
   ↓
Orientation Condition
```

All conditions must match for the styles to apply.

---

## Media Features and Responsive Design

Media features are one of the main tools used to make responsive layouts.

A responsive layout can respond to:

```text
Viewport Width
      ↓
Viewport Height
      ↓
Orientation
      ↓
Aspect Ratio
      ↓
Resolution
      ↓
Responsive CSS
```

For example:

```css
.container {
    width: 80%;
}

@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}

@media (orientation: landscape) {
    .container {
        max-width: 1000px;
    }
}
```

Different media features can therefore control different aspects of the design.

---

## Practical Example

Consider a card layout that needs to adapt to different viewport conditions.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

@media (max-width: 900px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout changes as the available width decreases.

```text
Large viewport

┌───────┬───────┬───────┐
│ Card  │ Card  │ Card  │
└───────┴───────┴───────┘


Medium viewport

┌───────┬───────┐
│ Card  │ Card  │
├───────┼───────┤
│ Card  │ Card  │
└───────┴───────┘


Small viewport

┌───────┐
│ Card  │
├───────┤
│ Card  │
├───────┤
│ Card  │
└───────┘
```

This demonstrates how media features can be used to create layouts that adapt to available space.

---

## Choosing the Right Media Feature

Different design problems require different media features.

```text
Need to respond to width?
        ↓
Use width / min-width / max-width

Need to respond to height?
        ↓
Use height / min-height / max-height

Need to respond to orientation?
        ↓
Use orientation

Need to respond to viewport proportions?
        ↓
Use aspect-ratio

Need to respond to display resolution?
        ↓
Use resolution
```

This makes it easier to choose an appropriate condition instead of using the same media feature for every situation.

---

## Common Mistake

Do not assume that `min-width` and `max-width` are the only media features available.

Responsive design can also respond to:

- Height
- Orientation
- Aspect ratio
- Resolution
- Other media characteristics

However, width-based conditions are commonly used because many layout changes are primarily caused by limited horizontal space.

---

> 💡 **Pro Tip:** Choose a media feature based on the actual design problem. If the layout breaks because there is not enough horizontal space, use a width-based condition. If the problem is vertical space or orientation, use the corresponding media feature.

---

> 💡 **Remember:** Media features describe characteristics of the viewing environment. Common examples include `width`, `height`, `min-width`, `max-width`, `orientation`, `aspect-ratio`, and `resolution`.

---

## Width and Height

The `width` and `height` media features allow CSS to respond to the dimensions of the viewport.

Viewport dimensions are important in responsive design because the available horizontal and vertical space can change significantly between devices and window sizes.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

Here, `max-width` checks the available viewport width.

The basic relationship is:

```text
Viewport
    ↓
┌──────────────────────────────┐
│                              │
│          Content             │
│                              │
└──────────────────────────────┘
      ←──── Width ────→

             ↑
             │
           Height
             │
             ↓
```

---

## Viewport Width

The viewport width represents the horizontal space available to the webpage.

For example:

```text
←────────────── Viewport Width ──────────────→

┌─────────────────────────────────────────────┐
│                                             │
│                 Webpage                     │
│                                             │
└─────────────────────────────────────────────┘
```

A media query can use the viewport width to change the layout.

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

When the viewport becomes `768px` or smaller, the styles inside the media query are applied.

---

## Exact `width`

The `width` media feature can check for an exact viewport width.

For example:

```css
@media (width: 600px) {
    .container {
        width: 100%;
    }
}
```

This condition checks whether the viewport width is exactly `600px`.

Conceptually:

```text
Viewport width
      ↓
Exactly 600px?
   ┌──┴──┐
  Yes    No
   ↓      ↓
Apply   Ignore
 CSS      CSS
```

Exact width conditions are less common in responsive layouts because viewport sizes can vary continuously.

Range-based features such as `min-width` and `max-width` are generally more useful.

---

## `min-width`

The `min-width` media feature checks whether the viewport width is at least a specified value.

For example:

```css
@media (min-width: 768px) {
    .container {
        width: 80%;
    }
}
```

The condition means:

```text
Viewport width >= 768px
```

Therefore:

```text
600px
   ↓
Condition false

768px
   ↓
Condition true

900px
   ↓
Condition true
```

The styles apply when the viewport is `768px` or wider.

---

## `max-width`

The `max-width` media feature checks whether the viewport width is at most a specified value.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 95%;
    }
}
```

The condition means:

```text
Viewport width <= 768px
```

Therefore:

```text
500px
   ↓
Condition true

768px
   ↓
Condition true

900px
   ↓
Condition false
```

The styles apply when the viewport is `768px` or narrower.

---

## Comparing `min-width` and `max-width`

The difference can be visualized as:

```text
min-width: 768px

0px ─────────── 767px │ 768px ───────────────→
                       ↑
                    Apply CSS
```

```text
max-width: 768px

0px ───────────────── 768px │ 769px ─────────→
                       ↑
                    Apply CSS
```

A simple rule to remember is:

```text
min-width
    ↓
768px and above

max-width
    ↓
768px and below
```

---

## Using Width Ranges

A design may need to respond only within a specific width range.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

The condition requires both rules to be satisfied.

```text
Viewport width
      ↓
At least 600px?
      ↓
     Yes
      ↓
At most 1000px?
      ↓
     Yes
      ↓
Apply CSS
```

The range can be visualized as:

```text
0px        600px                  1000px       →
│────────────│──────────────────────│────────────│
             ↑                      ↑
          Start                    End
```

Only the viewport widths inside the specified range match the condition.

---

## Width and Responsive Layouts

Width-based media queries are commonly used to change the structure of a layout.

For example:

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (max-width: 900px) {
    .container {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .container {
        grid-template-columns: 1fr;
    }
}
```

The layout changes as the viewport becomes narrower.

Large viewport:

```text
┌────────┬────────┬────────┐
│   1    │   2    │   3    │
└────────┴────────┴────────┘
```

Medium viewport:

```text
┌────────┬────────┐
│   1    │   2    │
├────────┼────────┤
│   3    │   4    │
└────────┴────────┘
```

Small viewport:

```text
┌────────┐
│   1    │
├────────┤
│   2    │
├────────┤
│   3    │
└────────┘
```

This is one of the most common uses of width-based media queries.

---

## Viewport Height

The viewport height represents the vertical space available to the webpage.

For example:

```text
        ↑
        │
      Height
        │
        ↓

┌──────────────────┐
│                  │
│                  │
│     Webpage      │
│                  │
│                  │
└──────────────────┘
   ←──── Width ───→
```

Height-based media queries can be useful when the amount of vertical space affects the layout.

---

## Exact `height`

The `height` media feature can check for an exact viewport height.

For example:

```css
@media (height: 800px) {
    .hero {
        min-height: 400px;
    }
}
```

This condition matches when the viewport height is exactly `800px`.

Conceptually:

```text
Viewport height
      ↓
Exactly 800px?
   ┌──┴──┐
  Yes    No
   ↓      ↓
Apply   Ignore
 CSS      CSS
```

As with exact width conditions, exact height queries are less common than minimum and maximum height conditions.

---

## `min-height`

The `min-height` media feature checks whether the viewport height is at least a specified value.

For example:

```css
@media (min-height: 700px) {
    .hero {
        min-height: 500px;
    }
}
```

The condition means:

```text
Viewport height >= 700px
```

Therefore, the styles apply when there is at least `700px` of vertical viewport space.

---

## `max-height`

The `max-height` media feature checks whether the viewport height is at most a specified value.

For example:

```css
@media (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The condition means:

```text
Viewport height <= 600px
```

The styles apply when the available vertical space is limited.

---

## Comparing `min-height` and `max-height`

The difference is similar to `min-width` and `max-width`.

```text
min-height
    ↓
At or above the specified height
```

```text
max-height
    ↓
At or below the specified height
```

For example:

```css
@media (min-height: 700px) {
    /* 700px and taller */
}
```

```css
@media (max-height: 600px) {
    /* 600px and shorter */
}
```

---

## Width and Height Together

Width and height can be used together in the same media query.

For example:

```css
@media (max-width: 768px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The CSS is applied only when both conditions are satisfied.

Conceptually:

```text
Viewport
    ↓
Width <= 768px?
    ↓
   Yes
    ↓
Height <= 600px?
    ↓
   Yes
    ↓
Apply CSS
```

If either condition is false, the complete media query does not match.

---

## Practical Example: Limited Vertical Space

Consider a hero section with a large amount of padding.

```css
.hero {
    padding: 100px 20px;
}
```

On a viewport with limited height, this may consume too much vertical space.

A media query can reduce the padding:

```css
@media (max-height: 600px) {
    .hero {
        padding: 40px 20px;
    }
}
```

The result can be represented as:

```text
Normal height

┌──────────────────────────┐
│                          │
│       Large padding      │
│                          │
│        HERO CONTENT      │
│                          │
│       Large padding      │
│                          │
└──────────────────────────┘
```

With limited height:

```text
┌──────────────────────────┐
│      Smaller padding     │
│      HERO CONTENT        │
│      Smaller padding     │
└──────────────────────────┘
```

This prevents the hero section from consuming too much vertical space.

---

## Practical Example: Full-Screen Layout

A page may use a minimum height based on the viewport.

```css
.hero {
    min-height: 100vh;
}
```

A height-based media query can further adjust the design when the viewport becomes very short.

```css
@media (max-height: 600px) {
    .hero {
        min-height: auto;
        padding: 40px 20px;
    }
}
```

This gives the layout more flexibility when vertical space is limited.

---

## Width and Height With Flexbox

Width and height conditions can also work together with Flexbox.

For example:

```css
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-height: 100vh;
}

@media (max-height: 600px) {
    .container {
        justify-content: flex-start;
        padding-top: 30px;
    }
}
```

The normal layout centers the content vertically.

When the viewport becomes short, the layout moves the content toward the top.

Conceptually:

```text
Normal viewport
       ↓
┌───────────────┐
│               │
│               │
│    CONTENT    │
│               │
│               │
└───────────────┘
       ↓
    Centered


Short viewport
       ↓
┌───────────────┐
│    CONTENT    │
│               │
│               │
└───────────────┘
       ↓
    Top aligned
```

---

## Width and Height With Navigation

A navigation layout may also need to respond to both width and height.

For example:

```css
.navigation {
    padding: 20px;
}

@media (max-width: 600px) {
    .navigation {
        padding: 10px;
    }
}

@media (max-height: 500px) {
    .navigation {
        padding: 5px;
    }
}
```

Different conditions can therefore adjust the same component according to different constraints.

---

## Width vs Height

Width and height solve different responsive problems.

| Media Feature | Checks |
|---|---|
| `width` | Exact viewport width |
| `min-width` | Minimum viewport width |
| `max-width` | Maximum viewport width |
| `height` | Exact viewport height |
| `min-height` | Minimum viewport height |
| `max-height` | Maximum viewport height |

A useful mental model is:

```text
Horizontal space
       ↓
width
min-width
max-width

Vertical space
       ↓
height
min-height
max-height
```

---

## Choosing Width or Height

When deciding which feature to use, first identify what is causing the layout problem.

```text
Layout problem
      ↓
Is horizontal space the issue?
      ↓
     Yes
      ↓
Use width-based media features
```

Or:

```text
Layout problem
      ↓
Is vertical space the issue?
      ↓
     Yes
      ↓
Use height-based media features
```

This helps avoid adding unnecessary media queries.

---

## Common Mistake

Do not assume that every responsive change should be based on width.

Width is often the most important factor because layouts frequently become constrained horizontally, but some interfaces also depend heavily on vertical space.

For example:

```css
@media (max-height: 500px) {
    .hero {
        padding: 20px;
    }
}
```

This is useful when the problem is limited height rather than limited width.

---

## Another Common Mistake

Do not confuse CSS element dimensions with viewport media features.

For example:

```css
.container {
    width: 600px;
}
```

This changes the width of an element.

Whereas:

```css
@media (max-width: 600px) {
    .container {
        width: 100%;
    }
}
```

checks the viewport width before applying the CSS rule.

Conceptually:

```text
Element property
    ↓
Changes an element

Media feature
    ↓
Checks the viewing environment
```

---

> 💡 **Pro Tip:** Start by identifying whether your responsive problem comes from limited horizontal space or limited vertical space. Then choose a width-based or height-based media feature accordingly.

---

> 💡 **Remember:** `width`, `min-width`, and `max-width` respond to viewport width, while `height`, `min-height`, and `max-height` respond to viewport height. Use the feature that matches the actual responsive problem.

---

## Combining Conditions

Media queries can combine multiple conditions to create more specific responsive rules.

Instead of checking only one condition, a media query can check several conditions at the same time.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

This query checks two conditions:

```text
Viewport width
      ↓
At least 600px?
      ↓
     Yes
      ↓
At most 1000px?
      ↓
     Yes
      ↓
Apply the CSS
```

The styles are applied only when both conditions are satisfied.

---

## Why Combine Conditions?

A single media feature may not always be enough to describe the situation a layout needs to respond to.

For example:

```css
@media (max-width: 768px) {
    .container {
        width: 100%;
    }
}
```

This checks only the viewport width.

Sometimes a design needs to consider additional conditions such as:

- Minimum width
- Maximum width
- Height
- Orientation
- Media type
- Aspect ratio

Combining conditions allows CSS to target a more specific situation.

---

## Using `and`

The `and` operator is used to combine media conditions.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

The two conditions are:

```text
(min-width: 600px)
        AND
(max-width: 1000px)
```

Both must be true.

Conceptually:

```text
Condition 1
    ↓
   TRUE
    ↓
Condition 2
    ↓
   TRUE
    ↓
Apply CSS
```

If either condition is false, the complete media query does not match.

---

## Combining `min-width` and `max-width`

One of the most common combinations is:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

This creates a width range.

```text
0px          600px                 1000px          →
│──────────────│──────────────────────│──────────────│
               ↑                      ↑
            Minimum                Maximum
```

The styles apply between the specified limits.

Conceptually:

```text
600px ≤ viewport width ≤ 1000px
```

This is useful when a layout needs a specific design for medium-sized viewports.

---

## Combining Width and Height

Width and height conditions can also be combined.

For example:

```css
@media (max-width: 768px) and (max-height: 600px) {
    .hero {
        padding: 20px;
    }
}
```

The browser checks:

```text
Width <= 768px?
       ↓
      Yes
       ↓
Height <= 600px?
       ↓
      Yes
       ↓
Apply CSS
```

The CSS is therefore applied only when both the width and height conditions match.

---

## Combining a Media Type and a Feature

A media type can also be combined with a media feature.

For example:

```css
@media screen and (max-width: 600px) {
    .navigation {
        flex-direction: column;
    }
}
```

The query contains:

```text
screen
   ↓
Media Type

and
   ↓
Combines Conditions

(max-width: 600px)
   ↓
Media Feature
```

The CSS is applied when the query matches the screen media type and the viewport width is `600px` or less.

---

## Combining Multiple Features

More than two conditions can be combined.

For example:

```css
@media screen and (min-width: 768px) and (max-width: 1200px) and (orientation: landscape) {
    .container {
        width: 80%;
    }
}
```

This query contains three conditions:

```text
screen
   ↓
Media Type

min-width: 768px
   ↓
Minimum Width

max-width: 1200px
   ↓
Maximum Width

orientation: landscape
   ↓
Orientation
```

All conditions must match.

The logical flow is:

```text
screen?
   ↓
 Yes
   ↓
Width >= 768px?
   ↓
 Yes
   ↓
Width <= 1200px?
   ↓
 Yes
   ↓
Landscape?
   ↓
 Yes
   ↓
Apply CSS
```

If any condition fails, the complete query does not match.

---

## Combining Conditions as a Range

Combining `min-width` and `max-width` is especially useful for creating responsive ranges.

For example:

```css
@media (min-width: 768px) and (max-width: 1199px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

The layout can be represented as:

```text
Small
0px ──────────────── 767px
                         ↓
                      Other CSS


Medium
768px ─────────────── 1199px
   ↓                       ↓
   └────── Apply CSS ──────┘


Large
1200px ─────────────────────→
             ↓
          Other CSS
```

This allows a specific layout to be used for a specific viewport range.

---

## Combining Conditions With Flexbox

Media query conditions can be used to control Flexbox layouts.

For example:

```css
.navigation {
    display: flex;
}

@media (max-width: 600px) and (orientation: portrait) {
    .navigation {
        flex-direction: column;
    }
}
```

The navigation changes to a column only when:

```text
Viewport <= 600px
        AND
Orientation = portrait
```

This allows the responsive behavior to be more specific than using width alone.

---

## Combining Conditions With Grid

Multiple conditions can also control CSS Grid layouts.

For example:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

@media (min-width: 600px) and (max-width: 900px) {
    .cards {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 599px) {
    .cards {
        grid-template-columns: 1fr;
    }
}
```

The layout can therefore respond to different viewport ranges.

```text
Large
┌──────┬──────┬──────┐
│ Card │ Card │ Card │
└──────┴──────┴──────┘

Medium
┌──────┬──────┐
│ Card │ Card │
├──────┼──────┤
│ Card │ Card │
└──────┴──────┘

Small
┌──────┐
│ Card │
├──────┤
│ Card │
├──────┤
│ Card │
└──────┘
```

---

## Multiple Conditions Must Match

When conditions are combined with `and`, every condition must match.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 80%;
    }
}
```

Consider different viewport widths:

```text
500px
  ↓
min-width: 600px → FALSE
  ↓
Do not apply


800px
  ↓
min-width: 600px → TRUE
  ↓
max-width: 1000px → TRUE
  ↓
Apply CSS


1200px
  ↓
min-width: 600px → TRUE
  ↓
max-width: 1000px → FALSE
  ↓
Do not apply
```

This is the key behavior of combined `and` conditions.

---

## Combining Width, Height, and Orientation

A more specific query can combine width, height, and orientation.

For example:

```css
@media (max-width: 800px) and (max-height: 600px) and (orientation: landscape) {
    .hero {
        padding: 20px;
    }
}
```

The CSS applies only when all three conditions match:

```text
Width <= 800px
       ↓
Height <= 600px
       ↓
Landscape orientation
       ↓
Apply CSS
```

This can be useful for layouts that have very limited space in both dimensions.

---

## Combining Conditions With `print`

Conditions can also be combined with the `print` media type.

For example:

```css
@media print and (orientation: landscape) {
    .report {
        width: 100%;
    }
}
```

This targets printed output in landscape orientation.

The query can be understood as:

```text
Print?
   ↓
 Yes
   ↓
Landscape?
   ↓
 Yes
   ↓
Apply CSS
```

This can be useful for reports, tables, charts, and other content that may need a different print layout.

---

## Conditions and Specific Responsive Behavior

Combining conditions allows different parts of a design to respond to different situations.

For example:

```css
@media (max-width: 600px) {
    .container {
        width: 95%;
    }
}

@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}

@media (min-width: 1001px) {
    .container {
        width: 75%;
    }
}
```

The design can be divided into different ranges:

```text
Small
     ↓
0px ───────────── 599px

Medium
     ↓
600px ─────────── 1000px

Large
     ↓
1001px ─────────────────→
```

Each range can have its own responsive rules.

---

## Practical Example: Responsive Dashboard

Consider a dashboard with several cards.

```css
.dashboard {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

@media (min-width: 768px) and (max-width: 1200px) {
    .dashboard {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 767px) {
    .dashboard {
        grid-template-columns: 1fr;
    }
}
```

The dashboard changes according to viewport width.

```text
Large

┌────┬────┬────┬────┐
│  1 │  2 │  3 │  4 │
└────┴────┴────┴────┘


Medium

┌────┬────┐
│  1 │  2 │
├────┼────┤
│  3 │  4 │
└────┴────┘


Small

┌────┐
│  1 │
├────┤
│  2 │
├────┤
│  3 │
├────┤
│  4 │
└────┘
```

The media queries allow the same dashboard to adapt without changing the HTML structure.

---

## Practical Example: Short Mobile Landscape View

A mobile device can have a small width and limited height when rotated into landscape mode.

A media query can target that situation:

```css
@media (max-width: 800px) and (max-height: 500px) and (orientation: landscape) {
    .header {
        padding: 10px;
    }

    .hero {
        min-height: auto;
    }
}
```

The layout can therefore respond to the combination of:

```text
Small width
    +
Short height
    +
Landscape orientation
```

This is more precise than using only one condition.

---

## Combining Conditions vs Separate Media Queries

Sometimes several conditions can be combined into one query.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        width: 85%;
    }
}
```

Instead of writing separate rules for each condition:

```css
@media (min-width: 600px) {
    /* ... */
}

@media (max-width: 1000px) {
    /* ... */
}
```

The combined version is more precise when the CSS should apply only to the overlapping range.

Conceptually:

```text
min-width: 600px
       ↓
     Range
       ↓
max-width: 1000px
       ↓
Specific target area
```

---

## Common Mistake

A common mistake is assuming that:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    /* CSS */
}
```

means either condition can be true.

It does not.

With `and`, both conditions must be satisfied.

```text
Condition A = TRUE
Condition B = TRUE
        ↓
   Apply CSS
```

But:

```text
Condition A = TRUE
Condition B = FALSE
        ↓
 Do not apply CSS
```

---

## Another Common Mistake

Avoid combining conditions unnecessarily.

For example:

```css
@media (min-width: 600px) and (max-width: 1000px) {
    .container {
        color: red;
    }
}
```

If the color does not actually need to change based on this range, the condition may add unnecessary complexity.

Media queries should represent a real responsive requirement.

---

## Practical Decision Guide

When deciding whether to combine conditions, ask:

```text
Does one condition describe the situation?
        ↓
       Yes
        ↓
Use one media feature


Do multiple conditions need to be true?
        ↓
       Yes
        ↓
Combine them with "and"
```

For example:

```text
Need a style below 600px?
        ↓
max-width


Need a style between 600px and 1000px?
        ↓
min-width + max-width


Need a style only in portrait?
        ↓
orientation


Need a style for a small portrait screen?
        ↓
max-width + orientation
```

---

> 💡 **Pro Tip:** Combine conditions only when the design actually depends on multiple characteristics. This keeps your media queries easier to read, debug, and maintain.

---

> 💡 **Remember:** When media query conditions are combined with `and`, all conditions must match before the CSS rules are applied. Combining `min-width` and `max-width` is a common way to target a specific viewport range.