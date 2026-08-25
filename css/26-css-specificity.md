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