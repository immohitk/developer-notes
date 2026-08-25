## Table of Contents

1. [Introduction](#introduction)
2. [What Is CSS Specificity?](#what-is-css-specificity)
3. [Why CSS Specificity Matters](#why-css-specificity-matters)
4. [The CSS Cascade](#the-css-cascade)
5. [Specificity Calculation](#specificity-calculation)
6. [Inline Styles](#inline-styles)
7. [ID Selectors](#id-selectors)
8. [Class Selectors](#class-selectors)
9. [Type Selectors](#type-selectors)
10. [Universal Selector](#universal-selector)
11. [Specificity Comparison](#specificity-comparison)
12. [The `!important` Rule](#the-important-rule)
13. [Specificity and Source Order](#specificity-and-source-order)
14. [The `:is()` Function](#the-is-function)
15. [The `:where()` Function](#the-where-function)
16. [The `:not()` Function](#the-not-function)
17. [The `:has()` Function](#the-has-function)
18. [Inheritance vs Specificity](#inheritance-vs-specificity)
19. [Practical Examples](#practical-examples)
20. [How to Avoid Specificity Problems](#how-to-avoid-specificity-problems)
21. [Best Practices](#best-practices)
22. [Common Mistakes](#common-mistakes)
23. [Interview Questions](#interview-questions)
24. [Practice Exercises](#practice-exercises)
25. [Key Takeaways](#key-takeaways)
26. [References](#references)
27. [Related Topics](#related-topics)

---

## Introduction

CSS specificity is a set of rules used by the browser to determine which CSS declaration should be applied when multiple rules target the same element.

For example, an element may match several CSS selectors:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#content {
    color: red;
}
```

If multiple rules apply to the same element, the browser must determine which declaration has higher priority.

```text
Multiple CSS rules
        ↓
Same element
        ↓
Compare priority
        ↓
Apply the winning declaration
```

CSS specificity helps determine that priority.

### A Simple Example

Consider the following HTML:

```html
<p id="content" class="text">
    Hello World
</p>
```

And the following CSS:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#content {
    color: red;
}
```

All three selectors match the same paragraph.

```text
p
↓
Matches element

.text
↓
Matches element

#content
↓
Matches element
```

The browser compares the rules according to the CSS cascade and specificity.

The selector with higher specificity can override a selector with lower specificity when the competing declarations have the same origin and importance.

### Why Learn Specificity?

Understanding specificity helps you:

- Predict which CSS rule will be applied
- Avoid unexpected style conflicts
- Write more maintainable CSS
- Reduce the need for `!important`
- Debug CSS more effectively

### Specificity Is Part of the CSS Cascade

Specificity is not the only rule used to determine which CSS declaration wins.

Other factors can also matter, including:

```text
CSS Cascade
│
├── Origin and importance
│
├── Specificity
│
└── Source order
```

Specificity is therefore one important part of understanding how CSS resolves conflicting styles.

### Main Idea

```text
Multiple rules
      ↓
Target the same element
      ↓
CSS cascade compares declarations
      ↓
Specificity can determine priority
      ↓
Winning style is applied
```

> 💡 **Remember:** CSS specificity helps determine which CSS rule takes priority when multiple selectors target the same element. However, specificity works as part of the larger CSS cascade.

---

## What Is CSS Specificity?

CSS specificity is a way of determining which selector has higher priority when multiple CSS rules target the same element.

Consider the following CSS:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#title {
    color: red;
}
```

And the following HTML:

```html
<p id="title" class="text">
    Hello World
</p>
```

All three selectors target the same paragraph:

```text
p
↓
Matches the element

.text
↓
Matches the element

#title
↓
Matches the element
```

Because multiple declarations apply, the browser compares their specificity.

```text
Multiple matching selectors
        ↓
Compare specificity
        ↓
Higher specificity
        ↓
Declaration can win
```

### Specificity Represents Selector Weight

Different types of selectors have different levels of specificity.

For example:

```text
Type selector
→ Lower specificity

Class selector
→ Higher specificity

ID selector
→ Even higher specificity
```

Consider:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#title {
    color: red;
}
```

The selectors have different levels of priority.

```text
p
↓
Type selector

.text
↓
Class selector

#title
↓
ID selector
```

When all three rules apply to the same element under the same cascade conditions, the selector with the higher specificity wins.

### Specificity Does Not Mean Everything

Specificity is important, but it is only one part of the CSS cascade.

The browser also considers other factors.

```text
CSS declarations
        ↓
Cascade rules
        ↓
Origin and importance
        ↓
Specificity
        ↓
Source order
```

Because of this, a selector with higher specificity does not automatically win in every possible situation.

### A Simple Comparison

Consider:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

Both selectors match the paragraph.

```text
p
↓
Matches

.text
↓
Matches
```

The class selector has higher specificity than the type selector.

Therefore:

```text
p
→ blue

.text
→ green

Winning color
→ green
```

### Main Concept

CSS specificity can be understood as a selector's priority when competing with other selectors.

```text
Multiple selectors
        ↓
Target same element
        ↓
Compare specificity
        ↓
Higher priority selector
        ↓
Winning declaration
```

> 💡 **Remember:** CSS specificity determines how selectors are compared when multiple CSS rules target the same element. However, specificity is only one part of the overall CSS cascade.

---

## Why CSS Specificity Matters

CSS specificity matters because multiple CSS rules can target the same element.

When this happens, the browser needs to determine which declaration should be applied.

Understanding specificity helps you predict the final appearance of an element.

### Multiple Rules Can Target One Element

Consider the following HTML:

```html
<button id="submit" class="button">
    Submit
</button>
```

Several CSS rules can target the same button:

```css
button {
    background-color: gray;
}

.button {
    background-color: blue;
}

#submit {
    background-color: green;
}
```

All three selectors match the same element.

```text
button
   ↓
Matches button

.button
   ↓
Matches button

#submit
   ↓
Matches button
```

Specificity helps determine which declaration has higher priority.

### It Helps Predict CSS Results

Without understanding specificity, CSS may sometimes appear to behave unexpectedly.

For example:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

Both rules match the paragraph.

The class selector has higher specificity than the type selector.

Therefore:

```text
p
→ blue

.text
→ green

Final color
→ green
```

Understanding specificity allows you to predict this result.

### It Helps Avoid CSS Conflicts

Large projects can contain many CSS rules.

Different selectors may target the same elements.

```text
Component styles
       +
Layout styles
       +
Utility styles
       +
Custom styles
       ↓
Possible conflicts
```

Understanding specificity helps identify why one rule overrides another.

### It Reduces the Need for `!important`

When developers do not understand why a CSS rule is being overridden, they may use:

```css
!important
```

Example:

```css
color: red !important;
```

Although `!important` can be useful in some situations, using it repeatedly can make CSS difficult to maintain.

A better approach is to understand why the competing rule has higher priority.

```text
CSS rule not working
        ↓
Check cascade
        ↓
Check specificity
        ↓
Find conflicting rule
        ↓
Fix the selector structure
```

### It Makes CSS Easier to Maintain

CSS with unnecessarily high specificity can become difficult to override.

For example:

```css
#header .navigation .menu li a {
    color: blue;
}
```

Overly complex selectors can make future styling changes more difficult.

A simpler selector may be easier to maintain:

```css
.menu-link {
    color: blue;
}
```

Lower and more predictable specificity can make CSS easier to manage.

### It Helps Debug CSS

When a style is not applied as expected, specificity is one possible reason.

A useful debugging process is:

```text
CSS declaration not applied
        ↓
Check whether another rule matches
        ↓
Compare importance
        ↓
Compare specificity
        ↓
Check source order
```

Browser developer tools can also help identify which declarations are active and which ones are overridden.

### It Is Important in Large Projects

Specificity problems become more noticeable as projects grow.

```text
Small project
    ↓
Fewer selectors
    ↓
Fewer conflicts

Large project
    ↓
More selectors
    ↓
More possible conflicts
    ↓
Specificity becomes more important
```

Understanding specificity helps developers create CSS systems that are easier to maintain as a project becomes larger.

### Main Benefits

Understanding CSS specificity helps you:

- Predict which styles will be applied
- Understand CSS conflicts
- Debug overridden declarations
- Avoid unnecessary `!important`
- Write more maintainable selectors
- Keep selector priority predictable

### Main Concept

```text
Understand specificity
        ↓
Understand CSS conflicts
        ↓
Predict winning declarations
        ↓
Write cleaner CSS
        ↓
Maintain styles more easily
```

> 💡 **Remember:** CSS specificity matters because multiple selectors can target the same element. Understanding how selector priority works helps you avoid conflicts and write CSS that is easier to predict and maintain.

---

## The CSS Cascade

The CSS cascade is the process the browser uses to determine which CSS declaration should be applied when multiple declarations affect the same element.

The word **cascade** refers to the system of rules used to resolve conflicts between CSS declarations.

```text
Multiple CSS declarations
        ↓
Target the same element
        ↓
CSS Cascade
        ↓
Determine the winning declaration
```

### Example

Consider the following HTML:

```html
<p class="text">
    Hello World
</p>
```

And the following CSS:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

Both declarations target the same paragraph.

```text
p
↓
Matches the paragraph

.text
↓
Matches the paragraph
```

The CSS cascade determines which declaration wins.

### Important Parts of the Cascade

When declarations conflict, CSS considers several factors.

A simplified view is:

```text
CSS Declarations
        ↓
Origin and Importance
        ↓
Specificity
        ↓
Source Order
```

Each factor can help determine which declaration wins.

### Origin and Importance

CSS declarations can come from different origins.

Common sources include:

```text
Browser styles
        ↓
Author styles
        ↓
User styles
```

The importance of a declaration can also affect the cascade.

For example:

```css
color: red !important;
```

The `!important` rule changes how the declaration participates in the cascade.

### Specificity

If competing declarations have the same relevant origin and importance, specificity can determine which declaration wins.

Example:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

The class selector has higher specificity than the type selector.

```text
p
→ Type selector

.text
→ Class selector
     ↓
Higher specificity
```

Therefore, the class declaration can win.

### Source Order

If competing declarations have the same origin, importance, and specificity, the declaration that appears later can win.

Example:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

Both selectors have the same specificity.

The second declaration appears later.

Therefore:

```text
First declaration
→ blue

Second declaration
→ green

Winning declaration
→ green
```

### The Cascade Works Step by Step

A simplified process looks like this:

```text
Multiple declarations
        ↓
Check origin and importance
        ↓
Check specificity
        ↓
Check source order
        ↓
Apply winning declaration
```

This process explains why a CSS declaration may override another declaration.

### Cascade and Specificity

Specificity is an important part of CSS, but it does not work alone.

```text
CSS Cascade
│
├── Origin and importance
│
├── Specificity
│
└── Source order
```

Understanding the cascade helps explain when specificity matters and when another rule has higher priority.

### Main Concept

```text
Multiple CSS rules
        ↓
CSS Cascade compares them
        ↓
Origin and importance
        ↓
Specificity
        ↓
Source order
        ↓
Winning declaration
```

> 💡 **Remember:** CSS specificity is only one part of the CSS cascade. To understand why a CSS rule wins or loses, you should consider origin, importance, specificity, and source order.

---

## Specificity Calculation

CSS specificity is calculated by comparing the types of selectors used in a CSS rule.

A common way to represent specificity is:

```text
A-B-C
```

Where:

```text
A
→ Number of ID selectors

B
→ Number of class selectors, attribute selectors,
  and pseudo-classes

C
→ Number of type selectors and pseudo-elements
```

### Specificity Components

Consider the selector:

```css
#header .menu li
```

Its specificity can be calculated as:

```text
#header
→ 1 ID selector

.menu
→ 1 class selector

li
→ 1 type selector
```

Therefore:

```text
1-1-1
```

### ID Selectors

Each ID selector increases the first value.

Example:

```css
#title {
    color: red;
}
```

Specificity:

```text
1-0-0
```

Another example:

```css
#header #logo {
    color: blue;
}
```

Specificity:

```text
2-0-0
```

### Class Selectors

Each class selector increases the second value.

Example:

```css
.button {
    color: blue;
}
```

Specificity:

```text
0-1-0
```

Multiple classes:

```css
.button.primary {
    color: green;
}
```

Specificity:

```text
0-2-0
```

### Attribute Selectors and Pseudo-Classes

Attribute selectors and pseudo-classes are also counted in the second value.

Example:

```css
input[type="text"] {
    color: blue;
}
```

Specificity:

```text
0-1-1
```

The attribute selector contributes:

```text
[type="text"]
→ 0-1-0
```

The type selector contributes:

```text
input
→ 0-0-1
```

Combined:

```text
0-1-1
```

Example using a pseudo-class:

```css
.button:hover {
    color: red;
}
```

Specificity:

```text
0-2-0
```

```text
.button
→ 0-1-0

:hover
→ 0-1-0
```

### Type Selectors

Each type selector increases the third value.

Example:

```css
p {
    color: blue;
}
```

Specificity:

```text
0-0-1
```

Another example:

```css
main article p {
    color: green;
}
```

Specificity:

```text
0-0-3
```

### A Complete Example

Consider:

```css
#content .article p {
    color: blue;
}
```

Calculate each selector:

```text
#content
→ 1 ID selector

.article
→ 1 class selector

p
→ 1 type selector
```

Specificity:

```text
1-1-1
```

### Comparing Specificity

Specificity values are compared from left to right.

Consider:

```text
1-0-0

0-10-10
```

The first selector has higher specificity because the first value is larger.

```text
1-0-0
↑
Higher ID count
```

An ID selector is compared before class and type selector counts.

Another example:

```text
0-2-1

0-1-5
```

Compare from left to right:

```text
ID count
0 = 0

Class count
2 > 1
```

Therefore:

```text
0-2-1
```

has higher specificity.

### Specificity Calculation Process

A simple way to calculate specificity is:

```text
Look at selector
        ↓
Count ID selectors
        ↓
Count classes,
attributes,
and pseudo-classes
        ↓
Count type selectors
and pseudo-elements
        ↓
Write specificity
as A-B-C
```

### Important Note

Specificity is not usually calculated by simply adding all values together.

For example:

```text
0-10-0
```

does not automatically have higher specificity than:

```text
1-0-0
```

The values are compared by category from left to right.

```text
ID
↓
Class
↓
Type
```

### Main Concept

```text
Specificity
│
├── A
│   → ID selectors
│
├── B
│   → Classes
│   → Attributes
│   → Pseudo-classes
│
└── C
    → Type selectors
    → Pseudo-elements
```

> 💡 **Remember:** CSS specificity is compared from left to right. ID selectors are compared first, followed by class-related selectors, and finally type selectors.

---

## Inline Styles

Inline styles are CSS declarations written directly inside an HTML element using the `style` attribute.

Example:

```html
<p style="color: red;">
    Hello World
</p>
```

The CSS declaration is applied directly to the element.

```text
HTML element
     ↓
style attribute
     ↓
CSS declaration
     ↓
Style applied
```

### Inline Styles and Specificity

Inline styles have higher priority than normal author styles that are not marked with `!important`.

Consider the following HTML:

```html
<p class="text" style="color: red;">
    Hello World
</p>
```

And the CSS:

```css
.text {
    color: blue;
}
```

Both declarations target the paragraph.

However, the inline style has higher priority in the normal author cascade.

Therefore, the final color is:

```text
red
```

### Representing Inline Styles

A common way to represent inline styles in specificity discussions is:

```text
1-0-0-0
```

Where the first value represents the inline style.

For normal selector specificity, we previously used:

```text
A-B-C
```

```text
A
→ ID selectors

B
→ Classes, attributes, and pseudo-classes

C
→ Type selectors and pseudo-elements
```

Inline styles are often shown separately because they are applied directly through the HTML `style` attribute.

### Example Comparison

Consider:

```html
<p
    id="message"
    class="text"
    style="color: red;"
>
    Hello World
</p>
```

CSS:

```css
#message {
    color: blue;
}

.text {
    color: green;
}

p {
    color: purple;
}
```

The element matches all selectors.

```text
Inline style
→ color: red

#message
→ color: blue

.text
→ color: green

p
→ color: purple
```

Under normal author styles, the inline declaration wins.

```text
Inline style
        ↓
Higher priority
        ↓
Final color
        ↓
red
```

### Can Inline Styles Be Overridden?

An inline style can be overridden by an `!important` declaration in the appropriate cascade context.

Example:

```html
<p style="color: red;">
    Hello World
</p>
```

CSS:

```css
p {
    color: blue !important;
}
```

The `!important` declaration participates in a different importance level of the cascade.

Therefore, `!important` should be understood separately from normal specificity comparisons.

### Why Avoid Excessive Inline Styles?

Inline styles can make HTML and CSS harder to maintain.

Example:

```html
<button
    style="
        background-color: blue;
        color: white;
        padding: 10px;
    "
>
    Submit
</button>
```

A reusable CSS class is often easier to maintain:

```html
<button class="button">
    Submit
</button>
```

```css
.button {
    background-color: blue;
    color: white;
    padding: 10px;
}
```

### Inline Style Summary

```text
Inline Styles
│
├── Written in the style attribute
│
├── Applied directly to an element
│
├── Have high priority in normal author styles
│
├── Can be affected by !important
│
└── Can reduce maintainability when overused
```

> 💡 **Remember:** Inline styles are written directly inside HTML elements and generally have higher priority than normal CSS selectors. However, `!important` and other cascade rules can affect the final result.

---

## ID Selectors

An ID selector targets an HTML element using the value of its `id` attribute.

The `id` selector uses the `#` symbol.

Example:

```css
#title {
    color: red;
}
```

HTML:

```html
<h1 id="title">
    Hello World
</h1>
```

The selector:

```css
#title
```

targets the element with:

```text
id="title"
```

### ID Selector Specificity

Each ID selector increases the first specificity value.

Example:

```css
#title {
    color: red;
}
```

Specificity:

```text
1-0-0
```

```text
1
↓
ID selector

0
↓
Class-related selectors

0
↓
Type selectors
```

### ID Selectors Have High Specificity

ID selectors have higher specificity than class selectors and type selectors.

Consider:

```css
p {
    color: blue;
}

.text {
    color: green;
}

#message {
    color: red;
}
```

HTML:

```html
<p id="message" class="text">
    Hello World
</p>
```

All three selectors match the same paragraph.

Their specificity is:

```text
p
→ 0-0-1

.text
→ 0-1-0

#message
→ 1-0-0
```

The ID selector has the highest specificity.

Therefore:

```text
Final color
→ red
```

### Multiple ID Selectors

Each ID selector increases the ID part of specificity.

Example:

```css
#header #logo {
    color: blue;
}
```

Specificity:

```text
2-0-0
```

However, using multiple ID selectors is usually unnecessary and can make CSS difficult to override.

### ID Selectors and Maintainability

ID selectors can create high-specificity CSS rules.

Example:

```css
#header .navigation .menu-link {
    color: blue;
}
```

This can be more difficult to override later.

A class-based selector may be easier to maintain:

```css
.menu-link {
    color: blue;
}
```

Class selectors usually provide more flexibility for reusable components.

### Reusing IDs

In HTML, an `id` should uniquely identify an element within a document.

Example:

```html
<h1 id="title">
    Page Title
</h1>
```

For styles that need to be reused across multiple elements, classes are generally more appropriate.

Example:

```html
<p class="highlight">
    First paragraph
</p>

<p class="highlight">
    Second paragraph
</p>
```

CSS:

```css
.highlight {
    color: blue;
}
```

### ID Selector Summary

```text
ID Selectors
│
├── Use the # symbol
│
├── Target an element by its id
│
├── Specificity
│   → 1-0-0
│
├── Have higher specificity than
│   → Class selectors
│   → Type selectors
│
└── Can make styles harder to override
    when overused
```

> 💡 **Remember:** ID selectors have high specificity. They are useful for targeting uniquely identified elements, but excessive use of IDs for styling can make CSS harder to override and maintain.

---

## Class Selectors

A class selector targets HTML elements using the value of their `class` attribute.

A class selector uses a period (`.`) before the class name.

Example:

```css
.button {
    color: blue;
}
```

HTML:

```html
<button class="button">
    Submit
</button>
```

The selector:

```css
.button
```

targets elements with:

```text
class="button"
```

### Class Selector Specificity

Each class selector increases the second specificity value.

Example:

```css
.button {
    color: blue;
}
```

Specificity:

```text
0-1-0
```

```text
0
↓
ID selectors

1
↓
Class-related selectors

0
↓
Type selectors
```

### Multiple Class Selectors

Multiple class selectors increase the class-related specificity value.

Example:

```css
.button.primary {
    color: white;
}
```

Specificity:

```text
0-2-0
```

```text
.button
→ 0-1-0

.primary
→ 0-1-0

Total
→ 0-2-0
```

The selector targets an element that has both classes.

Example:

```html
<button class="button primary">
    Submit
</button>
```

### Class Selectors Compared With ID Selectors

Consider:

```css
.button {
    color: blue;
}

#submit {
    color: green;
}
```

HTML:

```html
<button
    id="submit"
    class="button"
>
    Submit
</button>
```

Specificity:

```text
.button
→ 0-1-0

#submit
→ 1-0-0
```

The ID selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### Class Selectors Compared With Type Selectors

Consider:

```css
button {
    color: blue;
}

.button {
    color: green;
}
```

HTML:

```html
<button class="button">
    Submit
</button>
```

Specificity:

```text
button
→ 0-0-1

.button
→ 0-1-0
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### Classes Are Reusable

One of the main advantages of classes is that they can be reused.

Example:

```html
<button class="button">
    Submit
</button>

<button class="button">
    Cancel
</button>

<button class="button">
    Save
</button>
```

The same CSS rule can style all of these elements.

```css
.button {
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
}
```

### Multiple Classes Can Be Used

An HTML element can have multiple classes.

Example:

```html
<button class="button primary large">
    Submit
</button>
```

Each class can provide different styles.

```css
.button {
    padding: 10px;
}

.primary {
    background-color: blue;
    color: white;
}

.large {
    font-size: 1.2rem;
}
```

This makes classes useful for reusable and flexible styling.

### Class Selector Summary

```text
Class Selectors
│
├── Use the . symbol
│
├── Target elements by class
│
├── Specificity
│   → 0-1-0
│
├── Can be combined
│
├── Can be reused
│
└── Are useful for
    reusable component styles
```

> 💡 **Remember:** Class selectors have higher specificity than type selectors but lower specificity than ID selectors. Classes are reusable, flexible, and commonly used for styling components.

---

## Type Selectors

A type selector targets HTML elements based on their element name.

Type selectors are also commonly called element selectors.

Example:

```css
p {
    color: blue;
}
```

The selector:

```css
p
```

targets all `<p>` elements.

Example HTML:

```html
<p>First paragraph</p>

<p>Second paragraph</p>

<p>Third paragraph</p>
```

All matching paragraph elements receive the style.

### Type Selector Specificity

Each type selector increases the third specificity value.

Example:

```css
p {
    color: blue;
}
```

Specificity:

```text
0-0-1
```

```text
0
↓
ID selectors

0
↓
Class-related selectors

1
↓
Type selector
```

### Multiple Type Selectors

Multiple type selectors increase the type selector value.

Example:

```css
main article p {
    color: blue;
}
```

Specificity:

```text
0-0-3
```

```text
main
→ 0-0-1

article
→ 0-0-1

p
→ 0-0-1

Total
→ 0-0-3
```

The selector targets paragraph elements inside an `article` inside a `main` element.

### Type Selectors Compared With Class Selectors

Consider:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

Both selectors match the paragraph.

Specificity:

```text
p
→ 0-0-1

.text
→ 0-1-0
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### Type Selectors Compared With ID Selectors

Consider:

```css
p {
    color: blue;
}

#message {
    color: red;
}
```

HTML:

```html
<p id="message">
    Hello World
</p>
```

Specificity:

```text
p
→ 0-0-1

#message
→ 1-0-0
```

The ID selector has higher specificity.

Therefore:

```text
Final color
→ red
```

### Type Selectors Are Useful for General Styles

Type selectors are useful when applying styles to a group of similar HTML elements.

Example:

```css
h1 {
    font-size: 2rem;
}

p {
    line-height: 1.6;
}

button {
    cursor: pointer;
}
```

These rules apply to all matching elements.

### Type Selector Summary

```text
Type Selectors
│
├── Target elements by name
│
├── Examples
│   → p
│   → h1
│   → button
│
├── Specificity
│   → 0-0-1
│
├── Have lower specificity than
│   → Class selectors
│   → ID selectors
│
└── Useful for
    general element styles
```

> 💡 **Remember:** Type selectors target HTML elements by their element name. They have relatively low specificity and are useful for applying general styles across a page.

---

## Universal Selector

The universal selector matches every element.

It is written using an asterisk:

```css
*
```

Example:

```css
* {
    margin: 0;
    padding: 0;
}
```

This rule targets all elements on the page.

### Universal Selector Specificity

The universal selector has zero specificity.

```text
*
→ 0-0-0
```

Because it adds no specificity, almost any other selector that matches the same element can override it when the declarations have the same origin and importance.

For example:

```css
* {
    color: blue;
}

p {
    color: green;
}
```

The paragraph selector has higher specificity.

```text
*
→ 0-0-0

p
→ 0-0-1
```

Therefore, the paragraph text is:

```text
green
```

### Using the Universal Selector

The universal selector is often used for global styles.

Example:

```css
* {
    box-sizing: border-box;
}
```

This applies:

```text
box-sizing: border-box;
```

to every element.

Another common pattern is:

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

This applies the rule to:

```text
All elements
        +
Before pseudo-elements
        +
After pseudo-elements
```

### Universal Selector With Other Selectors

The universal selector can be combined with other selectors.

Example:

```css
.container * {
    color: blue;
}
```

This selector matches all descendant elements inside `.container`.

The universal selector itself adds zero specificity.

Specificity:

```text
.container *
→ 0-1-0
```

Only the `.container` class contributes to specificity.

Another example:

```css
#content * {
    margin-bottom: 10px;
}
```

Specificity:

```text
#content *
→ 1-0-0
```

Only the ID selector contributes to specificity.

### Universal Selector and Maintainability

The universal selector can be useful, but broad rules may affect more elements than expected.

For example:

```css
* {
    color: red;
}
```

This applies the color to every element that uses the declaration directly or inherits it where applicable.

Using more targeted selectors is often clearer when styling specific components.

### Universal Selector Summary

```text
Universal Selector
│
├── Uses the *
│
├── Matches all elements
│
├── Specificity
│   → 0-0-0
│
├── Adds no specificity
│
└── Often used for
    global styles
```

> 💡 **Remember:** The universal selector matches all elements but contributes zero specificity. When competing rules have the same origin and importance, a selector with any positive specificity can override it.

---

## Specificity Comparison

When multiple CSS selectors target the same element, their specificity can be compared to determine which selector has higher priority.

Specificity values are compared from left to right.

```text
A-B-C

A → ID selectors
B → Class-related selectors
C → Type selectors
```

### Comparing ID Selectors

Consider:

```css
#title {
    color: blue;
}

.text {
    color: green;
}
```

Specificity:

```text
#title
→ 1-0-0

.text
→ 0-1-0
```

Compare the first value:

```text
1 > 0
```

Therefore:

```text
#title
```

has higher specificity.

### Comparing Class Selectors

Consider:

```css
.button.primary {
    color: blue;
}

.button {
    color: green;
}
```

Specificity:

```text
.button.primary
→ 0-2-0

.button
→ 0-1-0
```

Compare the values from left to right:

```text
ID selectors
0 = 0

Class selectors
2 > 1
```

Therefore:

```text
.button.primary
```

has higher specificity.

### Comparing Type Selectors

Consider:

```css
main article p {
    color: blue;
}

p {
    color: green;
}
```

Specificity:

```text
main article p
→ 0-0-3

p
→ 0-0-1
```

Compare the values:

```text
ID selectors
0 = 0

Class-related selectors
0 = 0

Type selectors
3 > 1
```

Therefore:

```text
main article p
```

has higher specificity.

### More Classes Do Not Beat an ID

Consider:

```text
1-0-0

0-10-0
```

The first selector has higher specificity.

Why?

Specificity is compared by category from left to right.

```text
ID selectors
1 > 0
```

The comparison stops at the first different value.

Therefore:

```text
1-0-0
```

has higher specificity than:

```text
0-10-0
```

### Another Comparison

Consider:

```text
0-2-1

0-1-10
```

Compare from left to right.

```text
ID selectors
0 = 0

Class-related selectors
2 > 1
```

Therefore:

```text
0-2-1
```

has higher specificity.

The number of type selectors does not matter because the class-related values already determined the result.

### Equal Specificity

Consider:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

Both selectors have the same specificity:

```text
0-1-0
```

When specificity is equal, source order can determine which declaration wins.

Because the second rule appears later:

```text
Final color
→ green
```

### Specificity Comparison Process

A simple process is:

```text
Compare ID selectors
        ↓
If equal
        ↓
Compare class-related selectors
        ↓
If equal
        ↓
Compare type selectors
        ↓
If equal
        ↓
Check source order
```

### Comparison Examples

```text
Selector                  Specificity

p                         0-0-1

.text                     0-1-0

.button.primary           0-2-0

#header                   1-0-0

#header .menu a           1-1-1
```

From lower to higher specificity:

```text
p
        ↓
.text
        ↓
.button.primary
        ↓
#header
        ↓
#header .menu a
```

### Main Concept

```text
Specificity values
        ↓
Compare from left to right
        ↓
First larger value wins
        ↓
If values are equal
        ↓
Check source order
```

> 💡 **Remember:** Do not add specificity values together like normal numbers. Compare IDs first, then class-related selectors, and finally type selectors.

---

## The `!important` Rule

The `!important` rule changes the importance of a CSS declaration in the cascade.

It is added after a property value.

Example:

```css
p {
    color: red !important;
}
```

The declaration:

```css
color: red !important;
```

is treated as an important declaration.

### Normal Declarations

A normal CSS declaration does not use `!important`.

Example:

```css
p {
    color: blue;
}
```

This is a normal declaration.

```text
color: blue;
```

### Important Declarations

Adding `!important` makes the declaration important.

Example:

```css
p {
    color: red !important;
}
```

```text
color: red !important;
```

When declarations conflict, importance is considered as part of the CSS cascade.

### Example

Consider:

```css
.text {
    color: blue;
}

p {
    color: red !important;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

Both rules match the paragraph.

The class selector has higher normal specificity:

```text
.text
→ 0-1-0

p
→ 0-0-1
```

However, the `!important` declaration changes the importance level in the cascade.

Therefore, the important declaration can override the normal declaration.

```text
.text
→ color: blue

p
→ color: red !important

Final color
→ red
```

### `!important` and Specificity

Specificity is compared between declarations that are competing at the same relevant level of the cascade.

A declaration marked with `!important` should not simply be treated as having a larger specificity number.

Instead:

```text
Cascade
    ↓
Importance considered
    ↓
Specificity comparison
    ↓
Source order if needed
```

This means `!important` and specificity are different concepts.

### Important Declarations Can Also Compete

Consider:

```css
p {
    color: blue !important;
}

.text {
    color: green !important;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

Both declarations are important.

Their specificity is compared:

```text
p
→ 0-0-1

.text
→ 0-1-0
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### When Specificity Is Equal

Consider:

```css
.text {
    color: blue !important;
}

.text {
    color: green !important;
}
```

Both declarations:

- Have the same importance
- Have the same specificity

Source order can determine the result.

Because the second rule appears later:

```text
Final color
→ green
```

### Why `!important` Should Be Used Carefully

Using `!important` can make CSS harder to maintain.

For example:

```css
.button {
    color: blue !important;
}
```

Later, another developer may need to override the style:

```css
.button {
    color: red !important;
}
```

This can lead to repeated use of `!important`.

```text
Rule overridden
      ↓
Add !important
      ↓
Another rule overridden
      ↓
Add !important again
      ↓
CSS becomes harder to manage
```

### Prefer Understanding the Conflict

Before using `!important`, it is often better to check:

```text
Why is the rule being overridden?
        ↓
Check the cascade
        ↓
Check importance
        ↓
Check specificity
        ↓
Check source order
```

The problem may be solved by restructuring the CSS rather than increasing importance.

### Example of a Better Approach

Instead of:

```css
.button {
    background-color: blue !important;
}
```

Consider using a more appropriate selector or organizing component styles clearly:

```css
.primary-button {
    background-color: blue;
}
```

This can make the CSS easier to understand and maintain.

### The `!important` Rule Summary

```text
!important
│
├── Changes declaration importance
│
├── Is part of the CSS cascade
│
├── Is not a specificity value
│
├── Can override normal declarations
│
├── Still allows specificity comparison
│   between competing important declarations
│
└── Should be used carefully
```

> 💡 **Remember:** `!important` affects the importance of a declaration, not its specificity score. Use it carefully because excessive use can make CSS conflicts more difficult to manage.

---

## Specificity and Source Order

Source order is used to determine which CSS declaration wins when competing declarations have the same origin, importance, and specificity.

In simple terms:

```text
Same importance
        ↓
Same specificity
        ↓
Later declaration wins
```

### A Simple Example

Consider the following CSS:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

Both selectors are identical.

Their specificity is:

```text
0-1-0
```

Because the specificity is equal, source order is considered.

The second declaration appears later in the stylesheet.

Therefore:

```text
Final color
→ green
```

### Source Order Does Not Override Higher Specificity

Source order is considered only after the competing declarations have the same relevant cascade conditions and specificity.

Consider:

```css
.text {
    color: blue;
}

p {
    color: green;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

The selectors have different specificity:

```text
.text
→ 0-1-0

p
→ 0-0-1
```

The class selector has higher specificity.

Even though the `p` rule appears later, the class selector wins.

Therefore:

```text
Final color
→ blue
```

### Equal Specificity Example

Consider:

```css
p.text {
    color: blue;
}

.text p {
    color: green;
}
```

The selectors do not necessarily target the same element in the same HTML structure, but when two competing selectors have equal specificity and match the same property on the same element, source order can determine the winner.

A clearer example is:

```css
.button.primary {
    color: blue;
}

.button.secondary {
    color: green;
}
```

Both selectors have:

```text
0-2-0
```

If an element has both matching class combinations, the rule that appears later can win.

Example:

```html
<button class="button primary secondary">
    Submit
</button>
```

The second rule appears later.

Therefore:

```text
Final color
→ green
```

### Source Order in the Same Stylesheet

Consider:

```css
.title {
    color: red;
}

/* Other CSS rules */

.title {
    color: blue;
}
```

Both declarations have the same:

```text
Origin
Importance
Specificity
```

Therefore, the later declaration wins.

```text
First rule
→ red

Later rule
→ blue

Final color
→ blue
```

### Source Order and Linked Stylesheets

Source order can also matter when multiple stylesheets are loaded.

For example:

```html
<link rel="stylesheet" href="base.css">
<link rel="stylesheet" href="theme.css">
```

When competing declarations have the same relevant cascade conditions and specificity, rules from the later stylesheet can take precedence over earlier competing rules.

```text
base.css
    ↓

theme.css
    ↓
Later source
```

### Source Order in CSS

A simplified process is:

```text
Multiple matching declarations
        ↓
Compare origin and importance
        ↓
Compare specificity
        ↓
If equal
        ↓
Compare source order
        ↓
Later declaration wins
```

### Source Order Summary

```text
Source Order
│
├── Considered after
│   → Origin
│   → Importance
│   → Specificity
│
├── Applies when competing rules are equal
│   in the relevant earlier comparisons
│
└── Later declaration can win
```

> 💡 **Remember:** Source order is usually the deciding factor when competing CSS declarations have the same relevant origin, importance, and specificity. In that situation, the declaration that appears later can win.

---

## The `:is()` Function

The `:is()` pseudo-class allows multiple selectors to be grouped together.

It can make CSS selectors shorter and easier to read.

Example:

```css
:is(h1, h2, h3) {
    color: blue;
}
```

This selector targets:

```text
h1
h2
h3
```

### Without `:is()`

Without `:is()`, the same selectors can be written separately:

```css
h1,
h2,
h3 {
    color: blue;
}
```

The `:is()` function can be especially useful when a longer part of a selector is repeated.

### Example With Repeated Selectors

Consider:

```css
article h1,
article h2,
article h3 {
    color: blue;
}
```

Using `:is()`:

```css
article :is(h1, h2, h3) {
    color: blue;
}
```

This reduces repeated selector code.

### Specificity of `:is()`

The `:is()` pseudo-class itself does not simply add a fixed specificity value.

Instead, its specificity is replaced by the specificity of the most specific selector in its selector list.

Consider:

```css
:is(p, .text) {
    color: blue;
}
```

The selectors inside `:is()` have:

```text
p
→ 0-0-1

.text
→ 0-1-0
```

The most specific selector is:

```text
.text
→ 0-1-0
```

Therefore, the `:is()` selector has:

```text
0-1-0
```

specificity.

### Example With an ID Selector

Consider:

```css
:is(p, .text, #title) {
    color: blue;
}
```

The selectors have:

```text
p
→ 0-0-1

.text
→ 0-1-0

#title
→ 1-0-0
```

The most specific selector is:

```text
#title
→ 1-0-0
```

Therefore, the selector:

```css
:is(p, .text, #title)
```

has specificity:

```text
1-0-0
```

This applies even when the matched element matches a less specific selector inside the `:is()` list.

### `:is()` With Other Selectors

The specificity of selectors outside `:is()` is also included.

Example:

```css
article :is(h1, .title) {
    color: blue;
}
```

Specificity:

```text
article
→ 0-0-1

.title
→ 0-1-0
```

The most specific selector inside `:is()` is `.title`.

Therefore:

```text
article :is(h1, .title)
→ 0-1-1
```

### Why Specificity Matters With `:is()`

The presence of a highly specific selector inside `:is()` can increase the specificity of the entire selector.

Example:

```css
:is(.button, #submit) {
    color: blue;
}
```

Because `#submit` is an ID selector, the selector has:

```text
1-0-0
```

specificity.

This can be surprising when the rule is intended to style elements matching `.button`.

### A Simpler Example

Consider:

```css
.button {
    color: green;
}

:is(.button, #submit) {
    color: blue;
}
```

An element with:

```html
<button class="button">
    Submit
</button>
```

matches both rules.

Specificity:

```text
.button
→ 0-1-0

:is(.button, #submit)
→ 1-0-0
```

The `:is()` rule has higher specificity because the selector list contains an ID selector.

Therefore:

```text
Final color
→ blue
```

### `:is()` Summary

```text
:is()
│
├── Groups multiple selectors
│
├── Reduces repeated selector code
│
├── Uses the specificity of the
│   most specific selector in its list
│
└── Can unexpectedly increase
    selector specificity
```

> 💡 **Remember:** The specificity of `:is()` is based on the most specific selector in its selector list. Be careful when placing highly specific selectors, such as IDs, inside `:is()`.

---

## The `:where()` Function

The `:where()` pseudo-class allows multiple selectors to be grouped together.

Its syntax is similar to `:is()`.

Example:

```css
:where(h1, h2, h3) {
    color: blue;
}
```

This selector targets:

```text
h1
h2
h3
```

### The Main Difference Between `:is()` and `:where()`

Although `:is()` and `:where()` can group selectors in a similar way, they handle specificity differently.

```text
:is()
→ Uses the specificity of the most specific selector

:where()
→ Always has zero specificity
```

This makes `:where()` especially useful when you want to group selectors without increasing selector specificity.

### Specificity of `:where()`

The `:where()` pseudo-class always contributes zero specificity.

Consider:

```css
:where(p, .text, #title) {
    color: blue;
}
```

The selector list contains:

```text
p
→ Type selector

.text
→ Class selector

#title
→ ID selector
```

However, the entire `:where()` selector still has:

```text
0-0-0
```

specificity.

The selectors inside `:where()` do not increase its specificity.

### Example

Consider:

```css
:where(.button, #submit) {
    color: blue;
}

.button {
    color: green;
}
```

An element with:

```html
<button class="button">
    Submit
</button>
```

matches both rules.

Specificity:

```text
:where(.button, #submit)
→ 0-0-0

.button
→ 0-1-0
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ green
```

Even though `#submit` appears inside `:where()`, it does not increase the selector's specificity.

### `:where()` With Other Selectors

Selectors outside `:where()` still contribute to specificity.

Example:

```css
article :where(h1, .title, #heading) {
    color: blue;
}
```

The `:where()` part contributes:

```text
0-0-0
```

The `article` type selector contributes:

```text
0-0-1
```

Therefore, the complete selector has:

```text
0-0-1
```

specificity.

### Why Use `:where()`?

The `:where()` function can help create selectors that are easy to override.

Example:

```css
:where(.button, .link, .input) {
    font: inherit;
}
```

Because the selector has zero specificity, other component selectors can easily override the declaration.

```css
.button {
    font-size: 1.2rem;
}
```

The `.button` selector has higher specificity.

### `:is()` vs `:where()`

```text
:is()
│
├── Groups selectors
│
└── Uses specificity of
    the most specific selector


:where()
│
├── Groups selectors
│
└── Always has
    zero specificity
```

### `:where()` Summary

```text
:where()
│
├── Groups multiple selectors
│
├── Reduces repeated selector code
│
├── Always has zero specificity
│
├── Selectors inside it do not
│   increase specificity
│
└── Useful for styles that should
    be easy to override
```

> 💡 **Remember:** `:where()` always has zero specificity. This is the main difference between `:where()` and `:is()`, making `:where()` useful for creating flexible and easily overridable CSS rules.

---

## The `:not()` Function

The `:not()` pseudo-class selects elements that do not match a specified selector.

It is useful for excluding certain elements from a CSS rule.

Example:

```css
p:not(.special) {
    color: blue;
}
```

This selector targets paragraph elements that do not have the `special` class.

Example HTML:

```html
<p>First paragraph</p>

<p class="special">
    Special paragraph
</p>
```

The result is:

```text
First paragraph
→ Matches

Special paragraph
→ Does not match
```

### Basic Syntax

The basic syntax is:

```css
:not(selector)
```

Example:

```css
button:not(.primary) {
    background-color: gray;
}
```

This targets buttons that do not have the `primary` class.

### Specificity of `:not()`

The `:not()` pseudo-class itself does not add a fixed specificity value.

Instead, its specificity is determined by the most specific selector inside its selector list.

For example:

```css
:not(.hidden)
```

Specificity:

```text
.hidden
→ 0-1-0

:not(.hidden)
→ 0-1-0
```

### Example With an ID Selector

Consider:

```css
:not(p, .text, #title) {
    color: blue;
}
```

The selectors inside `:not()` have:

```text
p
→ 0-0-1

.text
→ 0-1-0

#title
→ 1-0-0
```

The most specific selector is:

```text
#title
→ 1-0-0
```

Therefore, the `:not()` selector has:

```text
1-0-0
```

specificity.

### `:not()` With Other Selectors

Selectors outside `:not()` also contribute to the total specificity.

Example:

```css
button:not(.primary) {
    color: blue;
}
```

Specificity:

```text
button
→ 0-0-1

.primary
→ 0-1-0
```

Total:

```text
0-1-1
```

### Multiple Selectors Inside `:not()`

Modern CSS allows multiple selectors inside `:not()`.

Example:

```css
button:not(.primary, .secondary) {
    background-color: gray;
}
```

This targets buttons that are neither:

```text
.primary
```

nor:

```text
.secondary
```

Example HTML:

```html
<button>Default</button>

<button class="primary">
    Primary
</button>

<button class="secondary">
    Secondary
</button>
```

The result:

```text
Default
→ Matches

Primary
→ Does not match

Secondary
→ Does not match
```

### A Practical Example

Consider a list:

```html
<ul>
    <li>Home</li>
    <li class="active">About</li>
    <li>Contact</li>
</ul>
```

CSS:

```css
li:not(.active) {
    color: gray;
}
```

The result:

```text
Home
→ Gray

About
→ Not affected

Contact
→ Gray
```

### `:not()` and Specificity

A highly specific selector inside `:not()` can increase the specificity of the complete selector.

Example:

```css
.button:not(#submit) {
    color: blue;
}
```

Specificity:

```text
.button
→ 0-1-0

#submit
→ 1-0-0

Total
→ 1-1-0
```

For this reason, it is important to be careful when placing ID selectors inside `:not()`.

### `:not()` Summary

```text
:not()
│
├── Excludes matching elements
│
├── Useful for targeting exceptions
│
├── Supports selector lists
│
├── Uses the specificity of the
│   most specific selector in its list
│
└── Can increase selector specificity
    when highly specific selectors are used
```

> 💡 **Remember:** `:not()` selects elements that do not match the selector inside it. Its specificity is based on the most specific selector in its argument.

---

## The `:has()` Function

The `:has()` pseudo-class allows a selector to target an element based on the elements or conditions related to it.

It is often described as a relational pseudo-class because it can select an element when it contains or is related to another matching element.

Example:

```css
.card:has(img) {
    border: 2px solid blue;
}
```

This selector targets `.card` elements that contain an `img` element.

### Basic Syntax

The basic syntax is:

```css
:has(selector)
```

Example:

```css
article:has(h1) {
    padding: 20px;
}
```

This targets `article` elements that contain an `h1`.

### Example

Consider the following HTML:

```html
<div class="card">
    <img src="image.jpg" alt="Example">
    <p>Card content</p>
</div>

<div class="card">
    <p>Another card</p>
</div>
```

CSS:

```css
.card:has(img) {
    border: 2px solid blue;
}
```

The result:

```text
First card
→ Contains an img
→ Matches

Second card
→ Does not contain an img
→ Does not match
```

### Selecting a Parent Based on a Child

One useful feature of `:has()` is that it can style an element based on one of its descendants.

Example:

```css
form:has(input:invalid) {
    border: 2px solid red;
}
```

This targets a `form` containing an invalid input.

```text
form
  ↓
Contains invalid input?
  ↓
Yes
  ↓
Apply style
```

### Selecting Based on a Following Sibling

The `:has()` pseudo-class can also work with relative selectors.

Example:

```css
h2:has(+ p) {
    margin-bottom: 0;
}
```

This targets an `h2` that is immediately followed by a paragraph.

The `+` selector represents the adjacent sibling relationship.

```text
h2
↓
Immediately followed by
↓
p
```

### Specificity of `:has()`

The `:has()` pseudo-class itself does not add a fixed specificity value.

Its specificity is replaced by the specificity of the most specific selector in its argument.

Consider:

```css
.card:has(img)
```

Specificity:

```text
.card
→ 0-1-0

img
→ 0-0-1

Total
→ 0-1-1
```

### Example With Multiple Selectors

Consider:

```css
.card:has(img, .featured, #special) {
    border-color: blue;
}
```

The selectors inside `:has()` include:

```text
img
→ 0-0-1

.featured
→ 0-1-0

#special
→ 1-0-0
```

The most specific selector is:

```text
#special
→ 1-0-0
```

Including `.card`:

```text
.card
→ 0-1-0
```

The total specificity becomes:

```text
1-1-0
```

### Practical Example

Consider product cards:

```html
<div class="product">
    <h2>Product One</h2>
    <span class="sale">Sale</span>
</div>

<div class="product">
    <h2>Product Two</h2>
</div>
```

CSS:

```css
.product:has(.sale) {
    border: 2px solid green;
}
```

Only the product containing `.sale` matches.

```text
Product One
→ Contains .sale
→ Matches

Product Two
→ Does not contain .sale
→ Does not match
```

### Be Careful With Specificity

A highly specific selector inside `:has()` can increase the specificity of the complete selector.

Example:

```css
.card:has(#special) {
    border-color: red;
}
```

Specificity:

```text
.card
→ 0-1-0

#special
→ 1-0-0

Total
→ 1-1-0
```

Because of this, it is important to understand the selectors used inside `:has()`.

### `:has()` Summary

```text
:has()
│
├── Selects elements based on
│   related matching elements
│
├── Can select a parent based on
│   its descendants
│
├── Can work with relative selectors
│
├── Uses the specificity of the
│   most specific selector in its argument
│
└── Can increase selector specificity
```

> 💡 **Remember:** `:has()` allows CSS selectors to match an element based on related elements. Its specificity is affected by the most specific selector inside its argument.

---

## Inheritance vs Specificity

Inheritance and specificity are both important concepts in CSS, but they solve different problems.

```text
Inheritance
→ Determines whether a property value can pass
  from a parent element to its descendants

Specificity
→ Helps determine which competing CSS declaration wins
```

Understanding the difference helps explain why a CSS property may appear on an element even when no rule directly targets that element.

### What Is Inheritance?

Some CSS properties can be inherited from a parent element.

Example:

```html
<div class="container">
    <p>Hello World</p>
</div>
```

CSS:

```css
.container {
    color: blue;
}
```

The `color` property is inherited by default.

Therefore, the paragraph can display blue text.

```text
.container
→ color: blue
        ↓
Inheritance
        ↓
p
→ blue text
```

### What Is Specificity?

Specificity is used when multiple CSS declarations directly compete to apply a property to the same element.

Example:

```css
p {
    color: blue;
}

.text {
    color: green;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

Both rules directly target the paragraph.

Specificity:

```text
p
→ 0-0-1

.text
→ 0-1-0
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### Inheritance Does Not Compete Like a Direct Declaration

Consider:

```html
<div class="container">
    <p class="text">
        Hello World
    </p>
</div>
```

CSS:

```css
.container {
    color: blue;
}

.text {
    color: green;
}
```

The paragraph can inherit `color: blue` from its parent.

However, the `.text` rule directly applies:

```css
color: green;
```

to the paragraph.

The direct declaration is used instead of the inherited value.

```text
Parent
→ color: blue
        ↓
Inherited value available

Paragraph
→ color: green
        ↓
Direct declaration
        ↓
Final color
→ green
```

### Inheritance and Specificity Together

Consider:

```html
<div id="container">
    <p class="text">
        Hello World
    </p>
</div>
```

CSS:

```css
#container {
    color: blue;
}

.text {
    color: green;
}
```

The parent selector has high specificity:

```text
#container
→ 1-0-0
```

The paragraph selector has:

```text
.text
→ 0-1-0
```

However, these selectors do not directly compete for the same element.

```text
#container
→ Targets the div

.text
→ Targets the paragraph
```

The paragraph inherits a value from the parent only when an appropriate property is inheritable and no applicable value overrides it.

Therefore, the parent's high specificity does not automatically override a declaration directly targeting the child.

### Example With an Inherited Property

Consider:

```html
<div class="container">
    <p>Hello World</p>
</div>
```

CSS:

```css
.container {
    color: blue;
}
```

No rule directly sets the paragraph's `color`.

Therefore:

```text
p
↓
Inherits color
↓
blue
```

Now add:

```css
p {
    color: red;
}
```

The paragraph has a directly specified value.

```text
Parent
→ color: blue

Paragraph
→ color: red
        ↓
Final color
→ red
```

### Not Every Property Is Inherited

Some properties are inherited by default, while others are not.

For example:

```text
Commonly inherited
→ color
→ font-family
→ font-size

Not inherited by default
→ margin
→ padding
→ border
→ width
```

A child element does not automatically receive every CSS property from its parent.

### A Common Misunderstanding

Consider:

```css
#parent {
    color: blue;
}

.child {
    color: red;
}
```

HTML:

```html
<div id="parent">
    <p class="child">
        Hello World
    </p>
</div>
```

The parent selector has higher specificity:

```text
#parent
→ 1-0-0
```

The child selector has:

```text
.child
→ 0-1-0
```

But specificity is not compared between these two selectors because they target different elements.

The final paragraph color is:

```text
red
```

### Inheritance vs Specificity Summary

```text
Inheritance
│
├── Passes some property values
│   from parent to child
│
├── Depends on whether the
│   property is inheritable
│
└── Does not directly compete
    with child selector specificity


Specificity
│
├── Compares competing selectors
│   targeting the same element
│
├── Helps determine which
│   declaration wins
│
└── Works as part of the
    CSS cascade
```

> 💡 **Remember:** Inheritance determines whether a property value can pass from a parent to a child, while specificity helps determine which competing declaration wins on the same element. A parent's high specificity does not automatically override a directly applied style on a child.

---

## Practical Examples

The best way to understand CSS specificity is to compare selectors that target the same element.

The following examples demonstrate how the CSS cascade, specificity, and source order work together.

### Example 1: Type Selector vs Class Selector

HTML:

```html
<p class="message">
    Hello World
</p>
```

CSS:

```css
p {
    color: blue;
}

.message {
    color: green;
}
```

Both selectors target the paragraph.

Specificity:

```text
p
→ 0-0-1

.message
→ 0-1-0
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### Example 2: Class Selector vs ID Selector

HTML:

```html
<p id="message" class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: green;
}

#message {
    color: red;
}
```

Specificity:

```text
.text
→ 0-1-0

#message
→ 1-0-0
```

The ID selector has higher specificity.

Therefore:

```text
Final color
→ red
```

### Example 3: Multiple Classes

HTML:

```html
<button class="button primary">
    Submit
</button>
```

CSS:

```css
.button {
    background-color: gray;
}

.button.primary {
    background-color: blue;
}
```

Specificity:

```text
.button
→ 0-1-0

.button.primary
→ 0-2-0
```

The selector containing both classes has higher specificity.

Therefore:

```text
Final background color
→ blue
```

### Example 4: Equal Specificity

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

Both selectors have:

```text
0-1-0
```

The specificity is equal.

Therefore, source order determines the winner.

The later declaration wins.

```text
Final color
→ green
```

### Example 5: More Type Selectors

HTML:

```html
<main>
    <article>
        <p>Hello World</p>
    </article>
</main>
```

CSS:

```css
p {
    color: green;
}

main article p {
    color: blue;
}
```

Specificity:

```text
p
→ 0-0-1

main article p
→ 0-0-3
```

The second selector has higher specificity.

Therefore:

```text
Final color
→ blue
```

### Example 6: `!important`

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: blue;
}

p {
    color: red !important;
}
```

The `.text` selector has higher normal specificity.

However, the `p` declaration is marked with `!important`.

Therefore:

```text
Final color
→ red
```

This demonstrates that importance and specificity are different parts of the CSS cascade.

### Example 7: Inline Style

HTML:

```html
<p class="text" style="color: red;">
    Hello World
</p>
```

CSS:

```css
.text {
    color: blue;
}
```

The inline declaration directly applies:

```text
color: red
```

Under normal author styles, the inline declaration has higher priority than the normal class declaration.

Therefore:

```text
Final color
→ red
```

### Example 8: `:is()` Specificity

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: green;
}

:is(.text, #message) {
    color: blue;
}
```

Specificity:

```text
.text
→ 0-1-0

:is(.text, #message)
→ 1-0-0
```

The `:is()` selector uses the specificity of the most specific selector in its list.

Because the list contains `#message`, the `:is()` selector has higher specificity.

Therefore:

```text
Final color
→ blue
```

### Example 9: `:where()` Specificity

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
:where(.text, #message) {
    color: blue;
}

.text {
    color: green;
}
```

Specificity:

```text
:where(.text, #message)
→ 0-0-0

.text
→ 0-1-0
```

The `.text` selector has higher specificity.

Therefore:

```text
Final color
→ green
```

### Example 10: Inheritance and Direct Styles

HTML:

```html
<div id="container">
    <p class="text">
        Hello World
    </p>
</div>
```

CSS:

```css
#container {
    color: blue;
}

.text {
    color: red;
}
```

The paragraph can inherit the `color` property from its parent.

However, `.text` directly applies:

```text
color: red
```

to the paragraph.

Therefore:

```text
Final color
→ red
```

The parent's higher specificity does not override a declaration targeting the child.

### Practical Example Summary

```text
Type selector
        ↓
0-0-1

Class selector
        ↓
0-1-0

Multiple classes
        ↓
0-2-0

ID selector
        ↓
1-0-0
```

When declarations compete:

```text
Check the cascade
        ↓
Check importance
        ↓
Compare specificity
        ↓
If equal
        ↓
Check source order
```

> 💡 **Remember:** The easiest way to understand specificity is to compare selectors that target the same element and property. Always consider the full CSS cascade before assuming that a selector wins because it appears more specific.

---

## How to Avoid Specificity Problems

CSS specificity problems often occur when selectors become unnecessarily complex and difficult to override.

A good approach is to keep selectors simple and maintain a consistent styling strategy.

### Avoid Unnecessarily Specific Selectors

Consider:

```css
#header .navigation ul li a {
    color: blue;
}
```

This selector has high specificity and may be difficult to override.

A simpler selector may be easier to maintain:

```css
.navigation-link {
    color: blue;
}
```

Simple selectors make future changes easier.

### Prefer Classes for Styling

Classes are reusable and usually provide a manageable level of specificity.

Example:

```css
.button {
    padding: 10px;
}

.button-primary {
    background-color: blue;
}

.button-large {
    font-size: 1.2rem;
}
```

HTML:

```html
<button class="button button-primary button-large">
    Submit
</button>
```

This approach avoids relying on highly specific selectors.

### Avoid Excessive ID Selectors

ID selectors have high specificity.

Example:

```css
#header {
    background-color: blue;
}
```

When used repeatedly for styling, ID selectors can make future overrides more difficult.

For reusable components, classes are often a better choice:

```css
.header {
    background-color: blue;
}
```

### Avoid Deeply Nested Selectors

Consider:

```css
.main .content .article .section .title {
    color: blue;
}
```

This selector can be difficult to override.

A simpler alternative:

```css
.article-title {
    color: blue;
}
```

Deep selector chains can create unnecessary specificity.

### Do Not Use `!important` as a Default Solution

When a style does not work as expected, adding `!important` may appear to solve the problem:

```css
.button {
    color: blue !important;
}
```

However, repeated use can create more conflicts later.

Instead, check:

```text
Which selectors match?
        ↓
Which declaration has higher importance?
        ↓
Which selector has higher specificity?
        ↓
Does source order matter?
```

Understanding the reason for the conflict is usually better than repeatedly adding `!important`.

### Keep Specificity Consistent

A consistent specificity level makes CSS easier to maintain.

For example:

```css
.card {
    padding: 20px;
}

.card-title {
    font-size: 1.5rem;
}

.card-description {
    line-height: 1.6;
}
```

These selectors have a predictable structure.

Avoid mixing simple component selectors with unnecessarily complex selectors.

```text
Simple selectors
        +
Consistent naming
        +
Predictable specificity
        ↓
Easier CSS maintenance
```

### Use `:where()` for Easily Overridable Styles

The `:where()` function has zero specificity.

Example:

```css
:where(h1, h2, h3) {
    margin-top: 0;
}
```

A more specific selector can easily override this rule:

```css
.article-title {
    margin-top: 20px;
}
```

This can be useful when creating base styles that should remain easy to customize.

### Organize CSS Clearly

Organizing styles can reduce accidental conflicts.

For example:

```text
Base styles
        ↓
Layout styles
        ↓
Component styles
        ↓
Utility styles
```

A clear structure makes it easier to understand where styles are defined and why a declaration is being overridden.

### A Simple Strategy

When writing CSS:

```text
Start with simple selectors
        ↓
Prefer reusable classes
        ↓
Avoid unnecessary nesting
        ↓
Avoid excessive IDs
        ↓
Use !important carefully
        ↓
Keep specificity predictable
```

### How to Avoid Specificity Problems Summary

```text
Avoid Specificity Problems
│
├── Prefer simple selectors
│
├── Use classes for reusable styles
│
├── Avoid excessive ID selectors
│
├── Avoid deeply nested selectors
│
├── Do not rely on !important
│
├── Keep specificity consistent
│
├── Use :where() when appropriate
│
└── Organize CSS clearly
```

> 💡 **Remember:** The best way to avoid specificity problems is to keep selectors simple, predictable, and easy to override. Avoid increasing specificity unless it is genuinely necessary.

---

## Best Practices

Following good CSS specificity practices helps keep stylesheets predictable, reusable, and easier to maintain.

The goal is not to always use the lowest possible specificity.

Instead, the goal is to use specificity intentionally.

### Prefer Simple Selectors

Simple selectors are generally easier to understand and override.

Example:

```css
.button {
    color: white;
}
```

Instead of:

```css
main .content .section .button {
    color: white;
}
```

The simpler selector has fewer dependencies on the HTML structure.

### Prefer Classes for Components

Classes are useful for reusable component styles.

Example:

```css
.card {
    padding: 20px;
}

.card-title {
    font-size: 1.5rem;
}

.card-content {
    line-height: 1.6;
}
```

This creates predictable and reusable selectors.

### Keep Specificity Low and Predictable

Avoid unnecessarily increasing specificity.

Example:

```css
.button.primary {
    background-color: blue;
}
```

Use additional selector complexity only when it is needed.

Avoid patterns such as:

```css
#app .container .content .button.primary {
    background-color: blue;
}
```

unless the additional specificity is genuinely required.

### Avoid Styling With IDs When Possible

ID selectors have high specificity.

Example:

```css
#submit-button {
    background-color: blue;
}
```

For reusable styles, a class is often easier to override:

```css
.submit-button {
    background-color: blue;
}
```

### Avoid Deep Selector Nesting

Deeply nested selectors can create tightly coupled CSS.

Example:

```css
.page .content .article .section .title {
    color: blue;
}
```

A component-based selector may be simpler:

```css
.article-title {
    color: blue;
}
```

This reduces dependence on a specific HTML structure.

### Avoid Unnecessary `!important`

`!important` should not be the default solution for CSS conflicts.

Instead of immediately writing:

```css
.button {
    color: blue !important;
}
```

first investigate:

```text
What rule is overriding this?
        ↓
Check importance
        ↓
Check specificity
        ↓
Check source order
```

Use `!important` only when there is a clear reason.

### Make Styles Easy to Override

Reusable CSS should often allow customization.

For example:

```css
:where(.card) {
    padding: 20px;
}
```

A regular class selector can easily override it:

```css
.card {
    padding: 30px;
}
```

This can be useful for base or framework styles.

### Use a Consistent Naming Strategy

Consistent class naming helps reduce the need for complex selectors.

Example:

```css
.card {}
.card-title {}
.card-description {}
```

A predictable naming structure makes it easier to understand which styles belong together.

### Separate Base and Component Styles

A clear stylesheet structure can reduce conflicts.

Example:

```text
Base styles
        ↓
Layout styles
        ↓
Component styles
        ↓
Utility styles
```

Each layer should have a clear purpose.

This makes CSS easier to debug and maintain.

### Debug Before Increasing Specificity

When a CSS declaration does not apply, avoid immediately making the selector more specific.

Instead:

```text
Inspect the element
        ↓
Find competing declarations
        ↓
Check the CSS cascade
        ↓
Check importance
        ↓
Compare specificity
        ↓
Check source order
```

Understanding the cause of the conflict usually produces a better solution.

### Best Practices Summary

```text
Good Specificity Practices
│
├── Prefer simple selectors
│
├── Prefer reusable classes
│
├── Keep specificity predictable
│
├── Avoid excessive IDs
│
├── Avoid deep nesting
│
├── Use !important carefully
│
├── Make styles easy to override
│
├── Use consistent naming
│
└── Debug before increasing specificity
```

> 💡 **Remember:** Good CSS specificity is predictable CSS specificity. Keep selectors simple and intentional so that styles remain easy to understand, override, and maintain.

---

## Common Mistakes

CSS specificity can be confusing because several parts of the CSS cascade work together.

The following are common mistakes developers make when working with CSS specificity.

### Assuming the Last Rule Always Wins

A common mistake is believing that the CSS rule written later always wins.

Consider:

```css
.text {
    color: blue;
}

p {
    color: green;
}
```

HTML:

```html
<p class="text">
    Hello World
</p>
```

The `p` rule appears later.

However:

```text
.text
→ 0-1-0

p
→ 0-0-1
```

The class selector has higher specificity.

Therefore:

```text
Final color
→ blue
```

Source order matters only when the competing declarations have the same relevant cascade conditions and specificity.

### Adding Specificity Values Together

Another mistake is treating specificity values like normal numbers.

Consider:

```text
1-0-0

0-10-0
```

It may appear that:

```text
0-10-0
```

should be larger because it contains more selectors.

However, specificity is compared from left to right.

```text
ID selectors
1 > 0
```

Therefore:

```text
1-0-0
```

has higher specificity.

### Using `!important` for Every Conflict

When a style does not apply, developers may immediately write:

```css
.button {
    color: blue !important;
}
```

This may solve the immediate problem but can create more problems later.

Repeated use can lead to:

```text
Style conflict
        ↓
Add !important
        ↓
Another conflict
        ↓
Add another !important
        ↓
CSS becomes difficult to manage
```

It is usually better to first inspect the CSS cascade and identify why the declaration is being overridden.

### Overusing ID Selectors

ID selectors have high specificity.

Example:

```css
#header .menu .item {
    color: blue;
}
```

Rules with high specificity can become difficult to override.

For reusable components, class selectors are often easier to manage:

```css
.menu-item {
    color: blue;
}
```

### Creating Deeply Nested Selectors

Consider:

```css
.page .main .content .article .section .title {
    color: blue;
}
```

This selector depends heavily on the HTML structure.

If the structure changes, the selector may no longer match.

It also creates higher specificity.

A simpler component-based selector may be easier to maintain:

```css
.article-title {
    color: blue;
}
```

### Increasing Specificity to Fix Every Problem

Consider:

```css
.button {
    color: blue;
}
```

Later, another rule overrides it.

A common reaction is to increase specificity:

```css
.container .button {
    color: blue;
}
```

Then:

```css
.page .container .button {
    color: blue;
}
```

This can create a specificity escalation.

```text
Rule overridden
        ↓
Increase specificity
        ↓
Rule overridden again
        ↓
Increase specificity again
        ↓
Hard-to-maintain CSS
```

Instead, investigate the original conflict.

### Forgetting About Inheritance

A parent selector may have high specificity:

```css
#container {
    color: blue;
}
```

A child may have:

```css
.text {
    color: red;
}
```

HTML:

```html
<div id="container">
    <p class="text">
        Hello World
    </p>
</div>
```

The parent's selector specificity does not directly compete with the child's selector because they target different elements.

The paragraph has a direct `color` declaration.

Therefore:

```text
Final color
→ red
```

### Forgetting That `:is()` Can Increase Specificity

Consider:

```css
:is(.button, #submit) {
    color: blue;
}
```

The presence of `#submit` affects the specificity of the entire `:is()` selector.

Specificity:

```text
1-0-0
```

Even an element matching `.button` can be affected by the higher specificity.

This can create unexpected conflicts.

### Confusing `:where()` With `:is()`

Both functions can group selectors.

However:

```text
:is()
→ Uses the specificity of the most specific selector

:where()
→ Always has zero specificity
```

Choosing the wrong function can lead to unexpected cascade behavior.

### Ignoring the Full CSS Cascade

Specificity is only one part of the CSS cascade.

A common mistake is checking specificity without considering:

```text
Origin
        ↓
Importance
        ↓
Specificity
        ↓
Source order
```

For example, a normal declaration with higher specificity may still lose to an applicable important declaration.

### Common Mistakes Summary

```text
Common Specificity Mistakes
│
├── Assuming the last rule always wins
│
├── Adding specificity values together
│
├── Overusing !important
│
├── Overusing ID selectors
│
├── Creating deeply nested selectors
│
├── Escalating specificity repeatedly
│
├── Confusing inheritance with specificity
│
├── Forgetting :is() specificity
│
├── Confusing :where() with :is()
│
└── Ignoring the full CSS cascade
```

> 💡 **Remember:** When a CSS rule does not behave as expected, do not immediately increase specificity. First identify which declarations are competing and then check the full cascade.

---

## Interview Questions

The following questions can help you prepare for CSS interviews and test your understanding of CSS specificity and the cascade.

### 1. What is CSS specificity?

CSS specificity is a system used to determine which CSS selector has higher priority when multiple declarations target the same element.

Specificity is one part of the CSS cascade.

### 2. How is CSS specificity calculated?

Specificity is commonly represented as:

```text
A-B-C
```

Where:

```text
A
→ ID selectors

B
→ Class selectors
→ Attribute selectors
→ Pseudo-classes

C
→ Type selectors
→ Pseudo-elements
```

Example:

```css
#header .menu a
```

Specificity:

```text
1-1-1
```

### 3. Which has higher specificity: a class selector or a type selector?

A class selector has higher specificity.

```text
.text
→ 0-1-0

p
→ 0-0-1
```

Therefore:

```text
.text
```

has higher specificity.

### 4. Which has higher specificity: an ID selector or multiple class selectors?

An ID selector has higher specificity than any number of class selectors.

Example:

```text
#title
→ 1-0-0

.class-one.class-two.class-three
→ 0-3-0
```

The ID selector has higher specificity because specificity is compared from left to right.

### 5. Does the CSS rule written last always win?

No.

The later rule wins only when competing declarations have the same relevant cascade conditions and specificity.

Example:

```css
.text {
    color: blue;
}

p {
    color: green;
}
```

The `.text` selector can still win because it has higher specificity.

### 6. What happens when two selectors have the same specificity?

Source order can determine the winner.

Example:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

The second declaration appears later.

Therefore:

```text
Final color
→ green
```

### 7. What specificity does the universal selector have?

The universal selector has:

```text
0-0-0
```

Example:

```css
*
```

It matches all elements but adds no specificity.

### 8. What is the specificity of an inline style?

Inline styles are commonly represented separately from normal selectors.

A common representation is:

```text
1-0-0-0
```

Inline styles generally have higher priority than normal author declarations.

### 9. What does `!important` do?

`!important` changes the importance of a CSS declaration.

Example:

```css
p {
    color: red !important;
}
```

It is part of the CSS cascade and is not a specificity score.

### 10. Does `!important` increase specificity?

No.

`!important` changes declaration importance.

Specificity is still compared between competing declarations at the same relevant importance level.

### 11. What is the difference between `:is()` and `:where()`?

```text
:is()
→ Uses the specificity of the most specific selector
  in its selector list

:where()
→ Always has zero specificity
```

Both can be used to group selectors.

### 12. How does `:not()` affect specificity?

The specificity of `:not()` is based on the most specific selector in its selector list.

Example:

```css
:not(.hidden)
```

Specificity:

```text
0-1-0
```

### 13. How does `:has()` affect specificity?

The specificity of `:has()` is based on the most specific selector in its argument.

Example:

```css
.card:has(img)
```

Specificity:

```text
.card
→ 0-1-0

img
→ 0-0-1

Total
→ 0-1-1
```

### 14. What is the difference between inheritance and specificity?

Inheritance determines whether a property value can pass from a parent element to a child.

Specificity determines which competing declaration wins when multiple declarations target the same element.

A parent's high specificity does not automatically override a declaration directly targeting a child.

### 15. Why can high specificity be a problem?

Highly specific selectors can be difficult to override.

Example:

```css
#app .container .content .button {
    color: blue;
}
```

Developers may need increasingly specific selectors to override such rules.

This can create a specificity escalation problem.

### 16. Why should ID selectors be used carefully for styling?

ID selectors have high specificity.

Repeated use of IDs for styling can make CSS rules harder to override.

Classes are often more flexible for reusable components.

### 17. What is source order in CSS?

Source order refers to the order in which CSS declarations appear.

When competing declarations have equal relevant cascade conditions and specificity, the later declaration can win.

### 18. How can you avoid CSS specificity problems?

Some good practices include:

```text
Use simple selectors
        ↓
Prefer reusable classes
        ↓
Avoid excessive IDs
        ↓
Avoid deeply nested selectors
        ↓
Use !important carefully
        ↓
Keep specificity predictable
```

### 19. What should you check when a CSS rule is being overridden?

A useful process is:

```text
Check competing declarations
        ↓
Check origin and importance
        ↓
Compare specificity
        ↓
Check source order
```

### 20. What is the most important thing to remember about specificity?

Specificity is only one part of the CSS cascade.

When a CSS rule behaves unexpectedly, consider:

```text
CSS Cascade
│
├── Origin
│
├── Importance
│
├── Specificity
│
└── Source order
```

Understanding the complete cascade is more useful than focusing only on specificity.

---

## Practice Exercises

The following exercises will help you practice calculating CSS specificity and understanding how the CSS cascade determines which declaration wins.

Try to answer each question before checking the solution.

### Exercise 1: Type Selector vs Class Selector

HTML:

```html
<p class="message">
    Hello World
</p>
```

CSS:

```css
p {
    color: blue;
}

.message {
    color: green;
}
```

Questions:

```text
1. What is the specificity of p?
2. What is the specificity of .message?
3. Which color will be applied?
```

Solution:

```text
p
→ 0-0-1

.message
→ 0-1-0

Final color
→ green
```

The class selector has higher specificity.

### Exercise 2: Class Selector vs ID Selector

HTML:

```html
<p id="title" class="heading">
    Hello World
</p>
```

CSS:

```css
.heading {
    color: blue;
}

#title {
    color: red;
}
```

Questions:

```text
1. What is the specificity of .heading?
2. What is the specificity of #title?
3. Which color will be applied?
```

Solution:

```text
.heading
→ 0-1-0

#title
→ 1-0-0

Final color
→ red
```

The ID selector has higher specificity.

### Exercise 3: Multiple Classes

HTML:

```html
<button class="button primary">
    Submit
</button>
```

CSS:

```css
.button {
    background-color: gray;
}

.button.primary {
    background-color: blue;
}
```

Questions:

```text
1. What is the specificity of .button?
2. What is the specificity of .button.primary?
3. Which background color will be applied?
```

Solution:

```text
.button
→ 0-1-0

.button.primary
→ 0-2-0

Final background color
→ blue
```

### Exercise 4: Source Order

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

Questions:

```text
1. Do both selectors have the same specificity?
2. Which declaration appears later?
3. Which color will be applied?
```

Solution:

```text
Both selectors
→ 0-1-0

Later declaration
→ color: green

Final color
→ green
```

### Exercise 5: More Type Selectors

HTML:

```html
<main>
    <article>
        <p>Hello World</p>
    </article>
</main>
```

CSS:

```css
p {
    color: green;
}

main article p {
    color: blue;
}
```

Questions:

```text
1. What is the specificity of p?
2. What is the specificity of main article p?
3. Which color will be applied?
```

Solution:

```text
p
→ 0-0-1

main article p
→ 0-0-3

Final color
→ blue
```

### Exercise 6: `!important`

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: blue;
}

p {
    color: red !important;
}
```

Questions:

```text
1. Which selector has higher normal specificity?
2. Which declaration is important?
3. Which color will be applied?
```

Solution:

```text
.text
→ Higher normal specificity

p
→ Contains !important

Final color
→ red
```

### Exercise 7: `:is()`

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
.text {
    color: green;
}

:is(.text, #title) {
    color: blue;
}
```

Questions:

```text
1. What is the specificity of .text?
2. What is the specificity of :is(.text, #title)?
3. Which color will be applied?
```

Solution:

```text
.text
→ 0-1-0

:is(.text, #title)
→ 1-0-0

Final color
→ blue
```

### Exercise 8: `:where()`

HTML:

```html
<p class="text">
    Hello World
</p>
```

CSS:

```css
:where(.text, #title) {
    color: blue;
}

.text {
    color: green;
}
```

Questions:

```text
1. What is the specificity of :where(.text, #title)?
2. What is the specificity of .text?
3. Which color will be applied?
```

Solution:

```text
:where(.text, #title)
→ 0-0-0

.text
→ 0-1-0

Final color
→ green
```

### Exercise 9: Calculate Specificity

Calculate the specificity of:

```css
#app .container article p.title
```

Break the selector into parts:

```text
#app
→ ID selector

.container
→ Class selector

article
→ Type selector

p
→ Type selector

.title
→ Class selector
```

Solution:

```text
IDs
→ 1

Classes
→ 2

Type selectors
→ 2

Specificity
→ 1-2-2
```

### Exercise 10: Find the Winning Rule

HTML:

```html
<div id="app">
    <p class="message">
        Hello World
    </p>
</div>
```

CSS:

```css
p {
    color: blue;
}

.message {
    color: green;
}

#app p {
    color: red;
}
```

Questions:

```text
1. What is the specificity of each selector?
2. Which rules match the paragraph?
3. Which declaration wins?
```

Solution:

```text
p
→ 0-0-1

.message
→ 0-1-0

#app p
→ 1-0-1

Final color
→ red
```

### Practice Challenge

Create your own HTML element and write three CSS rules that target it.

For example:

```html
<p id="example" class="text">
    Hello World
</p>
```

Write three selectors with different specificity values.

Then:

```text
1. Calculate the specificity of each selector.
2. Determine which declarations compete.
3. Predict which declaration wins.
4. Test the result in a browser.
```

### Practice Exercises Summary

```text
Practice CSS Specificity
│
├── Calculate specificity
│
├── Compare selectors
│
├── Identify competing rules
│
├── Check importance
│
├── Check source order
│
└── Predict the final result
```

> 💡 **Remember:** The best way to learn CSS specificity is to practice comparing selectors and predicting which declaration will win before testing the result.

---

## Key Takeaways

CSS specificity is an important part of the CSS cascade.

It helps determine which declaration wins when multiple CSS rules target the same element and property.

### Specificity Basics

Specificity can be represented as:

```text
A-B-C
```

Where:

```text
A
→ ID selectors

B
→ Class selectors
→ Attribute selectors
→ Pseudo-classes

C
→ Type selectors
→ Pseudo-elements
```

Selectors with a higher value in the first different category have higher specificity.

### Specificity Order

A simplified order is:

```text
Inline styles
        ↓
ID selectors
        ↓
Class selectors
        ↓
Type selectors
        ↓
Universal selector
```

Examples:

```text
#title
→ 1-0-0

.title
→ 0-1-0

p
→ 0-0-1

*
→ 0-0-0
```

### Specificity Is Not Simple Addition

Specificity values are compared from left to right.

Example:

```text
1-0-0

0-100-0
```

The first selector has higher specificity because the ID column is compared first.

```text
1 > 0
```

### Source Order Matters When Specificity Is Equal

Consider:

```css
.text {
    color: blue;
}

.text {
    color: green;
}
```

Both selectors have the same specificity.

Therefore, the later declaration can win.

```text
Final color
→ green
```

### `!important` Is Part of the Cascade

`!important` does not increase a selector's specificity score.

Instead, it changes the importance of a declaration.

Example:

```css
p {
    color: red !important;
}
```

When applicable, importance is considered as part of the cascade before normal specificity comparison.

### Modern Pseudo-Class Specificity

Some pseudo-classes have special specificity behavior.

```text
:is()
→ Uses the specificity of the most
  specific selector in its list

:where()
→ Always has zero specificity

:not()
→ Uses the specificity of the most
  specific selector in its selector list

:has()
→ Uses the specificity of the most
  specific selector in its argument
```

Be careful when placing highly specific selectors, such as ID selectors, inside these functions.

### Inheritance Is Different From Specificity

Inheritance and specificity solve different problems.

```text
Inheritance
→ Allows some property values to pass
  from parent to child

Specificity
→ Determines which competing declaration
  wins for the same element
```

A parent's high specificity does not automatically override a declaration directly applied to a child.

### Good Specificity Practices

```text
Prefer simple selectors
        ↓
Prefer reusable classes
        ↓
Avoid excessive ID selectors
        ↓
Avoid deep nesting
        ↓
Avoid unnecessary !important
        ↓
Keep specificity predictable
```

### When Debugging CSS

When a declaration does not apply as expected:

```text
Find competing declarations
        ↓
Check the CSS cascade
        ↓
Check importance
        ↓
Compare specificity
        ↓
Check source order
```

Avoid immediately increasing specificity or adding `!important`.

### Final Summary

```text
CSS Specificity
│
├── Helps determine which
│   competing declaration wins
│
├── Is part of the CSS cascade
│
├── Is compared category by category
│
├── Does not work like normal addition
│
├── Uses source order when relevant
│   specificity is equal
│
├── Is affected by modern pseudo-classes
│   such as :is(), :not(), and :has()
│
├── Treats :where() as zero specificity
│
└── Should be kept predictable
    and easy to manage
```

> 💡 **Remember:** The goal is not to create the most specific selector. The goal is to write CSS that is predictable, maintainable, and easy to override when necessary.

---

## References

The following resources can be used to learn more about CSS specificity and the CSS cascade.

### MDN Web Docs

MDN Web Docs provides detailed documentation about CSS specificity, selectors, and the cascade.

Useful topics include:

```text
CSS Specificity
CSS Cascade
CSS Selectors
Pseudo-classes
!important
Inheritance
```

### CSS Specifications

The official CSS specifications provide detailed information about how selectors and the cascade work.

Relevant areas include:

```text
CSS Cascading and Inheritance
Selectors
Specificity
Pseudo-classes
```

### Browser Developer Tools

Browser developer tools are useful for understanding CSS specificity in practice.

Most modern browsers allow developers to:

```text
Inspect elements
        ↓
View matching CSS rules
        ↓
See overridden declarations
        ↓
Compare specificity
        ↓
Understand the cascade
```

Practicing with browser developer tools is one of the best ways to understand why a CSS declaration wins or loses.

### Recommended Topics for Further Study

After learning CSS specificity, useful related topics include:

```text
CSS Cascade
CSS Inheritance
CSS Selectors
CSS Pseudo-classes
CSS Pseudo-elements
CSS Custom Properties
CSS Layers
!important
```

### Official Documentation

For detailed and up-to-date documentation, refer to:

```text
MDN Web Docs
→ CSS Specificity

MDN Web Docs
→ CSS Cascade

MDN Web Docs
→ CSS Selectors

W3C and CSS Working Group
→ CSS Specifications
```

### Learning Strategy

A useful way to improve your understanding is:

```text
Learn selector types
        ↓
Calculate specificity
        ↓
Compare competing rules
        ↓
Understand the CSS cascade
        ↓
Practice with browser developer tools
        ↓
Experiment with real examples
```

### References Summary

```text
Learn From
│
├── MDN Web Docs
│
├── Official CSS specifications
│
├── Browser developer tools
│
└── Practical experimentation
```

> 💡 **Remember:** CSS specificity is easier to understand through practice. Use browser developer tools to inspect real CSS rules and experiment with selectors, specificity, importance, and source order.

---

## Related Topics

### Previous Topics

- [CSS Basics](01-css-basics.md)
- [Ways to Add CSS](02-ways-to-add-css.md)
- [CSS Selectors](03-css-selectors.md)
- [CSS Colors](04-css-colors.md)
- [CSS Text and Fonts](05-css-text-and-fonts.md)
- [CSS Box Model](06-css-box-model.md)
- [CSS Display](07-css-display.md)
- [CSS Units](08-css-units.md)
- [CSS Position](09-css-position.md)
- [CSS Z-Index](10-css-z-index.md)
- [CSS Backgrounds](11-css-backgrounds.md)
- [CSS Flexbox](12-css-flexbox.md)
- [CSS Media Queries](13-css-media-queries.md)
- [CSS Transforms](14-css-transforms.md)
- [CSS Transitions](15-css-transitions.md)
- [CSS Animations](16-css-animations.md)
- [CSS Pseudo-Classes](17-css-pseudo-classes.md)
- [CSS Pseudo-Elements](18-css-pseudo-elements.md)
- [CSS Variables](19-css-variables.md)
- [CSS Grid](20-css-grid.md)
- [CSS Overflow](21-css-overflow.md)
- [CSS Opacity](22-css-opacity.md)
- [CSS Object Fit](23-css-object-fit.md)
- [CSS Cursor](24-css-cursor.md)
- [CSS Functions](25-css-functions.md)

### Next Topics

- [CSS Best Practices](27-css-best-practices.md)