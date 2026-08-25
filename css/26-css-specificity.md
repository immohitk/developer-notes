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